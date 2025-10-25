---
title: "Bài 3: Câu lệnh điều kiện và Vòng lặp - Giúp chương trình thông minh hơn"
date: 2024-05-25
description: "Tìm hiểu về câu lệnh điều kiện (if-else) và các loại vòng lặp (for, while) trong Java để giúp chương trình của bạn có khả năng ra quyết định và lặp lại công việc."
series: ["Chinh phục Java từ con số 0"]
series_order: 3
tags: ["Java", "Câu Lệnh Điều Kiện", "Vòng Lặp", "Lập Trình Cơ Bản"]
categories: ["Java"]
slug: "java-dieu-kien-vong-lap"
---

## Giúp chương trình thông minh hơn

Chào mừng các bạn đã quay trở lại với series "Chinh phục Java từ con số 0"! Ở bài học trước, chúng ta đã làm quen với "những viên gạch" cơ bản là biến và kiểu dữ liệu. Chúng ta đã có thể lưu trữ thông tin, nhưng chương trình của chúng ta vẫn còn khá "ngô nghê" - nó chỉ chạy các lệnh từ trên xuống dưới một cách tuần tự.

Trong bài học này, chúng ta sẽ trang bị cho chương trình khả năng "tư duy": đưa ra quyết định và lặp lại các công việc. Đây là lúc mọi thứ trở nên thú vị hơn!

## Tại sao chương trình cần có Logic?

Trong đời thực, chúng ta liên tục đưa ra quyết định ("Nếu trời mưa, tôi sẽ mang ô") và thực hiện các công việc lặp đi lặp lại ("Tôi sẽ làm bài tập cho đến khi xong"). Lập trình cũng vậy. Chúng ta cần các câu lệnh logic để:

- **Ra quyết định**: Giúp chương trình rẽ nhánh, thực hiện các hành động khác nhau dựa trên những điều kiện cụ thể.

- **Lặp lại công việc**: Giúp chương trình thực hiện một tác vụ nhiều lần mà không cần chúng ta phải viết lại cùng một đoạn mã.

Để làm được điều này, Java cung cấp cho chúng ta Câu lệnh điều kiện (If-Else) và Vòng lặp (For, While).

## Câu lệnh điều kiện (If-Else)

Đây là công cụ giúp chương trình của bạn đưa ra quyết định. Cấu trúc của nó rất giống với cách chúng ta suy nghĩ hằng ngày.

### Cú pháp if (nếu)

Dùng để kiểm tra một điều kiện. Nếu điều kiện đó là true, khối mã bên trong if sẽ được thực thi.

```java
int score = 85;

if (score > 50) {
    System.out.println("Chúc mừng, bạn đã qua môn!");
}
```

### Cú pháp else (trường hợp còn lại)

Thường đi kèm với if. Nếu điều kiện của if là false, khối mã bên trong else sẽ được thực thi.

```java
int temperature = 15;

if (temperature > 25) {
    System.out.println("Trời nóng, hãy bật điều hòa.");
} else {
    System.out.println("Trời mát mẻ.");
}
```

### Cú pháp else if (nếu không thì...)

Dùng khi bạn có nhiều hơn hai trường hợp cần kiểm tra.

### Ví dụ: Kiểm tra một số là chẵn hay lẻ

Hãy xem một ví dụ hoàn chỉnh sử dụng toán tử % (chia lấy dư). Một số chẵn khi chia cho 2 sẽ có số dư là 0.

```java
public class EvenOddChecker {
    public static void main(String[] args) {
        int number = 7;

        // Kiểm tra nếu số dư khi chia cho 2 bằng 0
        if (number % 2 == 0) {
            System.out.println(number + " là số chẵn.");
        } else {
            System.out.println(number + " là số lẻ.");
        }
    }
}
```

Kết quả khi chạy: `7 là số lẻ.`

## Vòng lặp (Loops)

Vòng lặp là cứu cánh giúp bạn không phải lặp lại việc viết code. Có hai loại vòng lặp chính bạn cần biết.

