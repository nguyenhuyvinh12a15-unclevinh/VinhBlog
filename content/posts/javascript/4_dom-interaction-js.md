---
title: "Bài 4: Giới thiệu về DOM - Khi JavaScript gặp HTML"
date: 2024-05-26
description: "Tìm hiểu về DOM (Document Object Model), cách JavaScript truy xuất (getElementById, querySelector) và thay đổi nội dung (textContent, innerHTML), style của các phần tử HTML."
series: ["Làm chủ JavaScript"]
series_order: 4
tags: ["JavaScript", "DOM", "HTML", "Cơ bản"]
categories: ["JavaScript"]
slug: "javascript-dom-interaction"
---

## Bài 4: Giới thiệu về DOM - Khi JavaScript gặp HTML 🤝

Chào mừng bạn đã quay trở lại! Chúng ta đã học về Biến (lưu trữ) và Hàm (hành động). Nhưng cho đến giờ, mã JavaScript của chúng ta vẫn chạy "ngầm" bên trong console. Làm thế nào để JavaScript có thể tương tác, thay đổi những gì người dùng nhìn thấy trên trang web (như thay đổi một dòng chữ, ẩn/hiện một hình ảnh)?

Câu trả lời chính là DOM.

## DOM là gì?

DOM là viết tắt của Document Object Model (Mô hình Đối tượng Tài liệu).

Nghe phức tạp vậy, nhưng bạn có thể hiểu đơn giản:

Khi trình duyệt tải tệp HTML của bạn, nó sẽ tạo ra một "bản đồ" dạng cây biểu diễn cấu trúc của trang web đó. "Bản đồ" này được gọi là DOM. JavaScript có thể đọc và thay đổi "bản đồ" này, và khi "bản đồ" thay đổi, những gì người dùng thấy trên trang web cũng sẽ thay đổi theo.

Hãy xem cấu trúc cây của một file HTML đơn giản.

**HTML:**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Trang của tôi</title>
  </head>
  <body>
    <h1>Tiêu đề chính</h1>
    <p>Một đoạn văn.</p>
  </body>
</html>
```

**Cây DOM (minh họa):**

```text
Document
└── html
    ├── head
    │   └── title
    │       └── "Trang của tôi"
    └── body
        ├── h1
        │   └── "Tiêu đề chính"
        └── p
            └── "Một đoạn văn."
```

Đối với JavaScript, document là đối tượng gốc, và mọi thứ (như head, body, h1, p) đều là các nút (nodes) trên cây mà nó có thể truy cập.

## 1. Truy xuất phần tử (Selecting Elements)

Trước khi thay đổi bất cứ thứ gì, JavaScript cần phải "chọn" được phần tử HTML mà nó muốn tác động. Đây là những "tọa độ" trên bản đồ DOM.

Có hai cách phổ biến nhất để làm điều này:

### document.getElementById('id-cua-ban')

Đây là cách nhanh và đơn giản nhất. Bạn chỉ cần đặt một thuộc tính id (duy nhất) cho thẻ HTML của mình.

**HTML:**

```html
<h1 id="tieu-de">Tiêu đề ban đầu</h1>
```

**JavaScript:**

```javascript
// 1. Truy xuất (chọn) phần tử có id là "tieu-de"
const h1Element = document.getElementById("tieu-de");

// 2. In ra console để xem thử
console.log(h1Element); // Sẽ in ra thẻ <h1 id="tieu-de">...</h1>
```

### document.querySelector('selector')

Cách này linh hoạt hơn rất nhiều. Bạn có thể chọn phần tử bằng bất cứ CSS selector nào (chọn theo id, class, tên thẻ, v.v.).

- Chọn theo id: `document.querySelector('#tieu-de')`
- Chọn theo class: `document.querySelector('.ten-class')`
- Chọn theo tên thẻ: `document.querySelector('p')` (Cách này sẽ chỉ trả về phần tử đầu tiên mà nó tìm thấy)

**HTML:**

```html
<p class="doan-van">Đoạn văn đầu tiên.</p>
<p class="doan-van">Đoạn văn thứ hai.</p>
```

**JavaScript:**

```javascript
// Chỉ chọn được phần tử CÓ CLASS "doan-van" ĐẦU TIÊN
const pElement = document.querySelector(".doan-van");
console.log(pElement);
```

**Lưu ý:** Nếu bạn muốn chọn tất cả các phần tử có class "doan-van", bạn dùng `document.querySelectorAll('.doan-van')`.

## 2. Thay đổi nội dung (Changing Content)

Khi đã "nắm" được phần tử trong tay (lưu nó vào một biến), bạn có thể thay đổi nội dung bên trong nó.

### .textContent

Cách này an toàn và được khuyên dùng nhất. Nó sẽ thay đổi chỉ nội dung văn bản bên trong thẻ, bỏ qua mọi thẻ HTML.

**HTML:**

```html
<h1 id="tieu-de">Đây là tiêu đề cũ</h1>
```

**JavaScript:**

```javascript
// 1. Chọn phần tử
const h1Element = document.getElementById("tieu-de");

// 2. Thay đổi nội dung text của nó
h1Element.textContent = "Đây là tiêu đề MỚI!";
```

Kết quả trên trình duyệt: Chữ Đây là tiêu đề cũ sẽ ngay lập tức bị đổi thành Đây là tiêu đề MỚI!.

### .innerHTML

Cách này cho phép bạn chèn cả thẻ HTML vào bên trong phần tử.

Cảnh báo: Hãy cẩn thận khi dùng .innerHTML với dữ liệu do người dùng nhập vào, vì nó có thể tiềm ẩn rủi ro bảo mật (XSS). Nhưng nếu bạn tự kiểm soát nội dung, nó rất hữu ích.

**HTML:**

```html
<div id="container"></div>
```

**JavaScript:**

```javascript
const container = document.getElementById("container");
container.innerHTML = "<h2>Đây là thẻ H2</h2><p>Và đây là đoạn văn.</p>";
```

Kết quả: Trình duyệt sẽ hiển thị một thẻ h2 và một thẻ p bên trong div container.

## 3. Thay đổi thuộc tính và Style (Attributes & CSS)

Bạn cũng có thể thay đổi các thuộc tính (như src của ảnh) hoặc style (CSS) của phần tử.

**HTML:**

```html
<img id="my-image" src="link-anh-cu.jpg" alt="ảnh cũ" />
<p id="my-text">Đoạn văn này sẽ đổi màu.</p>
```

**JavaScript:**

```javascript
// Thay đổi thuộc tính 'src' của ảnh
const img = document.getElementById("my-image");
img.src = "link-anh-moi.png";
img.alt = "ảnh mới";

// Thay đổi style (CSS)
const pText = document.getElementById("my-text");
pText.style.color = "red";
pText.style.fontSize = "24px"; // Lưu ý: thuộc tính CSS có dấu gạch (font-size) sẽ viết liền (fontSize)
```

## Tổng kết

Bạn vừa học được cách sử dụng sức mạnh lớn nhất của JavaScript: thay đổi trang web một cách linh hoạt! Đây là nền tảng cho mọi thứ, từ việc hiển thị thông báo, tạo hiệu ứng, cho đến xây dựng các ứng dụng web phức tạp.

Nhưng làm thế nào để chúng ta thực hiện các thay đổi này khi người dùng làm gì đó (ví dụ: khi họ click chuột)? Đó là nội dung của bài học tiếp theo: **Bắt sự kiện (Events)**.
