# Buổi 1: Giới thiệu khóa học phát triển web

## Mục tiêu học tập

Sau buổi học này, bạn sẽ:

- Hiểu được cách hoạt động của một trang web hiện đại
- Nắm vững các khái niệm cơ bản về HTML và CSS
- Có thể tự tay dựng layout web đơn giản
- Đạt 10 điểm giữa kỳ môn "Xây dựng ứng dụng web"

## Nội quy lớp học

- **Chuyên cần**: Không được nghỉ quá 2 buổi (80% số buổi học)
- **Camera**: Bật camera trong suốt buổi học
- **Bài tập**: Hoàn thành đầy đủ các bài tập được giao

## Các khái niệm cơ bản

### Frontend

Là phần "mặt tiền" mà người dùng nhìn thấy và tương tác trực tiếp. Bao gồm giao diện, màu sắc, nút bấm, form nhập liệu, menu... Tất cả những gì bạn click chuột hay gõ phím đều thuộc về frontend.

### Backend

Là phần "hậu trường" chạy ngầm mà người dùng không nhìn thấy. Xử lý logic, quản lý cơ sở dữ liệu, xác thực người dùng... Ví dụ: khi bạn đăng nhập Facebook, frontend hiển thị form đăng nhập, còn backend kiểm tra tài khoản có đúng không.

### Fullstack

Developer biết làm cả frontend lẫn backend. Nói cách khác là "biết làm từ A đến Z" một trang web hoàn chỉnh.

### HTML

**HyperText Markup Language** - Ngôn ngữ đánh dấu tạo cấu trúc trang web. HTML giống như bộ xương của trang web, quy định đâu là tiêu đề, đâu là đoạn văn, đâu là hình ảnh...

### CSS

**Cascading Style Sheets** - Ngôn ngữ trang trí, làm đẹp cho trang web. Nếu HTML là bộ xương thì CSS là "trang phục", quy định màu sắc, font chữ, kích thước, vị trí các phần tử.

### UI (User Interface)

Giao diện người dùng - tất cả những gì người dùng nhìn thấy trên màn hình như button, menu, form, hình ảnh...

### UX (User Experience)

Trải nghiệm người dùng - tập trung vào cảm giác khi sử dụng trang web. Website có dễ dùng không? Tìm thông tin có nhanh chóng không? Có cảm thấy thoải mái không?

## Cài đặt công cụ lập trình

### Phần mềm chính

**Visual Studio Code** - Trình soạn thảo code miễn phí, nhẹ và phổ biến nhất cho phát triển web.
📥 Tải về tại: https://code.visualstudio.com/download

### Các tiện ích mở rộng cần thiết

Sau khi cài VS Code, hãy cài thêm các extension này:

- **Auto Rename Tag** - Đổi tên thẻ mở thì thẻ đóng tự động đổi theo
- **Beautify** - Sắp xếp code gọn gàng, dễ đọc
- **Color Highlight** - Hiển thị màu sắc ngay trong code
- **CSS Variables Autocomplete** - Gợi ý tên biến CSS
- **HTML Boilerplate** - Tạo khung HTML cơ bản nhanh chóng
- **HTML Snippets** - Gợi ý code HTML khi gõ
- **Live Server** - Tự động làm mới trang web khi lưu code
- **Material Icon Theme** - Icon đẹp cho các file
- **Path Intellisense** - Gợi ý đường dẫn file

**Cách cài extension**: Mở VS Code → Click biểu tượng Extensions ở thanh bên trái → Tìm tên extension → Click Install.

## Học HTML

### Khái niệm cơ bản về HTML

- **HTML** viết tắt của **HyperText Markup Language**
- Là ngôn ngữ đánh dấu siêu văn bản
- **Không phải** là ngôn ngữ lập trình
- Có tác dụng tạo bố cục và định dạng trang web

### Cấu trúc file HTML cơ bản

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Tiêu đề trên tab</title>
  </head>
  <body>
    <h1>Tiêu đề chính</h1>
    <p>Đoạn văn bản...</p>
  </body>
