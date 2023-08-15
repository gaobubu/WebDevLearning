# Khái niệm
- HTML là viết tắt của **HyperText Markup Language**
- Để đánh dấu, định dạng nội dung, xác định cấu trúc của trang
- Xác định các phần tử như tiêu đề nội dung chính, hình ảnh, chân trang
	- các thẻ thường gặp: `<html>`, `<head>`, `<body>`

# CLass, ID, DOM, Attribute
## Khai niệm
- ### Class
	- Xác định nhóm phần tử chung đặc điểm
	- Sử dụng cho nhiều phần tử 
		```html
		<body>
		<style>
		.highlight { 
			background-color: yellow; 
			font-weight: bold; 
			}
		</style>
		<p class="highlight">This is an important paragraph.</p>
		<p class="highlight">Another important paragraph.</p>
		</body>
		```
- ### ID
	- Xác định duy nhất cho 1 phần tử cụ thể
	- Mỗi phần tử chỉ có 1 ID duy nhất
	- Sử dụng ID thường dùng để chọn và thao tác với một phần tử cụ thể trong CSS hoặc JavaScript
		```html
		<body>
		<style>
		#special-box {
		  background-color: lightblue;
		  border: 1px solid darkblue;
		  padding: 10px;
		}
		</style>
			<div id="special-box">This is a special box.</div>
		</body>
		```
- ### DOM
	- **DOM (Document Object Model):**  là một cách để biểu diễn cấu trúc của một trang web hoặc tài liệu XML dưới dạng một cây đối tượng
	- Cho phép javascript tương tác và thay đổi cấu trúc, nội dung, tạo các tương tác animation mà ko cần load trang
		- VD: cho đoạn mã html sau
		```html
		<!DOCTYPE html>
		<html>
		<head>
		  <title>DOM Example</title>
		</head>
		<body>
		  <h1>Hello, DOM!</h1>
		  <p>This is an example of using the DOM.</p>
		</body>
		</html>
		```
		- DOM sẽ tạo một cây đối tượng sau
		```
		- Document (root node)
		 - html
			- head
			 - title
			 - Text node: "DOM Example"
			- body
			 - h1
			 - Text node: "Hello, DOM!"
			 - p
			 - Text node: "This is an example of using the DOM."
		```
		- JavaScript có thể được sử dụng để truy cập và thay đổi các phần tử trong cây DOM. VD thay đổi thẻ `<h1>`
		```js
		let headingElement = document.querySelector("h1");
		headingElement.textContent = "Hello, Updated DOM!";
		```
		
- ### Attribute(thuộc tính)
	- Thông tin bổ sung được đặt trong các thẻ HTML để xác định các đặc tính hoặc thông tin liên quan đến phần tử đó
	- VD trong thẻ `<img>`
		```html
		<img src="image.jpg" alt="A beautiful image" width="300" height="200">
		```
		- **src:** Xác định nguồn (URL) của hình ảnh.
		- **alt:** Cung cấp văn bản thay thế cho hình ảnh (hiển thị khi hình ảnh không thể tải hoặc cho người dùng không thể xem hình ảnh).
		- **width:** Xác định chiều rộng của hình ảnh.
		- **height:** Xác định chiều cao của hình ảnh.

# Thẻ cơ bản trong HTML
- ## Các loại thẻ cơ bản
	```html
	<!DOCTYPE>      <!--xác định phiên bản html-->
	<html></html>   <!--bắt đầu tài liệu-->
	<head></head>   <!--chứa tiêu đề tập tin css-->
	<title></title> <!--tiêu đề-->
	<body></body>   <!--nội dung chính-->
	<div></div>     <!--khối phần tử-->
	```
	- ### Văn bản
		```html
		<h1><h6><!--làm tiêu đề-->
		<p> <!--tạo văn bản-->
		<span><!--nhóm các phần tử văn bản để áp dụng css-->
		<strong>  <!--chữ đậm-->
		<em> <!--chữ nghiêng-->
		```
	- ### Danh sách
		```html
		<ul>  <!-- unordered list -->
		<ol> <!-- ordered list -->
		<li> <!-- list item -->
		```
	- ### Liên kết
		```html
		<a href="địa chỉ URL liên kết"> 
		<!-- liên kết web ở tài liệu khác -->
		```
	- ### Hình ảnh
		```html
		<img src="đường dẫn vào ảnh">
		<!-- hiển thị hình ảnh -->
		```
	- ### Định dạng
		```html
		<br>
		<!-- xuống dòng  -->
		<hr>
		<!-- kẻ ngang chia văn bản -->
		```
	- ### Biểu mẫu
		```html
		<form><!-- tạo biểu mẫu login, signup -->
		<input><textarea><select><!-- thu thập dữ liệu -->
		```
	- ### Bảng
		```html
		<table><!--bảng-->
		<th><!-- table header -->
		<tr><!-- hàng -->
		<td><!-- ô -->
		```
	- ### Phương tiện
		```html
		<video src="">
		<!-- nhúng video -->
		<audio src="">
		<!-- nhúng âm thanh -->
		```
