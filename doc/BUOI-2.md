## Bài 2: Học HTML, HTML5

### Nội dung bài học

1. Thẻ `<a>` (Chèn link)
2. Thẻ `<img>` (Chèn ảnh)
3. File Paths (Đường dẫn)
4. Thẻ `<video>` (Chèn video)
5. Thẻ `<audio>` (Chèn audio)
6. Thẻ `<table>` (Chèn bảng)
7. Thẻ `<ul>`, `<ol>` (Chèn danh sách)
8. Phân biệt kiểu hiển thị của element: block và inline
9. Class và Id

---

## 1. Thẻ `<a>` (Chèn link)

**Định nghĩa**: Thẻ `<a></a>` (anchor - mỏ neo) là thẻ để khi click vào thẻ đó sẽ chuyển hướng đến trang khác.

**Cú pháp**:

```html
<a href="url">Text</a>
```

**Thuộc tính**:

- **href** (Hypertext Reference): thuộc tính xác định địa chỉ liên kết
- **target**: thuộc tính xác định nơi mà tài liệu được mở
  - `_self`: Mặc định. Mở tài liệu ở tab hiện tại
  - `_blank`: Mở tài liệu trong tab mới
- **title**: Thông tin bổ sung về một element

---

## 2. Thẻ `<img>` (Chèn ảnh)

**Định nghĩa**: Thẻ `<img />` là thẻ để nhúng ảnh vào trang web, thẻ img là thẻ trống, chỉ chứa các thuộc tính và không có thẻ đóng.

**Cú pháp**:

```html
<img src="duong-dan-hinh-anh.jpg" alt="Mô tả hình ảnh" />
```

**Thuộc tính**:

- **src** (source): Chèn đường dẫn ảnh
- **alt** (alternate): Văn bản thay thế cho hình ảnh, hiển thị khi đường dẫn ảnh bị lỗi

---

## 3. File Paths (Đường dẫn)

### Absolute File Paths (Đường dẫn tệp tuyệt đối)

Đường dẫn tệp tuyệt đối là URL đầy đủ của tệp.

```html
<img src="https://28tech.com.vn/assets/img/logo.png" alt="Logo 28tech" />
```

### Relative File Paths (Đường dẫn tệp tương đối)

Đường dẫn tệp tương đối trỏ đến một tệp liên quan đến trang hiện tại.

```html
<!-- File nằm cùng thư mục với trang hiện tại -->
<img src="logo.png" alt="Logo" />

<!-- File nằm trong thư mục images trong thư mục hiện tại -->
<img src="images/logo.png" />

<!-- File nằm trong thư mục images ở thư mục gốc của trang web -->
<img src="/images/logo.png" />

<!-- File nằm trong thư mục tăng một cấp so với thư mục hiện tại -->
<img src="../logo.png" />
```

### Ví dụ kết hợp thẻ `<a>` và `<img>`

```html
<a href="https://28tech.com.vn/">
  <img src="https://28tech.com.vn/assets/img/logo.png" alt="Logo 28tech" />
</a>
```

---

## 4. Thẻ `<video>` (Chèn video)

**Định nghĩa**: Thẻ `<video></video>` là thẻ để nhúng video vào trang web. Trong thẻ video có thẻ `<source>` để chứa đường dẫn file video và kiểu video.

**Cú pháp**:

```html
<video width="320" height="240" controls>
  <source src="link-video.mp4" type="video/mp4" />
</video>
```

**Thuộc tính**:

- **width/height**: Chiều rộng và chiều cao của video
- **controls**: Thuộc tính điều khiển (bật, tạm dừng, âm lượng)
- **loop**: Lặp lại video
- **src**: Đường dẫn video
- **type**: Kiểu video (mp4, ogg, webm)
- **autoplay**: Tự động phát video
- **muted**: Tắt tiếng

**Lưu ý**:

