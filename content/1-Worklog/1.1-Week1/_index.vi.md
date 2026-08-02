---
title: "Worklog Tuần 1"
date: 2026-06-15
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1

- Làm quen và kết nối với các thành viên trong chương trình First Cloud AI Journey.
- Tham gia buổi họp khởi động dự án và thống nhất định hướng kiến trúc AWS Hybrid.
- Nghiên cứu kiến trúc Monolith và Serverless để hiểu cách kết hợp hai mô hình trong hệ thống.
- Tìm hiểu tổng quan các dịch vụ AWS xuất hiện trong sơ đồ kiến trúc.
- Hoàn thành việc tạo tài khoản AWS Free Tier.

### Các công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tham gia buổi họp kick-off của nhóm.<br>- Thảo luận và thống nhất phương án kiến trúc AWS Hybrid.<br>- Phân chia nhiệm vụ cho các nhóm Frontend, Backend và AWS Admin. | 15/06/2026 | 15/06/2026 | |
| 3 | - Tìm hiểu về kiến trúc Monolith và Serverless, bao gồm đặc điểm, ưu điểm và các trường hợp sử dụng. | 16/06/2026 | 16/06/2026 | |
| 4 | - Nghiên cứu các dịch vụ AWS trong sơ đồ kiến trúc:<br>&emsp;+ EC2, Lambda (Compute)<br>&emsp;+ Amazon RDS PostgreSQL (Database)<br>&emsp;+ API Gateway, Elastic Load Balancer (Networking)<br>&emsp;+ Cognito, IAM (Security & Identity)<br>&emsp;+ SNS (Messaging)<br>&emsp;+ Amazon S3 (Storage)<br>&emsp;+ CloudWatch (Monitoring) | 17/06/2026 | 18/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Đăng ký và thiết lập tài khoản AWS Free Tier phục vụ cho quá trình học tập và phát triển dự án. | 19/06/2026 | 19/06/2026 | |

### Kết quả đạt được tuần 1

- Tham gia đầy đủ buổi họp kick-off và thống nhất lựa chọn kiến trúc AWS Hybrid cho hệ thống đặt sân thể thao, trong đó:
  - Chức năng **Đăng ký/Đăng nhập** và **Quản lý đặt sân** được triển khai theo mô hình Monolith trên EC2.
  - Chức năng **Thanh toán** được triển khai theo mô hình Serverless sử dụng Lambda và API Gateway.

- Hiểu được sự khác biệt giữa hai mô hình triển khai:
  - **Monolith:** Toàn bộ nghiệp vụ được triển khai trong một ứng dụng duy nhất, phù hợp với các chức năng cần xử lý liên tục và có độ trễ thấp.
  - **Serverless:** Hoạt động theo cơ chế sự kiện, có khả năng mở rộng linh hoạt và không cần quản lý máy chủ, phù hợp với xử lý webhook thanh toán.

- Nắm được vai trò của các dịch vụ AWS trong hệ thống:
  - **Compute:** Amazon EC2 vận hành ứng dụng FastAPI, AWS Lambda xử lý quy trình thanh toán.
  - **Database:** Amazon RDS PostgreSQL lưu trữ dữ liệu tập trung và hỗ trợ hạn chế tình trạng đặt trùng sân.
  - **Networking:** API Gateway tiếp nhận webhook, Elastic Load Balancer phân phối lưu lượng đến EC2.
  - **Security & Identity:** Amazon Cognito thực hiện xác thực người dùng, IAM quản lý quyền truy cập giữa các dịch vụ.
  - **Messaging:** Amazon SNS gửi thông báo xác nhận đặt sân.
  - **Storage:** Amazon S3 lưu trữ hình ảnh sân và các tài nguyên tĩnh.
  - **Monitoring:** Amazon CloudWatch theo dõi log và giám sát hoạt động của hệ thống.

- Đã tạo thành công tài khoản AWS Free Tier để chuẩn bị cho các giai đoạn triển khai tiếp theo.

---

### Biên bản họp nhóm — 20/06/2026

**Thành viên tham dự:** Hiếu, Thành, Danh *(Vắng: Nguyên, Hùng)*

#### Quyết định kiến trúc

Sau khi Hiếu trình bày phương án kiến trúc AWS Hybrid cho ứng dụng đặt sân thể thao, nhóm thống nhất triển khai các chức năng như sau:

| Tính năng | Mô hình triển khai |
| --- | --- |
| Đăng ký / Đăng nhập | Monolith (EC2) |
| Quản lý đặt sân (Tạo / Sửa / Hủy / Xem / Tìm kiếm) | Monolith (EC2) |
| Thanh toán | Serverless (Lambda + API Gateway) |

#### Phân công công việc

| Nhóm | Người phụ trách | Nội dung thực hiện |
| --- | --- | --- |
| Toàn bộ thành viên | Cả nhóm | Đánh giá và đóng góp ý kiến cho kiến trúc đề xuất. |
| Frontend | Nhóm FE | Nghiên cứu các ứng dụng tương tự, xây dựng UX/UI, đề xuất design system (màu sắc, font chữ, icon) và danh sách các màn hình. |
| Backend — Quản lý đặt sân | Thanh | Thiết kế API, mô tả use case và xây dựng cơ sở dữ liệu cho chức năng đặt sân. |
| Backend — Xác thực người dùng | Nguyen | Thiết kế API và cơ sở dữ liệu cho chức năng xác thực. |
| Backend — Thanh toán | Hieu | Thiết kế API và cơ sở dữ liệu cho chức năng thanh toán. |
| AWS Admin | AWS Admin | Thiết lập AWS Organization, tài khoản, IAM Users, Roles và Policies. |

#### Kế hoạch tuần tiếp theo

- Nhóm Frontend hoàn thành nghiên cứu thị trường và bản thiết kế UI sơ bộ trước cuối tuần 2.
- Nhóm Backend hoàn thiện tài liệu API và thiết kế cơ sở dữ liệu trong tuần 2.
- AWS Admin hoàn thành cấu hình tài khoản và phân quyền cơ bản để chuẩn bị triển khai hạ tầng ở tuần 3.

---

### Bảng thuật ngữ

| Viết tắt | Ý nghĩa |
| --- | --- |
| AI | Trí tuệ nhân tạo |
| API | Giao diện lập trình ứng dụng, cho phép các thành phần phần mềm trao đổi dữ liệu với nhau |
| AWS | Amazon Web Services – nền tảng điện toán đám mây của Amazon |
| BE | Backend – phần xử lý phía máy chủ |
| DB | Cơ sở dữ liệu |
| EC2 | Amazon Elastic Compute Cloud – dịch vụ máy chủ ảo |
| ELB | Elastic Load Balancer – dịch vụ cân bằng tải |
| FE | Frontend – giao diện phía người dùng |
| IAM | Identity and Access Management – dịch vụ quản lý danh tính và quyền truy cập |
| RDS | Relational Database Service – dịch vụ cơ sở dữ liệu quan hệ |
| S3 | Simple Storage Service – dịch vụ lưu trữ đối tượng |
| SNS | Simple Notification Service – dịch vụ gửi thông báo |
| UI | User Interface – giao diện người dùng |
| UX | User Experience – trải nghiệm người dùng |
