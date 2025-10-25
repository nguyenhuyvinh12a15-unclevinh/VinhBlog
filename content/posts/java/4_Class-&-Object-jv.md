---
title: "Bài 4: Lớp (Class) và Đối tượng (Object) - Cốt lõi của OOP"
date: 2024-05-26
description: "Tìm hiểu về Lớp (Class) và Đối tượng (Object), hai khái niệm nền tảng của Lập trình Hướng đối tượng (OOP) trong Java, giúp bạn tổ chức code hiệu quả."
series: ["Chinh phục Java từ con số 0"]
series_order: 4
tags: ["Java", "OOP", "Class", "Object", "Lập trình cơ bản"]
categories: ["Java"]
slug: "java-class-object"
---

Xin chào các bạn đã quay trở lại với series "Chinh phục Java từ con số 0"! Trong các bài học trước, chúng ta đã học cách ra lệnh cho máy tính lưu trữ dữ liệu, đưa ra quyết định và lặp lại công việc. Về cơ bản, chúng ta đã viết code theo lối "tuần tự" - một danh sách các hướng dẫn từ trên xuống dưới.

Hôm nay, chúng ta sẽ thực hiện một bước nhảy vọt về tư duy lập trình. Chúng ta sẽ tìm hiểu về Lập trình Hướng đối tượng (Object-Oriented Programming - OOP), triết lý đã làm nên sức mạnh và sự thành công của Java.

## Giới thiệu về Lập trình Hướng đối tượng (OOP)

Nghe có vẻ "hàn lâm", nhưng ý tưởng của OOP lại vô cùng tự nhiên. Thay vì viết một chương trình như một chuỗi dài các mệnh lệnh, OOP giúp chúng ta mô phỏng thế giới thực.

Hãy nhìn xung quanh bạn: có một chiếc điện thoại, một cái bàn, một cuốn sách. Mỗi thứ đều là một "vật thể" (object), và mỗi vật thể có những đặc điểm riêng (màu sắc, trọng lượng) và những hành vi riêng (điện thoại có thể gọi, cuốn sách có thể lật trang).

OOP cho phép chúng ta mang tư duy này vào trong code. Chúng ta tạo ra các "đối tượng" ảo, gói ghém dữ liệu (đặc điểm) và hành vi của chúng lại với nhau. Cách làm này giúp code trở nên có tổ chức, dễ quản lý, dễ tái sử dụng và cực kỳ hiệu quả cho các dự án lớn.

Để làm được điều này, chúng ta cần hiểu hai khái niệm nền tảng: Lớp (Class) và Đối tượng (Object).

## Lớp (Class) là gì? - Bản thiết kế

Hãy tưởng tượng bạn muốn chế tạo một chiếc xe hơi. Trước tiên, bạn cần một bản thiết kế chi tiết. Bản thiết kế này sẽ định nghĩa mọi thứ về một chiếc xe hơi nói chung:

- Nó phải có những bộ phận gì? (Bánh xe, động cơ, vô lăng...).
- Nó có thể làm được những gì? (Chạy, dừng, rẽ trái, rẽ phải...).

Trong Java, Lớp (Class) chính là bản thiết kế đó. Nó không phải là một chiếc xe hơi thật, mà là một khuôn mẫu định nghĩa nên cấu trúc và hành vi của một loại đối tượng nào đó.

> **Class** là một khuôn mẫu, một bản thiết kế, định nghĩa các thuộc tính và phương thức mà các đối tượng của nó sẽ có.

## Đối tượng (Object) là gì? - Sản phẩm thực tế

Từ một bản thiết kế xe hơi, nhà máy có thể sản xuất ra hàng ngàn chiếc xe. Mỗi chiếc xe được tạo ra là một sản phẩm thực tế. Ví dụ, chiếc Vinfast Fadil màu đỏ của bạn là một chiếc xe, chiếc Toyota Vios màu trắng của người hàng xóm cũng là một chiếc xe.

