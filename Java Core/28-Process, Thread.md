# Tất Tần Tật về Process và Thread trong Java

## 1. Process là gì?
**Process** (tiến trình) là một chương trình đang chạy trong bộ nhớ. Mỗi tiến trình là một đơn vị độc lập và có tài nguyên riêng như không gian bộ nhớ, các biến, và xử lý của CPU.

- **Đặc điểm của Process:**
  - Hoạt động độc lập.
  - Có tài nguyên riêng như bộ nhớ, tài nguyên I/O.
  - Nặng hơn so với thread do cần nhiều tài nguyên hệ thống.
  - Giao tiếp giữa các process khó khăn hơn (IPC - Inter-Process Communication).

---

## 2. Thread là gì?
**Thread** (luồng) là một đơn vị xử lý nhỏ nhất trong một process. Một process có thể chứa nhiều thread hoạt động đồng thời.

- **Đặc điểm của Thread:**
  - Nhẹ hơn process, chia sẻ tài nguyên với các thread khác trong cùng một process.
  - Có stack riêng nhưng dùng chung heap với các thread khác.
  - Thích hợp cho các tác vụ cần thực thi song song.

---

## 3. So sánh Process và Thread

| **Đặc điểm**              | **Process**                                      | **Thread**                               |
|---------------------------|-------------------------------------------------|------------------------------------------|
| **Độc lập**               | Hoàn toàn độc lập                               | Phụ thuộc vào process chứa nó            |
| **Chia sẻ tài nguyên**    | Không chia sẻ tài nguyên với process khác       | Chia sẻ tài nguyên trong cùng một process|
| **Thời gian tạo**         | Tốn nhiều thời gian hơn                         | Nhanh hơn                                |
| **Cách giao tiếp**        | Khó khăn hơn (IPC)                              | Dễ dàng qua shared memory                |

---

## 4. Tạo Process trong Java
Java không cung cấp cách trực tiếp tạo process nhưng có thể sử dụng `ProcessBuilder` hoặc `Runtime`.

### Ví dụ sử dụng `ProcessBuilder`
```java
import java.io.*;

public class Main {
    public static void main(String[] args) {
        try {
            ProcessBuilder processBuilder = new ProcessBuilder("notepad.exe");
            Process process = processBuilder.start();

            // Kiểm tra trạng thái của process
            System.out.println("Process đang chạy: " + process.isAlive());

            // Đợi process kết thúc
            process.waitFor();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

---

## 5. Tạo Thread trong Java
Java cung cấp nhiều cách để tạo thread, bao gồm:
1. **Kế thừa lớp `Thread`.**
2. **Triển khai giao diện `Runnable`.**
3. **Sử dụng `ExecutorService`.**

### 5.1. Tạo Thread bằng cách kế thừa lớp `Thread`
```java
class MyThread extends Thread {
    @Override
    public void run() {
        System.out.println("Thread đang chạy: " + Thread.currentThread().getName());
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread thread = new MyThread();
        thread.start();
    }
}
```

### 5.2. Tạo Thread bằng cách triển khai `Runnable`
```java
class MyRunnable implements Runnable {
    @Override
    public void run() {
        System.out.println("Runnable đang chạy: " + Thread.currentThread().getName());
    }
}

public class Main {
    public static void main(String[] args) {
        Thread thread = new Thread(new MyRunnable());
        thread.start();
    }
}
```

### 5.3. Sử dụng ExecutorService
```java
import java.util.concurrent.*;

public class Main {
    public static void main(String[] args) {
        ExecutorService executor = Executors.newFixedThreadPool(2);

        Runnable task = () -> {
            System.out.println("Task đang chạy trong thread: " + Thread.currentThread().getName());
        };

        executor.submit(task);
        executor.shutdown();
    }
}
```

---

## 6. Các trạng thái của Thread
Thread trong Java có 6 trạng thái chính:

| **Trạng thái**         | **Mô tả**                                                                 |
|-------------------------|---------------------------------------------------------------------------|
| **NEW**                | Thread được tạo nhưng chưa chạy (`start()` chưa được gọi).               |
| **RUNNABLE**           | Thread đang sẵn sàng chạy nhưng chưa được CPU cấp phát.                  |
| **BLOCKED**            | Thread bị chặn, đang chờ tài nguyên được giải phóng.                     |
| **WAITING**            | Thread đang chờ vô thời hạn cho một tín hiệu từ thread khác.              |
| **TIMED_WAITING**      | Thread chờ với khoảng thời gian giới hạn.                                |
| **TERMINATED**         | Thread đã kết thúc sau khi hoàn thành nhiệm vụ.                          |

---

## 7. Đồng bộ hóa (Synchronization)
Khi nhiều thread chia sẻ tài nguyên, có thể xảy ra **race condition**. Java cung cấp từ khóa `synchronized` để đảm bảo an toàn.

### Ví dụ về Synchronized
```java
class Counter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public int getCount() {
        return count;
    }
}

public class Main {
    public static void main(String[] args) {
        Counter counter = new Counter();

        Thread t1 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                counter.increment();
            }
        });

        Thread t2 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                counter.increment();
            }
        });

        t1.start();
        t2.start();

        try {
            t1.join();
            t2.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println("Final count: " + counter.getCount());
    }
}
```
**Kết quả:**
```
Final count: 2000
```

---

## 8. Kết Luận
- **Process** thích hợp cho các tác vụ độc lập, không chia sẻ tài nguyên.
- **Thread** phù hợp khi cần xử lý song song, chia sẻ tài nguyên trong cùng một ứng dụng.
- Sử dụng `synchronized` hoặc các công cụ đồng bộ để tránh lỗi trong môi trường đa luồng.

✨ **Mẹo:** Sử dụng thread pool (`ExecutorService`) để quản lý các thread hiệu quả hơn. 🚀

---

📝 **Created by ducanhduocdochu**
