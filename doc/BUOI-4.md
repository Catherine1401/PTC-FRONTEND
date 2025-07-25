## Bài 04: Học CSS, CSS3 cơ bản

### Nội dung bài học

1. Khái niệm, cú pháp, selectors
2. 3 kiểu chèn CSS
3. Colors (Màu sắc), Backgrounds (Nền)
4. Box Model, Borders, Padding, Margins
5. Thuộc tính height, width
6. Text, Fonts, Icons

---

## 01. Khái niệm, cú pháp, selectors

### 1.1. Khái niệm

- **CSS**: viết tắt của Cascading Style Sheets
- Là ngôn ngữ được dùng để định dạng kiểu hiển thị cho các phần tử HTML

### 1.2. Cú pháp

```css
selector {
  property: value;
}
```

Trong đó:

- **selector**: Được gọi là bộ chọn
- **property**: Được gọi là thuộc tính
- **value**: Được gọi là giá trị của thuộc tính

### 1.3. Selectors (Bộ chọn)

Bộ chọn CSS chọn (các) phần tử HTML mà bạn muốn tạo kiểu.

Bộ chọn CSS được chia thành 5 loại:

- Simple selectors (Bộ chọn đơn giản)
- Combinator selectors (Bộ chọn tổ hợp)
- Pseudo-class selectors (Bộ chọn lớp giả)
- Pseudo-elements selectors (Bộ chọn phần tử giả)
- Attribute selectors (Bộ chọn thuộc tính)

### 1.4. Simple selectors (Bộ chọn đơn giản)

#### Bộ chọn element (element selector)

Chọn các phần tử HTML dựa trên tên phần tử.

```css
p {
  text-align: center;
  color: red;
}
```

#### Bộ chọn id (id selector)

Sử dụng thuộc tính id của một phần tử HTML để chọn một phần tử cụ thể.

> **Lưu ý**: Tên id không được bắt đầu bằng số.

```css
#title {
  text-align: center;
  color: red;
}
```

#### Bộ chọn class (class selector)

Chọn các thành phần HTML với một thuộc tính class cụ thể.

> **Lưu ý**: Tên class không được bắt đầu bằng số.

```css
.title {
  text-align: center;
  color: red;
}
```

#### Bộ chọn chung (universal selector)

Chọn tất cả các thành phần HTML trên trang.

```css
* {
  text-align: center;
  color: red;
}
```

#### Bộ chọn nhóm (grouping selector)

Chọn tất cả các element, id, class có cùng thuộc tính và giá trị thuộc tính.

```css
h1,
h2,
p {
  text-align: center;
  color: red;
}
```

---

## 02. 3 kiểu chèn CSS

### 2.1. Inline CSS (Nội tuyến)

- Thêm thuộc tính `style` vào trong thẻ mà muốn sửa CSS
- Có thể được sử dụng để áp dụng một kiểu duy nhất cho một element

```html
<p style="color:red;">This is a paragraph.</p>
```

### 2.2. Internal CSS (Nội bộ)

- Thêm thẻ `<style></style>` vào trong file HTML
- Thường thì thẻ `<style>` này sẽ nằm trong thẻ `<head></head>`
- Có thể được sử dụng nếu có một trang HTML duy nhất

```html
<style>
  p {
    color: red;
  }
</style>
```

### 2.3. External CSS (Bên ngoài)

- Tạo một file CSS ở bên ngoài
- Sử dụng thẻ `<link />` đặt trong thẻ `<head></head>`
- Chèn đường dẫn vào thuộc tính `href` trong thẻ link
- Có thể thay đổi giao diện của toàn bộ trang web bằng cách chỉ thay đổi một tệp

```html
<link rel="stylesheet" href="mystyle.css" />
```

### Lưu ý về thứ tự ưu tiên

Nếu trùng bộ chọn và tên thuộc tính, thì giá trị của bộ chọn cuối cùng được sử dụng.

Ví dụ:

```css
h1 {
  color: navy;
}
h1 {
  color: orange;
}
```

→ Màu được chọn sẽ là màu orange.

---

## 03. Colors (Màu sắc), Backgrounds (Nền)

### 3.1. Colors (Màu sắc)

#### Các cách định nghĩa màu

