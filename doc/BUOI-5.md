## Bài 05: Học CSS, CSS3 cơ bản (tiếp)

### Nội dung

1. List (Danh sách)
2. Table (Bảng)
3. Display (Hiển thị)
4. Position (Vị trí)
5. Z-index
6. Overflow (Tràn ra)
7. Combinator selectors (Bộ chọn tổ hợp)
8. Pseudo-class selectors (Bộ chọn lớp giả)
9. Pseudo-elements selectors (Bộ chọn phần tử giả)
10. Opacity (Độ mờ)

---

## 01. List (Danh sách)

### list-style-type

Chỉ định kiểu đánh dấu mục danh sách.

**Các giá trị phổ biến:**

- `list-style-type: disc;` - Hình tròn đen (Mặc định)
- `list-style-type: circle;` - Hình tròn có viền đen và trống bên trong
- `list-style-type: square;` - Hình vuông
- `list-style-type: disclosure-closed;` - Hình tam giác trỏ sang phải
- `list-style-type: none;` - Bị ẩn
- `list-style-type: upper-roman;` - Chữ la mã I, II, III
- `list-style-type: lower-alpha;` - Chữ cái a, b, c

**Link nghiên cứu thêm:** [MDN list-style-type](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)

### list-style-position

Chỉ định vị trí của các điểm đánh dấu mục danh sách.

**Các giá trị:**

- `list-style-position: outside;` - Các điểm đánh dấu nằm bên ngoài
- `list-style-position: inside;` - Các điểm đánh dấu nằm bên trong

---

## 02. Table (Bảng)

### Bài tập thực hành

Code các bảng sau, sử dụng HTML và CSS:

### Ví dụ 1: Bảng cơ bản với viền

**HTML:**

```html
<table class="table-basic">
  <thead>
    <tr>
      <th>Tên</th>
      <th>Tuổi</th>
      <th>Nghề nghiệp</th>
      <th>Thành phố</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Nguyễn Văn A</td>
      <td>25</td>
      <td>Lập trình viên</td>
      <td>Hà Nội</td>
    </tr>
    <tr>
      <td>Trần Thị B</td>
      <td>28</td>
      <td>Thiết kế</td>
      <td>TP.HCM</td>
    </tr>
    <tr>
      <td>Lê Văn C</td>
      <td>30</td>
      <td>Marketing</td>
      <td>Đà Nẵng</td>
    </tr>
  </tbody>
</table>
```

**CSS:**

```css
.table-basic {
  width: 100%;
  border-collapse: collapse;
  margin: 20px 0;
}

.table-basic th,
.table-basic td {
  border: 1px solid #ddd;
  padding: 12px;
  text-align: left;
}

.table-basic th {
  background-color: #f2f2f2;
  font-weight: bold;
  color: #333;
}
```

### Ví dụ 2: Bảng có màu nền xen kẽ (Striped Table)

**HTML:**

```html
<table class="table-striped">
  <thead>
    <tr>
      <th>Sản phẩm</th>
      <th>Giá</th>
      <th>Số lượng</th>
      <th>Tổng tiền</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Laptop Dell</td>
      <td>15,000,000 VNĐ</td>
      <td>2</td>
      <td>30,000,000 VNĐ</td>
    </tr>
    <tr>
      <td>iPhone 15</td>
      <td>25,000,000 VNĐ</td>
      <td>1</td>
      <td>25,000,000 VNĐ</td>
    </tr>
    <tr>
      <td>Chuột không dây</td>
      <td>500,000 VNĐ</td>
      <td>3</td>
      <td>1,500,000 VNĐ</td>
    </tr>
    <tr>
      <td>Bàn phím cơ</td>
      <td>2,000,000 VNĐ</td>
      <td>1</td>
      <td>2,000,000 VNĐ</td>
    </tr>
  </tbody>
</table>
```

**CSS:**

```css
.table-striped {
  width: 100%;
  border-collapse: collapse;
  margin: 20px 0;
}

.table-striped th,
.table-striped td {
  border: 1px solid #ddd;
  padding: 12px;
  text-align: left;
}

.table-striped th {
  background-color: #4caf50;
  color: white;
  font-weight: bold;
}

.table-striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

.table-striped tr:nth-child(odd) {
  background-color: #ffffff;
}
```

### Ví dụ 3: Bảng có hover effect

**HTML:**

```html
<table class="table-hover">
  <thead>
    <tr>
      <th>Khóa học</th>
      <th>Thời gian</th>
      <th>Học phí</th>
      <th>Trạng thái</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Front-end cơ bản</td>
      <td>3 tháng</td>
      <td>5,000,000 VNĐ</td>
      <td>Đang mở</td>
    </tr>
    <tr>
      <td>React.js nâng cao</td>
      <td>2 tháng</td>
      <td>7,000,000 VNĐ</td>
      <td>Sắp mở</td>
    </tr>
    <tr>
      <td>Node.js Backend</td>
      <td>4 tháng</td>
      <td>8,000,000 VNĐ</td>
      <td>Đang mở</td>
    </tr>
    <tr>
      <td>Full-stack Developer</td>
      <td>6 tháng</td>
      <td>12,000,000 VNĐ</td>
      <td>Hết slot</td>
    </tr>
  </tbody>
</table>
```

