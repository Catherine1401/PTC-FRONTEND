## Bài 06: Học CSS, CSS3 nâng cao

---

## Nội dung bài học

1. **Float và Clear**
2. **Attribute selectors** (Bộ chọn thuộc tính)
3. **Units** (Đơn vị)
4. **Specificity và !important**
5. **Math Functions** (Hàm toán học)
6. **CSS function attr()**
7. **Variables** (Biến)
8. **Box Sizing** (Kích thước hộp)
9. **Khái niệm Responsive**
10. **Media Queries**

---

## 1. Float và Clear

### 1.1. Float

**Thuộc tính float** được sử dụng để chuyển một phần tử sang góc trái hoặc góc bên phải của không gian bao quanh nó.

**Các giá trị của Float:**

- `float: left;` - Phần tử nằm phía bên trái
- `float: right;` - Phần tử nằm phía bên phải
- `float: none;` - Phần tử nằm tại chính vị trí của nó (Mặc định)

### 1.2. Clear

**Thuộc tính Clear** là một thuộc tính ngược lại hoàn toàn với Float.

**Mục đích:** Ngăn chặn phần tử B chiếm vùng không gian của phần tử A (với A là phần tử sử dụng float).

**Các giá trị của Clear:**

- `clear: left;`

  - Ngăn chặn phần tử B chiếm chỗ phần tử A, khi phần tử A có sử dụng `float: left;`
  - Không có tác dụng khi phần tử A sử dụng `float: right;`

- `clear: right;`

  - Ngăn chặn phần tử B chiếm chỗ phần tử A, khi phần tử A có sử dụng `float: right;`
  - Không có tác dụng khi phần tử A sử dụng `float: left;`

- `clear: both;`

  - Ngăn chặn sự chiếm vùng không gian cả khi chỉ có một phần tử sử dụng float
  - Sử dụng khi cả 2 phần tử A và B sử dụng float

- `clear: none;`
  - Dạng phục hồi khi thành phần sử dụng thuộc tính clear

---

## 2. Attribute Selectors (Bộ chọn thuộc tính)

Bộ chọn attribute được sử dụng để chọn các phần tử có thuộc tính được chỉ định.

### Các kiểu chọn:

**`[attribute]`**

- Chọn tất cả các phần tử có thuộc tính [attribute]

**`[attribute="value"]`**

- Chọn tất cả các phần tử có thuộc tính [attribute] phải chứa giá trị value
- Chỉ được có giá trị duy nhất là value
- Giá trị có thể bao gồm nhiều từ

**`[attribute~="value"]`**

- Chọn tất cả các phần tử có thuộc tính [attribute] phải chứa giá trị value
- value đó phải đứng độc lập, không được viết liền với từ khác
- value phải là 1 từ khóa duy nhất

**`[attribute|="value"]`**

- Chọn các phần tử có thuộc tính [attribute], giá trị có thể chính xác là giá trị được chỉ định hoặc giá trị được chỉ định theo sau dấu gạch nối (-)
- Giá trị phải là một từ nguyên vẹn, đơn lẻ như `class="top"` hoặc theo sau là dấu gạch ngang như `class="top-text"`

**`[attribute^="value"]`**

- Chọn tất cả các phần tử có thuộc tính [attribute] bắt đầu bằng giá trị value
- Được phép viết liền với các từ khác

**`[attribute$="value"]`**

- Chọn tất cả các phần tử có thuộc tính [attribute] kết thúc bằng giá trị value
- Giá trị có thể được viết liền với từ khác

**`[attribute*="value"]`**

- Chọn tất cả các phần tử có thuộc tính [attribute] chứa giá trị value
- Giá trị không nhất thiết phải là một từ nguyên vẹn

---

## 3. Units (Đơn vị)

### Độ dài tuyệt đối

Là loại đơn vị có giá trị cố định và thể hiện chính xác chiều dài kích thước nó hiển thị, không phụ thuộc cũng như không thay đổi bởi bất kỳ tác động bên ngoài nào.

**Một số đơn vị:**

- `cm` - Centimeter
- `mm` - Millimeter
- `in` - Inches (1in = 96px = 2.54cm)
- `px` - Pixels (1px = 1/96 in) tương ứng với một điểm ảnh trên máy tính
- `pt` - Points (1pt = 1/72 in)
- `pc` - Picas (1pc = 12 pt)

### Độ dài tương đối

Là đơn vị đo lường được sử dụng trong CSS ở mức tương đối, thường phụ thuộc vào 1 thành phần nào đó thì mới xác định được giá trị của nó.

**Một số đơn vị:**

- `%` - Giá trị tương đối so với phần tử cha
- `rem` - Giá trị tương đối với font-size của phần tử gốc (thẻ html)
- `em` - 1em tương đương với kích cỡ của font-size của phần tử cha có định nghĩa font-size
- `vw` (viewport width) - 1vw tương đương với 1% của chiều rộng cửa sổ trình duyệt
- `vh` (viewport height) - 1vh tương đương với 1% của chiều cao cửa sổ trình duyệt
- `ex` - 1ex tương đương với chiều cao của một chữ x (in thường) của font hiện tại
- `ch` - 1ch tương đương với chiều rộng của một số 0 theo size hiện tại

---

## 4. Specificity (Tính đặc hiệu) và !important

### 4.1. Specificity (Tính đặc hiệu)

**Tính đặc hiệu** là cách mà trình duyệt quyết định sẽ áp dụng thuộc tính CSS nào với một phần tử khi có nhiều quy tắc CSS cùng trỏ đến phần tử đó.

**Sự phân cấp tính đặc hiệu:**

```
Inline > ID > Classes/Attributes/Pseudo-classes > Elements/Pseudo-elements
```

**Cách tính toán:**