- Đoạn văn bản ở trong thẻ video sẽ chỉ hiển thị khi trình duyệt không hỗ trợ thẻ video
- Trình duyệt Chrome không cho phép tự động phát video. Nếu muốn tự động phát được video thì phải thêm thuộc tính `muted`

---

## 5. Thẻ `<audio>` (Chèn audio)

**Định nghĩa**: Thẻ `<audio></audio>` là thẻ dùng để nhúng audio vào trang web. Trong thẻ audio có thẻ `<source>` để chứa đường dẫn file audio và kiểu audio.

**Cú pháp**:

```html
<audio controls>
  <source src="link-audio.mp3" type="audio/mpeg" />
</audio>
```

**Thuộc tính**:

- **controls**: Thuộc tính điều khiển (bật, tạm dừng, âm lượng)
- **loop**: Lặp lại audio
- **src**: Đường dẫn audio
- **type**: Kiểu audio (mpeg - mp3, ogg, webm, wav)
- **autoplay**: Tự động phát audio
- **muted**: Tắt tiếng

**Lưu ý**:

- Đoạn văn bản ở trong thẻ audio sẽ chỉ hiển thị khi trình duyệt không hỗ trợ thẻ audio
- Trình duyệt Chrome không cho phép tự động phát audio. Nếu muốn tự động phát được audio thì phải thêm thuộc tính `muted`

---

## 6. Thẻ `<table>` (Chèn bảng)

**Định nghĩa**: Thẻ `<table></table>` dùng để tạo bảng trong HTML.

**Ví dụ**:

```html
<table>
  <thead>
    <tr>
      <th>STT</th>
      <th>Họ tên</th>
      <th>Số điện thoại</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Le Van A</td>
      <td>0123456789</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Nguyen Thi B</td>
      <td>0987654321</td>
    </tr>
  </tbody>
</table>
```

**Ý nghĩa các thẻ**:

- `<table></table>`: Xác định một bảng
- `<thead></thead>`: Phần đầu của bảng
- `<tbody></tbody>`: Phần thân của bảng
- `<tr></tr>` (table row): Xác định một hàng của bảng
- `<th></th>` (table header): Xác định tiêu đề của bảng
- `<td></td>` (table data): Xác định dữ liệu ô của bảng

**Thuộc tính**:

- **colspan**: tạo ô mở rộng trên nhiều cột
- **rowspan**: tạo ô kéo dài trên nhiều hàng

---

## 7. Thẻ `<ul>`, `<ol>` (Chèn danh sách)

### Kiểu `<ul>` (Unordered List - Không sắp xếp)

Các mục con sẽ không được đánh số, mà chỉ được đánh dấu bằng hình tròn.

**Cú pháp**:

```html
<ul>
  <li>Mục 1</li>
  <li>Mục 2</li>
  <li>Mục 3</li>
</ul>
```

### Kiểu `<ol>` (Ordered List - Sắp xếp)

Các mục con được sắp xếp theo thứ tự bằng số hoặc chữ cái.

**Cú pháp**:

```html
<ol>
  <li>Mục 1</li>
  <li>Mục 2</li>
  <li>Mục 3</li>
</ol>
```

**Thuộc tính dành riêng cho thẻ `<ol>`**:

- `type="1"`: Mặc định. Đánh số
- `type="A"`: Chữ hoa
- `type="a"`: Chữ thường
- `type="I"`: Số La Mã viết hoa
- `type="i"`: Số La Mã viết thường

**Ý nghĩa các thẻ**:

- `<ul></ul>`: Danh sách không đánh số
- `<ol></ol>`: Danh sách đánh số
- `<li></li>` (List Item): Một mục trong danh sách

---

## 8. Phân biệt kiểu hiển thị của element: block và inline

### Kiểu block (khối)

- Luôn bắt đầu trên một dòng mới
- Trình duyệt tự động thêm khoảng trống trước và sau element
- Luôn chiếm toàn bộ chiều rộng có sẵn

