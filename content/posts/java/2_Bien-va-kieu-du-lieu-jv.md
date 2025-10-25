---
title: "Bài 2: Biến và Kiểu dữ liệu - Những viên gạch cơ bản"
date: 2024-05-24
description: "Tìm hiểu về Biến (Variable) và Kiểu dữ liệu (Data Type) trong Java, bao gồm các kiểu nguyên thủy (int, double, boolean) và kiểu tham chiếu (String)."
series: ["Chinh phục Java từ con số 0"]
series_order: 2
tags: ["Java", "Biến", "Kiểu dữ liệu", "Lập trình cơ bản"]
categories: ["Java"]
slug: "java-bien-va-kieu-du-lieu"
---

## Bài 2: Biến và Kiểu dữ liệu - Những viên gạch cơ bản

Chào mừng bạn đến với bài học thứ hai trong series "Chinh phục Java từ con số 0"! Ở bài trước, chúng ta đã thành công cài đặt môi trường và chạy chương trình "Hello, World!" đầu tiên. Đó là một khởi đầu tuyệt vời!

Bây giờ, hãy cùng nhau tìm hiểu về một trong những khái niệm nền tảng nhất trong lập trình: Biến (Variable) và Kiểu dữ liệu (Data Type).

## Biến là gì?

Hãy tưởng tượng biến giống như một chiếc hộp có dán nhãn. Bạn có thể đặt một thứ gì đó vào chiếc hộp này để lưu trữ và lấy ra sử dụng sau này.

Trong lập trình:

- **Chiếc hộp** chính là một vùng trong bộ nhớ máy tính.

- **Cái nhãn** là tên biến (ví dụ: `age`, `score`, `username`).

- **Thứ bên trong hộp** là giá trị của biến (ví dụ: `25`, `9.5`, `"peter"`).

Biến cho phép chúng ta lưu trữ, truy cập và thay đổi dữ liệu một cách linh hoạt trong suốt quá trình chương trình chạy.

## Các kiểu dữ liệu - Bạn đang lưu trữ thứ gì?

Trong Java, khi tạo một "chiếc hộp", bạn phải nói rõ bạn định chứa loại đồ vật gì bên trong. Java là một ngôn ngữ kiểu tĩnh (statically typed), nghĩa là bạn phải xác định kiểu dữ liệu cho mỗi biến ngay khi khai báo.

Có hai nhóm chính: Kiểu dữ liệu nguyên thủy và Kiểu dữ liệu tham chiếu.

### 1. Kiểu dữ liệu nguyên thủy (Primitive Types)

Đây là 8 kiểu dữ liệu cơ bản và đơn giản nhất, được Java xây dựng sẵn.

**Số nguyên:** Dùng để lưu các số không có phần thập phân.

- `int`: Kiểu thông dụng nhất để lưu số nguyên (ví dụ: `10`, `99`, `-500`).

- `long`: Dùng khi số nguyên quá lớn, vượt quá khả năng lưu trữ của `int`.

**Số thực:** Dùng để lưu các số có phần thập phân.

- `double`: Kiểu thông dụng nhất để lưu số thực, có độ chính xác cao (ví dụ: `3.14`, `9.8`, `-15.5`).

- `float`: Ít dùng hơn, độ chính xác thấp hơn `double`.

**Logic:**

- `boolean`: Chỉ có thể nhận một trong hai giá trị: `true` (đúng) hoặc `false` (sai). Thường dùng trong các câu lệnh điều kiện.

**Ký tự:**

- `char`: Dùng để lưu một ký tự duy nhất, được đặt trong dấu nháy đơn (ví dụ: `'A'`, `'b'`, `'5'`).

### 2. Kiểu dữ liệu tham chiếu (Reference Type)

Bất cứ thứ gì không phải là kiểu nguyên thủy đều là kiểu tham chiếu. Chúng phức tạp hơn và có thể chứa nhiều dữ liệu hoặc hành vi. Hiện tại, chúng ta chỉ cần quan tâm đến kiểu phổ biến nhất:

- **String (Chuỗi):** Dùng để lưu trữ một chuỗi các ký tự (văn bản). Giá trị của `String` được đặt trong dấu nháy kép.

  Ví dụ: `"Hello, Java"`, `"Đây là một chuỗi"`.

## Cách khai báo và gán giá trị

Cú pháp để tạo một biến trong Java rất đơn giản:

```java
Kiểu_dữ_liệu tên_biến = giá_trị;
```

**Quy tắc đặt tên biến:**

- Nên bắt đầu bằng một chữ cái thường.
- Sử dụng quy tắc **camelCase**: từ đầu tiên viết thường, các từ tiếp theo viết hoa chữ cái đầu (ví dụ: `firstName`, `playerScore`, `accountBalance`).
- Tên biến không được chứa khoảng trắng và các ký tự đặc biệt (trừ `$` và `_`).
- Tên biến phải có ý nghĩa, giúp bạn đọc lại code dễ hiểu hơn.

## Ví dụ thực tế

Hãy cùng xem một đoạn code hoàn chỉnh khai báo một vài biến và in chúng ra màn hình.

Tạo một file mới Variables.java và gõ đoạn mã sau:

```java
public class Variables {
    public static void main(String[] args) {
        // Khai báo biến kiểu String để lưu tên
        String studentName = "Alice";

        // Khai báo biến kiểu int để lưu tuổi
        int studentAge = 20;

        // Khai báo biến kiểu double để lưu điểm trung bình
        double gpa = 8.5;

        // Khai báo biến kiểu boolean để kiểm tra tình trạng tốt nghiệp
        boolean isGraduated = false;

        // In các thông tin đã lưu ra màn hình
        System.out.println("Tên sinh viên: " + studentName);
        System.out.println("Tuổi: " + studentAge);
        System.out.println("Điểm trung bình: " + gpa);
        System.out.println("Đã tốt nghiệp chưa? " + isGraduated);
    }
}
```

Kết quả khi chạy:

```plaintext
Tên sinh viên: Alice
Tuổi: 20
Điểm trung bình: 8.5
Đã tốt nghiệp chưa? false
```

Như bạn thấy, chúng ta đã tạo ra các "chiếc hộp" (studentName, studentAge, gpa, isGraduated), đặt giá trị vào chúng, và sau đó lấy giá trị đó ra để hiển thị.

## Tổng kết

Nắm vững biến và kiểu dữ liệu là bước đầu tiên để bạn có thể ra lệnh cho máy tính xử lý thông tin. Trong bài tiếp theo, chúng ta sẽ học cách thực hiện các phép toán với những biến này thông qua các **Toán tử**. Hẹn gặp lại bạn!
Kết quả khi chạy:

```plaintext
Tên sinh viên: Alice
Tuổi: 20
Điểm trung bình: 8.5
Đã tốt nghiệp chưa? false
```

Như bạn thấy, chúng ta đã tạo ra các "chiếc hộp" (studentName, studentAge, gpa, isGraduated), đặt giá trị vào chúng, và sau đó lấy giá trị đó ra để hiển thị.

Nắm vững biến và kiểu dữ liệu là bước đầu tiên để bạn có thể ra lệnh cho máy tính xử lý thông tin. Trong bài tiếp theo, chúng ta sẽ học cách làm cho chương trình trở nên thông minh hơn với Câu lệnh điều kiện và Vòng lặp. Hẹn gặp lại bạn!

## 🎯 Tổng kết

Nắm vững biến và kiểu dữ liệu là bước đầu tiên để bạn có thể ra lệnh cho máy tính xử lý thông tin. Trong bài tiếp theo, chúng ta sẽ học cách thực hiện các phép toán với những biến này thông qua các **Toán tử**. Hẹn gặp lại bạn!