- ## Các attribure(thuộc tính) đi kèm với các thẻ trong HTML
	1. **`<a>` (liên kết):**
		- `href`: Đường dẫn đến tài liệu hoặc trang web liên kết.
		- `target`: Xác định cách mở liên kết (ví dụ: `_blank` để mở trong cửa sổ mới).
		- `title`: Tiêu đề mô tả hoặc thông tin gợi ý khi di chuột qua liên kết.
	1. ** `<img>` (hình ảnh):**
		- `src`: Đường dẫn tới hình ảnh.
		 - `alt`: Văn bản mô tả thay thế khi hình ảnh không thể tải.
		 - `width` và `height`: Kích thước của hình ảnh.
	1. **`<input>` (ô nhập liệu):**
		- `type`: Xác định loại dữ liệu (ví dụ: `text`, `password`, `email`, `checkbox`, `radio`, v.v.).
		 - `name`: Tên trường dữ liệu để gửi đi khi form được gửi.
		- `id`: Định danh duy nhất cho ô nhập liệu để kết nối với các thẻ `<label>` hoặc sử dụng trong JavaScript.
		 - `value`: Giá trị mặc định của ô nhập liệu.
	2. **`<button>` (nút bấm):**
		- `type`: Xác định loại nút (ví dụ: `submit`, `reset`, `button`).
		 - `onclick`: Xử lý sự kiện click bằng JavaScript.
	3. **`<textarea>` (ô nhập liệu đa dòng):**
		- `name`: Tên trường dữ liệu để gửi đi khi form được gửi.
		- `id`: Định danh duy nhất để kết nối với các thẻ `<label>` hoặc sử dụng trong JavaScript.
		   - `rows` và `cols`: Số hàng và cột hiển thị.
	4. **`<select>` (danh sách rớt): **
		 - `name`: Tên trường dữ liệu để gửi đi khi form được gửi.
		 - `id`: Định danh duy nhất để kết nối với các thẻ `<label>` hoặc sử dụng trong JavaScript.
	5. **`<form>` (biểu mẫu): **
		 - `action`: Đường dẫn xử lý dữ liệu form trên máy chủ.
		- `method`: Phương thức gửi dữ liệu (ví dụ: `get`, `post`).
		- `name`: Tên của form.
	6. **`<label>` (nhãn):**
		 - `for`: Liên kết với trường nhập liệu bằng cách sử dụng `id`.
	7. **`<table>` (bảng)**
		- `border`: Độ rộng đường viền bảng.
		 - `width`: Độ rộng bảng.
	8. **`<meta>` (thẻ meta):**
		 - `charset`: Định rõ bảng mã ký tự sử dụng cho trang web.
		- `name` và `content`: Để cung cấp các thông tin khác nhau như mô tả, từ khóa, tác giả, v.v.
# Heading, paragraph
## Khái niệm
- Tiêu đề **(heading)** và đoạn văn bản **(paragraph)** là hai loại phần tử cơ bản trong HTML được sử dụng để tổ chức và hiển thị nội dung trên trang web. 
- #### Heading(tiêu đề)
	- **Mục đích:** Các thẻ heading được sử dụng để định dạng và hiển thị các tiêu đề hoặc phần tiêu đề của nội dung trang web. Chúng giúp tạo ra cấu trúc nội dung, chỉ dẫn người đọc về chủ đề chính và phân loại các phần khác nhau.
	- **Cấp độ tiêu đề:** Có 6 cấp độ tiêu đề từ `<h1>` đến `<h6>`, trong đó `<h1>` là tiêu đề lớn nhất và `<h6>` là tiêu đề nhỏ nhất. Thường chỉ nên có một thẻ `<h1>` duy nhất trong mỗi trang để xác định chủ đề chính.
		```html
		<h1>Tiêu đề chính</h1>
		<h2>Phần tiêu đề con</h2>
		<h3>Phần tiêu đề nhỏ hơn</h3>
		```
