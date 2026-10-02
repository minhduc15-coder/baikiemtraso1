# baikiemtraso1
bài1
Value Types và Reference Types khác nhau về cơ chế lưu trữ trong bộ nhớ Stack và Heap.
Value Type (kiểu giá trị): biến lưu trực tiếp giá trị của dữ liệu. Đối với biến cục bộ, dữ liệu thường được lưu trên Stack. Khi gán một biến cho biến khác, giá trị được sao chép sang vùng nhớ mới nên hai biến độc lập nhau. Ví dụ: int, double, bool, struct, enum.
Reference Type (kiểu tham chiếu): biến lưu địa chỉ tham chiếu đến đối tượng. Đối tượng thường được lưu trên Heap, còn biến chứa tham chiếu đến đối tượng đó. Khi gán một biến cho biến khác, tham chiếu được sao chép nên hai biến có thể cùng trỏ đến một đối tượng trên Heap. Ví dụ: class, object,
Value Type chủ yếu lưu giá trị trực tiếp, còn Reference Type lưu tham chiếu đến đối tượng; đối tượng của Reference Type được cấp phát trên Heap.
câu2
Init-only Properties (init) là tính năng được giới thiệu trong C# 9, cho phép một thuộc tính chỉ được gán giá trị trong quá trình khởi tạo đối tượng. Sau khi đối tượng đã được khởi tạo, giá trị của thuộc tính sử dụng init không thể thay đổi.
Trong khi đó, thuộc tính sử dụng set thông thường cho phép gán và thay đổi giá trị của thuộc tính bất kỳ lúc nào sau khi đối tượng được tạo.
Ví dụ:
class SinhVien
{
public string MaSV { get; init; }
public string HoTen { get; set; }
}
Thuộc tính có set cho phép thay đổi giá trị sau khi đối tượng được khởi tạo, còn thuộc tính có init chỉ cho phép gán giá trị trong quá trình khởi tạo. Vì vậy, init giúp hạn chế việc thay đổi những dữ liệu không nên thay đổi sau khi đối tượng được tạo.
câu3
Virtual: Là phương thức được khai báo ở lớp cha, cho phép lớp con có thể ghi đè lại phương thức. Phương thức virtual thường cung cấp cách thực hiện mặc định.
Override: Là phương thức được khai báo ở lớp con để ghi đè và thay đổi cách thực hiện phương thức virtual của lớp cha.
Ví dụ:
class Animal
{
public virtual void Sound()
{
Console.WriteLine("Animal sound");
}
}
class Dog : Animal
{
public override void Sound()
{
Console.WriteLine("Dog barks");
}
}
Khi gọi Animal a = new Dog(); a.Sound(); thì phương thức Sound() của lớp Dog được thực hiện.
Kết luận: virtual cho phép ghi đè ở lớp con, còn override thực hiện việc ghi đè. Hai từ khóa này kết hợp để triển khai tính đa hình trong C#.
câu4
Thành phần static thuộc về lớp (Class) chứ không thuộc về một đối tượng cụ thể. Vì vậy, nó được tạo và quản lý một lần duy nhất khi lớp được sử dụng và được dùng chung cho tất cả các đối tượng của lớp.
Trong khi đó, đối tượng được tạo bằng toán tử new là một thể hiện (Instance) riêng của lớp thuộc object. Các thành phần không phải static thuộc về từng đối tượng.
Do đó, thành phần static phải được truy xuất thông qua tên lớp, không truy xuất thông qua đối tượng.
Ví dụ:
class SinhVien
{
public static int SoLuong = 0;
}
Có thể truy xuất:
SinhVien.SoLuong;
Không thể truy xuất theo cách:
SinhVien sv = new SinhVien();
sv.SoLuong; // Lỗi
