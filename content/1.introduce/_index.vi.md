---
title: "Giới thiệu"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

Dự án **Tạo trình tường thuật sách** sử dụng **AWS Polly**, một dịch vụ đám mây mạnh mẽ giúp chuyển đổi văn bản thành giọng nói có âm thanh tự nhiên. Mục tiêu là cung cấp trải nghiệm thính giác hấp dẫn và dễ tiếp cận cho người đọc bằng cách chuyển đổi nội dung văn bản thành âm thanh chất lượng cao.

### AWS Polly là gì?

AWS Polly là dịch vụ Amazon Web Services (AWS) cung cấp khả năng chuyển văn bản thành giọng nói. Nó cho phép các nhà phát triển tạo ra lời nói sống động như thật từ văn bản thuần túy bằng nhiều giọng nói có thể tùy chỉnh. Polly hỗ trợ nhiều ngôn ngữ và cung cấp một cách liền mạch để tích hợp tổng hợp giọng nói vào các ứng dụng, trang web và nền tảng khác.

### Chương trình hoạt động như thế nào?

![sơ đồ dự án](/images/diagrams/project-diagram.png)

- **Nội dung văn bản được tải lên bởi người dùng:**

  - Người dùng tải sách hoặc tài liệu mong muốn của họ ở định dạng văn bản lên Amazon S3 bucket.
  - S3 bucket hoạt động như một kho lưu trữ cho các tệp văn bản đầu vào.

- **Kích hoạt hàm Lambda:**

  - Khi một tệp văn bản mới được tải lên, một hàm AWS Lambda sẽ được kích hoạt.
  - Hàm Lambda xử lý văn bản mới được tải lên và bắt đầu quá trình chuyển đổi.

- **Chuyển đổi văn bản thành âm thanh:**

  - Hàm Lambda tương tác với AWS Polly để chuyển đổi văn bản thành âm thanh chất lượng cao.
  - Polly sử dụng các thuật toán nâng cao để tạo ra giọng nói tự nhiên với các đặc điểm giọng nói có thể tùy chỉnh.

- **Lưu tệp âm thanh:**

  - Tệp âm thanh thu được được tạo bởi Polly.
  - Hàm Lambda lưu tệp âm thanh trở lại bộ chứa S3 khác được chỉ định để lưu trữ âm thanh.

- **Truy cập nội dung tường thuật:**
  - Người dùng có thể truy cập nội dung tường thuật bằng cách truy xuất tệp âm thanh từ bộ chứa S3 được chỉ định.
  - Họ có thể nghe sách hoặc tài liệu bằng bất kỳ trình phát âm thanh tương thích nào.