**Một số thẻ dạng block**:
`<address>`, `<article>`, `<aside>`, `<blockquote>`, `<canvas>`, `<dd>`, `<div>`, `<dl>`, `<dt>`, `<fieldset>`, `<figcaption>`, `<figure>`, `<footer>`, `<form>`, `<h1>-<h6>`, `<header>`, `<hr>`, `<li>`, `<main>`, `<nav>`, `<noscript>`, `<ol>`, `<p>`, `<pre>`, `<section>`, `<table>`, `<tfoot>`, `<ul>`

### Kiểu inline (nội tuyến - trong hàng)

- Không bắt đầu trên một dòng mới
- Chiều rộng bằng với chiều rộng của element đó

**Một số thẻ dạng inline**:
`<a>`, `<abbr>`, `<acronym>`, `<b>`, `<bdo>`, `<big>`, `<br>`, `<button>`, `<cite>`, `<code>`, `<em>`, `<i>`, `<img>`, `<input>`, `<kbd>`, `<label>`, `<map>`, `<object>`, `<output>`, `<q>`, `<samp>`, `<script>`, `<select>`, `<small>`, `<span>`, `<strong>`, `<sub>`, `<sup>`, `<textarea>`, `<time>`, `<tt>`, `<var>`

### Lưu ý về quy tắc mô hình nội dung HTML

- Phần tử cấp độ inline không được chứa phần tử cấp độ block
- Inline chỉ chứa dữ liệu hoặc các phần tử inline khác
- Phần tử block được chứa các phần tử block, inline, dữ liệu
- **Ngoại lệ**: Thẻ `<a>` (kiểu inline) nhưng có thể chứa phần tử kiểu block

---

## 9. Class và Id

### Class

**Thuộc tính class** dùng để xác định một hoặc nhiều tên lớp cho phần tử HTML.

**Đặc điểm**:

- Một class có thể áp dụng cho nhiều element
- Một element có thể có nhiều class
- Thuộc tính class có thể được sử dụng trên bất kỳ phần tử HTML nào
- Tên lớp có phân biệt chữ hoa chữ thường

### Id

**Thuộc tính id** dùng để xác định một id duy nhất cho một element.

**Đặc điểm**:

- Trong một trang các element không được phép trùng tên id
- Tên id có phân biệt chữ hoa chữ thường
- Tên id phải chứa ít nhất một ký tự
- Không được bắt đầu bằng số
- Không được chứa khoảng trắng

### Quy tắc đặt tên class và id

**Ký tự được phép sử dụng**:

- Chữ cái viết thường: a → z
- Chữ cái viết hoa: A → Z
- Chữ số: 0 → 9
- Dấu gạch dưới: \_
- Dấu gạch nối: -

**Lưu ý**:

- Không chứa các ký tự đặc biệt (! @ # $ % ^ &)
- Không bắt đầu bằng số từ 0 → 9

### Ví dụ về việc đặt tên id và class

**ĐÚNG**:

- `webcoban`
- `Webcoban`
- `webCobAn`
- `we9co3an`
- `_webc_oban`
- `web-Cob-An`

**SAI**:

- `9webcoban` (sai vì bắt đầu bằng chữ số)
- `web%^coban` (sai vì có chứa các ký tự đặc biệt)

### Điểm khác nhau giữa thuộc tính id và class

| **Thuộc tính id**                                   | **Thuộc tính class**                                  |
| --------------------------------------------------- | ----------------------------------------------------- |
| Một phần tử chỉ nhận một id                         | Một phần tử có thể nhận một hoặc nhiều class          |
| Một tên id chỉ có thể dùng cho một phần tử duy nhất | Một tên class có thể dùng cho nhiều phần tử khác nhau |
| Chọn phần tử: `#ten-id`                             | Chọn phần tử: `.ten-class`                            |

---
