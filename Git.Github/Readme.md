📚 Tổng quan về Git và GitHub cùng với các ví dụ cụ thể:

---

# 1. 🛠️ Git là gì?
Git là một hệ thống quản lý phiên bản phân tán, cho phép nhiều lập trình viên cùng làm việc trên một dự án mà không gặp vấn đề xung đột. Nó lưu trữ lịch sử thay đổi của mã nguồn, giúp bạn quay lại các phiên bản trước nếu cần. Một số lợi ích của Git:

🕒 Theo dõi lịch sử thay đổi mã nguồn.
🌐 Làm việc offline, vì Git lưu trữ toàn bộ repository trên máy cá nhân.
👥 Hỗ trợ cộng tác hiệu quả giữa nhiều lập trình viên.

<p align="center">
  <img src="https://github.com/ducanhduocdochu/docs-by-me/blob/main/Git.Github/git.jpg" alt="overview" width="500"/>
</p>

---

# 2. 💻 GitHub là gì?
GitHub là một dịch vụ lưu trữ mã nguồn dựa trên Git, cung cấp giao diện web để quản lý các dự án Git. Ngoài GitHub, còn có các dịch vụ khác như GitLab, Bitbucket, nhưng GitHub là phổ biến nhất. Những điểm nổi bật của GitHub:

📂 Lưu trữ và chia sẻ mã nguồn dễ dàng.
🚀 Hỗ trợ CI/CD để tự động hóa quá trình build, test, và deploy.
👨‍💻 Cộng đồng đông đảo, dễ dàng tham gia và hợp tác vào các dự án mã nguồn mở.

<p align="center">
  <img src="https://github.com/ducanhduocdochu/docs-by-me/blob/main/Git.Github/GitHub.png" alt="overview" width="500"/>
</p>

---

# 3. 💻 Các lệnh cơ bản của Git
## 3.1 🛠️ Git Configuration Guide

Trước khi sử dụng Git, bạn cần cấu hình một số thông tin cơ bản để bắt đầu làm việc hiệu quả. Dưới đây là các bước và lệnh Git giúp bạn cấu hình môi trường làm việc của mình.

### a. 📝 Cấu hình tên người dùng
Git sẽ ghi lại thông tin người thực hiện mỗi lần bạn commit. Để cấu hình tên người dùng, bạn sử dụng lệnh sau:

```bash
git config --global user.name "Tên của bạn"
```

Ví dụ:
```bash
git config --global user.name "Duc Anh Tran"
```

Tên này sẽ xuất hiện trong lịch sử commit, giúp dễ dàng theo dõi ai đã thực hiện thay đổi nào.

### b. 📧 Cấu hình địa chỉ email
Cấu hình địa chỉ email liên kết với tài khoản Git của bạn. Email này thường là email mà bạn dùng để đăng ký GitHub:

```bash
git config --global user.email "email@example.com"
```

Ví dụ:
```bash
git config --global user.email "ducanh@example.com"
```

### c. 🔧 Cấu hình trình soạn thảo mặc định
Git thường mở trình soạn thảo văn bản mỗi khi bạn cần nhập thông tin như thông điệp commit hoặc khi xử lý xung đột (merge conflict). Bạn có thể thay đổi trình soạn thảo mặc định:

Sử dụng VS Code:
```bash
git config --global core.editor "code --wait"
```

Sử dụng Vim:
```bash
git config --global core.editor "vim"
```

### d. 🌿 Tạo bí danh (alias) cho các lệnh Git
Bạn có thể tạo bí danh để rút gọn các lệnh Git dài dòng, giúp tiết kiệm thời gian khi làm việc.

Ví dụ, tạo alias cho `git status`:
```bash
git config --global alias.st status
```

Hoặc tạo alias cho `git checkout`:
```bash
git config --global alias.co checkout
```

Sau đó, bạn chỉ cần gõ `git st` thay vì `git status`.

### e. 🌍 Xử lý Line Endings trên nhiều hệ điều hành
Khi làm việc trên nhiều hệ điều hành khác nhau, có thể xảy ra xung đột về cách dòng được kết thúc (CRLF hoặc LF). Để Git tự động xử lý vấn đề này:

Trên Windows:
```bash
git config --global core.autocrlf true
```

Trên macOS hoặc Linux:
```bash
git config --global core.autocrlf input
```

### f. 🎨 Bật màu sắc trong Git
Bạn có thể bật tính năng hiển thị màu sắc để làm cho việc đọc kết quả lệnh Git trực quan hơn.

```bash
git config --global color.ui auto
```

### g. 🔐 Lưu thông tin xác thực
Nếu bạn không muốn phải nhập lại thông tin đăng nhập GitHub mỗi lần thực hiện `git push` hoặc `git pull`, hãy sử dụng lệnh sau để lưu thông tin đăng nhập trong một khoảng thời gian:

```bash
git config --global credential.helper 'cache --timeout=3600'
```