- **Màu được đặt tên sẵn**: white, black, red, green, blue, yellow, orange,... (ít sử dụng)
- **HEX** (Phổ biến nhất)
- **RGB** (ít sử dụng)
- **HSL** (cực ít sử dụng)

#### HEX (Phổ biến nhất)

- Màu HEX được chỉ định bằng: `#RRGGBB`
- Các số nguyên thập lục phân RR (đỏ), GG (xanh lục) và BB (xanh dương) chỉ định các thành phần của màu
- Cú pháp: `#RRGGBB`

Ví dụ:

- `#000000` (màu đen)
- `#FFFFFF` (màu trắng)
- `#FF0000` (màu đỏ)

```css
h1 {
  color: #ff0000;
}
```

> **Công cụ hỗ trợ**: Cài đặt phần mềm Just Color Picker

### 3.2. Backgrounds (Nền)

Dùng để thêm nền vào cho element.

#### background-color

Nền là màu sắc

```css
body {
  background-color: lightblue;
}
```

#### background-clip

Xác định phạm vi được thiết lập màu nền của phần tử (Áp dụng cho background là màu sắc)

- `border-box`: Mặc định. Đổ màu từ content cho đến hết border
- `padding-box`: Đổ màu từ content cho đến hết padding
- `content-box`: Chỉ đổ màu phần content

#### background-image

Nền là hình ảnh hoặc màu gradient.

**Với hình ảnh:**

```css
background-image: url("hinh-anh.jpg");
```

**Với nhiều hình ảnh** (url nào ở trước thì sẽ nằm bên trên):

```css
background-image: url("hinh-1.png"), url("hinh-2.jpg");
```

**Với gradient:**

```css
background-image: linear-gradient(180deg, #000000, #ffffff);
```

**Kết hợp cả hình ảnh và gradient:**

```css
background-image: linear-gradient(180deg, #00000080, #ffffffad),
  url("hinh-anh.jpg");
```

#### background-size

Kích thước của background.

```css
background-size: 100% auto;
```

- `contain`: co dãn hình ảnh để hình ảnh nằm trọn trong khung element, hình ảnh không bị vỡ
- `cover`: kéo dãn hình ảnh sao cho vừa với khung, cắt bỏ đi những phần ảnh thừa để hình ảnh không bị vỡ

#### background-repeat

Nền được lặp lại hay không.

```css
background-repeat: no-repeat; /* Không lặp lại ảnh */
background-repeat: repeat-x; /* Lặp theo trục ngang */
background-repeat: repeat-y; /* Lặp theo trục dọc */
```

#### background-position

Vị trí hình nền so với element. Có các giá trị: top, left, right, bottom, center.

```css
background-position: top left; /* trên - trái */
background-position: top right; /* trên - phải */
background-position: top center; /* trên - giữa */
background-position: bottom left; /* dưới - trái */
background-position: bottom right; /* dưới - phải */
background-position: bottom 30px right 20px; /* cách dưới 30px - cách phải 20px */
```

#### background-attachment

Nền sẽ được cuộn hoặc cố định.

```css
background-attachment: fixed; /* Hình nền được fix cố định khi di cuộn web */
```

#### background-origin

Giống background-clip, nhưng background-clip là dành cho nền là màu sắc, còn background-origin là dùng cho nền ảnh.

- `content-box`: background chỉ chiếm phần content
- `padding-box`: background chiếm phần content và padding
- `border-box`: background chiếm phần content, padding và border

#### background (cách viết ngắn)

```css
background: #ffffff url("hinh-anh.png") no-repeat top right;
```

---

## 04. Box Model, Borders, Padding, Margins

### 4.1. Box Model (Mô hình hộp)

Tất cả các element có thể được coi là các cái hộp. Hộp này bao gồm:

- **Content (Nội dung)**: Nội dung của element, nơi văn bản và hình ảnh xuất hiện
- **Padding**: Tạo một khoảng trống xung quanh nội dung. Phần đệm trong suốt
- **Border (Đường viền)**: Đường viền bao quanh padding (phần đệm) và nội dung
- **Margin (Lề)**: Tạo khoảng cách cho vùng bên ngoài border (đường viền). Lề trong suốt

> **Tip**: Vào dev tools chọn tab Computed sẽ thấy sơ đồ của một element dùng để biểu diễn cho element ta đã chọn.