- #### Paragraph (Đoạn văn bản)
	- **Mục đích:** Thẻ `<p>` được sử dụng để tạo và hiển thị đoạn văn bản thông thường. Chúng thường chứa nội dung mô tả, thông tin chi tiết và các đoạn văn bản liên quan đến chủ đề chính.
	- **Cấu trúc nội dung:** Thẻ `<p>` không tạo ra cấu trúc nội dung như heading. Chúng chỉ tạo ra các đoạn văn bản thông thường mà không phân loại nội dung thành các mức độ ưu tiên như heading
		```html
		<p>Đây là một ví dụ về cách sử dụng thẻ &lt;p&gt; để tạo đoạn văn bản trong HTML.</p>
		<p>Mỗi thẻ &lt;p&gt; sẽ tạo một đoạn văn bản riêng biệt.</p>
		```

# From, Table
- ## Xử lý form submit
	- Thực hiện bằng cách sử dụng thuộc tính `action` của thẻ `<form>` để xác định URL hoặc tệp xử lý dữ liệu form trên máy chủ. Khi người dùng nhấn nút Submit trong form, dữ liệu trong form sẽ được gửi đến URL hoặc tệp xử lý được chỉ định trong thuộc tính `action`.
	- VD cơ bản về cách xử lý form submit
		```html
		<!DOCTYPE html>
		<html>
		<head>
		    <title>Form Submit Example</title>
		</head>
		<body>
		    <form method="post" action="process_form.php">
		        <label for="name">Name:</label>
		        <input type="text" name="name" id="name">
		        <br>
		        <label for="email">Email:</label>
		        <input type="email" name="email" id="email">
		        <br>
		        <input type="submit" value="Submit">
		    </form>
		</body>
		</html>
		```
	- Trong ví dụ trên:
		- `method="post"` xác định phương thức gửi dữ liệu, có thể là "post" hoặc "get".
		- `action="process_form.php"` xác định tệp PHP (hoặc URL) mà dữ liệu form sẽ được gửi đến để xử lý.
		- Khi người dùng nhấn nút Submit, trình duyệt sẽ gửi dữ liệu trong form đến tệp `process_form.php` để xử lý. Trong tệp này, bạn có thể sử dụng các biến như `$_POST["name"]` và `$_POST["email"]` để truy cập dữ liệu được gửi từ form.
	- Hoặc VD trong tệp PHP
		```php
		<?php
		if ($_SERVER["REQUEST_METHOD"] == "POST") {
		    $name = $_POST["name"];
		    $email = $_POST["email"];
		
		    // Xử lý dữ liệu ở đây (lưu vào cơ sở dữ liệu, gửi email, v.v.)
		    // ...
		
		    // Chuyển hướng hoặc hiển thị thông báo thành công
		    header("Location: success_page.html");
		    exit;
		}
		?>
		```
		- Trong ví dụ này, sau khi xử lý dữ liệu, chúng ta sử dụng hàm `header()` để chuyển hướng trình duyệt sang trang `success_page.html` để thông báo cho người dùng rằng dữ liệu đã được gửi thành công.
