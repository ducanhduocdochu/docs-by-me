
# 🎨 Design Pattern: Adapter

---

## 📖 1. Overview of Adapter
The Adapter Design Pattern is a **Structural Design Pattern** that allows incompatible interfaces to work together. It acts as a bridge between two different interfaces, enabling classes with incompatible interfaces to interact without changing their code.

- 💡 **Key Features**:
  - **Interface Compatibility**: Adapts an interface to another one expected by the client.
  - **Reusability**: Makes it easier to reuse existing classes in new applications.
  - **Separation of Concerns**: The Adapter isolates the client from the incompatible interface, promoting cleaner code.

---

## 🚀 2. Adapter Pattern in Action
Here's a practical example of the Adapter Pattern in Java:

### 🎯 Code Example: Connecting Incompatible Interfaces with Adapter
```java
// Target interface
interface Target {
    void request();
}

// Adaptee: The existing class with an incompatible interface
class Adaptee {
    public void specificRequest() {
        System.out.println("Adaptee: Specific request.");
    }
}

// Adapter: Converts the interface of Adaptee to the Target interface
class Adapter implements Target {
    private Adaptee adaptee;

    public Adapter(Adaptee adaptee) {
        this.adaptee = adaptee;
    }

    public void request() {
        adaptee.specificRequest();  // Delegating call to Adaptee
    }
}

// Client code
public class Main {
    public static void main(String[] args) {
        Adaptee adaptee = new Adaptee();
        Target adapter = new Adapter(adaptee);
        adapter.request();  // Output: Adaptee: Specific request.
    }
}
```

### 🛠️ How It Works:
- **Target interface**: Defines the interface that the client expects.
- **Adaptee**: The existing class that has an incompatible interface.
- **Adapter**: A class that implements the Target interface and translates requests to the Adaptee.

---

## 🌐 3. Adapter Pattern in Real Systems
A real-world example: Adapting legacy systems or APIs to work with modern applications.

### 🖥️ Example: Media Player Adapter
```java
// Target interface for the media player
interface MediaPlayer {
    void play(String fileType);
}

// Adaptee: Advanced media player with different functionality
class AdvancedMediaPlayer {
    public void playMP4() {
        System.out.println("Playing MP4 file");
    }

    public void playVLC() {
        System.out.println("Playing VLC file");
    }
}

// Adapter: Converts MediaPlayer requests to AdvancedMediaPlayer actions
class MediaAdapter implements MediaPlayer {
    private AdvancedMediaPlayer advancedPlayer;

    public MediaAdapter(String fileType) {
        advancedPlayer = new AdvancedMediaPlayer();
    }

    public void play(String fileType) {
        if (fileType.equalsIgnoreCase("mp4")) {
            advancedPlayer.playMP4();
        } else if (fileType.equalsIgnoreCase("vlc")) {
            advancedPlayer.playVLC();
        }
    }
}

// Client code
public class Main {
    public static void main(String[] args) {
        MediaPlayer player = new MediaAdapter("mp4");
        player.play("mp4");  // Output: Playing MP4 file

        MediaPlayer anotherPlayer = new MediaAdapter("vlc");
        anotherPlayer.play("vlc");  // Output: Playing VLC file
    }
}
```

📘 In this example:
- The **MediaAdapter** bridges the gap between the **MediaPlayer** interface and the advanced functionality of **AdvancedMediaPlayer**, enabling different media formats to be played through a uniform interface.

---

## ⚙️ 4. Pros and Cons of Adapter

### ✅ **Advantages**:
- **Interface compatibility**: Allows incompatible interfaces to work together without modifying the client or the adaptee.
- **Improved reusability**: Makes it easier to use existing functionality without rewriting code.
- **Flexibility**: Decouples the client from the implementation details of the adaptee.

### ❌ **Disadvantages**:
- **Extra complexity**: Can add complexity if not used wisely, particularly in systems with many adapters.
- **Performance**: Depending on the implementation, it could introduce performance overhead.

---

## 🌍 5. Real-World Applications
The Adapter Pattern is widely used in various systems:
- **Legacy systems**: Adapting legacy interfaces to modern software.
- **Third-party libraries**: Integrating third-party libraries that may have different interfaces.
- **Device drivers**: Adapters are often used to create drivers for different hardware.

---

📝 **Created by ducanhduocdochu**