### 4.2. Borders (Đường viền)

Đường viền bao quanh padding (phần đệm) và nội dung. Dùng để bao bọc 1 element.

#### border-style

Các kiểu border:

- `dotted`: Đường viền chấm
- `dashed`: Đường viền nét đứt
- `solid`: Đường viền liền
- `double`: Đường viền kép
- `groove`: Đường viền có rãnh 3D
- `ridge`: Đường viền có gờ 3D
- `inset`: Đường viền 3D chìm vào trong
- `outset`: Đường viền 3D nổi lên trên
- `none`: Không có viền
- `hidden`: Đường viền bị ẩn

```css
p {
  border: 5px solid red;
}
```

### 4.3. Padding (Phần đệm)

Padding (phần đệm) tạo một khoảng trống xung quanh nội dung, và nằm bên trong đường viền.

```css
padding: 10px;
```

### 4.4. Margins (Lề)

Margin (Lề) để tạo khoảng cách giữa element này với element khác. Margin nằm bên ngoài border.

```css
margin: 10px;
```

---

## 05. Thuộc tính height, width

- `height`: Chiều cao của element
- `width`: Chiều rộng của element
- `min-height`: chiều cao tối thiểu của element
- `min-width`: chiều rộng tối thiểu của element
- `max-height`: chiều cao tối đa của element
- `max-width`: chiều rộng tối đa của element

> **Lưu ý**: Chiều cao và chiều rộng là của phần content nằm bên trong phần padding. Không bao gồm padding, border, margin.

---

## 06. Text, Fonts, Icons

### 6.1. Text

#### Text Color

Thuộc tính `color` được sử dụng để đặt màu cho văn bản.

```css
color: green;
```

#### Text Align

Được sử dụng để thiết lập căn lề ngang của văn bản.

```css
text-align: center; /* Căn giữa */
text-align: left; /* Căn trái */
text-align: right; /* Căn phải */
text-align: justify; /* Căn đều 2 bên */
```

#### Text Transform

Thuộc tính `text-transform` được sử dụng để chỉ định chữ hoa và chữ thường trong văn bản.

```css
text-transform: uppercase; /* VIẾT CHỮ HOA */
text-transform: lowercase; /* viết chữ thường */
text-transform: capitalize; /* Viết Hoa Các Chữ Cái Đầu */
```

### 6.2. Fonts

#### Các họ phông chữ trong CSS

- **Serif (có chân)**: có một nét nhỏ ở các cạnh của mỗi chữ cái
- **Sans-serif (không chân)**: có đường kẻ rõ ràng (không có nét nhỏ đi kèm)
- **Monospace (Đơn cách)**: tất cả các chữ cái có cùng chiều rộng cố định
- **Cursive (Chữ viết ẩu)**: bắt chước chữ viết tay của con người
- **Fantasy (tưởng tượng)**: phông chữ trang trí/vui tươi

#### font-family

Để chỉ định font chữ của văn bản.

```css
font-family: "Times New Roman", Times, serif;
font-family: Arial, Helvetica, sans-serif;
font-family: "Lucida Console", "Courier New", monospace;
```

> **Tài nguyên**: Trang Google Fonts: https://fonts.google.com/

#### font-style

Thuộc tính `font-style` chủ yếu được sử dụng để chỉ định văn bản in nghiêng.

- `normal`: Văn bản được hiển thị bình thường
- `italic`: Văn bản được hiển thị in nghiêng
- `oblique`: Văn bản "nghiêng" (xiên rất giống với chữ nghiêng, nhưng nghiêng hơn và ít được sử dụng)

#### font-weight

Thuộc tính `font-weight` để chỉ định độ dày của chữ.

Giá trị có thể là: normal, bold, 100, 200, 300,..., 800, 900

```css
font-weight: 700;
font-weight: bold;
font-weight: normal;
font-weight: 400;
```

#### font-size

Thuộc tính `font-size` dùng để đặt kích thước của văn bản.

```css
font-size: 12px;
font-size: 14px;
font-size: 16px;
font-size: 18px;
```

### 6.3. Icons

#### Font Awesome

- **Website**: https://fontawesome.com/search?o=r&m=free
- **Link CDN**: https://cdnjs.com/libraries/font-awesome
