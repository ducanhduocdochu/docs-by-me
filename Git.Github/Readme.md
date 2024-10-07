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
## 📂 3.4. **Thêm tập tin vào Staging Area – Chuẩn bị commit**

Trước khi lưu (commit) những thay đổi của bạn, các tập tin cần được thêm vào **Staging Area**. **Staging Area** là một không gian tạm thời nơi bạn có thể chuẩn bị các tập tin mà bạn muốn đưa vào commit. Điều này cho phép bạn kiểm soát chính xác những gì sẽ được lưu trữ trong mỗi commit.

### 1. **Thêm tập tin cụ thể vào Staging Area**

Để thêm một tập tin cụ thể vào Staging Area, bạn sử dụng lệnh:

```bash
git add <tên_tập_tin>
```

Ví dụ:
```bash
git add index.html
```

Sau khi thêm tập tin, Git sẽ theo dõi nó và tập tin sẽ được đưa vào commit tiếp theo.

### 2. **Thêm tất cả các tập tin vào Staging Area**

Nếu bạn muốn thêm tất cả các tập tin đã được sửa đổi vào Staging Area, bạn có thể sử dụng dấu `.` để chỉ định toàn bộ thư mục hiện tại:

```bash
git add .
```

Lệnh này sẽ thêm tất cả các tập tin đã thay đổi hoặc mới vào Staging Area, giúp bạn nhanh chóng đưa toàn bộ dự án vào trạng thái sẵn sàng để commit.

### 3. **Kiểm tra trạng thái Staging Area**

Sau khi thêm các tập tin vào Staging Area, bạn có thể kiểm tra trạng thái của chúng bằng lệnh:

```bash
git status
```

Lệnh này sẽ hiển thị danh sách các tập tin đã được thêm vào Staging Area và các tập tin nào chưa được theo dõi (untracked). 

Ví dụ:
```bash
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   index.html
```

### 4. **Xóa tập tin khỏi Staging Area**

Nếu bạn vô tình thêm một tập tin vào Staging Area và không muốn commit nó nữa, bạn có thể loại bỏ tập tin khỏi Staging Area mà không ảnh hưởng đến tập tin trong thư mục làm việc của bạn, bằng lệnh:

```bash
git restore --staged <tên_tập_tin>
```

Ví dụ:
```bash
git restore --staged index.html
```

---
## 🔖 3.5. **Commit các thay đổi – Lưu lại lịch sử với thông điệp**

Sau khi các tập tin đã được thêm vào **Staging Area**, bước tiếp theo là **commit** để lưu lại thay đổi vào lịch sử của Git. Commit là một thao tác quan trọng trong việc ghi lại sự tiến bộ của dự án, đồng thời cho phép bạn quay lại các phiên bản trước nếu cần.

### 1. **Commit với thông điệp miêu tả**
Khi commit, bạn cần cung cấp một thông điệp ngắn gọn và súc tích để miêu tả những thay đổi mà bạn đã thực hiện. Sử dụng lệnh sau để thực hiện commit:

```bash
git commit -m "Miêu tả thay đổi"
```

Ví dụ:
```bash
git commit -m "Thêm trang chủ và chỉnh sửa menu điều hướng"
```

- **`-m`**: Tham số này chỉ định thông điệp commit được đưa vào trong dòng lệnh, thay vì mở trình soạn thảo văn bản.
- **"Miêu tả thay đổi"**: Đây là nội dung thông điệp mà bạn muốn ghi lại, giúp giải thích ngắn gọn về các thay đổi.

### 2. **Commit nhiều thay đổi cùng lúc**
Nếu bạn đã thêm nhiều tập tin vào Staging Area, tất cả những thay đổi đó sẽ được commit cùng lúc khi bạn sử dụng lệnh `git commit`.

Ví dụ, sau khi chạy lệnh `git add .` để thêm tất cả các tập tin, bạn có thể commit chúng với một thông điệp duy nhất:
```bash
git commit -m "Cập nhật toàn bộ mã nguồn và fix lỗi nhỏ"
```

### 3. **Kiểm tra lịch sử commit**
Sau khi commit, bạn có thể kiểm tra danh sách các commit trước đó bằng lệnh:

```bash
git log
```

Lệnh này sẽ hiển thị lịch sử commit, bao gồm mã hash của từng commit, thông điệp commit, và thông tin người thực hiện commit.

Ví dụ:
```bash
commit 1a2b3c4d5e6f7g8h9i0jklmnopqrstuvwxyz
Author: Ducanh <email@example.com>
Date:   Sat Oct 7 14:12:34 2023 +0700

    Thêm trang chủ và chỉnh sửa menu điều hướng
```

### 4. **Chỉnh sửa thông điệp commit**
Nếu bạn cần chỉnh sửa thông điệp commit gần nhất (và chưa đẩy lên repository từ xa), bạn có thể sử dụng lệnh:

```bash
git commit --amend -m "Thông điệp mới"
```

Lệnh này cho phép thay đổi nội dung của thông điệp commit trước mà không tạo commit mới.

---
## 🚀 3.6. **Push lên GitHub – Đưa các commit lên repository từ xa**

Sau khi bạn đã commit các thay đổi cục bộ (local), bước tiếp theo là **đẩy** (push) chúng lên repository từ xa, như GitHub, để lưu trữ và chia sẻ với nhóm phát triển hoặc sao lưu. Đây là bước quan trọng để đồng bộ hóa các thay đổi từ máy của bạn với phiên bản trên server.

### 1. **Push các commit lên nhánh từ xa**
Để đẩy các commit từ máy cục bộ lên nhánh trên repository từ xa, bạn sử dụng lệnh:

```bash
git push origin <nhánh>
```

- **origin**: Là tên mặc định của repository từ xa (thường là GitHub).
- **<nhánh>**: Là tên nhánh mà bạn muốn đẩy commit lên. Thường là `main` hoặc `master`.

Ví dụ, để đẩy commit lên nhánh chính (`main`):
```bash
git push origin main
```

### 2. **Push lên nhánh khác**
Nếu bạn đang làm việc trên một nhánh khác ngoài nhánh chính, chẳng hạn như `feature-branch`, bạn cần chỉ định tên nhánh đó:

```bash
git push origin feature-branch
```

Điều này sẽ đẩy tất cả các commit trong nhánh cục bộ `feature-branch` lên GitHub trong nhánh từ xa tương ứng.

### 3. **Push lần đầu tiên với thiết lập nhánh**
Nếu bạn vừa mới tạo một nhánh mới và đẩy lần đầu, bạn có thể cần sử dụng lệnh này để thiết lập nhánh từ xa và đẩy luôn:

```bash
git push --set-upstream origin <nhánh_mới>
```

Ví dụ:
```bash
git push --set-upstream origin feature-login
```

Sau khi thiết lập, bạn có thể sử dụng lệnh `git push` mà không cần phải chỉ định nhánh mỗi lần.

### 4. **Kiểm tra kết quả trên GitHub**
Sau khi hoàn tất việc đẩy commit, bạn có thể kiểm tra lại repository trên GitHub. Tại đây, bạn sẽ thấy các thay đổi mới đã được cập nhật lên nhánh từ xa.

---

## 🔄 3.7. Pull thay đổi từ GitHub – Kéo các thay đổi về từ repository từ xa
Khi có những thay đổi được đẩy lên repository từ xa (ví dụ như GitHub) bởi các thành viên khác, bạn cần phải cập nhật nhánh cục bộ của mình bằng cách kéo (pull) các thay đổi đó về. Lệnh git pull giúp bạn đồng bộ các thay đổi từ repository từ xa về máy của mình.

### 1. Lệnh cơ bản để kéo các thay đổi
Bạn sử dụng lệnh sau để kéo các thay đổi từ nhánh chỉ định trên repository từ xa về nhánh cục bộ của mình:

```bash
git pull origin <nhánh>
```
- **origin**: Là tên mặc định của repository từ xa (GitHub).
- **<nhánh>**: Là tên của nhánh mà bạn muốn kéo thay đổi về. Ví dụ: main.

Ví dụ, để kéo các thay đổi từ nhánh main:

```bash
git pull origin main
```
### 2. Làm việc với nhiều nhánh
Nếu bạn đang làm việc trên một nhánh khác ngoài main (ví dụ như feature-branch), bạn cần chỉ định nhánh đó khi thực hiện pull:

