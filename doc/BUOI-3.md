# Bài 3: Học HTML, HTML5 (tiếp)

## Nội dung

1. Nhúng Iframe
2. Một số thẻ Semantic
3. Forms (Form Attributes, Form Elements, Input Types, Input Attributes)
4. Những tính năng HTML5 có mà HTML không có

---

## 1. Nhúng Iframe

### Khái niệm

- Thẻ `<iframe></iframe>` được sử dụng để hiển thị một trang web trong một trang web.

### Cú pháp

```html
<iframe src="url" title="description" height="200" width="300"></iframe>
```

### Ví dụ

```html
<iframe
  src="https://daca.vn/"
  title="Website Daca"
  width="1200"
  height="600"
></iframe>
<iframe
  src="https://khoahoc.28tech.com.vn/"
  title="Website 28Tech"
  width="1200"
  height="600"
></iframe>
```

### Mục tiêu cho một liên kết

- Thuộc tính `target` của liên kết phải tham chiếu đến thuộc tính `name` của iframe.

#### Ví dụ:

```html
<iframe
  src="https://www.bing.com/"
  name="web_bing"
  width="1000"
  height="600"
></iframe>
<p>
  <a href="https://coccoc.com/search" target="web_bing"
    >Tìm kiếm trên Cốc Cốc</a
  >
</p>
```

**Lưu ý:** Một số trang như google.com không cho phép nhúng iframe, nên sẽ thấy thông báo từ chối kết nối, chỉ những trang nào cho phép nhúng vào thì ta mới nhúng được.

---

## 2. Một số thẻ Semantic

### Khái niệm

**Semantic:** Dịch ra là ngữ nghĩa. Là những thẻ có nội dung bên trong có ý nghĩa tương ứng với tên thẻ đó.

### Danh sách các thẻ Semantic:

- `<article>`: Xác định nội dung độc lập, khép kín
- `<aside>`: Xác định nội dung ngoài nội dung trang
- `<details>`: Xác định các chi tiết bổ sung mà người dùng có thể xem hoặc ẩn
- `<summary>`: Xác định tiêu đề hiển thị cho phần tử `<details>`
- `<figcaption>`: Xác định chú thích cho phần tử `<figure>`
- `<figure>`: Chỉ định nội dung độc lập, như hình minh họa, sơ đồ, ảnh, danh sách mã, v.v.
- `<header>`: Chỉ định tiêu đề cho một tài liệu hoặc section
- `<footer>`: Xác định chân trang cho tài liệu hoặc section
- `<main>`: Chỉ định nội dung chính của một tài liệu
- `<mark>`: Xác định văn bản được đánh dấu / nhấn mạnh
- `<nav>` (navigation - dẫn đường): Xác định các liên kết điều hướng
- `<section>`: Xác định một phần trong tài liệu
- `<time>`: Xác định ngày / giờ

---

## 3. Forms

### 3.1. Form là gì?

Là một biểu mẫu HTML được sử dụng để thu thập thông tin đầu vào của người dùng. Đầu vào của người dùng thường được gửi đến máy chủ để xử lý.

#### Ví dụ:

```html
<form action="">
  <label for="fullName">Họ tên:</label>
  <br />
  <input type="text" id="fullName" name="full_name" />
  <br />
  <label for="email">Email:</label>
  <br />
  <input type="text" id="email" name="email" />
  <br /><br />
  <input type="submit" value="Gửi" />
</form>
```

### 3.2. Form Attributes (Những thuộc tính của form)

#### action

- Thuộc tính `action` xác định hành động sẽ được thực hiện khi biểu mẫu được gửi
- Giá trị là một đường dẫn
- Thông thường, dữ liệu biểu mẫu được gửi đến tệp trên máy chủ khi người dùng nhấp vào nút gửi

#### target

- Thuộc tính `target` chỉ định nơi hiển thị phản hồi nhận được sau khi gửi biểu mẫu

#### method

- Thuộc tính `method` chỉ định giao thức HTTP sẽ được sử dụng khi gửi dữ liệu biểu mẫu
- Có 2 phương thức là GET và POST

**Phương thức GET:**

- Nối dữ liệu biểu mẫu vào URL, theo cặp name/value
- **KHÔNG BAO GIỜ** sử dụng GET để gửi dữ liệu bảo mật. Như tài khoản, mật khẩu
- Độ dài của URL bị giới hạn (2048 ký tự)

**Phương thức POST:**

- Dữ liệu biểu mẫu đã gửi không được hiển thị trong URL
- POST không có giới hạn về kích thước và có thể được sử dụng để gửi một lượng lớn dữ liệu

#### autocomplete

