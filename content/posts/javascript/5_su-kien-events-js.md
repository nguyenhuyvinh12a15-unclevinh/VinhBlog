---
title: "Bài 5: Bắt sự kiện (Events) - Khiến trang web tương tác"
date: 2024-05-27
description: "Tìm hiểu về Sự kiện (Events) trong JavaScript, cách sử dụng addEventListener để bắt các hành động của người dùng như click, mouseover và thực thi mã."
series: ["Làm chủ JavaScript"]
series_order: 5
tags: ["JavaScript", "Events", "DOM", "Cơ bản"]
categories: ["JavaScript"]
slug: "javascript-events"
---

## Bài 5: Bắt sự kiện (Events) - Khiến trang web tương tác 💥

Chào mừng bạn đến với bài học thứ 5! Ở bài trước, chúng ta đã học cách dùng DOM để "ra lệnh" cho HTML thay đổi (như đổi màu, đổi chữ). Nhưng chúng ta vẫn đang "ra lệnh" ngay khi trang web vừa tải xong.

Làm thế nào để chúng ta có thể chờ người dùng thực hiện một hành động (như click chuột, gõ phím) rồi mới thực thi mã JavaScript?

Đó chính là lúc Sự kiện (Events) vào cuộc.

## Sự kiện (Event) là gì?

Sự kiện là bất kỳ hành động nào xảy ra trên trang web mà JavaScript có thể "nghe" được.
Ví dụ về các sự kiện phổ biến:

- **click**: Người dùng click chuột vào một phần tử.
- **mouseover**: Người dùng di chuột LÊN TRÊN một phần tử.
- **mouseout**: Người dùng di chuột RA KHỎI một phần tử.
- **keydown**: Người dùng nhấn một phím (khi đang gõ trong ô input).
- **submit**: Người dùng gửi (submit) một biểu mẫu (form).

JavaScript cho phép chúng ta "lắng nghe" những sự kiện này và gắn một hàm (function) vào đó. Hàm này sẽ được tự động gọi mỗi khi sự kiện đó xảy ra.

## Cách lắng nghe sự kiện: addEventListener()

Đây là cách hiện đại và được khuyên dùng nhất để xử lý sự kiện. Nó cho phép bạn gắn nhiều "tai nghe" vào cùng một sự kiện trên một phần tử.

Cú pháp cơ bản:

```javascript
element.addEventListener("tenSuKien", hamXuLy);
```

Trong đó:

- **element**: Phần tử DOM mà bạn đã chọn (bằng `getElementById` hoặc `querySelector`).
- **'tenSuKien'**: Tên của sự kiện bạn muốn nghe (ví dụ: `'click'`, `'mouseover'`).
- **hamXuLy**: Tên của hàm (function) sẽ được gọi khi sự kiện xảy ra.

## Ví dụ hoàn chỉnh: Click để đổi chữ

Hãy tạo một ví dụ cổ điển: Có một nút bấm và một đoạn văn. Khi người dùng click vào nút, nội dung của đoạn văn sẽ thay đổi.

### Bước 1: Chuẩn bị file HTML (index.html)

Chúng ta cần một nút bấm (button) và một đoạn văn (p). Hãy đặt id cho chúng để dễ dàng truy xuất.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Sự kiện Click</title>
  </head>
  <body>
    <h1>Click vào nút để xem điều kỳ diệu!</h1>

    <button id="myButton">Click tôi đi!</button>
    <p id="message">Nội dung ban đầu...</p>

    <script src="app.js"></script>
  </body>
</html>
```

### Bước 2: Viết mã JavaScript (app.js)

```javascript
// --- BƯỚC 1: TRUY XUẤT CÁC PHẦN TỬ DOM ---
// Lấy cái nút bấm và lưu vào biến
const nutBam = document.getElementById("myButton");

// Lấy đoạn văn và lưu vào biến
const thongBao = document.getElementById("message");

