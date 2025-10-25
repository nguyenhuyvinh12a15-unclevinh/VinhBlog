---
title: 'Bài 2: Biến (var, let, const) và "Trí nhớ" của JavaScript'
date: 2024-05-24
description: "Tìm hiểu về biến (var, let, const) và các kiểu dữ liệu cơ bản (String, Number, Boolean, undefined, null) trong JavaScript."
series: ["Làm chủ JavaScript"]
series_order: 2
tags: ["JavaScript", "Biến", "Kiểu dữ liệu", "Cơ bản"]
categories: ["JavaScript"]
slug: "javascript-bien-kieu-du-lieu"
---

## Bài 2: Biến (var, let, const) và "Trí nhớ" của JavaScript 💾

Chào mừng bạn quay trở lại series "JavaScript - Làm chủ thế giới Web"! Ở bài 1, chúng ta đã biết cách "nói" Hello World với trình duyệt. Bây giờ, chúng ta sẽ học cách làm cho JavaScript có "trí nhớ" - đó chính là Biến (Variables).

## Biến là gì?

Hãy tưởng tượng Biến giống như một chiếc hộp có dán nhãn. Bạn có thể đặt thông tin vào chiếc hộp đó và đặt tên cho nó (ví dụ: "tuoi"). Bất cứ khi nào bạn cần thông tin bên trong, bạn chỉ cần gọi tên chiếc hộp.

Trong JavaScript, biến là tên mà chúng ta đặt cho một vùng nhớ, dùng để lưu trữ dữ liệu (như một con số, một dòng chữ, v.v.).

## var, let, hay const?

Trước đây, JavaScript chỉ có một cách để khai báo biến là dùng từ khóa var. Tuy nhiên, kể từ năm 2015 (với bản cập nhật ES6), chúng ta có thêm hai cách mới, mạnh mẽ và an toàn hơn là let và const.

Ngày nay, quy tắc chung là:
Ưu tiên dùng const. Nếu bạn biết giá trị của biến sẽ cần thay đổi, hãy dùng let. Hạn chế tối đa việc dùng var.

### const (Constant - Hằng số):

Dùng để khai báo một biến mà giá trị của nó sẽ không bao giờ thay đổi.

Bạn bắt buộc phải gán giá trị cho nó ngay khi khai báo.

Đây là lựa chọn ưu tiên hàng đầu vì nó giúp code của bạn an toàn hơn, tránh việc vô tình gán lại giá trị.

```javascript
const ten = "An";
const namSinh = 2000;
// ten = "Bình"; // Dòng này sẽ báo lỗi! Vì bạn không thể thay đổi giá trị của const.
```

### let:

Dùng để khai báo một biến mà giá trị của nó có thể thay đổi sau này.

Đây là lựaVchọn tốt thứ hai, chỉ dùng khi bạn biết chắc mình sẽ cần gán lại giá trị.

```javascript
let diem = 5;
console.log(diem); // In ra 5

diem = 10; // Gán lại giá trị mới
console.log(diem); // In ra 10
```

### var (Cách cũ):

Hoạt động tương tự let nhưng có một số khác biệt về "phạm vi hoạt động" (scope) có thể gây ra lỗi khó hiểu.

Bạn nên tránh dùng var trong code hiện đại để giữ cho code luôn rõ ràng.

## Các kiểu dữ liệu cơ bản (Dynamic Typing)

Không giống như Java, bạn không cần phải nói trước cho JavaScript biết biến này sẽ chứa kiểu dữ liệu gì. JavaScript rất thông minh, nó sẽ tự "đoán" kiểu dữ liệu khi bạn gán giá trị. Đây được gọi là Dynamic Typing (Kiểu dữ liệu động).

Các kiểu dữ liệu cơ bản và phổ biến nhất bao gồm:

### String (Chuỗi):

Dùng để lưu trữ văn bản.

Được đặt bên trong dấu nháy đơn (' ') hoặc nháy kép (" ").

Gần đây, Template Literals (dấu ``) được ưa chuộng vì cho phép bạn chèn biến vào chuỗi một cách dễ dàng.

```javascript
const loiChao = "Xin chào các bạn!";
const tenCuaBan = "Linh";
const chaoBan = `Chào bạn ${tenCuaBan}, rất vui được gặp bạn!`; // Dùng ` `
console.log(chaoBan); // In ra: Chào bạn Linh, rất vui được gặp bạn!
```

### Number (Số):

Dùng để lưu trữ cả số nguyên (integer) và số thực (float/double).

Bạn có thể thực hiện các phép toán +, -, \*, / với chúng.

```javascript
const tuoi = 30;
const chieuCao = 1.75;
const tong = 10 + 5;
```

### Boolean (Logic):

Chỉ có thể là true (đúng) hoặc false (sai).

Cực kỳ quan trọng, là nền tảng cho các câu lệnh logic và điều kiện mà chúng ta sẽ học sau.

```javascript
const daDangNhap = true;
const conBaiTap = false;
const diemQuaMon = 5 > 3; // Kết quả là true
```

## Các kiểu dữ liệu đặc biệt

### undefined (Chưa xác định):

Một biến đã được khai báo nhưng chưa được gán giá trị sẽ có giá trị là undefined.

```javascript
let tenCuaToi;

console.log(tenCuaToi); // In ra undefined
```

### null (Rỗng):

Đại diện cho sự "không có gì cả" hoặc "giá trị rỗng" một cách có chủ đích.

Nó khác với undefined ở chỗ, null là giá trị mà bạn (lập trình viên) chủ động gán cho biến.

```javascript
let nguoiDung = null; // Gán rỗng, có thể sau này sẽ gán bằng 1 đối tượng người dùng
```

## Giới thiệu sơ lược về Array và Object

Ngoài các kiểu dữ liệu cơ bản, JavaScript còn có hai kiểu cấu trúc dữ liệu cực kỳ quan trọng:

Array (Mảng): Dùng để lưu trữ một danh sách các giá trị. Chúng ta sẽ tìm hiểu kỹ hơn ở bài sau.

```javascript
const danhSachLop = ["An", "Bình", "Cường"];
```

Object (Đối tượng): Dùng để lưu trữ dữ liệu theo dạng cặp key: value (khóa: giá trị), mô tả một thực thể phức tạp.

```javascript
const sinhVien = {
  ten: "An",
  tuoi: 20,
  daTotNghiep: false,
};
```

## Tổng kết

Hôm nay chúng ta đã học được cách tạo ra "trí nhớ" cho JavaScript bằng let và const, cũng như các kiểu dữ liệu cơ bản mà nó có thể lưu trữ.

Trong bài học tiếp theo, chúng ta sẽ học cách gói các đoạn code lại thành những "cỗ máy" có thể tái sử dụng, đó chính là Hàm (Functions).