- Khi bật tính năng tự động điền, trình duyệt sẽ tự động gợi ý các giá trị dựa trên các giá trị mà người dùng đã nhập trước đó

#### novalidate

- Thuộc tính này đặc tả dữ liệu form không cần phải kiểm tra tính chính xác dữ liệu khi gửi đi
- Ví dụ email không cần nhập đúng định dạng vẫn gửi được

### 3.3. Form Elements (Những element trong form)

#### `<input>`

- Có thể được hiển thị theo nhiều cách, tùy thuộc vào thuộc tính `type`
- Mặc định `type="text"`

#### `<label>`

- Phần tử `<label>` xác định nhãn cho một số element trong biểu mẫu
- Để người dùng hiểu hơn về element đó
- Thuộc tính `for` của thẻ `<label>` phải bằng thuộc tính `id` của phần tử `<input>` để liên kết chúng lại với nhau
- Khi đó, click vào `<label>` thì con trỏ sẽ tự động focus vào ô input đó

#### `<select>`

- Hiển thị dạng danh sách thả xuống (dropdown)
- Các thẻ `<option>` xác định một tùy chọn có thể được chọn
- Theo mặc định, mục đầu tiên trong danh sách thả xuống sẽ được chọn
- Để thay đổi mặc định lựa chọn thì thêm thuộc tính `selected` vào `<option>` muốn chọn mặc định
- Sử dụng thuộc tính `size` để chỉ định số lượng giá trị hiển thị
- Sử dụng thuộc tính `multiple` để cho phép người dùng chọn nhiều giá trị

#### `<textarea>`

- Thẻ `<textarea>` xác định trường nhập liệu nhiều dòng
- Thuộc tính `rows` chỉ định số dòng hiển thị trong một vùng văn bản
- Thuộc tính `cols` chỉ định chiều rộng hiển thị của vùng văn bản

#### `<button>`

- Thẻ `<button>` xác định nút có thể nhấp

### 3.4. Input Types (Các kiểu của thẻ input)

- `<input type="text">`: Dùng để nhập text
- `<input type="email">`: Dùng để nhập email
- `<input type="password">`: Dùng để nhập mật khẩu
- `<input type="number">`: Dùng để nhập số, không nhập được chữ cái
- `<input type="date">`: Dùng để chọn: năm, tháng, ngày
- `<input type="time">`: Dùng để chọn: giờ, phút, giây
- `<input type="datetime-local">`: Dùng để chọn: năm, tháng, ngày, giờ, phút, giây
- `<input type="file">`: Dùng để tải file lên
- `<input type="checkbox">`: Các hộp kiểm cho phép người dùng chọn KHÔNG hoặc NHIỀU tùy chọn trong số các lựa chọn hạn chế
- `<input type="radio">`: Các nút radio cho phép người dùng CHỈ chọn MỘT trong số các lựa chọn
- `<input type="range">`: Tạo thanh trượt giá trị. Phạm vi mặc định là từ 0 đến 100. Step mặc định là 1
- `<input type="color">`: Dùng để chọn màu sắc

### 3.5. Input Attributes (Các thuộc tính của thẻ input)

#### value

- Thuộc tính `value` chỉ định giá trị ban đầu cho trường đầu vào

#### readonly

- Thuộc tính `readonly` xác định rằng trường đầu vào là chỉ đọc
- Giá trị của trường readonly sẽ được gửi khi gửi biểu mẫu

#### disabled

- Thuộc tính `disabled` chỉ định rằng một trường đầu vào sẽ bị vô hiệu hóa
- Giá trị của trường disabled sẽ không được gửi khi gửi biểu mẫu

#### maxlength

- Thuộc tính `maxlength` chỉ định số lượng ký tự tối đa được phép trong một trường đầu vào

#### min và max

- Chỉ định các giá trị tối thiểu và tối đa cho một trường đầu vào

#### multiple

- Xác định rằng người dùng được phép nhập nhiều hơn một giá trị vào trường đầu vào
- Áp dụng cho kiểu email, file

#### placeholder

- Chỉ định một gợi ý ngắn để mô tả giá trị dự kiến của trường đầu vào

#### required

- Xác định rằng trường đầu vào phải được điền trước khi gửi biểu mẫu

---

## 4. Những tính năng HTML5 có mà HTML không có

- HTML5 được tích hợp video và âm thanh trong khi HTML thì không có
- HTML5 có thêm các thẻ semantic mới: `<header>`, `<footer>`, `<article>`, `<section>`, `<nav>`, ....
- Cung cấp các kiểu input mẫu mới như: date, time, email,...
- Thẻ `<canvas>` giúp cho việc vẽ sơ đồ 2D
- Hỗ trợ CSS3

---