```bash
git pull origin feature-branch
```
### 3. Kết hợp pull và merge
Lệnh git pull thực chất là sự kết hợp của hai lệnh:

git fetch: Lệnh này lấy các thay đổi từ repository từ xa về máy cục bộ mà không tự động tích hợp (merge) chúng.
git merge: Sau khi fetch, lệnh pull tự động tích hợp các thay đổi vào nhánh cục bộ hiện tại.
Nếu có xung đột giữa các thay đổi từ xa và các thay đổi trên máy bạn, Git sẽ yêu cầu bạn giải quyết xung đột đó trước khi hoàn tất quá trình merge.

### 4. Lệnh pull nhanh với --rebase
Sử dụng lệnh git pull --rebase thay vì lệnh pull thông thường sẽ đảm bảo rằng Git không tạo một commit merge không cần thiết. Thay vào đó, nó sẽ áp dụng các thay đổi từ xa trước, sau đó áp dụng các thay đổi cục bộ của bạn lên trên, giúp giữ lịch sử commit gọn gàng hơn.

```bash
git pull --rebase origin main
```

---

## 🔍 3.8. Kiểm tra trạng thái của repository
Lệnh git status giúp bạn kiểm tra trạng thái hiện tại của repository, bao gồm các tập tin đã thay đổi nhưng chưa được thêm vào Staging Area, các tập tin đã được thêm nhưng chưa được commit, và cả các tập tin chưa được theo dõi (untracked files).

### 1. Sử dụng lệnh git status
```bash
git status
```
Kết quả của lệnh này sẽ cung cấp thông tin về:
- Các tập tin đã thay đổi nhưng chưa được thêm vào Staging Area.
- Các tập tin đã được thêm vào Staging Area nhưng chưa được commit.
- Các tập tin chưa được theo dõi (untracked), nghĩa là các tập tin mới nhưng chưa được thêm vào Staging Area.
### 2. Ví dụ sử dụng
```bash
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	newfile.txt
```
Lệnh này giúp bạn kiểm tra và theo dõi các thay đổi trước khi commit.

---

### 📜 3.9. Xem lịch sử commit
Lệnh git log giúp bạn xem lại lịch sử các commit đã được thực hiện trên repository, bao gồm các thông tin chi tiết về từng commit như: mã hash của commit, tên tác giả, ngày commit, và thông điệp commit.

## 1. Sử dụng lệnh git log
```bash
git log
```
### 2. Kết quả của lệnh git log
Lệnh này hiển thị chi tiết các commit theo thứ tự từ mới nhất đến cũ nhất. Mỗi commit sẽ hiển thị các thông tin sau:

- Mã hash: Một chuỗi ký tự duy nhất đại diện cho commit.
- Tác giả: Tên của người thực hiện commit.
- Ngày giờ: Thời gian commit được thực hiện.
- Thông điệp commit: Miêu tả ngắn gọn về những thay đổi đã được thực hiện trong commit.
Ví dụ kết quả:

```bash
commit 1a2b3c4d5e6f7g8h9i0j1k2l3m4n5o6p7q8r9
Author: John Doe <johndoe@example.com>
Date:   Mon Oct 7 10:00:00 2024 +0000

    Sửa lỗi hiển thị giao diện

commit 2b3c4d5e6f7g8h9i0j1k2l3m4n5o6p7q8r9a
Author: Jane Doe <janedoe@example.com>
Date:   Sun Oct 6 12:00:00 2024 +0000

    Thêm tính năng tải ảnh
```
### 3. Xem log rút gọn
Bạn có thể sử dụng --oneline để xem lịch sử commit một cách ngắn gọn, chỉ hiển thị mã hash và thông điệp commit:

```bash
git log --oneline
```
Ví dụ:

```bash
1a2b3c4 Sửa lỗi hiển thị giao diện
2b3c4d5 Thêm tính năng tải ảnh
```

---

### 🌿 4. Branching và Merging
## 4.1. Tạo nhánh mới
Khi bạn muốn phát triển một tính năng mới mà không làm ảnh hưởng đến nhánh chính, bạn cần tạo một nhánh mới. Sử dụng lệnh sau:

```bash
git branch <tên_nhánh>
```
-***<tên_nhánh>***: Tên của nhánh mới mà bạn muốn tạo. Ví dụ: feature-login.

---

## 4.2. Chuyển đổi giữa các nhánh
Để chuyển đổi giữa các nhánh, sử dụng lệnh checkout:

```bash
git checkout <tên_nhánh>
```
Lệnh này sẽ giúp bạn chuyển sang nhánh mà bạn chỉ định. Ví dụ: git checkout feature-login.

---

## 4.3. Merge nhánh
Khi bạn đã hoàn thành việc phát triển tính năng trên nhánh và muốn hợp nhất (merge) nó vào nhánh chính, thực hiện theo các bước sau:

Chuyển về nhánh chính (main hoặc master):
```bash
git checkout main
```
Thực hiện merge nhánh phát triển vào nhánh chính:
```bash
git merge <tên_nhánh>
```
Ví dụ: git merge feature-login.
## 4.4. Xóa nhánh
Sau khi đã merge nhánh phát triển vào nhánh chính và không còn cần thiết nữa, bạn có thể xóa nhánh đó bằng lệnh:

```bash
git branch -d <tên_nhánh>
```
Ví dụ: git branch -d feature-login.

--- 

## 💻 5. GitHub - Các thao tác quan trọng
### 5.1. Tạo repository mới trên GitHub
Để tạo một repository mới trên GitHub, làm theo các bước sau:

- Vào trang GitHub.
- Nhấn vào nút New Repository.
- Điền tên cho repository và cài đặt các tùy chọn cần thiết.
- Nhấn Create repository.

---

### 5.2. Liên kết repository Git với GitHub
Khi bạn đã có một repository Git trên máy của mình, bạn cần liên kết nó với repository trên GitHub:

``` bash
git remote add origin https://github.com/username/repo.git
Thay thế username và repo bằng tên người dùng và tên repository của bạn.
```

---

### 5.3. Tạo pull request (PR)
Khi bạn muốn merge các thay đổi từ nhánh phát triển vào nhánh chính, bạn cần tạo một Pull Request (PR) trên GitHub:

- Vào repository trên GitHub.
- Chọn nhánh mà bạn muốn merge.
- Nhấn vào nút New Pull Request và làm theo hướng dẫn để tạo PR.
- Chờ review và merge từ các thành viên khác trong nhóm.

---

### 5.4. Review code
GitHub cho phép bạn review code, thêm nhận xét vào các phần của mã trước khi thực hiện merge:

- Vào Pull Request mà bạn đã tạo.
- Xem xét các thay đổi và thêm nhận xét nếu cần.
- Chấp nhận hoặc từ chối PR.

---

⚠️ 6. Resolve Conflicts (Giải quyết xung đột)
Khi hai lập trình viên cùng thay đổi một tập tin và đẩy lên GitHub, có thể xảy ra xung đột. Để giải quyết xung đột, bạn cần thực hiện các bước sau:

Kéo các thay đổi về từ repository:
```bash
git pull origin main
```
Xử lý xung đột:

- Git sẽ báo có xung đột và yêu cầu bạn chỉnh sửa thủ công.
- Mở tập tin xung đột và chỉnh sửa các phần xung đột.
- Commit và push:

- Sau khi chỉnh sửa xong, bạn thực hiện commit và push các thay đổi:
```bash
git add <tập_tin>
git commit -m "Giải quyết xung đột"
git push origin main
```

---

🛠️ 7. Git Flow
Git Flow là một quy trình quản lý nhánh trong Git, giúp phát triển phần mềm theo một trình tự có tổ chức hơn. Quy trình này gồm các nhánh chính sau:

- master/main: Chứa mã nguồn ở trạng thái ổn định.
- develop: Nơi phát triển các tính năng mới.
- feature/: Tạo ra từ develop, chứa mã cho một tính năng mới.
- release/: Tạo ra từ develop, dùng để chuẩn bị cho phiên bản mới.
- hotfix/: Tạo ra từ master, dùng để sửa lỗi khẩn cấp.

---

📝 **Created by ducanhduocdochu**
