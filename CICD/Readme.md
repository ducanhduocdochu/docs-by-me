# 🚀 CI/CD Tổng Quan

CI/CD (Continuous Integration và Continuous Deployment/Delivery) là một phương pháp luận tự động hóa các giai đoạn tích hợp, kiểm thử và triển khai trong phát triển phần mềm, giúp tăng tốc độ và độ tin cậy khi cung cấp các bản cập nhật. Tài liệu này giải thích các khái niệm chính, thực tiễn, công cụ và lợi ích của CI/CD kèm theo các ví dụ minh họa.

<p align="center">
  <img src="https://github.com/ducanhduocdochu/docs-by-me/blob/main/CICD/overview.jpg" alt="overview" width="500"/>
</p>

---

## 1. 🛠️ Continuous Integration (CI)

**Continuous Integration (CI)** là thực tiễn hợp nhất các thay đổi mã nguồn vào kho lưu trữ chung thường xuyên. Mỗi thay đổi được xác minh qua quá trình xây dựng và kiểm thử tự động, giúp các nhóm phát hiện vấn đề sớm.

### ⚙️ Các Khái Niệm Chính
- **📁 Hệ Thống Quản Lý Phiên Bản (VCS)**: Sử dụng các công cụ như Git (GitHub, GitLab, Bitbucket) để quản lý mã nguồn.  
  *Ví dụ:* Khi một lập trình viên hoàn thành một tính năng mới, họ sẽ commit và push mã nguồn lên GitHub.

- **🔍 Kiểm Thử Tự Động**: Mỗi commit sẽ kích hoạt các bài kiểm thử tự động để xác nhận mã mới không gây lỗi cho các chức năng hiện tại.  
  *Ví dụ:* Một bài kiểm thử đơn vị (unit test) sẽ kiểm tra xem hàm mới có hoạt động đúng không sau mỗi lần commit.

- **🏗️ Tự Động Hóa Xây Dựng (Build Automation)**: Ứng dụng được xây dựng và kiểm thử tự động cho mỗi thay đổi mã nguồn.  
  *Ví dụ:* Jenkins sẽ tự động biên dịch mã nguồn và chạy các kiểm thử khi có thay đổi mới.

- **🔄 Tần Suất Tích Hợp**: Các lập trình viên tích hợp mã nhiều lần trong ngày, giảm thiểu xung đột và dễ dàng phát hiện lỗi.  
  *Ví dụ:* Thay vì tích hợp hàng tuần, nhóm phát triển tích hợp mỗi khi hoàn thành một tính năng nhỏ.

### 🛠️ Các Công Cụ CI Phổ Biến
- **Jenkins**: Công cụ tự động hóa mạnh mẽ, hỗ trợ nhiều plugin.
- **CircleCI**: Dịch vụ CI/CD đám mây dễ sử dụng.
- **Travis CI**: Tích hợp tốt với GitHub, phổ biến trong các dự án mã nguồn mở.
- **GitLab CI**: Được tích hợp sẵn trong GitLab, dễ dàng cấu hình.
- **TeamCity**: Công cụ CI của JetBrains, mạnh mẽ và linh hoạt.
- **GitHub Actions**: Tích hợp trực tiếp trong GitHub, hỗ trợ các workflow tùy chỉnh.

---

## 2. 🚢 Continuous Delivery (CD)

**Continuous Delivery (CD)** đảm bảo rằng phần mềm luôn trong trạng thái có thể triển khai. Trong khi CI tự động hóa việc tích hợp mã, CD mở rộng tự động hóa này để bao gồm việc phát hành lên môi trường sản xuất.

### ⚙️ Các Khái Niệm Chính
- **📦 Pipeline Triển Khai (Deployment Pipeline)**: Tự động hóa các quá trình xây dựng, kiểm thử và triển khai.  
  *Ví dụ:* Một pipeline có thể bao gồm các bước kiểm thử đơn vị, kiểm thử tích hợp, kiểm thử hiệu năng và triển khai lên môi trường staging.

- **✅ Kiểm Thử Tự Động**: Bao gồm các kiểm thử tích hợp, kiểm thử hiệu năng và kiểm thử end-to-end để đảm bảo chất lượng mã.  
  *Ví dụ:* Sau khi chạy các kiểm thử đơn vị, hệ thống sẽ chạy kiểm thử tích hợp để đảm bảo các module hoạt động cùng nhau.

- **📝 Phê Duyệt Thủ Công**: Mã có thể được triển khai lên sản xuất bất cứ lúc nào nhưng thường yêu cầu phê duyệt thủ công từ nhóm phát triển hoặc quản lý.  
  *Ví dụ:* Sau khi pipeline hoàn thành, quản lý dự án có thể kiểm tra và phê duyệt triển khai lên sản xuất.