**CSS:**

```css
.table-hover {
  width: 100%;
  border-collapse: collapse;
  margin: 20px 0;
}

.table-hover th,
.table-hover td {
  border: 1px solid #ddd;
  padding: 12px;
  text-align: left;
  transition: background-color 0.3s ease;
}

.table-hover th {
  background-color: #2196f3;
  color: white;
  font-weight: bold;
}

.table-hover tr:hover {
  background-color: #e3f2fd;
  cursor: pointer;
}

.table-hover tr:hover td {
  color: #1976d2;
}
```

### Ví dụ 4: Bảng responsive

**HTML:**

```html
<div class="table-responsive">
  <table>
    <thead>
      <tr>
        <th>Mã đơn hàng</th>
        <th>Tên khách hàng</th>
        <th>Email</th>
        <th>Số điện thoại</th>
        <th>Địa chỉ</th>
        <th>Ngày đặt</th>
        <th>Tổng tiền</th>
        <th>Trạng thái</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>DH001</td>
        <td>Nguyễn Văn A</td>
        <td>nguyenvana@email.com</td>
        <td>0901234567</td>
        <td>123 Đường ABC, Quận 1, TP.HCM</td>
        <td>15/07/2024</td>
        <td>2,500,000 VNĐ</td>
        <td>Đã giao</td>
      </tr>
      <tr>
        <td>DH002</td>
        <td>Trần Thị B</td>
        <td>tranthib@email.com</td>
        <td>0902345678</td>
        <td>456 Đường XYZ, Quận 2, TP.HCM</td>
        <td>16/07/2024</td>
        <td>1,800,000 VNĐ</td>
        <td>Đang giao</td>
      </tr>
      <tr>
        <td>DH003</td>
        <td>Lê Văn C</td>
        <td>levanc@email.com</td>
        <td>0903456789</td>
        <td>789 Đường DEF, Quận 3, TP.HCM</td>
        <td>17/07/2024</td>
        <td>3,200,000 VNĐ</td>
        <td>Chờ xử lý</td>
      </tr>
    </tbody>
  </table>
</div>
```

**CSS:**

```css
.table-responsive {
  overflow-x: auto;
  margin: 20px 0;
}

.table-responsive table {
  width: 100%;
  border-collapse: collapse;
  min-width: 800px;
}

.table-responsive th,
.table-responsive td {
  border: 1px solid #ddd;
  padding: 12px;
  text-align: left;
  white-space: nowrap;
}

.table-responsive th {
  background-color: #ff9800;
  color: white;
  font-weight: bold;
  position: sticky;
  top: 0;
}

.table-responsive tr:nth-child(even) {
  background-color: #fff3e0;
}

/* Media query cho responsive */
@media screen and (max-width: 768px) {
  .table-responsive {
    font-size: 14px;
  }

  .table-responsive th,
  .table-responsive td {
    padding: 8px;
  }
}
```

---

## 03. Display (Hiển thị)

### Các giá trị của display

**`display: inline;`**

- Không đặt được chiều rộng và chiều cao
- Không thêm được margin và padding cho bên trên và bên dưới

**`display: block;`**

- Chiều rộng kéo dài từ trái sang phải
- Luôn bắt đầu ở một hàng mới
- Cho phép đặt chiều rộng và chiều cao
- Cho phép đặt margin, padding cho bên trên và bên dưới

**`display: inline-block;`**

- Chiều rộng mặc định bằng chiều rộng của element
- Không bắt đầu ở một hàng mới
- Cho phép đặt chiều rộng và chiều cao
- Cho phép đặt margin, padding cho bên trên và bên dưới

**`display: none;`**

- Ẩn đi hoàn toàn

### Visibility (Hiển thị)

**`visibility: hidden;`** - Ẩn nhưng vẫn chiếm một khoảng trống
**`visibility: visible;`** - Hiển thị (mặc định)

---

## 04. Position (Vị trí)

Thuộc tính position để xác định vị trí element muốn hiển thị. Có 5 giá trị khác nhau:

### `position: static;`

Vị trí ở trạng thái mặc định của phần tử (các thuộc tính top, bottom, right, left không có hiệu lực)

### `position: relative;`

Vị trí tương đối so với vị trí mặc định và áp dụng được các thuộc tính top, right, bottom, left

### `position: absolute;`

Vị trí tuyệt đối cho các thành phần theo thành phần bao ngoài hoặc cửa sổ trình duyệt

### `position: fixed;`

Được định vị so với khung nhìn (viewport), có nghĩa là nó luôn ở một vị trí cố định ngay cả khi trang được cuộn. Các thuộc tính top, right, bottom và left được sử dụng để định vị element

### `position: sticky;`

Có thể hiểu đơn giản là sự kết hợp của position: relative và position: fixed. Nó cũng na ná relative nhưng mà khi các bạn scroll đến vị trí của nó sẽ giống hệt như fixed và khi các bạn scroll lên ra khỏi nó thì nó sẽ quay lại vị trí ban đầu dưới dạng relative

