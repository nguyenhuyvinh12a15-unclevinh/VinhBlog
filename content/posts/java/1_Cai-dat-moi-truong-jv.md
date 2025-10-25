---
title: 'Bài 1: Cài đặt môi trường và "Hello, World!" đầu tiên với Java'
date: 2024-05-23
description: "Hướng dẫn cài đặt JDK, IDE (VS Code, IntelliJ) và viết chương trình Java 'Hello, World!' đầu tiên, bước khởi đầu quan trọng trong series Chinh phục Java."
series: ["Chinh phục Java từ con số 0"]
series_order: 1
tags: ["Java", "Cài đặt", "JDK", "IDE", "Hello World"]
categories: ["Java"]
slug: "java-cai-dat-moi-truong-hello-world"
---

## Bài 1: Cài đặt môi trường và "Hello, World!" đầu tiên với Java

Chào mừng bạn đã quay trở lại với series "Chinh phục Java từ con số 0"! Trong bài viết trước, chúng ta đã tìm hiểu Java là gì và tại sao nó lại quyền năng đến vậy. Bây giờ là lúc để "xắn tay áo lên" và chuẩn bị mọi thứ cần thiết để viết những dòng code đầu tiên.

Để bắt đầu cuộc hành trình lập trình Java, chúng ta cần hai công cụ không thể thiếu: JDK và IDE. Nghe có vẻ phức tạp, nhưng đừng lo, chúng ta sẽ cùng nhau tìm hiểu nhé.

## JDK là gì? - Hộp dụng cụ của lập trình viên

JDK (Java Development Kit) chính là Bộ công cụ phát triển Java. Hãy tưởng tượng nó như một hộp dụng cụ đầy đủ của người thợ mộc. Bên trong đó có chứa mọi thứ bạn cần để "xây dựng" và "chạy" một chương trình Java, quan trọng nhất là:

Compiler (Trình biên dịch): Công cụ để dịch mã Java mà bạn viết (con người đọc hiểu) sang bytecode (máy ảo Java hiểu).

JVM (Máy ảo Java): "Thông dịch viên" mà chúng ta đã nói ở bài trước, chịu trách nhiệm thực thi file bytecode trên bất kỳ máy tính nào.

Nói tóm lại, không có JDK, bạn không thể lập trình Java.

## IDE là gì? - Không gian làm việc của bạn

IDE (Integrated Development Environment) là Môi trường phát triển tích hợp. Nếu JDK là hộp dụng cụ, thì IDE chính là xưởng làm việc hiện đại của bạn. Về cơ bản, nó là một trình soạn thảo văn bản (text editor) siêu cấp với rất nhiều tính năng hỗ trợ như:

Gợi ý code thông minh (code completion).

Phát hiện lỗi cú pháp ngay khi bạn gõ.

Tích hợp sẵn nút "Chạy" để xem kết quả ngay lập tức.

Các công cụ gỡ lỗi (debug) mạnh mẽ.

Đối với người mới bắt đầu, có hai IDE miễn phí và cực kỳ phổ biến được khuyên dùng:

Visual Studio Code (VS Code): Nhẹ nhàng, linh hoạt, với kho tiện ích mở rộng khổng lồ. Bạn chỉ cần cài thêm gói "Extension Pack for Java".

IntelliJ IDEA (Community Edition): Một IDE cực kỳ mạnh mẽ và thông minh, được rất nhiều lập trình viên Java chuyên nghiệp yêu thích.

## Hướng dẫn cài đặt JDK

Chúng ta sẽ cài đặt OpenJDK, một phiên bản Java hoàn toàn miễn phí và mã nguồn mở.

Truy cập trang web: Mở trình duyệt và truy cập Eclipse Temurin. Đây là một nơi uy tín để tải OpenJDK.

Tải về: Trang web sẽ tự động nhận diện hệ điều hành của bạn (Windows, macOS, Linux) và đề xuất phiên bản phù hợp. Hãy chọn phiên bản LTS (Long-Term Support) mới nhất và nhấn nút tải về.

Cài đặt: Mở file vừa tải về và làm theo các bước hướng dẫn. Quá trình này khá đơn giản, bạn chỉ cần nhấn "Next" và đồng ý với các điều khoản. Điều quan trọng là hãy đảm bảo bạn đã tick vào tùy chọn "Add to PATH" trong quá trình cài đặt.

Vậy là xong! Bạn đã có đủ "dụng cụ" cần thiết.

## Chương trình "Hello, World!" - Lời chào đầu tiên

Bây giờ, hãy mở IDE của bạn lên, tạo một file mới tên là Main.java và gõ đoạn mã sau:

```java
public class Main {
    public static void main(String[] args) {
        // In dòng chữ "Hello, World!" ra màn hình
        System.out.println("Hello, World!");
    }
}
```

Hãy cùng "mổ xẻ" từng dòng nhé:

`public class Main { ... }`: Mỗi chương trình Java đều cần ít nhất một lớp (class). Nó giống như một bản thiết kế hoặc một cái thùng chứa cho code của bạn. `Main` là tên chúng ta đặt cho lớp này.

`public static void main(String[] args) { ... }`: Đây là một phương thức (method) cực kỳ đặc biệt. Nó chính là điểm bắt đầu của chương trình. Khi bạn chạy code, Máy ảo Java (JVM) sẽ tìm đến đúng phương thức `main` này để thực thi. Bạn sẽ hiểu rõ hơn về `public`, `static`, `void` trong các bài sau.

`System.out.println("Hello, World!");`: Đây là câu lệnh ra lệnh cho máy tính in ra dòng chữ `Hello, World!` trên màn hình console, sau đó xuống một dòng mới.

## Cách chạy chương trình

Điều tuyệt vời của các IDE hiện đại là chúng làm cho việc chạy code trở nên vô cùng đơn giản.

Bên cạnh dòng `public static void main...`, bạn sẽ thấy một biểu tượng hình tam giác màu xanh (nút Run). Chỉ cần nhấp vào đó!

Ngay lập tức, một cửa sổ console hoặc terminal sẽ hiện lên ở phía dưới màn hình, và bạn sẽ thấy kết quả:

```plaintext
Hello, World!
```

Xin chúc mừng! Bạn vừa viết và chạy thành công chương trình Java đầu tiên của mình. Đây là một bước khởi đầu vô cùng quan trọng.

## Tổng kết

Trong bài học tiếp theo, chúng ta sẽ tìm hiểu về những viên gạch cơ bản nhất của mọi ngôn ngữ lập trình: Biến và Kiểu dữ liệu. Hẹn gặp lại!
