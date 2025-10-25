---
title: 'Bài 1: Cách JavaScript "giao tiếp" với HTML và "Hello, World!"'
date: 2024-05-23
description: "Tìm hiểu 3 cách nhúng JavaScript vào HTML và viết chương trình 'Hello, World!' đầu tiên bằng alert() và console.log()."
series: ["Làm chủ JavaScript"]
series_order: 1
tags: ["JavaScript", "HTML", "Cơ Bản", "Hello World"]
categories: ["JavaScript"]
slug: "javascript-hello-world"
---

![Javascript logo](/img/javascript.png)

## Bài 1: Cách JavaScript "giao tiếp" với HTML và "Hello, World!" 🚀

Chào mừng bạn đến với series "JavaScript - Làm chủ thế giới Web"! Ở bài mở đầu, chúng ta đã thống nhất rằng HTML là khung xương, CSS là da thịt, còn JavaScript chính là "bộ não" mang lại sự sống và khả năng tương tác.

Vậy, làm thế nào để "lắp" bộ não JavaScript này vào "cơ thể" HTML? Trong bài hôm nay, chúng ta sẽ học cách thực hiện điều đó và "nói" lời chào đầu tiên.

## JavaScript "sống" ở đâu trên trang HTML?

Giống như một chiếc xe cần hệ thống điện để hoạt động, một trang HTML cần thẻ <script> để "chạy" được mã JavaScript. Có 3 cách chính để thêm hệ thống điện này:

### 1. External Script (File riêng) - Cách chuyên nghiệp (Khuyên dùng)

Đây là cách làm sạch sẽ và được khuyến khích nhất. Bạn sẽ viết tất cả mã JavaScript của mình vào một tệp riêng biệt có đuôi là .js (ví dụ: app.js).

Hãy tưởng tượng HTML là bản thiết kế ngôi nhà, CSS là bản vẽ nội thất, và app.js là bản thiết kế hệ thống điện. Mỗi thứ ở một tệp riêng, rất ngăn nắp.

**Trong file `index.html`:**
Bạn dùng thẻ `<script>` với thuộc tính `src` (source - nguồn) để trỏ đến file `.js` đó.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Trang Web</title>
  </head>
  <body>
    <h1>Trang web của tôi</h1>

    <!-- ... toàn bộ nội dung HTML ... -->

    <!-- Nhúng file JS ở ngay trước khi đóng thẻ body -->
    <script src="app.js"></script>
  </body>
</html>
```

**Trong file `app.js`:**

```javascript
// Toàn bộ mã JavaScript của bạn sẽ nằm ở đây.
// Ví dụ:
console.log("File app.js đã được tải!");
```

### 2. Internal Script (Nội tuyến) - Cách dùng để thử nhanh

Bạn có thể viết mã JavaScript trực tiếp vào bên trong tệp HTML, bằng cách đặt chúng giữa cặp thẻ `<script>...</script>`.

Cách này tiện lợi khi bạn chỉ muốn thử nghiệm nhanh một đoạn code nhỏ mà không muốn tạo file mới.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Trang Web</title>
  </head>
  <body>
    <h1>Trang web của tôi</h1>

    <script>
      // Bạn có thể viết code JS thẳng vào đây
      alert("Đây là Internal Script!");
    </script>
  </body>
</html>
```

⭐ **Quy tắc vàng:** Dù là External hay Internal, hãy luôn đặt thẻ `<script>` của bạn ở ngay trước khi đóng thẻ `</body>`.

**Tại sao?** Trình duyệt đọc file HTML từ trên xuống dưới. Nếu bạn đặt script ở `<head>`, nó sẽ chạy trước khi các thẻ HTML (như `<h1>`, `<p>`) kịp hiển thị. Nếu JavaScript của bạn cố gắng tìm một thẻ `<h1>` chưa tồn tại, nó sẽ báo lỗi.

Đặt ở cuối đảm bảo rằng toàn bộ "cơ thể" HTML đã được tải xong, và JavaScript có thể an toàn tương tác với chúng.

### 3. Inline Script (Trên dòng) - Cách nên tránh

Đây là cách viết code JavaScript thẳng vào thuộc tính của một thẻ HTML (ví dụ: `onclick`).

```html
<!-- KHÔNG NÊN DÙNG CÁCH NÀY -->
<button onclick="alert('Bạn đã click tôi!')">Click thử xem</button>
```

Cách này làm cho code của bạn bị "trộn lẫn" lung tung (logic nằm trong cấu trúc), khiến việc đọc, sửa lỗi và bảo trì sau này trở thành một cơn ác mộng. Chúng ta sẽ không sử dụng cách này.

## Lời chào đầu tiên: "Hello, World!"

Bây giờ, hãy thử "nói" điều gì đó. Có 2 cách "nói" cơ bản:

### 1. alert() - "Hét lên" với người dùng

Lệnh `alert()` sẽ hiển thị một hộp thoại pop-up ngay trên trình duyệt. Nó sẽ chặn đứng mọi thứ và buộc người dùng phải nhấn "OK".

**Trong file `app.js` (hoặc trong thẻ `<script>`):**

```javascript
alert("Xin chào! Bạn vừa thấy một thông báo!");
```

Cách này hữu ích khi bạn muốn thông báo một điều gì đó thật sự khẩn cấp. Nhưng đừng lạm dụng nó, vì alert liên tục sẽ làm người dùng rất khó chịu.

### 2. console.log() - "Thì thầm" với lập trình viên (Bạn!)

Đây mới là người bạn thân nhất của bạn. `console.log()` không hiển thị cho người dùng thông thường xem. Nó in thông điệp của bạn vào một khu vực "hậu trường" gọi là **Bảng điều khiển (Console)**.

Đây là nơi bạn dùng để kiểm tra giá trị, xem code có chạy đúng hay không, và gỡ lỗi (debug).

**Trong file `app.js`:**

```javascript
console.log("Hello, World!");
console.log("Kiểm tra giá trị 5 + 5 =", 5 + 5);
```

**Làm sao để xem Console?**
Trên Chrome, Firefox, hay Edge:

- Nhấn phím `F12`.
- Hoặc **Click chuột phải** vào trang web, chọn **"Inspect"** (Kiểm tra).
- Tìm và nhấn vào tab có tên **"Console"**.

Bạn sẽ thấy các dòng chữ mình đã log ra xuất hiện ở đó.

## Tổng kết

Tuyệt vời! Bạn đã biết 3 cách để "lắp" JavaScript vào HTML (và biết cách tốt nhất là External Script đặt ở cuối body). Bạn cũng đã học được cách dùng alert() để thông báo cho người dùng và console.log() để kiểm tra code "hậu trường".

Bạn đã sẵn sàng để ra những mệnh lệnh thực sự. Trong bài học tiếp theo, chúng ta sẽ học cách "nhớ" thông tin bằng cách sử dụng **Biến (Variables)**. Hẹn gặp lại bạn!
