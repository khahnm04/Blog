# **Git**

## **1. Giới thiệu về __`Git`__**
- Git là một hệ thống __quản lý phiên bản__

- Git cung cấp __kho lưu trữ (repository)__ để chứa toàn bộ lịch sử phiên bản
- Ưu điểm: tốc độ nhanh, đơn giản, phù hợp với tất cả dự án.
- Ví dụ khi Khi sử dụng Facebook hay nhiều ứng dụng khác, bạn sẽ thấy chúng thường xuyên cập nhật phiên bản: hôm nay là 1.1.1, ngày mai lên 1.1.2, rồi 1.1.3, 1.1.4,... Những bản cập nhật này giúp sửa lỗi hoặc thêm tính năng mới. Tuy nhiên, đôi khi phiên bản mới lại phát sinh lỗi - ví dụ, bạn cập nhật xong thì trang đăng ký bị lỗi, trong khi trước đó nó vẫn hoạt động bình thường. Trong những trường hợp như vậy, việc quay lại phiên bản cũ là rất quan trọng. Nhờ có hệ thống quản lý phiên bản (version control), bạn có thể xem lại lịch sử các phiên bản trước, biết được thay đổi nào đã được thực hiện, và dễ dàng khôi phục lại phiên bản ổn định trước đó.
- Link cài đặt: https://git-scm.com/downloads


## **2. Các thuật ngữ trong __`Git`__**
```
Working directory     Staging area         Repository
       |                   |                    |
       |----- git add ---->|                    |
       |                   |---- git commit --->|
       |                   |                    |
       |                   |                    |
       |                   |                    |
```
- Working directory (Thư mục làm việc): Khu vực chứa toàn bộ mã nguồn của dự án mà chúng ta đang làm việc. Nó chính là thư mục bạn mở trong IDE (như IntelliJ, VS Code) hoặc trình chỉnh sửa văn bản (text editor).
  
- Staging area (Khu vực sắp xếp): Staging area (Khu vực sắp xếp): Đây là nơi tạm lưu các thay đổi của file trước khi bạn chính thức lưu vào lịch sử Git. Bạn có thể xem nó như một bản nháp, nơi bạn chuẩn bị các thay đổi trước khi "chốt" chúng vào kho lưu trữ (repository).
- Repository (Kho lưu trữ): Đây là nơi lưu trữ toàn bộ mã nguồn và lịch sử các phiên bản của dự án. Nó giúp bạn theo dõi, quay lại các phiên bản trước và làm việc nhóm dễ dàng hơn.
  > - Ví dụ:
  >   - Working directory (Thư mục làm việc):
  >     Bạn bắt đầu code cả trang Giới thiệu và trang Liên hệ trong IDE của mình (VS Code, IntelliJ,...). Đây là nơi bạn trực tiếp chỉnh sửa nội dung các file HTML.
  >
  >   - Staging area (Khu vực sắp xếp):
  >     Sau khi code xong, bạn cảm thấy cả hai trang đều tạm ổn, nên dùng lệnh __`git add`__ để đưa cả file gioi-thieu.html và file lien-he.html vào vùng staging. Đây là nơi bạn chuẩn bị mọi thứ trước khi "đóng gói" lại.
  > 
  >   - Khách hàng kiểm tra và phản hồi. Họ bảo rằng trang Giới thiệu đã OK, không cần chỉnh sửa gì. Nhưng trang Liên hệ thì chưa ổn, cần sửa lại nội dung.
  >
  >   - Quay lại Working directory để chỉnh sửa:
  >     Bạn quay lại thư mục làm việc để chỉnh sửa lại file lien-he.html theo góp ý của khách hàng. Sau khi sửa xong, bạn dùng __`git add`__ lien-he.html để cập nhật bản sửa mới lên vùng staging.
  >
  >   - Staging area cập nhật:
  >     Lúc này vùng staging đã có: gioi-thieu.html (vẫn là bản cũ đã ổn) và lien-he.html (bản mới vừa sửa)
  >
  >   - Repository (Kho lưu trữ):
  >     Cuối cùng, bạn dùng __`git commit`__ để tạo một phiên bản mới chứa cả hai file. Git sẽ lưu lại toàn bộ lịch sử thay đổi, bao gồm cả lần bạn sửa lại trang Liên hệ. Nhờ vậy, bạn có thể dễ dàng xem lại hay quay về phiên bản trước nếu cần.