- ## Xử lý form handle error
	- Xử lý lỗi trong form thường liên quan đến việc kiểm tra dữ liệu người dùng nhập vào để đảm bảo rằng nó hợp lệ và đáp ứng các yêu cầu
		```html
		<!DOCTYPE html>
		<html>
		<head>
		    <title>Form with Error Handling</title>
		    <script src="script.js"></script>
		</head>
		<body>
		    <form id="myForm">
		        <label for="name">Name:</label>
		        <input type="text" name="name" id="name">
		        <br>
		        <label for="email">Email:</label>
		        <input type="email" name="email" id="email">
		        <br>
		        <input type="submit" value="Submit">
		    </form>
		    <div id="errorMessages" style="color: red;"></div>
		</body>
		</html>
		```
		- Chúng ta sẽ tạo một **form** đơn giản để nhập thông tin **tên** và **email** của người dùng. Chúng ta sẽ sử dụng **JavaScript** để kiểm tra dữ liệu ngay khi người dùng nhấn nút **Submit** và hiển thị thông báo lỗi nếu cần.
		```js
		document.getElementById("myForm").addEventListener("submit", function(event) {
		    var name = document.getElementById("name").value;
		    var email = document.getElementById("email").value;
		    var errorMessage = "";
		
		    if (name === "") {
		        errorMessage += "Name is required. ";
		    }
		
		    if (email === "") {
		        errorMessage += "Email is required. ";
		    } else if (!isValidEmail(email)) {
		        errorMessage += "Email is invalid. ";
		    }
		
		    if (errorMessage !== "") {
		        event.preventDefault(); // Ngăn chặn việc submit nếu có lỗi
		        document.getElementById("errorMessages").textContent = errorMessage;
		    }
		});
		
		function isValidEmail(email) {
		    // Đây chỉ là một hàm đơn giản kiểm tra định dạng email, bạn cần hàm phức tạp hơn trong thực tế
		    var emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
		    return emailPattern.test(email);
		}
		```
		- Chúng ta đã sử dụng **JavaScript** để ngăn việc **submit** form nếu có lỗi. Khi người dùng nhấn nút **Submit**, chúng ta kiểm tra dữ liệu nhập vào và hiển thị thông báo lỗi nếu cần. Hàm `isValidEmail` kiểm tra xem email có đúng định dạng không.
- ## FormData
	- ### khái niệm
		- Là một đối tượng trong HTML và JavaScript, được sử dụng để tạo và quản lý dữ liệu của một form HTML để có thể gửi dữ liệu đó đến máy chủ thông qua một yêu cầu HTTP, thường là một yêu cầu POST
		- Thu thập dữ liệu từ các trường `input` trong form **(như input text, checkbox, radio, file, v.v.)** và tạo một dạng dữ liệu có thể gửi đi thông qua AJAX hoặc Fetch API một cách dễ dàng
	- ### cách sử dụng cơ bản 
		- ##### HTML form
			- Trước hết, bạn cần có một form trong HTML để người dùng nhập thông tin.
			```html
			<!DOCTYPE html>
			<html>
			<head>
			    <title>Basic FormData Example</title>
			</head>
			<body>
			    <form id="myForm">
			        <label for="name">Name:</label>
			        <input type="text" name="name" id="name">
			        <br>
			        <label for="email">Email:</label>
			        <input type="email" name="email" id="email">
			        <br>
			        <input type="submit" value="Submit">
			    </form>
			
			    <script src="script.js"></script>
			</body>
			</html>
			```
		- ##### Javascript(script.js)
			- Bạn cần viết mã JavaScript để xử lý form và gửi dữ liệu bằng `FormData`
			```js
			document.getElementById("myForm").addEventListener("submit", function(event) {
			    event.preventDefault(); // Ngăn chặn việc submit mặc định của form
			
			    var formData = new FormData(this); // Tạo đối tượng FormData từ form
			
			    // Gửi dữ liệu formData đến máy chủ bằng cách sử dụng AJAX hoặc Fetch API
			    fetch("process_form.php", {
			        method: "POST",
			        body: formData
			    })
			    .then(response => response.text())
			    .then(result => {
			        console.log(result); // Xử lý kết quả từ máy chủ
			    })
			    .catch(error => {
			        console.error(error);
			    });
			});
			```
		- ##### Xử lý máy chủ(process_form.php)
			- Trên máy chủ, bạn có thể sử dụng `$_POST` để truy cập dữ liệu được gửi từ form
			```php
			<?php
			if ($_SERVER["REQUEST_METHOD"] == "POST") {
			    $name = $_POST["name"];
			    $email = $_POST["email"];
			
			    // Xử lý dữ liệu ở đây (lưu vào cơ sở dữ liệu, gửi email, v.v.)
			    // ...
			
			    echo "Data received and processed successfully.";
			}
			?>
			```
		- Trong ví dụ này, khi người dùng nhấn nút **Submit**, sự kiện submit form được bắt và mã JavaScript tạo một đối tượng `FormData` từ form. Sau đó, dữ liệu này được gửi đến máy chủ bằng Fetch API. Phía máy chủ sử dụng `$_POST` để truy cập dữ liệu và xử lý nó.