### 🛠️ Các Công Cụ CD Phổ Biến
- **Spinnaker**: Nền tảng triển khai đa đám mây mạnh mẽ.
- **Jenkins**: Ngoài CI, Jenkins cũng hỗ trợ triển khai tự động.
- **GitLab CI/CD**: Tích hợp mạnh mẽ với GitLab để triển khai liên tục.
- **Azure DevOps**: Dịch vụ CI/CD của Microsoft với tích hợp sâu vào các dịch vụ Azure.
- **Octopus Deploy**: Công cụ triển khai dễ sử dụng với nhiều tính năng mạnh mẽ.

---

## 3. 🚀 Continuous Deployment (CD)

**Continuous Deployment** là bước tiếp theo sau Continuous Delivery. Nó tự động hóa hoàn toàn quá trình triển khai, đẩy mã lên sản xuất tự động khi mã vượt qua tất cả các bước kiểm thử.

### ⚙️ Các Khái Niệm Chính
- **🤖 Pipeline Hoàn Toàn Tự Động**: Không cần sự can thiệp của con người trong quá trình triển khai.
- **📅 Triển Khai Thường Xuyên**: Mã được triển khai lên sản xuất nhiều lần trong ngày.
- **📊 Giám Sát và Rollbacks**: Giám sát liên tục để phát hiện vấn đề và quay lại phiên bản trước nếu cần.  
  *Ví dụ:* Nếu một triển khai mới gây ra lỗi, hệ thống có thể tự động quay lại phiên bản ổn định trước đó.

### 🛠️ Các Công Cụ Continuous Deployment Phổ Biến
- **Argo CD**: Công cụ triển khai liên tục cho Kubernetes.
- **Spinnaker**: Hỗ trợ triển khai đa đám mây với các tính năng nâng cao.
- **Jenkins**: Có thể được cấu hình để triển khai tự động sau khi kiểm thử thành công.
- **Kubernetes (với Helm Charts)**: Sử dụng Helm để quản lý các triển khai Kubernetes một cách hiệu quả.

---

## 4. 🏗️ Các Giai Đoạn của CI/CD Pipeline

<p align="center">
  <img src="https://github.com/ducanhduocdochu/docs-by-me/blob/main/CICD/cicdpipeline.jpg" alt="overview" width="500"/>
</p>

Một pipeline CI/CD điển hình bao gồm các giai đoạn sau:

1. **📂 Source**: Pipeline được kích hoạt khi mã được đẩy lên kho lưu trữ.  
   *Ví dụ:* Khi một lập trình viên push mã lên nhánh `main` trên GitHub, pipeline CI/CD sẽ bắt đầu.

2. **🏗️ Build**: Ứng dụng được xây dựng (biên dịch nếu cần).  
   *Ví dụ:* Jenkins sẽ biên dịch mã nguồn Java thành file `.jar`.

3. **✅ Test**: Chạy các kiểm thử tự động (đơn vị, tích hợp, end-to-end).  
   *Ví dụ:* Chạy các bài kiểm thử đơn vị bằng JUnit và kiểm thử tích hợp bằng Selenium.

4. **🚀 Deploy**: Nếu tất cả kiểm thử vượt qua, ứng dụng được triển khai lên môi trường staging hoặc sản xuất.  
   *Ví dụ:* Sử dụng Docker và Kubernetes để triển khai ứng dụng lên cluster staging.

5. **📊 Monitor**: Sau khi triển khai, các công cụ giám sát kiểm tra tình trạng sức khỏe của ứng dụng.  
   *Ví dụ:* Sử dụng Prometheus và Grafana để theo dõi hiệu suất ứng dụng.

---

## 5. 🎯 Lợi Ích của CI/CD

- **⚡ Phản Hồi Nhanh Chóng**: Các lập trình viên nhận được phản hồi ngay lập tức về chất lượng mã của họ.
- **🔄 Giảm Thiểu Vấn Đề Tích Hợp**: Tích hợp thường xuyên giúp giảm xung đột mã và dễ dàng giải quyết.
- **🛡️ Cải Thiện Chất Lượng Mã**: Các kiểm thử tự động và công cụ kiểm tra mã giúp duy trì chất lượng mã cao.
- **🚀 Thời Gian Thị Trường Nhanh Hơn**: Các pipeline tự động giúp phát hành tính năng mới nhanh chóng và an toàn hơn.
- **🔒 Giảm Thiểu Rủi Ro**: Tự động hóa giảm thiểu sai sót của con người trong quá trình kiểm thử và triển khai.

---

## 6. ✅ Các Thực Tiễn Tốt Nhất cho CI/CD

- **📅 Commit Thường Xuyên**: Khuyến khích lập trình viên commit mã thường xuyên để tránh việc hợp nhất lớn và khó debug.
  *Ví dụ:* Một nhóm phát triển có thể thiết lập quy định rằng mỗi thành viên phải commit ít nhất một lần mỗi ngày.

