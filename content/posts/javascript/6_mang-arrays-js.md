---
title: "Bài 6: Sức mạnh của Mảng (Arrays) - Lưu trữ và xử lý danh sách"
date: 2024-05-28
description: "Tìm hiểu về Mảng (Arrays) trong JavaScript, cách truy cập phần tử, các phương thức cơ bản như push, pop, và các cách duyệt mảng như for và forEach."
series: ["Làm chủ JavaScript"]
series_order: 6
tags: ["JavaScript", "Mảng", "Array", "Cơ bản", "DOM"]
categories: ["JavaScript"]
slug: "javascript-mang-arrays"
---

## Bài 6: Sức mạnh của Mảng (Arrays) - Lưu trữ và xử lý danh sách 📋

Chào các bạn! Trong series này, chúng ta đã đi qua các khái niệm trụ cột của JavaScript. Ở Bài 2, chúng ta đã "giới thiệu sơ lược" về Mảng (Array). Nhưng trên thực tế, Mảng là một chủ đề lớn và vô cùng quan trọng.

Hầu hết mọi ứng dụng web đều phải xử lý danh sách dữ liệu: danh sách bạn bè, danh sách sản phẩm, danh sách bình luận... Và Mảng chính là công cụ để làm việc đó.

## Mảng là gì?

Mảng (Array) là một kiểu dữ liệu đặc biệt, cho phép bạn lưu trữ nhiều giá trị trong một biến duy nhất. Thay vì tạo 10 biến cho 10 sinh viên, bạn chỉ cần tạo 1 Mảng danhSachSinhVien.

```javascript
// Cách tạo một mảng
const traiCay = ["Táo", "Cam", "Chuối", "Xoài"];
const diemSo = [10, 8, 9.5, 7];
const honHop = ["Xin chào", 100, true, null]; // Mảng có thể chứa nhiều kiểu dữ liệu
```

## Truy cập phần tử: Chỉ số (Index)

Các phần tử trong mảng được sắp xếp theo thứ tự và được đánh chỉ số (index), bắt đầu từ số 0.

Để lấy một phần tử, bạn dùng cú pháp `tenMang[chiSo]`.

```javascript
const traiCay = ["Táo", "Cam", "Chuối", "Xoài"];

console.log(traiCay[0]); // In ra "Táo" (phần tử đầu tiên)
console.log(traiCay[2]); // In ra "Chuối" (phần tử thứ ba)
console.log(traiCay[4]); // In ra undefined (vì không có phần tử ở chỉ số 4)

// Gán lại giá trị
traiCay[1] = "Nho"; // Thay thế "Cam" bằng "Nho"
console.log(traiCay); // In ra ["Táo", "Nho", "Chuối", "Xoài"]
```

## Các thuộc tính và phương thức cơ bản

Mảng không chỉ để lưu trữ, nó còn đi kèm rất nhiều "phương thức" (hàm có sẵn) tiện lợi.

### .length (Thuộc tính)

Cho bạn biết mảng có bao nhiêu phần tử.

```javascript
const traiCay = ["Táo", "Nho", "Chuối"];
console.log(traiCay.length); // In ra 3
```

### push() và pop() (Thay đổi mảng)

- `push(giaTri)`: Thêm một phần tử vào **cuối** mảng.
- `pop()`: Xóa một phần tử ở **cuối** mảng (và trả về phần tử bị xóa đó).

```javascript
const dongVat = ["Chó", "Mèo"];

dongVat.push("Chuột");
console.log(dongVat); // In ra ["Chó", "Mèo", "Chuột"]

dongVat.pop();
console.log(dongVat); // In ra ["Chó", "Mèo"]
```

## Duyệt mảng (Looping) - Cách xử lý danh sách

Đây là phần quan trọng nhất. Làm thế nào để thực hiện một hành động (ví dụ: in ra) với tất cả các phần tử trong mảng?

### 1. Dùng vòng lặp for (Cách cổ điển)

Chúng ta có thể dùng vòng lặp `for` kết hợp với thuộc tính `.length`.

```javascript
const traiCay = ["Táo", "Cam", "Chuối"];

for (let i = 0; i < traiCay.length; i++) {
  // i sẽ chạy từ 0, 1, 2
  console.log(traiCay[i]);
}
```

Kết quả:

```plaintext
Táo
Cam
Chuối
```

### 2. Dùng .forEach() (Cách hiện đại)

Đây là cách viết thanh lịch và dễ đọc hơn rất nhiều. Phương thức `.forEach()` nhận vào một hàm (function), và nó sẽ gọi hàm đó 1 lần cho mỗi phần tử trong mảng.

```javascript
const traiCay = ["Táo", "Cam", "Chuối"];

// "Với mỗi 'item' trong mảng 'traiCay', hãy thực hiện hàm này"
traiCay.forEach((item) => {
  console.log(item);
});
```

Kết quả: (Y hệt như trên).

## Ví dụ thực tế: Hiển thị danh sách lên trang web

Hãy kết hợp kiến thức về DOM (Bài 4) và Mảng để hiển thị một danh sách lên trang HTML.

**HTML (`index.html`):**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Danh sách trái cây</title>
  </head>
  <body>
    <h1>Các loại trái cây yêu thích của tôi</h1>
    <ul id="fruit-list">
      <!-- JavaScript sẽ chèn nội dung vào đây -->
    </ul>
    <script src="app.js"></script>
  </body>
</html>
```

**JavaScript (`app.js`):**

```javascript
// 1. Dữ liệu của chúng ta
const traiCay = ["Táo 🍎", "Cam 🍊", "Chuối 🍌", "Dâu 🍓"];

// 2. Truy xuất phần tử DOM
const listElement = document.getElementById("fruit-list");

// 3. Dùng vòng lặp để tạo và chèn HTML
traiCay.forEach((item) => {
  // 3.1. Tạo một thẻ <li> mới
  const li = document.createElement("li");

  // 3.2. Gán nội dung cho thẻ <li>
  li.textContent = item;

  // 3.3. Chèn thẻ <li> vào bên trong <ul>
  listElement.appendChild(li);
});
```

**Kết quả:** Trang web của bạn sẽ hiển thị một danh sách (dạng gạch đầu dòng) 4 loại trái cây.

## Tổng kết

Mảng là một công cụ không thể thiếu. Nắm vững cách duyệt mảng và các phương thức của nó là chìa khóa để xử lý dữ liệu động trong bất kỳ ứng dụng web nào. Với 6 bài học này, bạn đã có một nền tảng JavaScript cực kỳ vững chắc để bắt đầu xây dựng những dự án thực tế.