# Xữ lý data table (Hiển thị dữ liệu), phân trang
- Xử lý dữ liệu trong một data table trong HTML bao gồm việc **thêm, sửa, xóa và tìm kiếm dữ liệu**. Thường thì việc xử lý dữ liệu này sẽ sử dụng JavaScript để tạo tương tác trực tiếp trên trang web.
- ## Cách sử lý cơ bản bằng javascript
	- ##### HTML Table
		```html
		<!DOCTYPE html>
		<html>
		<head>
		    <title>Basic Data Table Handling Example</title>
		    <script src="script.js"></script>
		</head>
		<body>
		    <table id="dataTable">
		        <thead>
		            <tr>
		                <th>Name</th>
		                <th>Email</th>
		                <th>Action</th>
		            </tr>
		        </thead>
		        <tbody>
		            <!-- Dữ liệu sẽ được thêm bằng JavaScript -->
		        </tbody>
		    </table>
		    <button id="addRow">Add Row</button>
		</body>
		</html>
		```
	- ##### Javascript(script.js)
		- Bạn cần viết mã JavaScript để xử lý việc thêm và xóa dữ liệu từ bảng
			```js
			document.getElementById("addRow").addEventListener("click", function() {
				var table = document.getElementById("dataTable").getElementsByTagName('tbody')[0];
				var newRow = table.insertRow(table.rows.length);
					
				var nameCell = newRow.insertCell(0);
				var emailCell = newRow.insertCell(1);
				var actionCell = newRow.insertCell(2);
					
				nameCell.innerHTML = "New Name";
				emailCell.innerHTML = "new@example.com";
				actionCell.innerHTML = '<button
				onclick="deleteRow(this)">Delete</button>';
					});
					
					function deleteRow(button) {
					    var row = button.parentNode.parentNode;
					    row.parentNode.removeChild(row);
					}
			```
		- Khi bạn mở trang HTML và nhấn vào nút "Add Row", một dòng mới sẽ được thêm vào bảng với tùy chọn xóa dòng. Khi bạn nhấn vào nút "Delete" trong dòng, dòng đó sẽ bị xóa khỏi bảng.
		- Chúng ta đã sử dụng JavaScript để thêm và xóa dữ liệu từ bảng. Hàm `insertRow` và `insertCell` được sử dụng để thêm dòng và ô dữ liệu vào bảng. Hàm `deleteRow` được sử dụng để xóa dòng dựa trên nút xóa trong cùng một dòng.
	