- **🤖 Tự Động Hóa Mọi Thứ**: Tự động hóa không chỉ kiểm thử mà còn các kiểm tra chất lượng mã, quét bảo mật và triển khai.
  *Ví dụ:* Sử dụng ESLint để tự động kiểm tra chất lượng mã JavaScript trong quá trình build.

- **📈 Giám Sát Liên Tục**: Sử dụng các công cụ giám sát để đảm bảo triển khai thành công và theo dõi hiệu suất trong môi trường sản xuất.
  *Ví dụ:* Thiết lập cảnh báo trên Grafana để nhận biết ngay khi có vấn đề xảy ra sau triển khai.

- **⚠️ Fail Fast**: Nếu có lỗi trong pipeline, nó nên thất bại càng sớm càng tốt để dễ dàng khắc phục.
  *Ví dụ:* Nếu một bài kiểm thử đơn vị thất bại, pipeline nên dừng ngay và thông báo cho nhóm phát triển.

- **🐳 Sử Dụng Containers**: Container hóa (ví dụ: Docker) giúp duy trì môi trường nhất quán giữa phát triển, kiểm thử và sản xuất.
  *Ví dụ:* Sử dụng Docker Compose để thiết lập môi trường phát triển giống như môi trường sản xuất.

---

## 7. 🔧 Hệ Sinh Thái Công Cụ CI/CD

### 📁 Quản Lý Phiên Bản:
- **GitHub** / **GitLab** / **Bitbucket**

### 🛠️ Công Cụ CI:
- **Jenkins**
- **CircleCI**
- **Travis CI**
- **GitLab CI/CD**
- **Azure DevOps**

### 🚀 Công Cụ CD:
- **Spinnaker**
- **Octopus Deploy**
- **AWS CodeDeploy**

### 🐳 Containers & Orchestration:
- **Docker**
- **Kubernetes**
- **Helm**

### ⚙️ Quản Lý Cấu Hình:
- **Ansible**
- **Chef**
- **Puppet**

### 📊 Giám Sát và Ghi Log:
- **Prometheus**
- **Grafana**
- **ELK Stack (Elasticsearch, Logstash, Kibana)**

---

## 8. ☁️ CI/CD Pipelines trong Môi Trường Đám Mây

- **AWS**: Sử dụng AWS CodePipeline, CodeBuild, CodeDeploy và Elastic Beanstalk để xây dựng pipeline CI/CD trên nền tảng AWS.  
  *Ví dụ:* Tạo một pipeline với CodePipeline để tự động hóa việc triển khai ứng dụng Node.js lên Elastic Beanstalk.

- **Azure**: Sử dụng Azure Pipelines và Azure Kubernetes Service (AKS) để thiết lập CI/CD trên Azure.  
  *Ví dụ:* Sử dụng Azure Pipelines để xây dựng và triển khai ứng dụng .NET Core lên AKS.

- **Google Cloud**: Sử dụng Google Cloud Build và Google Kubernetes Engine (GKE) để xây dựng pipeline CI/CD trên Google Cloud.  
  *Ví dụ:* Thiết lập Cloud Build để tự động xây dựng Docker images và triển khai lên GKE.

---

CI/CD giúp tăng tốc độ, an toàn và độ tin cậy của các bản phát hành phần mềm bằng cách tự động hóa các quy trình chính và cung cấp phản hồi liên tục. Đây là nền tảng quan trọng của các chiến lược DevOps hiện đại.

---

## 🌟 Ví dụ Minh Họa Thực Tế
Để hiểu rõ hơn về CI/CD, hãy xem xét một ví dụ thực tế về cách một ứng dụng web có thể triển khai CI/CD:

Phát Triển Mã Nguồn: Lập trình viên làm việc trên tính năng mới của ứng dụng web và commit mã lên nhánh feature/new-feature trên GitHub.

CI Pipeline Kích Hoạt: Khi mã được đẩy lên nhánh, Jenkins tự động bắt đầu pipeline:

Build: Jenkins biên dịch mã nguồn và tạo Docker image.
Test: Chạy các bài kiểm thử đơn vị và kiểm thử tích hợp.
Deploy to Staging: Nếu tất cả các kiểm thử vượt qua, Jenkins triển khai ứng dụng lên môi trường staging trên Kubernetes.
Kiểm Tra và Phê Duyệt: Nhóm QA kiểm tra tính năng mới trên môi trường staging. Nếu mọi thứ ổn, quản lý dự án phê duyệt triển khai lên sản xuất.

vContinuous Deployment: Với phê duyệt, pipeline tự động triển khai Docker image mới lên môi trường sản xuất. Prometheus và Grafana giám sát hiệu suất và sức khỏe của ứng dụng.

Phản Hồi và Cải Thiện: Nếu có vấn đề phát sinh sau triển khai, hệ thống giám sát sẽ phát hiện và tự động rollback về phiên bản ổn định trước đó, đồng thời gửi thông báo tới nhóm phát triển để khắc phục.

---

📝 **Created by ducanhduocdochu**
