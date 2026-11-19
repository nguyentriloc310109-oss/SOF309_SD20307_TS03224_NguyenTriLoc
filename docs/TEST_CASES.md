# KỊCH BẢN KIỂM THỬ CÁ NHÂN - NGUYỄN TRÍ LỘC (TS03224)

- **Dự án:** Hệ thống quản lý & đặt mua linh kiện máy tính ApexGear
- **Sinh viên thực hiện:** Nguyễn Trí Lộc - MSSV: TS03224 - Lớp: SD20307
- **Phạm vi kiểm thử:** Kiểm tra đăng nhập nhân viên/khách hàng và kiểm tra hợp lệ dữ liệu sản phẩm phần cứng

| Mã TC | Nhóm chức năng | Mô tả kiểm thử | Loại | Các bước thực hiện | Dữ liệu đầu vào | Kết quả mong đợi | Trạng thái |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_LOC_01 | Xác thực tài khoản | Đăng nhập thành công bằng tài khoản sinh viên/nhân viên | Positive | 1. Mở trang đăng nhập<br>2. Nhập mã tài khoản và mật khẩu<br>3. Nhấn nút Đăng nhập | `locnt_ts03224` / `Loc@310109` | Chuyển sang trang danh sách sản phẩm và hiển thị tên tài khoản | Pass |
| TC_LOC_02 | Xác thực tài khoản | Từ chối đăng nhập khi mật khẩu không khớp | Negative | 1. Nhập tài khoản hợp lệ<br>2. Nhập mật khẩu sai<br>3. Nhấn nút Đăng nhập | `locnt_ts03224` / `sai_mat_khau_99` | Hiển thị thông báo lỗi sai thông tin đăng nhập, giữ nguyên trang | Pass |
| TC_LOC_03 | Xác thực tài khoản | Chặn đăng nhập khi bỏ trống tên đăng nhập | Negative | 1. Để trống ô tên đăng nhập<br>2. Nhập mật khẩu<br>3. Nhấn nút Đăng nhập | `""` / `Loc@310109` | Hiển thị thông báo yêu cầu nhập tên đăng nhập | Pass |
| TC_LOC_04 | Sản phẩm phần cứng | Thêm linh kiện mới với giá và số lượng hợp lệ | Positive | 1. Mở form thêm sản phẩm<br>2. Nhập tên, đơn giá, tồn kho<br>3. Nhấn Lưu | Tên: `SSD NVMe 1TB`, Giá: `2450000`, SL: `12` | Lưu bản ghi mới thành công và hiện trên bảng quản lý | Pass |
| TC_LOC_05 | Sản phẩm phần cứng | Từ chối thêm sản phẩm khi đơn giá âm | Negative | 1. Mở form thêm sản phẩm<br>2. Nhập đơn giá nhỏ hơn 0<br>3. Nhấn Lưu | Tên: `Mainboard B760M`, Giá: `-250000`, SL: `4` | Báo lỗi đơn giá phải lớn hơn 0, không lưu vào hệ thống | Pass |
| TC_LOC_06 | Sản phẩm phần cứng | Kiểm tra biên khi số lượng tồn kho bằng 0 | Positive | 1. Nhập sản phẩm hết hàng với số lượng `0`<br>2. Nhấn Lưu | Tên: `Nguồn PSU 750W`, Giá: `1890000`, SL: `0` | Chấp nhận lưu với trạng thái tồn kho bằng `0` | Pass |
