# Khái niệm
- JavaScript (JS) là một ngôn ngữ lập trình thông dịch, thường được sử dụng để thêm tính năng tương tác và động cho các trang web. Ban đầu, JavaScript được phát triển để thực hiện các tác vụ cơ bản trên giao diện người dùng trong trình duyệt web. Tuy nhiên, qua thời gian, nó đã trở thành một ngôn ngữ lập trình phía máy khách (client-side) mạnh mẽ và đa dạng.
	1. **Biến (Variables)**: Được sử dụng để lưu trữ dữ liệu như chuỗi (string), số (number), đối tượng (object), và nhiều loại dữ liệu khác. Khai báo biến bằng cách sử dụng từ khóa `var`, `let`, hoặc `const`.
	    
	2. **Hàm (Functions)**: Là một khối mã thực hiện một nhiệm vụ cụ thể. JavaScript cho phép bạn định nghĩa và sử dụng các hàm riêng biệt.
	    
	3. **Sự kiện (Events)**: JavaScript cho phép bạn phản ứng với các sự kiện trên trang web, như nhấp chuột, gõ phím, hoặc thay đổi kích thước cửa sổ trình duyệt.
	    
	4. **DOM (Document Object Model)**: Là một cấu trúc biểu diễn trang HTML, cho phép JavaScript tương tác và thay đổi nội dung, thuộc tính và cấu trúc của trang web.
	    
	5. **Biểu thức điều kiện (Conditional Statements)**: Câu lệnh `if`, `else if`, và `else` được sử dụng để kiểm tra điều kiện và thực hiện mã khác nhau dựa trên kết quả của điều kiện.
	    
	6. **Vòng lặp (Loops)**: Ví dụ như vòng lặp `for` và `while`, để lặp lại một tập hợp các câu lệnh một số lần hoặc cho đến khi một điều kiện không còn đúng.
	    
	7. **Mảng (Arrays)**: Là cấu trúc dữ liệu cho phép lưu trữ nhiều giá trị trong một biến duy nhất. Mảng được sử dụng rộng rãi để quản lý danh sách dữ liệu.
	    
	8. **Đối tượng (Objects)**: Là một tập hợp các cặp khóa-giá trị, cho phép bạn tạo ra các đối tượng có thuộc tính và phương thức riêng.
	    
	9. **Bất đồng bộ (Asynchronous)**: JavaScript hỗ trợ thực hiện các tác vụ bất đồng bộ thông qua sử dụng callback, Promise, và từ ES6 trở đi, Async/Await. Điều này cho phép xử lý các tác vụ như tải dữ liệu từ máy chủ mà không làm đứng giao diện người dùng
# Cách sử dụng (Internal/External)
- JavaScript có thể được sử dụng trong các trang web bằng cách nhúng mã JavaScript vào trong HTML
- Có 2 cách nhúng mã js vào trong HTML
	- ##### Internal JavaScript
		- Mã JavaScript được đặt trực tiếp trong thẻ `<script>` bên trong tài liệu HTML. Chỉ nên sử dụng với các tác vụ nhỏ hoặc tạm thời
			```html
			<!DOCTYPE html>
			<html>
			<head>
			    <title>Internal JavaScript</title>
			</head>
			<body>
			    <h1>Hello, world!</h1>
			
			    <script>
			        // Mã JavaScript
			        alert("This is an internal JavaScript example.");
			    </script>
			</body>
			</html>
			```
			>Lưu ý rằng các đoạn mã JavaScript nội tại thường được đặt bên trong thẻ `<head>` hoặc `<body>` của tài liệu HTML.
	- ##### External JavaScript 
		- Mã JavaScript được viết trong các tệp riêng biệt với phần mở rộng `.js`. Sau đó, bạn có thể nhúng tệp JavaScript này vào tài liệu HTML bằng cách sử dụng thẻ `<script>` với thuộc tính `src` để chỉ định đường dẫn đến tệp JavaScript.
		- Ví dụ tạo một tệp có tên `myscript.js`
			```js
			// File: myscript.js
			function showMessage() {
			    alert("This message is from an external JavaScript file.");
			}
			```
		- trong tài liệu HTML, có thể nhúng tệp JavaScript bên ngoài như sau
			```html
			<!DOCTYPE html>
			<html>
			<head>
			    <title>External JavaScript</title>
			    <script src="path/to/myscript.js"></script>
			</head>
			<body>
			    <h1>Hello, world!</h1>
			
			    <button onclick="showMessage()">Click me</button>
			</body>
			</html>
			```
			- Trong ví dụ trên, khi người dùng nhấp vào nút "Click me", hàm `showMessage()` từ tệp `myscript.js` sẽ được gọi và hiển thị cảnh báo.