- `1-0-0-0`: Inline styles
- `0-X-0-0`: Số lượng ID selector
- `0-0-Y-0`: Số lượng Classes, attributes và pseudo-classes
- `0-0-0-Z`: Số lượng Elements và pseudo-elements

**Lưu ý:**

- CSS theo kiểu Internal và External không có độ ưu tiên
- Universal selector (\*) và combinators selector (+, >, ~) không làm tăng tính đặc hiệu

### 4.2. !important (Quan trọng)

**Important** được sử dụng để thay đổi thứ tự ưu tiên của CSS. Khi một thuộc tính CSS nào đó được gán lệnh Important thì nó sẽ có mức ưu tiên cao nhất.

**Ví dụ:**

```css
h2 {
  color: red !important;
}
```

---

## 5. Math Functions (Hàm toán học)

Các hàm toán học CSS cho phép các biểu thức toán học được sử dụng làm giá trị thuộc tính.

### Các hàm toán học:

**Hàm `calc()`**

- Thực hiện một phép tính, kết quả sẽ lấy làm giá trị thuộc tính
- Các toán tử có thể sử dụng: `+ - * /`
- **Ví dụ:** `width: calc(100% - 100px);`

**Hàm `max()`**

- Sử dụng giá trị lớn nhất từ danh sách giá trị được phân tách bằng dấu phẩy
- **Cú pháp:** `max(value1, value2, …)`
- **Ví dụ:** `width: max(50%, 300px);`

**Hàm `min()`**

- Sử dụng giá trị nhỏ nhất từ danh sách giá trị được phân tách bằng dấu phẩy
- **Cú pháp:** `min(value1, value2, …)`
- **Ví dụ:** `width: min(50%, 300px);`

---

## 6. CSS Function attr()

`attr()` là một hàm CSS trả về giá trị của một thuộc tính.

**Ví dụ:**

```css
[data-text]::before {
  content: attr(data-text);
}
```

```html
<span data-text="Xin chào ">Đặng Phương Nam</span>
```

---

## 7. Variables (Biến)

**Mục đích:** Khai báo biến để có thể sử dụng được ở nhiều nơi.

### Biến Global (Toàn cục)

Có thể sử dụng được nhiều nơi trong file CSS.

**Cách tạo:**

```css
:root {
  --ten-bien: giá trị;
  --gray: #333333;
  --white: #ffffff;
}
```

**Cách sử dụng:**

```css
body {
  color: var(--gray);
  background-color: var(--white);
}
```

### Biến Local (Cục bộ)

Chỉ sử dụng được ở trong phạm vi của nó.

**Ví dụ:**

```css
h1 {
  --local-color: blue;
  color: var(--local-color);
}

p {
  color: var(--local-color); /* Không hoạt động */
}
```

---

## 8. Box Sizing (Kích thước hộp)

Mặc định khi sử dụng thuộc tính `width`, `height` thì chỉ áp dụng cho phần content của 1 element.

### 2 loại box-sizing:

**`content-box` (Mặc định)**

- Width/height chỉ bao gồm "nội dung" của phần tử
- `width, height = content`

**`border-box`**

- Width/height bao gồm: content, padding, border của phần tử
- `width, height = content + padding + border`

---

## 9. Khái niệm Responsive

**Responsive** là để chỉ một website có thể hiển thị tương thích trên mọi thiết bị, như máy tính, máy tính bảng, điện thoại.

**Sử dụng media query** để responsive giao diện.

### Khai báo meta viewport:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

**Trong đó:**

- `viewport`: Giúp trình duyệt hiểu thẻ meta này dùng để thiết lập khung nhìn
- `width=device-width`: Đặt chiều rộng bằng chiều rộng thiết bị
- `initial-scale=1.0`: Mức thu phóng của website (thường được đặt bằng 1)

---

## 10. Media Queries

`@media` CSS là một tính năng mới của CSS3. Tính năng này cho phép tùy chỉnh CSS cho nhiều thiết bị khác nhau từ máy tính cho đến iPad, điện thoại và các thiết bị in ấn.

### Cú pháp:

```css
@media mediaType and (mediafeature) {
  /* Code */
}
```

### MediaType:

- `all`: Dùng cho mọi thiết bị
- `print`: Dùng cho máy in
- `screen`: Dùng cho máy tính và các thiết bị di động

### MediaFeature:

- `max-width`: Chiều rộng tối đa của viewport
- `min-width`: Chiều rộng tối thiểu của viewport

### PC First (Responsive)

Lập trình giao diện từ màn hình to đến màn hình nhỏ. Sử dụng `max-width` trong media query.

```css
/* iPad ngang (1024 x 768) */
@media screen and (max-width: 1024px) {
  /* Code */
}

/* iPad dọc (768 x 1024) */
@media screen and (max-width: 768px) {
  /* Code */
}

/* Smart phone (480 x 640) */
@media screen and (max-width: 480px) {
  /* Code */
}

/* Smart phone nhỏ */
@media screen and (max-width: 320px) {
  /* Code */
}
```

### Mobile First

Lập trình giao diện từ màn hình nhỏ đến màn hình to. Sử dụng `min-width` trong media query.

```css
/* Smart phone nhỏ */
@media screen and (min-width: 320px) {
  /* Code */
}

/* Smart phone (480 x 640) */
@media screen and (min-width: 480px) {
  /* Code */
}

/* iPad dọc (768 x 1024) */
@media screen and (min-width: 768px) {
  /* Code */
}

/* iPad ngang (1024 x 768) */
@media screen and (min-width: 1024px) {
  /* Code */
}
```

---

## Kết thúc

**Link demo:** https://frontend.daca.vn/lessons/lesson-6/index.html

_Bài tập về PC first: Code ví dụ sử dụng mô hình PC first._