- ## Phân trang
	- Phân trang trong form và table thường áp dụng khi bạn có một lượng lớn dữ liệu cần hiển thị hoặc quản lý, và bạn muốn chia thành các trang nhỏ để giúp người dùng dễ dàng điều hướng và tìm kiếm thông tin
	- Cách thực hiện phân trang trong bảng và form bằng javascript
		- ##### HTML Table và form
			 Bắt đầu bằng việc tạo một bảng và một form trong HTML để hiển thị dữ liệu và phân trang
		```html
		<!DOCTYPE html>
		<html>
		<head>
		    <title>Pagination Example</title>
		    <script src="script.js"></script>
		</head>
		<body>
		    <form id="paginationForm">
		        <label for="perPage">Items per Page:</label>
		        <select id="perPage">
		            <option value="2">2</option>
		            <option value="5">5</option>
		            <option value="10">10</option>
		        </select>
		        <button type="button" id="prevPage">Previous</button>
		        <button type="button" id="nextPage">Next</button>
		    </form>
		    <table id="dataTable">
		        <thead>
		            <tr>
		                <th>Name</th>
		                <th>Email</th>
		            </tr>
		        </thead>
		        <tbody>
		            <!-- Dữ liệu sẽ được thêm bằng JavaScript -->
		        </tbody>
		    </table>
		</body>
		</html>
		```
	- ##### Javascript (script.js)
		- Sau đó, bạn cần viết mã JavaScript để thực hiện phân trang bằng việc thêm và xóa dữ liệu từ bảng
			```js
			var data = [
				{ name: "John Doe", email: "john@example.com" },
				{ name: "Jane Smith", email: "jane@example.com" },
					    // Các dòng dữ liệu khác
			];
					
				var itemsPerPage = 2; // Số mục hiển thị trên mỗi trang
				var currentPage = 0;
					
				function displayData(page) {
					var table= document.getElementById("dataTable").getElementsByTagName('tbody')[0];
					table.innerHTML = ""; // Xóa dữ liệu cũ
					
					var startIndex = page * itemsPerPage;
					var endIndex = startIndex + itemsPerPage;
						for (var i = startIndex; i < endIndex && i < data.length; i++) {
						    var row = table.insertRow(table.rows.length);
						    var nameCell = row.insertCell(0);
						    var emailCell = row.insertCell(1);
					
						    nameCell.innerHTML = data[i].name;
						    emailCell.innerHTML = data[i].email;
					}
				}
					
					displayData(currentPage); // Hiển thị trang đầu tiên
					
					document.getElementById("prevPage").addEventListener("click", function() {
					    if (currentPage > 0) {
					        currentPage--;
					        displayData(currentPage);
					    }
					});
					
					document.getElementById("nextPage").addEventListener("click", function() {
					    var maxPage = Math.ceil(data.length / itemsPerPage) - 1;
					    if (currentPage < maxPage) {
					        currentPage++;
					        displayData(currentPage);
					    }
					});
					
					document.getElementById("perPage").addEventListener("change", function() {
					    itemsPerPage = parseInt(this.value);
					    displayData(currentPage);
					});
			```
		- Khi bạn mở trang HTML, bạn sẽ thấy dữ liệu trong bảng được phân trang. Bạn có thể điều hướng giữa các trang bằng nút **"Previous"** và **"Next"**, và bạn cũng có thể chọn số lượng mục hiển thị trên mỗi trang bằng cách chọn từ danh sách thả xuống.
		- Chúng ta đã sử dụng JavaScript để thực hiện phân trang cho dữ liệu trong bảng. Dữ liệu được lưu trong mảng `data`. Các sự kiện nhấn nút và thay đổi lựa chọn được sử dụng để thay đổi số lượng mục hiển thị trên mỗi trang và điều hướng giữa các trang.
	
# Inline và Block
- Trong HTML, các phần tử cũng có thể được phân loại thành "inline" và "block" dựa trên cách chúng hiển thị trên trang web. Dưới đây là sự phân biệt giữa các phần tử "inline" và "block" trong HTML
	- ### Inline Elements (Phần tử inline)
		- **Khái niệm:** Các phần tử "inline" là những phần tử mà chúng hiển thị cùng một dòng với các phần tử khác, mà không làm ngắt dòng. Chúng chỉ chiếm một phần không gian cần thiết để chứa nội dung bên trong.    
		- **Ví dụ:** Các phần tử inline thường là các phần tử văn bản như `<span>`, `<a>`, `<strong>`, `<em>`, `<img>`, và nhiều phần tử văn bản khác.
		 - **Đặc điểm:**
		    - Không tạo một khung chứa riêng biệt, nếu có nhiều phần tử inline liên tiếp, chúng sẽ hiển thị trên cùng một dòng.
		    - Không thể đặt chiều rộng và chiều cao cho phần tử inline.
		    - Không thể thêm margin trên và dưới, nhưng có thể thêm margin bên trái và bên phải.
		    - Không thể đặt các thuộc tính `width` và `height`.

	- ### Block Elements (Phần tử block)
		- **Khái niệm:** Các phần tử "block" là những phần tử mà chúng hiển thị trên một dòng riêng biệt và tạo một khung chứa mới. Chúng làm ngắt dòng và chiếm toàn bộ chiều rộng của khung chứa mà chúng nằm trong.
		- **Ví dụ:** Các phần tử block thường là các phần tử cấu trúc như `<div>`, `<p>`, `<h1>`-`<h6>`, `<ul>`, `<li>`, và nhiều phần tử cấu trúc khác.
		- **Đặc điểm:**
			- Tạo một khung chứa mới và hiển thị trên một dòng riêng biệt.
			- Chiếm toàn bộ chiều rộng của khung chứa mà chúng nằm trong.
			- Có thể đặt chiều rộng và chiều cao cho phần tử block.
			- Có thể thêm padding, margin, và border theo cả hai hướng dọc và ngang

