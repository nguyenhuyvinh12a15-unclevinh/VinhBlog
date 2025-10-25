---
title: "Bài 3: Hàm (Functions) - Những cỗ máy tái sử dụng"
date: 2024-05-25
description: "Tìm hiểu về Hàm (Functions) trong JavaScript, bao gồm Function Declaration và Arrow Function, cách sử dụng tham số và giá trị trả về (return)."
series: ["Làm chủ JavaScript"]
series_order: 3
tags: ["JavaScript", "Hàm", "Function", "Cơ bản"]
categories: ["JavaScript"]
slug: "javascript-ham-functions"
---

## Bài 3: Hàm (Functions) - Những cỗ máy tái sử dụng ⚙️

Chào mừng các bạn đã quay trở lại! Ở bài trước, chúng ta đã học cách lưu trữ dữ liệu bằng Biến. Nhưng nếu chúng ta muốn thực hiện cùng một tác vụ (ví dụ: gửi lời chào) ở nhiều nơi khác nhau trong code thì sao? Chẳng lẽ chúng ta phải viết đi viết lại cùng một đoạn mã?

Câu trả lời là không! JavaScript cung cấp cho chúng ta một công cụ cực kỳ mạnh mẽ: Hàm (Functions).

## Hàm là gì?

Hãy tưởng tượng Hàm giống như một cỗ máy xay sinh tố:

1.  **Bạn đưa nguyên liệu vào** (dâu, sữa, đá - đây gọi là **tham số (parameters)**).
2.  **Bạn bấm nút** (đây là **gọi hàm (call function)**).
3.  **Cỗ máy thực hiện một loạt hành động** (xay, trộn...).
4.  **Nó trả về một kết quả** (một ly sinh tố dâu - đây là **giá trị trả về (return value)**).

Trong JavaScript, Hàm là một khối code được đặt tên, được thiết kế để thực hiện một công việc cụ thể. Bạn có thể "gọi" nó bất cứ khi nào bạn cần thực hiện công việc đó.

## Cách tạo và sử dụng Hàm

Có hai cách chính để khai báo một hàm trong JavaScript hiện đại:

### 1. Function Declaration (Khai báo hàm)

Đây là cách khai báo truyền thống và cơ bản nhất. Nó sử dụng từ khóa function, theo sau là tên hàm và cặp dấu ngoặc đơn ().
Đây là cách khai báo truyền thống và cơ bản nhất. Nó sử dụng từ khóa `function`, theo sau là tên hàm và cặp dấu ngoặc đơn `()`.

```javascript
// 1. Định nghĩa "cỗ máy"
// 'name' ở đây là một tham số (parameter)
function guiLoiChao(name) {
  const loiChao = `Chào bạn ${name}, chúc một ngày tốt lành!`;
  console.log(loiChao);
}

// 2. "Bấm nút" để chạy máy (gọi hàm)
// "An" và "Bình" ở đây là các đối số (arguments)
guiLoiChao("An");
guiLoiChao("Bình");
```

Kết quả khi chạy:

```plaintext
Chào bạn An, chúc một ngày tốt lành!
Chào bạn Bình, chúc một ngày tốt lành!
```

### 2. Arrow Function (ES6) - Cách hiện đại

Đây là cú pháp mới (từ 2015) và đang ngày càng trở nên phổ biến vì sự ngắn gọn của nó. Nó đặc biệt hữu ích khi dùng với các phương thức mảng (chúng ta sẽ học sau).

```javascript
// Cú pháp Arrow Function
const guiLoiChao2 = (name) => {
  const loiChao = `Chào bạn ${name}, chúc một ngày tốt lành!`;
  console.log(loiChao);
};

guiLoiChao2("Tâm");
```

Kết quả: `Chào bạn Tâm, chúc một ngày tốt lành!`

## Giá trị trả về (Return Value)

Không phải hàm nào cũng chỉ in ra console. Đa số các hàm sẽ làm một việc gì đó (như tính toán) và trả về kết quả để bạn có thể sử dụng ở nơi khác. Chúng ta dùng từ khóa return để làm việc này.

Hãy tạo một "cỗ máy" tính tổng hai số:

```javascript
// 'a' và 'b' là tham số
const tinhTong = (a, b) => {
  const ketQua = a + b;
  return ketQua; // Trả về kết quả
};

// Gọi hàm và hứng lấy giá trị trả về
const tongSo = tinhTong(5, 3);

console.log(tongSo); // In ra 8
console.log(tinhTong(10, 20)); // In ra 30
```

**Quan trọng:** Khi JavaScript gặp từ khóa `return`, hàm sẽ dừng lại ngay lập tức và trả về giá trị. Mọi dòng code bên dưới `return` (trong cùng một hàm) sẽ không được thực thi.

## Tại sao Hàm lại quan trọng?

- **Tái sử dụng (Reusability):** Bạn chỉ cần viết logic một lần và gọi nó ở 100 nơi khác nhau. Nếu cần sửa, bạn chỉ sửa ở một chỗ duy nhất.
- **Trừu tượng hóa (Abstraction):** Bạn không cần biết cách cỗ máy xay sinh tố hoạt động bên trong (mô-tơ quay, lưỡi dao cắt thế nào). Bạn chỉ cần biết "bỏ dâu vào" và "lấy sinh tố ra". Hàm cũng vậy, nó che giấu đi sự phức tạp bên trong, giúp code của bạn dễ đọc hơn.
- **Tính tổ chức (Organization):** Hàm giúp bạn chia chương trình lớn thành nhiều phần nhỏ, dễ quản lý hơn, mỗi hàm chịu trách nhiệm cho một việc cụ thể.

## Tổng kết

Bạn vừa học được một trong những khái niệm nền tảng quan trọng nhất của lập trình! Hàm là "những người thợ" xây dựng nên chương trình của bạn.

Trong bài học tiếp theo, chúng ta sẽ bắt đầu phần thú vị nhất: dùng JavaScript để "nói chuyện" và thay đổi giao diện HTML của trang web thông qua DOM.
Trong bài học tiếp theo, chúng ta sẽ bắt đầu phần thú vị nhất: dùng JavaScript để "nói chuyện" và thay đổi giao diện HTML của trang web thông qua **DOM (Document Object Model)**.