</html>
```

### Ý nghĩa các thẻ HTML cơ bản

#### Thẻ khai báo và cấu trúc chính

- **`<!DOCTYPE html>`**: Khai báo kiểu tài liệu - cho trình duyệt biết đây là tài liệu HTML
- **`<html></html>`**: Thẻ bắt buộc, element cấp cao nhất, bao bọc toàn bộ nội dung trang HTML
- **`<head></head>`**: Chứa các thông tin meta của trang web như tiêu đề, charset, không hiển thị trên trang
- **`<title></title>`**: Nằm bên trong thẻ `<head>`, dùng để khai báo tiêu đề của trang (hiển thị trên tab trình duyệt)
- **`<body></body>`**: Chứa tất cả các nội dung sẽ hiển thị trên trang web

#### Thẻ nội dung cơ bản

- **`<h1></h1>`**: Phần tử xác định một tiêu đề lớn (heading 1)
- **`<p></p>`**: Phần tử xác định một đoạn văn bản (paragraph)

### Hướng dẫn sử dụng Dev Tools

_(Sẽ được hướng dẫn trực tiếp khi học)_

### Các thẻ Meta quan trọng

Thẻ `<meta>` cung cấp thông tin metadata về trang web, đặt trong thẻ `<head>`:

```html
<meta charset="UTF-8" />
```

- Xác định bộ ký tự UTF-8 để hỗ trợ hiển thị tiếng Việt

```html
<meta name="keywords" content="HTML, CSS, JavaScript" />
```

- Xác định từ khóa cho công cụ tìm kiếm

```html
<meta name="description" content="Free Web tutorials" />
```

- Xác định mô tả về trang web (hiển thị trên Google)

```html
<meta name="author" content="John Doe" />
```

- Xác định tác giả của trang

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

- Đặt chế độ xem để trang web hiển thị tốt trên tất cả thiết bị (responsive)

### Comments, Elements, Attributes

#### Comments (Chú thích)

- Là các chú thích để dễ nhớ và hiểu code, không hiển thị lên giao diện
- **Cú pháp**: `<!-- Nội dung comment -->`
- **Phím tắt**: Ctrl + / (Windows) hoặc Cmd + / (Mac)

#### Elements (Phần tử)

- Được xác định bởi: thẻ bắt đầu + nội dung + thẻ kết thúc
- **Cú pháp**: `<tagname>Nội dung...</tagname>`
- **Ví dụ**: `<h1>Tiêu đề lớn</h1>`
- Tên thẻ không phân biệt hoa thường, nhưng nên viết thường

#### Attributes (Thuộc tính)

- Cung cấp thêm thông tin cho elements, nằm trong thẻ mở
- Một element có thể có nhiều thuộc tính
- **Cú pháp**: `<tagname attribute-name="value">Nội dung...</tagname>`
- **Ví dụ**: `<html lang="vi"></html>`

### Headings, Paragraphs, Formatting

#### Headings (Tiêu đề)

Có 6 thẻ heading từ quan trọng nhất đến ít quan trọng nhất:

- **`<h1></h1>`**: Tiêu đề quan trọng nhất, mỗi trang chỉ nên có 1 thẻ h1 (chuẩn SEO)
- **`<h2></h2>`**: Tiêu đề phụ cấp 2
- **`<h3></h3>`**: Tiêu đề phụ cấp 3
- **`<h4></h4>`**: Tiêu đề phụ cấp 4
- **`<h5></h5>`**: Tiêu đề phụ cấp 5
- **`<h6></h6>`**: Tiêu đề ít quan trọng nhất

#### Paragraphs (Đoạn văn)

- **`<p>Nội dung…</p>`**: Tạo đoạn văn, luôn bắt đầu trên dòng mới
- **`<hr>`**: Tạo đường kẻ ngang ngăn cách chủ đề (thẻ trống)
- **`<br>`**: Ngắt dòng trong đoạn văn bản (thẻ trống)

#### Formatting (Định dạng văn bản)

**Làm đậm văn bản:**

- **`<b></b>`**: Văn bản in đậm (chỉ hiển thị)
- **`<strong></strong>`**: Văn bản in đậm và quan trọng (có ý nghĩa)

**Làm nghiêng văn bản:**

- **`<i></i>`**: Văn bản in nghiêng (chỉ hiển thị)
- **`<em></em>`**: Văn bản in nghiêng và nhấn mạnh (có ý nghĩa)

**Các định dạng khác:**

- **`<small></small>`**: Văn bản chữ nhỏ hơn
- **`<sub></sub>`**: Văn bản có chỉ số dưới (H₂O)
- **`<sup></sup>`**: Văn bản có chỉ số trên (x²)
- **`<ins></ins>`**: Văn bản được chèn (gạch chân)
- **`<del></del>`**: Văn bản đã xóa (gạch ngang)
- **`<mark></mark>`**: Văn bản được đánh dấu (highlight)

### Lưu ý quan trọng

- File HTML phải có phần mở rộng `.html` hoặc `.htm`
- Thẻ `<head>` chứa thông tin cho trình duyệt, không hiển thị cho người dùng
- Thẻ `<body>` chứa nội dung hiển thị trên trang web
- Mỗi trang HTML chỉ nên có một thẻ `<h1>` để chuẩn SEO
- Nên dùng `<strong>` thay vì `<b>`, `<em>` thay vì `<i>` vì có ý nghĩa ngữ nghĩa
