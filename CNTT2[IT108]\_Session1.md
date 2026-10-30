## 1. Báo cáo phân tích (I/O) & Luồng dữ liệu (Data Flow)

Mô tả chi tiết luồng xử lý từ lúc lập trình viên thực hiện thao tác lưu file trên môi trường Local cho đến khi cập nhật lên Cloud:

1. **Thao tác lưu file (`Ctrl + S`):** Lập trình viên thay đổi mã nguồn trong thư mục `src/` và nhấn lưu. Hệ thống ghi nhận file thay đổi trên ổ cứng SSD cục bộ (Local Storage).
2. **Quét thay đổi (File System Watcher):** Phần mềm đồng bộ đám mây (OneDrive, Google Drive,...) quét qua thư mục dự án để phát hiện các file mới hoặc thay đổi.
3. **Kiểm tra bộ lọc (Ignore Rules):** Hệ thống kiểm tra tệp cấu hình `.gitignore` hoặc bộ lọc của ứng dụng sync để xác định xem tệp/thư mục có nằm trong diện bị loại trừ hay không.
4. **Đồng bộ có chọn lọc (Selective Sync):**
* Các file mã nguồn thực tế (`.js`, `.html`, `.css`, `package.json`) được mã hóa và tải lên Cloud Workspace an toàn.
* Thư mục nặng như `node_modules` (chứa hàng vạn file nhỏ) bị chặn lại hoàn toàn, không đưa lên đám mây nhằm tránh làm tràn dung lượng và treo ứng dụng.


5. **Hoàn tất (Sync Complete):** Biểu tượng tích xanh xuất hiện trên các file và thư mục đã đồng bộ thành công.

---

## 2. Thiết kế Sơ đồ tổ chức thư mục Cloud chuẩn cho Lập trình viên

Cấu trúc cây thư mục được thiết kế khoa học, tối ưu dung lượng và bảo mật khi làm việc trên môi trường Hybrid Workspace:

```text
Project_GreenTech_JS/
├── .github/                 # Cấu hình GitHub Actions & CI/CD workflow
├── docs/                    # Tài liệu đặc tả kỹ thuật, hướng dẫn cài đặt (Markdown, Word)
├── src/                     # Source code chính của ứng dụng (JavaScript / Frontend / Backend)
│   ├── config/              # Các file cấu hình kết nối hệ thống
│   ├── models/              # Định nghĩa cấu trúc dữ liệu
│   └── app.js               # File khởi chạy ứng dụng chính
├── .env                     # File chứa biến môi trường bảo mật (Tuyệt đối không đẩy lên public repo)
├── .gitignore               # Tệp quy định các thư mục bị loại trừ khỏi Git/Cloud Sync (đặc biệt là node_modules/)
├── package.json             # File quản lý các gói thư viện phụ thuộc của Node.js
└── README.md                # Tài liệu tổng quan dự án

```

---

## 3. Giải pháp kỹ thuật xử lý Bẫy dữ liệu (`node_modules`)

* **Vấn đề:** Thư mục `node_modules` chứa hàng chục nghìn file phụ thuộc rất nhỏ, khiến ứng dụng đồng bộ đám mây bị đơ (`freeze`), ngốn băng thông và làm cạn kiệt dung lượng Cloud miễn phí.
* **Cách khắc phục triệt để:**
1. Thêm ngay dòng `node_modules/` vào trong file `.gitignore` và thiết lập quy tắc ngoại trừ (Exclude) tương ứng trên phần mềm Cloud Sync.
2. Khi chuyển sang máy tính mới hoặc đồng bộ cho thành viên khác trong nhóm, chỉ cần đồng bộ file `package.json` và chạy lệnh `npm install` tại local để hệ thống tự động tải lại các thư viện cần thiết thay vì đồng bộ sẵn hàng vạn file rác lên mây.
