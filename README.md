# Portfolio CV cá nhân Đinh Công Tuấn Anh

Trang portfolio/CV cá nhân dạng tĩnh, giới thiệu thông tin cá nhân, kỹ năng, dự án và cách liên hệ. Giao diện được xây dựng theo hướng responsive, ưu tiên hiển thị tốt trên điện thoại, máy tính bảng và máy tính.

## Chức năng

- Hiển thị phần giới thiệu, vai trò và ảnh đại diện.
- Trình bày danh sách kỹ năng và các dự án tiêu biểu.
- Điều hướng đến các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ ngay trên trang.
- Cung cấp thông tin liên hệ qua email, GitHub và LinkedIn.
- Tương thích với các kích thước màn hình khác nhau.

> Đây là website tĩnh, chưa có backend, biểu mẫu gửi dữ liệu hay chức năng xử lý tài khoản. Nội dung dự án và một số thông tin liên hệ hiện là dữ liệu mẫu; hãy thay bằng thông tin thật trước khi xuất bản. Tên hiển thị trong một số phần của `index.html` hiện chưa đồng nhất.

## Công nghệ

- HTML5: cấu trúc và nội dung trang.
- CSS3: giao diện, responsive, Flexbox và CSS Grid.
- JavaScript: không sử dụng trong phiên bản hiện tại.
- Apache HTTP Server: có thể dùng để phục vụ trang trong Docker.

## Cấu trúc dự án

```text
CV-main/
├── index.html
├── README.md
└── assets/
	├── css/
	│   └── styles.css
	└── img/
		├── avatar.jpg
		└── nhung-buc-anh-an-tuong-dau-tien-cua-giai-thuong-nhiep-anh-the-gioi-sony-2019-docx-1552698917133.webp
```

## Yêu cầu môi trường

Để mở trang trực tiếp, chỉ cần một trình duyệt hiện đại như Chrome, Edge, Firefox hoặc Safari. Không cần cài Node.js, npm hay thư viện phụ thuộc.

Để chạy bằng máy chủ cục bộ, cài Python 3 (hoặc dùng tiện ích Live Server trong Visual Studio Code). Để chạy bằng container, cài Docker Desktop trên Windows/macOS hoặc Docker Engine và Docker CLI trên Linux.

## Cài đặt

1. Tải mã nguồn về máy hoặc giải nén tệp ZIP của dự án.
2. Mở thư mục `CV-main` trong Visual Studio Code hoặc trình quản lý tệp.
3. Có thể mở `index.html` trực tiếp bằng trình duyệt; không cần bước cài dependency.

Nếu đã cài Git, có thể sao chép dự án bằng URL repository của bạn:

```bash
git clone <URL-repository>
cd CV-main
```

Thay `<URL-repository>` bằng URL thực tế của repository.

## Cấu hình nội dung

Không có tệp cấu hình môi trường hoặc biến `.env`. Chỉnh sửa trực tiếp các tệp sau:

- `index.html`: tên, chức danh, phần giới thiệu, kỹ năng, nội dung dự án và thông tin liên hệ.
- `assets/css/styles.css`: màu sắc, kiểu chữ, bố cục và các quy tắc responsive.
- `assets/img/`: ảnh đại diện và các ảnh minh họa. Khi thay ảnh, cập nhật đường dẫn `src` trong `index.html` cho khớp tên tệp.

Trước khi công khai trang, hãy cập nhật các liên kết `href="#"`, email mẫu `an.nguyen@example.com`, đường dẫn mạng xã hội và các tên đang chưa thống nhất. Các thẻ dự án hiện chỉ là nội dung giới thiệu, không tự động liên kết tới ứng dụng bên ngoài.

## Chạy thử

### Windows

Mở PowerShell tại thư mục dự án rồi chạy:

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có nhưng đã cài Python, thử `python -m http.server 8000`. Mở <http://localhost:8000> trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

### macOS

Mở Terminal, chuyển đến thư mục dự án rồi chạy:

```bash
cd /duong-dan/toi/CV-main
python3 -m http.server 8000
```

Mở <http://localhost:8000>. Dừng máy chủ bằng `Ctrl+C`.

### Linux

Mở Terminal, chuyển đến thư mục dự án rồi chạy:

```bash
cd /duong-dan/toi/CV-main
python3 -m http.server 8000
```

Mở <http://localhost:8000>. Nếu hệ thống chưa có Python 3, hãy cài Python 3 bằng trình quản lý gói của bản phân phối hoặc dùng Docker theo hướng dẫn bên dưới. Dừng máy chủ bằng `Ctrl+C`.

### Visual Studio Code (mọi hệ điều hành)

Mở thư mục dự án trong Visual Studio Code, cài tiện ích Live Server nếu cần, nhấp chuột phải vào `index.html` và chọn **Open with Live Server**. Mở địa chỉ mà tiện ích hiển thị.

## Chạy bằng Docker

Dự án hiện không có `Dockerfile` hoặc `docker-compose.yml`. Các lệnh dưới đây dùng image Apache chính thức và gắn thư mục dự án ở chế độ chỉ đọc; cần Docker đang chạy và kết nối Internet ở lần tải image đầu tiên.

### Windows PowerShell

Mở PowerShell tại thư mục `CV-main`:

```powershell
docker run --rm --name portfolio-cv -p 8080:80 -v "${PWD}:/usr/local/apache2/htdocs:ro" httpd:2.4
```

### Windows Command Prompt (CMD)

Mở CMD tại thư mục `CV-main`:

```bat
docker run --rm --name portfolio-cv -p 8080:80 -v "%cd%:/usr/local/apache2/htdocs:ro" httpd:2.4
```

### macOS và Linux

Mở Terminal tại thư mục `CV-main`:

```bash
docker run --rm --name portfolio-cv -p 8080:80 -v "$(pwd):/usr/local/apache2/htdocs:ro" httpd:2.4
```

Sau khi container khởi động, mở <http://localhost:8080>. Nhấn `Ctrl+C` để dừng; tùy chọn `--rm` tự xóa container sau khi dừng. Nếu cổng `8080` đang được sử dụng, đổi phần `8080:80` thành cổng trống khác, ví dụ `8081:80`, rồi mở cổng mới tương ứng.

## Thông tin liên hệ

Thông tin liên hệ đang được hiển thị trên trang là dữ liệu mẫu. Vui lòng thay bằng thông tin của chủ dự án trong `index.html` trước khi sử dụng:

- Email: `an.nguyen@example.com`
- GitHub: `github.com/nguyenvanan` (liên kết hiện chưa được cấu hình)
- LinkedIn: `linkedin.com/in/nguyenvanan` (liên kết hiện chưa được cấu hình)

## Giấy phép

Chưa có thông tin giấy phép trong repository. Hãy bổ sung tệp `LICENSE` nếu muốn quy định cách người khác được sử dụng hoặc phân phối mã nguồn.