---

## 05. Z-index

**Định nghĩa:**

- Thuộc tính z-index thiết lập thứ tự xếp chồng nhau của một thành phần vị trí
- Giá trị mặc định là 0
- z-index càng cao thì element đó càng nằm trên

**Chú ý:** z-index chỉ làm việc cùng với thuộc tính position có giá trị sau: absolute, fixed, relative, sticky. Đối với giá trị static thì z-index không áp dụng được.

---

## 06. Overflow (Tràn ra)

Thuộc tính overflow xác định điều gì sẽ xảy ra nếu một thành phần box tràn nội dung.

### Các giá trị:

**`overflow: visible;`**
Khi chiều cao của box không đủ chứa text, thì text vẫn hiển thị tràn qua box (mặc định)

**`overflow: hidden;`**
Khi chiều cao của box không đủ chứa text, thì text bị tràn sẽ được ẩn đi

**`overflow: scroll;`**
Khi chiều cao của box không đủ chứa text, thì text bị tràn sẽ được ẩn đi và xuất hiện thanh scroll, khi cuộn sẽ hiển thị text. Khi sử dụng thành phần này sẽ xuất hiện cả thanh scroll ngang và dọc

**`overflow: auto;`**
Khi chiều cao của box không đủ chứa text, thì thanh scroll sẽ tự động hiển thị. Khi sử dụng thành phần này sẽ xuất hiện thanh scroll dọc

---

## 07. Combinator selectors (Bộ chọn tổ hợp)

### Adjacent sibling selectors (Bộ chọn anh chị em liền kề)

Chọn phần tử tag02 được đặt cùng cấp và phải kề ngay sau phần tử tag01 (mỗi tag01 chỉ có một tag02 kề ngay sau).

**Cú pháp:**

```css
tag01 + tag02 {
  /* Viết css trong này */
}
```

### General sibling selectors (Bộ chọn anh chị em chung)

Chọn tất cả phần tử tag02 cùng cấp với phần tử tag01, và những phần tử tag02 phải nằm sau phần tử tag01.

**Cú pháp:**

```css
tag01 ~ tag02 {
  /* Viết css trong này */
}
```

### Child selectors (Bộ chọn con)

Chọn tất cả phần tử tag02 là cấp con đầu tiên (cấp 1) của phần tử tag01.

**Cú pháp:**

```css
tag01 > tag02 {
  /* Viết css trong này */
}
```

### Descendant selectors (Bộ chọn hậu duệ)

Chọn tất cả phần tử tag02 bên trong phần tử tag01.

**Cú pháp:**

```css
tag01 tag02 {
  /* Viết css trong này */
}
```

---

## 08. Pseudo-class selectors (Bộ chọn lớp giả)

Dùng để xác định trạng thái đặc biệt của một element.

**Cú pháp:**

```css
selector:pseudo-class {
  property: value;
}
```

### Một số pseudo-class phổ biến:

- `:link` - khi liên kết chưa được truy cập lần nào (Chỉ dùng cho thẻ a)
- `:visited` - khi liên kết đã được truy cập sau lần đầu tiên (Chỉ dùng cho thẻ a)
- `:hover` - khi di chuyển chuột lên element
- `:active` - khi phần tử được click vào, áp dụng cho tất cả các thẻ
- `:first-child` - thiết lập thuộc tính cho element đầu tiên
- `:last-child` - thiết lập thuộc tính cho element cuối cùng
- `:nth-child(n)` - n có thể là các giá trị even (chẵn), odd (lẻ), một số, một biểu thức (an + b)

---

## 09. Pseudo-elements selectors (Bộ chọn phần tử giả)

Được sử dụng để tạo ra một phần tử giả và định kiểu (style) cho phần tử giả đó mà không cần tạo ra một phần tử thật.

**Cú pháp:**

```css
selector::pseudo-element {
  property: value;
}
```

### Danh sách pseudo-element:

- `::before` - Chèn nội dung nào đó trước nội dung của mỗi element (Phải thêm content: "";)
- `::after` - Chèn nội dung nào đó sau nội dung của mỗi element (Phải thêm content: "";)
- `::first-letter` - Chọn chữ cái đầu tiên của mỗi element
- `::first-line` - Chọn dòng đầu tiên của mỗi element
- `::marker` - Chọn các điểm đánh dấu của các mục danh sách (thẻ `<ul>` và `<ol>`)
- `::selection` - Được dùng để style cho một vùng văn bản được người dùng chọn (hay còn gọi là "bôi đen"). Chỉ có một số thuộc tính css khả dụng với ::selection là color, background, cursor, và outline

---

## 10. Opacity (Độ mờ)

**Định nghĩa:**

- Thuộc tính opacity chỉ định độ mờ/độ trong suốt của một element
- Thuộc tính opacity có thể nhận giá trị từ 0 đến 1. Giá trị càng thấp thì element càng mờ

**Cú pháp:**

```css
opacity: 0.6; /* Element sẽ mờ đi 40% */
```

---