### 1. Vòng lặp for

Bạn nên dùng vòng lặp for khi bạn biết trước chính xác số lần lặp.

Cú pháp của nó gồm 3 phần trong dấu ngoặc đơn:

- **Khởi tạo**: Chạy một lần duy nhất khi bắt đầu vòng lặp (ví dụ: `int i = 1`).
- **Điều kiện**: Vòng lặp sẽ tiếp tục chạy miễn là điều kiện này còn `true` (ví dụ: `i <= 10`).
- **Bước nhảy**: Thực thi sau mỗi lần lặp, thường dùng để tăng hoặc giảm biến đếm (ví dụ: `i++` tương đương `i = i + 1`).

**Ví dụ: In ra các số từ 1 đến 10**

```java
public class CountToTen {
    public static void main(String[] args) {
        System.out.println("Bắt đầu đếm:");

        for (int i = 1; i <= 10; i++) {
            System.out.println(i);
        }

        System.out.println("Kết thúc!");
    }
}
```

### 2. Vòng lặp while

Bạn nên dùng vòng lặp while khi bạn không biết trước số lần lặp, và vòng lặp sẽ chạy cho đến khi một điều kiện nào đó không còn đúng nữa.

**Ví dụ: Chương trình đếm ngược đơn giản**

```java
public class Countdown {
    public static void main(String[] args) {
        int count = 5;

        while (count > 0) {
            System.out.println("Đếm ngược: " + count);
            count--; // Giảm biến đếm đi 1 sau mỗi lần lặp
        }

        System.out.println("Chúc mừng năm mới!");
    }
}
```

Kết quả khi chạy:

```plaintext
Đếm ngược: 5
Đếm ngược: 4
Đếm ngược: 3
Đếm ngược: 2
Đếm ngược: 1
Chúc mừng năm mới!
```

## Tổng kết

Bây giờ chương trình của bạn đã có thể đưa ra quyết định và lặp lại công việc. Bạn đã tiến một bước rất dài!

- **Câu lệnh điều kiện (`if-else`)**: Giúp chương trình rẽ nhánh và thực hiện các hành động khác nhau dựa trên điều kiện.
- **Vòng lặp `for`**: Sử dụng khi biết trước số lần lặp.
- **Vòng lặp `while`**: Sử dụng khi lặp cho đến khi một điều kiện không còn đúng.

Trong bài học tiếp theo, chúng ta sẽ tìm hiểu về trái tim của Java: **Lớp (Class) và Đối tượng (Object)**, khái niệm cốt lõi của Lập trình Hướng đối tượng. Hẹn gặp lại bạn!
Đếm ngược: 1
Chúc mừng năm mới!

```

Bây giờ chương trình của bạn đã có thể đưa ra quyết định và lặp lại công việc. Bạn đã tiến một bước rất dài! Trong bài học tiếp theo, chúng ta sẽ tìm hiểu về trái tim của Java: Lớp (Class) và Đối tượng (Object), khái niệm cốt lõi của Lập trình Hướng đối tượng. Hẹn gặp lại bạn!

## 🎯 Tổng kết

Bây giờ chương trình của bạn đã có thể đưa ra quyết định và lặp lại công việc. Bạn đã tiến một bước rất dài!

- **Câu lệnh điều kiện (`if-else`)**: Giúp chương trình rẽ nhánh và thực hiện các hành động khác nhau dựa trên điều kiện.
- **Vòng lặp `for`**: Sử dụng khi biết trước số lần lặp.
- **Vòng lặp `while`**: Sử dụng khi lặp cho đến khi một điều kiện không còn đúng.

Trong bài học tiếp theo, chúng ta sẽ tìm hiểu về trái tim của Java: **Lớp (Class) và Đối tượng (Object)**, khái niệm cốt lõi của Lập trình Hướng đối tượng. Hẹn gặp lại bạn!
```