Trong Java, Đối tượng (Object) chính là sản phẩm thực tế đó. Nó là một thể hiện (instance) cụ thể được tạo ra từ một Lớp. Mỗi đối tượng sẽ có những đặc điểm riêng, dù chúng cùng được tạo ra từ một bản thiết kế.

> **Object** là một thể hiện cụ thể của một Class. Nó có trạng thái và hành vi riêng, dựa trên những gì được định nghĩa trong Class.

## Thuộc tính (Attributes) và Phương thức (Methods)

Mỗi bản thiết kế (Class) sẽ định nghĩa hai thứ quan trọng:

- **Thuộc tính (Attributes)**: Là những đặc điểm, những dữ liệu mô tả về đối tượng. Chúng chính là các biến nằm bên trong một lớp.
  - Ví dụ: Class `Car` có thể có các thuộc tính `String color;`, `int yearOfManufacture;`.
- **Phương thức (Methods)**: Là những hành vi, những hành động mà đối tượng có thể thực hiện. Chúng chính là các hàm nằm bên trong một lớp.
  - Ví dụ: Class `Car` có thể có các phương thức `void startEngine()`, `void accelerate()`.

## Ví dụ thực tế: Lớp Dog

Bây giờ, hãy tạo một lớp để mô phỏng một chú chó.

### 1. Tạo "bản thiết kế" - File Dog.java

Đầu tiên, hãy tạo một file mới tên là Dog.java và định nghĩa lớp Dog:

```java
// Đây là bản thiết kế cho tất cả các đối tượng Dog
public class Dog {
    // 1. Thuộc tính (Attribute)
    // Mỗi chú chó sẽ có một cái tên
    String name;

    // 2. Phương thức (Method)
    // Mỗi chú chó đều có thể sủa
    public void bark() {
        // Phương thức này sử dụng thuộc tính 'name' của chính đối tượng đó
        System.out.println(name + " đang sủa: Gâu! Gâu!");
    }
}
```

### 2. Tạo và sử dụng "sản phẩm" - File Main.java

Bây giờ, trong file `Main.java` quen thuộc, chúng ta sẽ tạo ra những chú chó thực tế từ bản thiết kế `Dog`.

```java
public class Main {
    public static void main(String[] args) {
        // Tạo một đối tượng (sản phẩm) đầu tiên từ lớp Dog
        Dog dog1 = new Dog();

        // Gán giá trị cho thuộc tính của đối tượng dog1
        dog1.name = "Milu";

        // Gọi phương thức (hành vi) của đối tượng dog1
        dog1.bark();

        // Tạo một đối tượng thứ hai từ cùng một lớp Dog
        Dog dog2 = new Dog();
        dog2.name = "Vàng";
        dog2.bark();
    }
}
```

Kết quả khi chạy:

```plaintext
Milu đang sủa: Gâu! Gâu!
Vàng đang sủa: Gâu! Gâu!
```

Hãy chú ý:

- Chúng ta dùng từ khóa `new` để tạo ra một đối tượng mới từ một lớp.
- Cả `dog1` và `dog2` đều được tạo ra từ lớp `Dog`, nhưng chúng là hai đối tượng hoàn toàn riêng biệt và có trạng thái (`name`) độc lập.
- Khi gọi phương thức `bark()`, mỗi đối tượng sẽ hành động dựa trên dữ liệu của chính nó.

## Tổng kết

Bạn vừa hoàn thành bài học quan trọng nhất để hiểu về tư duy hướng đối tượng.

- **Lớp (Class)**: Là một bản thiết kế hoặc khuôn mẫu, định nghĩa các thuộc tính (dữ liệu) và phương thức (hành vi) chung.
- **Đối tượng (Object)**: Là một thể hiện cụ thể được tạo ra từ một lớp, có trạng thái và hành vi riêng.
- **Từ khóa `new`**: Được sử dụng để tạo ra một đối tượng mới từ một lớp.

Nắm vững khái niệm Class và Object sẽ mở ra cho bạn một thế giới hoàn toàn mới trong lập trình. Trong các bài học sau, chúng ta sẽ khám phá sâu hơn về các sức mạnh khác của OOP. Hẹn gặp lại!