### h. 🛠️ Cấu hình công cụ merge
Khi gặp xung đột trong quá trình merge, bạn có thể cấu hình Git để sử dụng một công cụ giải quyết xung đột.

Ví dụ, sử dụng VS Code làm công cụ merge mặc định:
```bash
git config --global merge.tool vscode
git config --global mergetool.vscode.cmd 'code --wait $MERGED'
```

### i. 🎯 Kiểm tra lại cấu hình hiện tại
Sau khi thực hiện các cấu hình, bạn có thể kiểm tra lại bằng lệnh sau:
```bash
git config --global --list
```

---
## 🚀 3.2. **Khởi tạo Git – Bắt đầu quản lý dự án**

Sau khi cấu hình thông tin cá nhân trong Git, bạn có thể bắt đầu quản lý mã nguồn cho dự án của mình. Git cung cấp lệnh **`git init`** để khởi tạo một repository Git mới trong thư mục hiện tại. Điều này biến thư mục của bạn thành một dự án có thể quản lý được bằng Git.

### 1. **Khởi tạo một repository mới**

- Để tạo một Git repository trong thư mục hiện tại, bạn chỉ cần mở terminal và gõ lệnh:

```bash
git init
```

- 📝 **Lưu ý**: Lệnh này sẽ tạo một thư mục ẩn `.git/` trong thư mục làm việc của bạn, nơi Git sẽ lưu trữ tất cả các thông tin cần thiết để quản lý lịch sử thay đổi của dự án. 

Ví dụ:
```bash
cd /path/to/your/project
git init
```

Sau khi chạy lệnh, Git sẽ thông báo rằng một repository trống đã được khởi tạo:

```bash
Initialized empty Git repository in /path/to/your/project/.git/
```

### 2. **Kiểm tra trạng thái repository**
Sau khi khởi tạo, bạn có thể sử dụng lệnh `git status` để kiểm tra trạng thái repository:

```bash
git status
```

Lệnh này sẽ cho bạn biết thư mục hiện tại của bạn có đang được Git theo dõi không, và những file nào trong dự án đang trong trạng thái thay đổi.

### 3. **Thêm file vào Git repository**
Lúc này, thư mục của bạn vẫn chưa có file nào được Git theo dõi. Bạn có thể thêm file vào Git bằng cách sử dụng lệnh `git add`:

```bash
git add <tên-file>
```

Hoặc để thêm tất cả các file trong thư mục:
```bash
git add .
```

- Ví dụ, để thêm một file có tên `README.md`:
  
```bash
git add README.md
```

### 4. **Tạo commit đầu tiên**
Sau khi đã thêm các file, bạn có thể lưu thay đổi (commit) bằng lệnh:

```bash
git commit -m "Commit message"
```

Ví dụ:
```bash
git commit -m "Initial commit"
```

- **Commit message** nên rõ ràng và miêu tả đúng những thay đổi bạn đã thực hiện.

### 5. **Khởi tạo Git repository từ xa (Remote repository)**
Sau khi khởi tạo repository cục bộ, bạn có thể kết nối với repository từ xa trên GitHub hoặc GitLab.

1. Tạo repository trên GitHub (không cần khởi tạo README.md hoặc .gitignore từ xa).
2. Kết nối repository cục bộ với repository từ xa bằng lệnh:

```bash
git remote add origin <URL-repo-tu-xa>
```

Ví dụ:
```bash
git remote add origin https://github.com/username/repo.git
```

3. Đẩy (push) commit lên repository từ xa:

```bash
git push -u origin master
```

---

## 🌐 3.3. **Clone một repository – Sao chép dự án về máy**

Khi bạn muốn sao chép một dự án từ GitHub hoặc một repository từ xa khác về máy tính của mình, lệnh **`git clone`** sẽ giúp bạn thực hiện điều đó.

### 1. **Sao chép một repository từ GitHub**

Để sao chép một repository từ GitHub về máy tính, bạn sử dụng lệnh sau:

```bash
git clone https://github.com/username/repo.git
```

- **`https://github.com/username/repo.git`** là URL của repository mà bạn muốn clone. Bạn có thể lấy đường link này từ trang GitHub của dự án.

Ví dụ:
```bash
git clone https://github.com/ducanh/repo.git
```

Lệnh này sẽ sao chép toàn bộ mã nguồn và lịch sử commit của dự án vào một thư mục mới cùng tên với repository. Bạn sẽ thấy một thư mục mới được tạo trong thư mục hiện tại với tên `repo`, và bạn có thể bắt đầu làm việc trong đó.

### 2. **Clone vào một thư mục khác**
Nếu bạn muốn clone repository vào một thư mục có tên khác với tên gốc của repository, bạn chỉ cần chỉ định tên thư mục sau URL:

```bash
git clone https://github.com/username/repo.git new-folder-name
```

Ví dụ:
```bash
git clone https://github.com/ducanh/repo.git my-project
```

Lệnh này sẽ sao chép repository vào thư mục có tên `my-project` thay vì tên mặc định là `repo`.