#  Biến (khai báo, đặt tên, scope)
- ## 1.Khai báo biến
	- Sử dụng các từ khóa `var`, `let`, hoặc `const`. Tùy thuộc vào từ khóa mà bạn sử dụng
	- Biến có thể có **phạm vi (scope)** và khả năng **thay đổi (mutable)** khác nhau
		- `var`: Khi ta khai báo lại biến bên trong một block code khác với từ khóa `var` thì nó sẽ ảnh hướng đến biến cùng tên ở bên ngoài block đó.
			```js
			var a = 10;
			//--> ở đây a = 10
			{
				var a = 5;
			    //--> a = 5;
			}
			//--> a = 5
			```
			>Việc biến `a` nhận giá trị mới trong block code là do biến được khai báo bằng `var` sẽ có **Global scope** .
		- `let` và `count`:  khai báo bên trong một block code thì sẽ không ảnh hưởng gì đến biến có cùng tên đã được khai báo bên ngoài block trước đó.
			```js
			var a = 1, b = 2;
			//--> Tại đây a = 1 và b = 2
			{
				let a = 5;
			    const b = 10;
			    //--> a ở đây bằng 5, b bằng 10
			}
			//--> a ở đây vẫn bằng 1 và b vẫn bằng 2
			```
		- **Lưu ý : các biến không được khai báo thì sẽ không tồn tại, tuy nhên nếu biến không được khai báo mà ta gián giá trị cho nó thì nó trở thành một biến có 'Global Scope' và có kiểu dữ liệu trùng với kiểu giá trị mà nó được gán đó nhé**
			```js
			// Biến x chưa được khai báo, nhưng khi gán giá trị cho nó, nó trở thành biến toàn cục
			x = 10;
			console.log(x); // 10
			
			// Biến y cũng chưa được khai báo, nhưng khi gán giá trị là một chuỗi, nó trở thành biến toàn cục với kiểu dữ liệu là string
			y = "Hello, world!";
			console.log(y); // Hello, world!
			
			// Biến z chưa được khai báo, khi gán giá trị là một mảng, nó trở thành biến toàn cục với kiểu dữ liệu là array
			z = [1, 2, 3];
			console.log(z); // [1, 2, 3]
			
			```
	- ## 2.Đặt tên
		- Tên biến trong JavaScript phải tuân theo một số quy tắc:
			- Bắt đầu bằng một chữ cái (a-z, A-Z) hoặc dấu gạch dưới (_).
			- Có thể chứa chữ cái, số, hoặc dấu gạch dưới.
			- Không được sử dụng các từ khóa đã được định nghĩa trong JavaScript (như `if`, `for`, `function`, v.v.).
			- JavaScript phân biệt chữ hoa và chữ thường trong tên biến (`myVariable` và `MyVariable` được xem xét là hai biến khác nhau).
			- [link tham khảo](https://viblo.asia/p/cach-dat-ten-dep-trong-javascript-QpmlerNM5rd)
	- ## 3.Scope
		- Phạm vi của biến xác định nơi mà biến có thể được truy cập và sử dụng trong mã JavaScript. Có ba loại phạm vi:
			- **Global Scope**: Biến khai báo ở global scope có thể truy cập từ bất kỳ nơi nào trong mã JavaScript.
			- **Function Scope**: Biến khai báo bên trong một hàm chỉ có thể truy cập từ bên trong hàm đó.
			- **Block Scope**: Biến khai báo bên trong một khối ({}) chỉ có thể truy cập từ bên trong khối đó.
			- Dùng `var` trong hàm sẽ có **phạm vi hàm**, còn `let` và `const` sẽ có **phạm vi khối.**
			```js
			var globalVar = "Global variable"; // Biến global
			
			function myFunction() {
			    var functionVar = "Function-scoped variable"; // Biến phạm vi hàm
			    if (true) {
			        let blockVar = "Block-scoped variable"; // Biến phạm vi khối
			    }
			    console.log(functionVar); // Có thể truy cập ở trong hàm
			    console.log(globalVar); // Có thể truy cập ở mọi nơi
			    console.log(blockVar); // Sẽ gây lỗi vì không trong phạm vi
			}
			
			myFunction();
			console.log(globalVar); // Có thể truy cập ở mọi nơi
			console.log(functionVar); // Sẽ gây lỗi vì không trong phạm vi
			console.log(blockVar); // Sẽ gây lỗi vì không trong phạm vi
			
			```
		- **Lưu ý rằng việc sử dụng `var` nên được tránh để tránh các vấn đề liên quan đến quản lý phạm vi. Thay vào đó, `let` và `const` là những lựa chọn tốt hơn cho việc khai báo biến trong JavaScript.**
# Data Type (string, number, boolean, object, array, null, undefined)
- Trong JavaScript, có một số kiểu dữ liệu cơ bản để đại diện cho các loại giá trị khác nhau. Dưới đây là một số kiểu dữ liệu quan trọng:

	1. **String (Chuỗi)**: Sử dụng để đại diện cho các chuỗi ký tự, được bao quanh bởi dấu nháy đơn ('') hoặc dấu nháy kép ("").
		```js
		var greeting = "Hello, world!";
		```

	1. **Number (Số)**: Đại diện cho các số nguyên, số thập phân hoặc số mũ.
		```js
		var age = 25; 
		var pi = 3.14159;
		```
	1. **Boolean (Luận lý)**: Đại diện cho giá trị `true` (đúng) hoặc `false` (sai), thường được sử dụng trong các biểu thức điều kiện.
		```js
		var isStudent = true; var isLoggedIn = false;
		```
	1. **Object (Đối tượng)**: Là một cấu trúc dữ liệu phức tạp bao gồm nhiều thuộc tính (properties) và phương thức (methods) liên quan đến một đối tượng cụ thể.
		```js
		var person = {     
		firstName: "John",     
		lastName: "Doe",     
		age: 30,     
		sayHello: function() {         
		console.log("Hello!");     
		} 
		};
		```
	1. **Array (Mảng)**: Là một tập hợp các giá trị, thường được sắp xếp theo thứ tự và truy cập bằng chỉ số (index).
		```js
		var numbers = [1, 2, 3, 4, 5]; 
		var fruits = ["apple", "banana", "orange"];
		```

	1. **Null**: Đại diện cho giá trị không có hoặc không tồn tại. Nó là một kiểu dữ liệu đặc biệt chỉ có một giá trị là `null`.
		```js
		var emptyValue = null;
		```
	1. **Undefined**: Đại diện cho một biến đã được khai báo nhưng chưa được gán giá trị hoặc tồn tại nhưng không có giá trị nào.
		```js
		var undefinedVar;
		```
		>**Các kiểu dữ liệu này cùng với các kiểu dữ liệu phức tạp khác như `function` và `symbol` tạo nên nền tảng cho việc lưu trữ và xử lý thông tin trong mã JavaScript.**
# Data struct (Array, JSON, Set, Map)
- Trong JavaScript, có một số cấu trúc dữ liệu hữu ích để quản lý và tổ chức dữ liệu. Dưới đây là một số cấu trúc dữ liệu quan trọng:

	1. **Array (Mảng)**: Mảng là một cấu trúc dữ liệu tập hợp các phần tử được sắp xếp theo thứ tự và truy cập thông qua chỉ số (index). Các phần tử trong mảng có thể là bất kỳ kiểu dữ liệu nào.
		```js
		var numbers = [1, 2, 3, 4, 5]; 
		var fruits = ["apple", "banana", "orange"];
		```
	1. **JSON (JavaScript Object Notation)**: JSON là một định dạng dữ liệu phổ biến được sử dụng để truyền và lưu trữ dữ liệu dưới dạng văn bản. Nó là một cách biểu diễn đối tượng và dữ liệu dạng cặp khóa-giá trị.
		```js
		var person = {     
		"firstName": "John",     
		"lastName": "Doe",     
		"age": 30 };
		```
	1. **Set**: Set là một tập hợp dữ liệu không có thứ tự, không chứa các phần tử trùng lặp. Set thường được sử dụng để lưu trữ danh sách các giá trị duy nhất.
		```js
		var uniqueNumbers = new Set([1, 2, 3, 3, 4, 4, 5]);
		```


	1. **Map**: Map là một cấu trúc dữ liệu cho phép ánh xạ giữa các khóa và giá trị tương ứng. Mỗi khóa chỉ có thể tương ứng với một giá trị và các khóa có thể là bất kỳ kiểu dữ liệu nào.
		```js
		var ages = new Map(); ages.set("John", 30); ages.set("Jane", 25);
		```
		>**Các cấu trúc dữ liệu này giúp bạn tổ chức và xử lý dữ liệu một cách hiệu quả trong mã JavaScript. Hãy lựa chọn cấu trúc dữ liệu phù hợp với nhu cầu của bạn để làm cho mã của bạn dễ đọc và dễ bảo trì hơn**
# Loop (For, While, Do while)
- Trong JavaScript, có ba loại vòng lặp chính để lặp lại một tập hợp các câu lệnh hoặc thực hiện một khối mã nhiều lần: vòng lặp `for`, `while` và `do while`.
	1. **Vòng lặp for**
		- Vòng lặp `for` thường được sử dụng khi bạn biết chính xác số lần lặp lại cần thực hiện. Cú pháp của vòng lặp `for` như sau:
			```js
			for (khởi tạo; điều kiện; bước nhảy) {     
			// Khối mã lệnh được thực thi trong mỗi lần lặp 
			}
			```
		- Ví dụ:
			```js
			for (var i = 0; i < 5; i++) {     
				console.log("Iteration " + i); 
			}
			```

	2. **Vòng lặp while:**
		- Vòng lặp `while` được sử dụng khi bạn không biết trước số lần lặp lại cần thực hiện và chỉ kiểm tra điều kiện trước khi thực hiện mỗi lần lặp.
			```js
			while (điều kiện) {     
			// Khối mã lệnh được thực thi trong mỗi lần lặp nếu điều kiện đúng 
			}
			```
		- Ví dụ:
			```js
			var count = 0; 
			while (count < 5) {     
				console.log("Count: " + count);     
				count++; 
			}
			```

	3. **Vòng lặp do while:**
		- Vòng lặp `do while` tương tự với `while`, nhưng khối mã lệnh sẽ được thực hiện ít nhất một lần, ngay cả khi điều kiện không đúng.
			```js
			do {     
			// Khối mã lệnh được thực thi ít nhất một lần 
			} while (điều kiện);
			```
		- Ví dụ:
			```js
			var x = 0; 
			do {     
				console.log("x = " + x);     
				x++; 
			} while (x < 3);
			```

		>**Các vòng lặp này cho phép bạn thực hiện các tác vụ lặp lại một cách linh hoạt, tùy theo nhu cầu của bạn. Hãy chọn vòng lặp phù hợp với tình huống cụ thể của bạn.**
# Conditional statements (If..else, Switch)
- Trong JavaScript, có hai cấu trúc điều kiện chính để thực hiện các câu lệnh hoặc khối mã khác nhau dựa trên điều kiện: câu lệnh `if..else` và cấu trúc `switch`.
	1. **Câu lệnh if..else:**
		- Câu lệnh `if..else` cho phép bạn thực hiện một khối mã lệnh nếu điều kiện là đúng và một khối mã lệnh khác nếu điều kiện sai. Cú pháp của câu lệnh `if..else` như sau:
			```js
			if (điều kiện) {     
			// Khối mã lệnh thực thi nếu điều kiện đúng 
			} 
			else {     // Khối mã lệnh thực thi nếu điều kiện sai 
			}
			```
		- Ví dụ:
			```js
			var age = 18;  
			if (age >= 18) {     
				console.log("You are an adult."); 
			} else {     
				console.log("You are not an adult yet."); 
			}
			```

	2. **Cấu trúc switch:**
		- Cấu trúc `switch` cho phép bạn thực hiện một loạt các trường hợp khác nhau dựa trên giá trị của biểu thức. Cú pháp của cấu trúc `switch` như sau:
			```js
			switch (biểu thức) {     
				case giá trị1:         
				// Khối mã lệnh thực thi nếu biểu thức trùng với giá trị1         
					break;     
				case giá trị2:         
				// Khối mã lệnh thực thi nếu biểu thức trùng với giá trị2         
					break;     
					// Thêm các trường hợp khác nếu cần     
				default:         
				// Khối mã lệnh thực thi nếu không có trường hợp nào trùng khớp }
			```
		- ví dụ
			```js
			var dayOfWeek = 3;  
				switch (dayOfWeek) {     
					case 1:         
						console.log("Sunday");         
						break;     
					case 2:         
						console.log("Monday");         
						break;    
					case 3:         
						console.log("Tuesday");         
						break;        
					default:         
						console.log("Invalid day"); }
			```


		>**Cả hai cấu trúc điều kiện này cho phép bạn kiểm tra điều kiện và thực hiện các tác vụ khác nhau dựa trên kết quả của điều kiện đó. Sử dụng cấu trúc phù hợp với nhu cầu của bạn để kiểm soát luồng thực hiện của chương trình.**
		
# Xử lý sự kiện (onclick,...)
- Xử lý sự kiện trong JavaScript là cách bạn tạo sự tương tác và phản hồi của trang web khi người dùng thực hiện các hành động như nhấp chuột, gõ phím, hoặc thao tác trên giao diện người dùng. Dưới đây là cách bạn xử lý sự kiện bằng JavaScript:

	1. **Xử lý sự kiện onclick:**
		- Sự kiện `onclick` được kích hoạt khi người dùng nhấp chuột vào một phần tử HTML. Bạn có thể xử lý sự kiện này bằng cách gắn một hàm vào thuộc tính `onclick` của phần tử.
			```html
			<button id="myButton">Click me</button>  
			
			<script> 
			document.getElementById("myButton").onclick = function() {     
				alert("Button clicked!"); 
			}; 
			</script>
			```

	2. **Xử lý sự kiện addEventListener:**
		- Bạn cũng có thể sử dụng phương thức `addEventListener` để gắn các hàm xử lý sự kiện vào một phần tử HTML. Điều này cho phép bạn thêm nhiều hàm xử lý cho cùng một sự kiện.
			```html
			<button id="myButton">Click me</button>  
			
			<script> 
			document.getElementById("myButton").addEventListener("click", function(){
				alert("Button clicked!"); 
			}); 
			</script>
			```
	3. **Xử lý sự kiện trên input:**
		- Sự kiện `oninput` được kích hoạt khi người dùng thay đổi nội dung của một phần tử input.
			```html
			<input id="myInput" type="text">  
			
			<script> 
			document.getElementById("myInput").oninput = function() {     
				console.log("Input changed:", this.value); 
			}; 
			</script>
			```


	4. **Xử lý sự kiện trên form:**
		- Sự kiện `onsubmit` được kích hoạt khi người dùng gửi một biểu mẫu.
			```html
			<form id="myForm">    
				<input type="text" name="name">     
				<input type="submit" value="Submit"> 
			</form>  
			
			<script> 
			document.getElementById("myForm").onsubmit = function(event) {  
				event.preventDefault(); // Ngăn form gửi đi     
				var formData = new FormData(event.target);     
				console.log("Form submitted:", formData.get("name")); 
			}; 
			</script>
			```

		>Nhớ rằng việc xử lý sự kiện là một phần quan trọng của việc tạo trải nghiệm tương tác trên trang web.
		
# Functions (Function parameter, arrow funtion)
- Trong JavaScript, hàm (function) là một khối mã lệnh có thể được gọi và thực thi. Hàm giúp tổ chức mã của bạn thành các đơn vị tái sử dụng và dễ đọc. Dưới đây là cách bạn định nghĩa hàm, **truyền tham số(Function parameter)** và sử dụng **hàm mũi tên (arrow function)**
	- ## Function parameter
		 1. #### định nghĩa hàm
			- Để định nghĩa một hàm, bạn sử dụng từ khóa `function`, sau đó là tên hàm, danh sách các tham số trong dấu ngoặc đơn và khối mã lệnh bên trong dấu ngoặc nhọn.
				```js
				function sayHello(name) {     
					console.log("Hello, " + name + "!"); 
				}
				```
		2. #### Truyền tham số khi gọi hàm
			- Khi bạn gọi hàm, bạn có thể truyền giá trị hoặc đối tượng vào các tham số tương ứng trong cùng thứ tự
				```js
				greet("Alice"); // Kết quả: Hello, Alice!
				greet("Bob"); // Kết quả: Hello, Bob!
				```
		3. #### Sử dụng giá trị tham số trong hàm
			- Sau khi truyền tham số vào hàm, bạn có thể sử dụng giá trị của tham số bên trong khối mã lệnh của hàm
				```js
				function multiply(x, y) {
				    return x * y;
				}
				console.log(multiply(5, 3)); // Kết quả: 15
				```
				>Khi sử dụng tham số, hàm trở nên linh hoạt và có thể tái sử dụng cho nhiều tình huống khác nhau. Tham số cho phép bạn truyền dữ liệu vào hàm để thực hiện các tính toán hoặc xử lý dữ liệu cụ thể trong mỗi lần gọi hàm.
			- VD
				```js
				// Định nghĩa hàm tính tổng của một danh sách số
				function calculateSum(numbers) {
				    let sum = 0;
				    for (let i = 0; i < numbers.length; i++) {
				        sum += numbers[i];
				    }
				    return sum;
				}
				
				// Gọi hàm và truyền một mảng các số làm tham số
				const numbersList = [10, 5, 8, 12, 6];
				const totalSum = calculateSum(numbersList);
				
				console.log("Tổng của các số trong danh sách là: " + totalSum);
				
				```

			- Trong ví dụ này:
			1. Chúng ta đã định nghĩa hàm `calculateSum` với một tham số `numbers`, đại diện cho một mảng các số.
			2. Trong khối mã lệnh của hàm, chúng ta sử dụng vòng lặp để duyệt qua từng phần tử trong mảng và tính tổng của chúng.
			3. Sau khi tính tổng, chúng ta trả về giá trị tổng từ hàm.
			4. Sau đó, chúng ta tạo một mảng `numbersList` và gọi hàm `calculateSum` với mảng này làm tham số.
			5. Cuối cùng, chúng ta in ra tổng của các số trong danh sách.

	- ## arrow funtion
		- Arrow function (hàm mũi tên) là một cú pháp mới trong JavaScript để định nghĩa hàm một cách ngắn gọn. Arrow function thường được sử dụng cho các hàm đơn giản và không chứa nhiều mã lệnh phức tạp. Dưới đây là cách sử dụng arrow function:
		1. #### Arrow function cơ bản
			```js
			const functionName = (tham_so1, tham_so2, ...) => {
			    // Khối mã lệnh của hàm
			    return ket_qua;
			};
			```
		- Ví dụ:
			```js
			const add = (a, b) => {
			    return a + b;
			};
			```

		2. #### Arrow function ngắn gọn
		- Nếu khối mã lệnh chỉ chứa một biểu thức trả về, bạn có thể viết ngắn gọn bằng cách loại bỏ dấu ngoặc nhọn và từ khóa `return`.
			```js
			const multiply = (x, y) => x * y;
			```


		3. #### Sử dụng arrow function trong xử lý sự kiện
		- Arrow function thường được sử dụng để định nghĩa hàm xử lý sự kiện.
			```js
			const button = document.getElementById("myButton");
			button.addEventListener("click", () => {
			    console.log("Button clicked!");
			});
			```


		4. #### Arrow function và ngữ cảnh `this`
		- Một ưu điểm của arrow function là nó không tạo ra ngữ cảnh `this` mới. Điều này thường hữu ích khi bạn muốn truy cập biến `this` của phạm vi bên ngoài.
			```js
			function Counter() {
			    this.count = 0;
			    this.increment = () => {
			        this.count++;
			        console.log(this.count);
			    };
			}
			const myCounter = new Counter();
			myCounter.increment(); // Kết quả: 1
			myCounter.increment(); // Kết quả: 2
			```
			
			>**Arrow function thường rất hữu ích trong các trường hợp đơn giản, khi bạn muốn viết mã ngắn gọn và dễ đọc. Tuy nhiên, hãy lưu ý rằng arrow function không thể thay thế hoàn toàn cho các hàm thông thường, đặc biệt trong các tình huống phức tạp hơn.**
			
# Làm việc với API (XMLHTTPRequest, Fetch)
- Là một phần quan trọng của việc phát triển ứng dụng web để tương tác với dữ liệu từ các nguồn bên ngoài. Trong JavaScript, bạn có thể sử dụng `XMLHttpRequest` hoặc `fetch` để gửi các yêu cầu HTTP đến các API và nhận phản hồi từ chúng. 
	- ## XMLHTTPRequest
		- Là một cách truyền thống để tạo và gửi các yêu cầu HTTP.
			```js
			let xhr = new XMLHttpRequest();
			xhr.open('GET', 'http://domain/service');
			
			// request state change event
			xhr.onreadystatechange = function() {
			
			  // request completed?
			  if (xhr.readyState !== 4) return;
			
			  if (xhr.status === 200) {
			    // request successful - show response
			    console.log(xhr.responseText);
			  }
			  else {
			    // request error
			    console.log('HTTP error', xhr.status, xhr.statusText);
			  }
			};
			
			// start request
			xhr.send();
			```
		- Đối tượng `XMLHttpRequest` có nhiều tùy chọn, sự kiện và thuộc tính phản hồi khác.
		- Ví dụ có thể đặt và phát hiện thời gian timeout tính bằng mili giây
			```js
			// set timeout
			xhr.timeout = 3000; // 3 seconds
			xhr.ontimeout = () => console.log('timeout', xhr.responseURL);
			```
		- Và một sự kiện `progress` thông báo tiến trình tải lên một tệp tin dài
			```js
			// upload progress
			xhr.upload.onprogress = p => {
			  console.log( Math.round((p.loaded / p.total) * 100) + '%') ;
			}
			```
		- Số lượng tùy chọn nhiều và có một vài sự mâu thuẫn giữa các trình duyệt. Vì lý do này, hầu hết các thư viện và framework cung cấp các hàm bao bọc Ajax để xử lý sự phức tạp. Ví dụ phương thức `jQuery.ajax()`
			```js
			// jQuery Ajax
			$.ajax('http://domain/service')
			  .done(data => console.log(data))
			  .fail((xhr, status) => console.log('error:', status));
			```
	- ## Fletch
		- Fetch API là một thay thế hiện đại cho XMLHttpRequest. Các interface về `Headers`, `Request`, `Response` được cung cấp một cách nhất quán, `Promises` cho phép xâu chuỗi một cách dễ dàng hơn và `async/await` không có `callback`. Ví dụ XHR ở trên có thể được chuyển đổi thành `Fetch-based` code đơn giản hơn nhiều.
			```js
			fetch("https://api.example.com/data")
			    .then(response => {
			        if (!response.ok) {
			            throw new Error("Network response was not ok");
			        }
			        return response.json();
			    })
			    .then(data => {
			        console.log(data); // Dữ liệu đã được chuyển đổi thành JSON
			    })
			    .catch(error => {
			        console.error("Fetch error:", error);
			    });
			```
		- Trong ví dụ trên:
			1. Chúng ta sử dụng `fetch` để tạo yêu cầu GET đến URL `"https://api.example.com/data"`.
			2. Chúng ta sử dụng `.then()` để xử lý phản hồi. Trong trường hợp này, chúng ta kiểm tra xem phản hồi có trạng thái `ok` hay không. Nếu không, chúng ta ném một lỗi.
			3. Nếu phản hồi có trạng thái `ok`, chúng ta sử dụng `.json()` để chuyển đổi dữ liệu JSON của phản hồi thành đối tượng JavaScript.
			4. Cuối cùng, chúng ta sử dụng `.catch()` để xử lý bất kỳ lỗi nào trong quá trình yêu cầu hoặc xử lý phản hồi.
	- ## XMLHttpRequest hay Fetch API?
		- `XMLHttpRequest` và `Fetch API` đều là cách để tương tác với các nguồn dữ liệu từ máy chủ hoặc API trên web. Tuy nhiên, `Fetch API` thường được ưa chuộng hơn trong các ứng dụng hiện đại do cú pháp dễ đọc hơn và khả năng xử lý Promise tích hợp
		- Dưới đây là một số so sánh giữa `XMLHttpRequest` và `Fetch API`:

			1. **Cú pháp:**
			- `XMLHttpRequest`: Cú pháp của `XMLHttpRequest` phức tạp hơn và thường cần nhiều bước để tạo và thực hiện yêu cầu.
			- `Fetch API`: Cú pháp của `Fetch API` dễ đọc và sử dụng. Nó sử dụng cú pháp chuỗi hơn để xây dựng yêu cầu.

			2. **Promise tích hợp:**
			- `XMLHttpRequest`: Không tích hợp trực tiếp Promise, dẫn đến việc phải sử dụng callback để xử lý phản hồi.
			- `Fetch API`: Tích hợp Promise, giúp quản lý dễ dàng việc xử lý thành công và thất bại.

			3. **Xử lý JSON:**
			- `XMLHttpRequest`: Cần phải thực hiện việc chuyển đổi JSON bằng cách sử dụng `JSON.parse`.
			- `Fetch API`: Có thể trực tiếp gọi phương thức `.json()` để chuyển đổi dữ liệu JSON.

			4. **Xử lý CORS (Cross-Origin Resource Sharing):**
			- `XMLHttpRequest` và `Fetch API` đều có thể xử lý CORS, nhưng `Fetch API` cung cấp cách linh hoạt hơn trong việc xử lý CORS.