// --- BƯỚC 2: VIẾT HÀM XỬ LÝ SỰ KIỆN ---
// Đây là hàm sẽ được gọi KHI nút được click
const thayDoiNoiDung = () => {
  // Thay đổi nội dung của đoạn văn
  thongBao.textContent = "Bạn vừa click tôi! 😮";

  // Thay đổi cả style cho sinh động
  thongBao.style.color = "blue";
  thongBao.style.fontSize = "20px";
};

// --- BƯỚC 3: GẮN BỘ LẮNG NGHE SỰ KIỆN ---
// "Này nút bấm, hãy lắng nghe sự kiện 'click'"
// "Khi nào sự kiện 'click' xảy ra, hãy chạy hàm thayDoiNoiDung"
nutBam.addEventListener("click", thayDoiNoiDung);
```

**Kết quả:**

Khi mở trang index.html, bạn sẽ thấy nút bấm và dòng chữ "Nội dung ban đầu...".

Khi bạn click vào nút "Click tôi đi!", dòng chữ ngay lập tức đổi thành "Bạn vừa click tôi! 😮" với màu xanh và cỡ chữ 20px.

## Sử dụng hàm ẩn danh (Anonymous Function)

Trong ví dụ trên, chúng ta đã định nghĩa hàm thayDoiNoiDung rồi mới truyền tên nó vào addEventListener.

Một cách phổ biến (và ngắn gọn) hơn là viết hàm xử lý ngay bên trong addEventListener. Hàm này không có tên nên được gọi là "hàm ẩn danh" (anonymous function).

**Cách viết lại ví dụ trên (chỉ file `app.js`):**

```javascript
// --- BƯỚC 1: TRUY XUẤT ---
const nutBam = document.getElementById("myButton");
const thongBao = document.getElementById("message");

// --- BƯỚC 2 VÀ 3 (KẾT HỢP): GẮN SỰ KIỆN VỚI HÀM ẨN DANH ---
nutBam.addEventListener("click", () => {
  // Toàn bộ logic xử lý được viết trực tiếp ở đây
  thongBao.textContent = "Bạn vừa click tôi! 😮";
  thongBao.style.color = "blue";
  thongBao.style.fontSize = "20px";
});
```

Cách viết này cho kết quả y hệt nhưng gọn gàng hơn vì bạn không cần đặt tên cho một hàm mà chỉ dùng đúng một lần.

## Tổng kết

Xin chúc mừng! Bạn đã nắm được các trụ cột cơ bản của JavaScript phía client: Biến, Hàm, DOM, và Events.

Chỉ với những kiến thức này, bạn đã có thể xây dựng được rất nhiều trang web có tính tương tác cao: tạo menu ẩn/hiện, làm tab, tạo máy tính đơn giản, và nhiều hơn nữa.

Trong bài học tiếp theo, chúng ta sẽ xem xét kỹ hơn về **Mảng (Arrays)**, một kiểu dữ liệu cực kỳ quan trọng để làm việc với các danh sách.

## Tổng kết

Xin chúc mừng! Bạn đã nắm được 5 trụ cột cơ bản của JavaScript phía client: Biến, Hàm, DOM, và Events.
Xin chúc mừng! Bạn đã nắm được các trụ cột cơ bản của JavaScript phía client: Biến, Hàm, DOM, và Events.

Chỉ với những kiến thức này, bạn đã có thể xây dựng được rất nhiều trang web có tính tương tác cao: tạo menu ẩn/hiện, làm tab, tạo máy tính đơn giản, và nhiều hơn nữa.

Trong bài học tiếp theo, chúng ta sẽ xem xét kỹ hơn về Mảng (Arrays), một kiểu dữ liệu cực kỳ quan trọng để làm việc với các danh sách.
Trong bài học tiếp theo, chúng ta sẽ xem xét kỹ hơn về **Mảng (Arrays)**, một kiểu dữ liệu cực kỳ quan trọng để làm việc với các danh sách.