### 3. **Sao chép một repository với SSH**
Nếu bạn đã thiết lập SSH cho GitHub, bạn có thể clone repository bằng SSH thay vì HTTPS. Điều này giúp bạn không cần nhập thông tin xác thực mỗi lần đẩy hoặc kéo mã (push/pull):

```bash
git clone git@github.com:username/repo.git
```

Ví dụ:
```bash
git clone git@github.com:ducanh/repo.git
```

### 4. **Kiểm tra trạng thái sau khi clone**
Sau khi clone repository về máy, bạn có thể di chuyển vào thư mục của repository đó và kiểm tra trạng thái bằng lệnh:

```bash
cd repo
git status
```

Lệnh này sẽ hiển thị trạng thái của repository vừa clone và cho bạn biết nếu có bất kỳ thay đổi nào trong các file.

---
3.4. Thêm tập tin vào Staging Area
Trước khi commit, cần thêm các tập tin vào Staging Area:

bash
Copy code
git add <tên_tập_tin>
# Hoặc để thêm tất cả các tập tin
git add .
3.5. Commit các thay đổi
Commit là thao tác lưu lại thay đổi với một thông điệp miêu tả:

bash
Copy code
git commit -m "Miêu tả thay đổi"
3.6. Push lên GitHub
Đưa các commit lên GitHub:

bash
Copy code
git push origin <nhánh>
# Ví dụ: git push origin main
3.7. Pull thay đổi từ GitHub
Kéo những thay đổi từ GitHub về máy:

bash
Copy code
git pull origin <nhánh>
3.8. Kiểm tra trạng thái
Hiển thị trạng thái hiện tại của repository, bao gồm các tập tin đã thay đổi, đã thêm vào Staging Area:

bash
Copy code
git status
3.9. Lịch sử commit
Xem lịch sử commit:

bash
Copy code
git log
4. Branching và Merging
4.1. Tạo nhánh mới
Tạo một nhánh mới để phát triển một tính năng mới mà không ảnh hưởng đến nhánh chính:

bash
Copy code
git branch <tên_nhánh>
4.2. Chuyển đổi giữa các nhánh
Di chuyển đến một nhánh khác:

bash
Copy code
git checkout <tên_nhánh>
4.3. Merge nhánh
Khi hoàn thành phát triển, có thể merge nhánh vào nhánh chính:

bash
Copy code
git checkout main
git merge <tên_nhánh>
4.4. Xóa nhánh
Xóa một nhánh sau khi đã merge:

bash
Copy code
git branch -d <tên_nhánh>
5. GitHub - Các thao tác quan trọng
5.1. Tạo repository mới trên GitHub
Vào GitHub → New Repository → Điền tên và cài đặt cần thiết → Tạo repository.
5.2. Liên kết repository Git với GitHub
Khi có repository Git trên máy, cần liên kết với GitHub:

bash
Copy code
git remote add origin https://github.com/username/repo.git
5.3. Tạo pull request (PR)
Khi bạn muốn merge thay đổi của nhánh phát triển vào nhánh chính:

Tạo pull request trên GitHub, sau đó chờ review và merge.
5.4. Review code
GitHub cho phép review code, thêm nhận xét vào các phần của mã trước khi merge.

6. Resolve Conflicts (Giải quyết xung đột)
Khi hai lập trình viên cùng thay đổi một tập tin và đẩy lên GitHub, có thể xảy ra xung đột. Để giải quyết:

Pull các thay đổi về trước:
bash
Copy code
git pull origin main
Git sẽ báo xung đột và yêu cầu chỉnh sửa thủ công:
Mở tập tin xung đột và chỉnh sửa.
Sau khi chỉnh sửa xong, tiếp tục commit và push.
7. Làm việc với GitHub Actions
GitHub Actions là một tính năng giúp tự động hóa quy trình phát triển như kiểm tra code, build, deploy.

Ví dụ, tạo file .github/workflows/ci.yml để chạy tests khi có commit:

yaml
Copy code
name: CI
on:
  push:
    branches:
      - main
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Set up Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '14'
      - run: npm install
      - run: npm test
8. Tagging và Releases
8.1. Tạo tag
Khi phát hành phiên bản mới, bạn có thể tạo tag để đánh dấu:

bash
Copy code
git tag -a v1.0 -m "Phiên bản đầu tiên"
git push origin v1.0
8.2. Tạo release trên GitHub
GitHub hỗ trợ tạo release từ các tag, cho phép người dùng tải về phiên bản phát hành.

9. Git Flow
Git Flow là một quy trình quản lý nhánh trong Git, giúp phát triển phần mềm theo một trình tự có tổ chức hơn. Quy trình này gồm các nhánh chính sau:

master/main: Chứa mã nguồn ở trạng thái ổn định.
develop: Nơi phát triển các tính năng mới.
feature/: Tạo ra từ develop, chứa mã cho một tính năng mới.
release/: Tạo ra từ develop, dùng để chuẩn bị cho phiên bản mới.
hotfix/: Tạo ra từ master, dùng để sửa lỗi khẩn cấp.
