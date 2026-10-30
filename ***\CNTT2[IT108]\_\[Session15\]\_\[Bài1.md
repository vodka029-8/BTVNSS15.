Dưới đây là phần nội dung hoàn chỉnh và chi tiết nhất cho **Bài 10: Lựa Chọn Nền Tảng Giao Tiếp Nhóm** (thuộc Buổi 15 môn Nhập Môn Công Nghệ Thông Tin) để bạn đưa vào kho chứa GitHub theo đúng chuẩn quy định (`CNTT2_IT108_Session15_Bai10`) và nộp bài.

---

# BÀI TẬP VỀ NHÀ: LỰA CHỌN NỀN TẢNG GIAO TIẾP NHÓM (CAMPUSPAY)

## Phần 1: Phân tích & Đề xuất (Đa giải pháp)

### 1. Phân tích yêu cầu bài toán

* **Đầu vào (Nhu cầu thực tế của nhóm CampusPay - 4 đến 5 thành viên):** Nhóm đang phát triển dự án startup sinh viên, cần một môi trường thảo luận có cấu trúc, phân chia rõ ràng các ban (Kinh doanh, Kỹ thuật, Thiết kế, Truyền thông), có khả năng giao tiếp bất đồng bộ (tránh việc đọc tin nhắn trễ bị mất ngữ cảnh), tích hợp công cụ quản lý công việc và lưu trữ tài liệu lịch sử quyết định kiến trúc.
* **Đầu ngõ/Đầu ra mong đợi:** Tìm ra một nền tảng giao tiếp tối ưu giúp loại bỏ hoàn toàn tình trạng trôi tin nhắn, tăng tính kỷ luật, quản lý task trực tiếp và tối ưu hóa thời gian phối hợp nhóm.

### 2. Phân tích ưu và nhược điểm của Giải pháp A (Zalo) và Giải pháp B (Lark Suite) theo tiêu chí nghiệp vụ

#### Giải pháp A — Zalo (Chat cá nhân truyền thống)

* **Ưu điểm:**
* Cả nhóm đã dùng quen từ trước, giao diện thân quen, không mất thời gian học cách sử dụng.
* Hoàn toàn miễn phí, sẵn có trên điện thoại di động của tất cả thành viên.
* Hỗ trợ gửi hình ảnh, file nhanh chóng và tính năng ghim tin nhắn cơ bản.


* **Nhược điểm:**
* Dòng tin nhắn chat chung bị trôi rất nhanh do các thông tin tán gẫu, chào hỏi lẫn lộn với công việc.
* Không có tính năng tạo Task, phân công deadline hay quản lý trạng thái công việc (to-do, doing, done) trong cùng một giao diện.
* Khả năng tìm kiếm lại các quyết định cũ, file cũ rất kém, hay bị giới hạn thời gian lưu trữ file trên cloud cá nhân.



#### Giải pháp B — Lark Suite (Nền tảng cộng tác doanh nghiệp)

* **Ưu điểm:**
* Hệ thống hóa bằng **Channel (Kênh chuyên đề)** giúp phân chia rõ ràng từng chủ đề (`#thong-bao`, `#dev`, `#design`, `#kinh-doanh`).
* Tính năng **Reply in Thread** giúp giữ khung chat chính luôn sạch sẽ, gom các cuộc tranh luận kỹ thuật vào một luồng riêng biệt.
* Chuyển tin nhắn chat thành Task có deadline cụ thể chỉ với 1-click.
* Tích hợp toàn diện **Calendar, Docs, Video call** trong một hệ sinh thái duy nhất.


* **Nhược điểm:**
* Yêu cầu thời gian để làm quen (learning curve) khoảng 1–2 ngày đối với các thành viên mới lần đầu tiếp cận công cụ doanh nghiệp.



---

## Phần 2: So sánh & Lựa chọn

### 3. Bảng so sánh 5 tiêu chí nghiệp vụ

| Tiêu chí nghiệp vụ | Giải pháp A (Zalo) | Giải pháp B (Lark Suite) |
| --- | --- | --- |
| **1. Ngăn chặn tin nhắn bị trôi** | ❌ Kém (Trộn lẫn công việc và cá nhân) | ✅ Tốt (Chia channel chuyên đề & Thread) |
| **2. Quản lý công việc (Task & Deadline)** | ❌ Kém (Chỉ nhắn miệng, dễ quên) | ✅ Tốt (Chuyển chat thành task, gán hạn hoàn thành) |
| **3. Độ miễn phí & dễ cài đặt** | ✅ Tốt (Sẵn có, không tốn công cài) | ⚠️ Trung bình (Cần cài app và mất thời gian học) |
| **4. Tìm kiếm lịch sử (Audit Trail)** | ⚠️ Trung bình (Khó tìm từ khóa cũ, mất file) | ✅ Tốt (Bộ lọc tìm kiếm thông minh theo người/từ khóa) |
| **5. Giao tiếp bất đồng bộ (Context)** | ❌ Kém (Tin trôi làm mất ngữ cảnh) | ✅ Tốt (Ghi chú, tài liệu và thread chi tiết) |

### 4. Chốt lựa chọn & Lập luận xử lý bẫy dữ liệu

* **Chốt lựa chọn:** Áp dụng **Giải pháp lai (Hybrid Solution)** hoặc chuyển dịch cốt lõi sang **Lark Suite** cho toàn bộ hoạt động nội bộ nhóm, kết hợp một kênh nhỏ/nhóm Zalo riêng để liên lạc nhanh với đối tác ngoài trường (nếu đối tác đó hoàn toàn không dùng Lark).
* **Cách giải quyết 3 bẫy dữ liệu:**
* *Xử lý Bẫy 1 (Thành viên ban KD chỉ dùng điện thoại):* Lark Suite có ứng dụng di động (Mobile App) rất tối ưu, đầy đủ tính năng chat, xem task và duyệt tài liệu tương tự bản PC.
* *Xử lý Bẫy 2 (Chi phí học tập trong lúc gấp rút):* Khoảng thời gian 1-2 ngày đầu tư học Lark Suite là hoàn toàn xứng đáng vì về lâu dài nó tiết kiệm hàng chục giờ tranh cãi, mất file và trôi việc cho nhóm.
* *Xử lý Bẫy 3 (Đối tác ngoài chỉ dùng Zalo):* Chỉ duy trì nhóm Zalo cho công việc ngoại giao với đối tác bên ngoài, còn toàn bộ quy trình vận hành và tài nguyên của nhóm CampusPay bắt buộc chạy trên Lark Suite.



---

## Phần 3: Thiết kế & Triển khai (Lark Suite)

### 5. Cấu trúc Channel cho nhóm CampusPay (4 ban) và Quy tắc chống Spam

* **Danh sách các Channel tiêu chuẩn:**
1. `#01-thong-bao-chung`: Nơi đăng thông báo quan trọng từ trưởng nhóm. *Quyền đăng bài:* Chỉ Trưởng nhóm / Quản trị viên.
2. `#02-dev-ky-thuat`: Trao đổi code, lỗi hệ thống, triển khai hạ tầng. *Quyền đăng bài:* Thành viên ban Kỹ thuật.
3. `#03-design-giao-dien`: Thảo luận UI/UX, hình ảnh, banner. *Quyền đăng bài:* Thành viên ban Thiết kế & Truyền thông.
4. `#04-kinh-doanh-tai-chinh`: Báo cáo doanh thu, kế hoạch tiếp cận khách hàng. *Quyền đăng bài:* Thành viên ban Kinh doanh.
5. `#05-giai-tri-chung`: Góc thư giãn, trò chuyện ngoài giờ làm việc của cả nhóm. *Quyền đăng bài:* Tất cả thành viên.


* **Quy tắc phòng tránh Spam @all ("Quy tắc cờ đỏ"):**
* Cấm sử dụng thẻ `@all` hoặc `@channel` cho các thông tin mang tính chất trao đổi cá nhân hoặc không khẩn cấp.
* Chỉ được phép dùng `@all` trong các trường hợp **Khẩn cấp** (sập server, thay đổi lịch họp đột xuất, lỗi hệ thống thanh toán nghiêm trọng).
* Vi phạm quy tắc cờ đỏ sẽ bị phạt quỹ nhóm theo nội quy nội bộ đã thống nhất.
