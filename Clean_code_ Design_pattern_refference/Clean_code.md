# Coding convention
## Khái niệm
- **Coding convention (quy ước viết mã)** là một tập hợp các quy tắc và hướng dẫn về cách viết mã nguồn trong một ngôn ngữ lập trình cụ thể hoặc trong một dự án phần mềm cụ thể. Mục tiêu của coding convention là tạo ra một tiêu chuẩn chung để làm cho mã nguồn dễ đọc, dễ bảo trì và dễ hiểu cho cả những người viết mã và những người đọc mã.
- Thông thường, một code convention sẽ mô tả các thông tin sau:
	- Cách đặt tên biến (`camel case: variableName`, `snake case: variable_name`,…).
	- Kiểu thụt lề, độ rộng thụt lề, sử dụng tab hay space,…
	- Phương pháp đặt dấu ngoặc.
	- Cách dùng khoảng trắng trong các biểu thức logic và số học.
	- Cách viết comment cho code và tài liệu.
	- Quy ước đặt tên class, tên file.
	- Cách viết câu lệnh.
	- Cách khai báo class và giao diện.
	- Phương pháp tổ chức file.
### Tổng hợp những quy tắc chung khi viết code
1. ##### Quy tắc đặt tên (Naming convention)
	- Cách đặt tên những định danh (bao gồm các biến, hằng số, class,…) cũng có ảnh hưởng không nhỏ đến khả năng đọc hiểu code. Hãy tưởng tượng một phần mềm khổng lồ như Windows nhưng mỗi hàm số chỉ được đặt tên như `a, b, c, function1, function2`,… thì chắc chắn việc quản lý và bảo trì code là vô cùng khó khăn.
	- Có ba cú pháp phổ biến là camelCase, PascalCase, snake_case.
		- **CamelCase:** Quy ước ký tự đầu tiên viết thường, những ký tự đầu tiên của chữ cái tiếp theo viết hoa. **Ví dụ:** productName, productPrice, ....
		- **PascalCase:** Chữ cái đầu tiên viết hoa. **Ví dụ:** ProductName, ProductPrice, ....
		- **Snake_case:** Các chữ cái đều viết thường và các từ được phân tách bởi dấu gạch dưới. **Ví dụ:** product_name, product_price
	- **Một số nguyên tắc:**
		- **Tên lớp:** đặt theo PascalCase.
		- **Tên biến, tên hàm:** đặt theo camelCase hoặc snake_case.
		- **Hằng số:** đặt theo UPPER_CASE.
		- **Tên biến, tên lớp:** thường là danh từ, cụm danh từ hoặc tính từ. VD: UserModel, userName, downloadCounter.
		-  Tên hàm thường bắt đầu bằng động từ. VD: getUserName, setUserName
		- Tên phải có nghĩa, không được đặt tên kiểu viết tắt như uName, pName,...
1. ##### Quy tắc về số lượng
	- Quy tắc số lượng được nêu rất cụ thể để lập trình viên dễ dàng thực hiện
		- Một dòng Code không nên dài quá 80 ký tự.
		- Một câu lệnh nên lồng tối đa 4 cấp.
		- Một hàm không nên chứa quá 5 tham số.
		- Một hàm không nên quá 30 dòng.
		- Một class không nên vượt 500 dòng,…
		- Mỗi hàm chỉ nên làm duy nhất một việc, nếu thực hiện hai mục đích khác nhau thì tên hàm cần thể hiện rõ điều này. VD: increaseDownloadAndSaveToDatabase
1. ##### Quy tắc xuống hàng
	- Nếu một hàm có nhiều cấp lồng nhau, mỗi cấp nên xuống dòng.
	- Các đoạn code bằng cấp nên ở cùng một cột với nhau, dòng xuống hàng nên bắt đầu cùng cấp với dòng phía trên.
	- Xuống hàng trước các toán tử (ví dụ như +, -, *, ?,…).
		```
		        longName1 = longName2 * (longName3 + longName4 - longName5)
		                   + 4 * longname6; // PREFER
		
		        longName1 = longName2 * (longName3 + longName4
		                               - longName5) + 4 * longname6; 
		```
	- Nếu có dấu "," thì xuống hàng sau dấu ",".
		```
		        someMethod(longExpression1, longExpression2, longExpression3, 
		                longExpression4, longExpression5);
		
		        var = someMethod1(longExpression1,
		                        someMethod2(longExpression2,
		                                longExpression3)); 
		```
1. ##### Quy tắc comment
	- Hạn chế dùng comment để giải thích code hoặc chú thích những sự thật hiển nhiên
	```js
	/** * Hàm thêm role vào database. */ 
	function addRole(role) { 
		db.roles.add(role); }
	```
	- Không comment khi đóng/thẻ
	```html
	<!DOCTYPE html> 
	<html lang="en"> 
	<!-- mở head --> 
	<head> 
	... 
	</head> 
	<!-- kết thúc head --> 
	<!-- mở body --> 
	<body> 
	... 
	</body> 
	<!-- kết thúc body --> 
	</html>
	```
	- Chỉ dùng comment trong trường hợp documentation, các thông tin đính kèm cho class hoặc cho các thư viện.
- **Coding convention** giúp tạo ra sự thống nhất trong việc viết mã nguồn trong dự án, giúp tăng khả năng hiểu và bảo trì mã nguồn theo thời gian.