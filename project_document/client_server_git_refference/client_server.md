# Clientside và Serverside
- ## Khái niệm và cách sử dụng
	- ### Client-side (phía máy khách)
		- Là phần của ứng dụng web chạy trực tiếp trên máy của người dùng (trình duyệt web).
		- Chứa mã nguồn và tài nguyên (hình ảnh, styles, scripts) được tải về và thực thi trên máy khách.
		- Tương tác trực tiếp với người dùng, thường xuyên cập nhật giao diện người dùng và phản hồi nhanh chóng.
		- Sử dụng các ngôn ngữ như HTML, CSS, JavaScript để xây dựng giao diện tương tác và thực hiện các hoạt động trực tiếp trên máy khách.
		- #### cách hoạt động
			- trong phát triển ứng dụng web **cilent-side** đóng vai trò quan trọng trong việc hiển thị giao diện người dùng, tương tác  và xử lý hoạt động người dùng trực tiếp trong trình duyệt
			- **các bước hoạt động cơ bản của clientside**
				1. **tải trang web**
				- Khi người dùng truy cập vào một URL, trình duyệt sẽ tải các tệp HTML, CSS và JavaScript từ máy chủ và hiển thị trang web
				2. **Hiển thị giao diện:**
				- Trình duyệt sẽ dựa vào mã HTML và CSS để hiển thị giao diện người dùng trên màn hình. Mã HTML xác định cấu trúc và nội dung trang, trong khi CSS định dạng và thiết kế giao diện.
				3. **Tương tác người dùng:**
				- Khi người dùng tương tác với trang web (như nhấp chuột, nhập liệu), sự kiện sẽ được kích hoạt. JavaScript sẽ được sử dụng để xử lý sự kiện và thực hiện hành động tương ứng.
				4. **Xử lý bên trong trình duyệt:**
				- JavaScript thường được thực thi bên trong trình duyệt của người dùng. Trình duyệt có một môi trường thực thi JavaScript, cung cấp các API để tương tác với giao diện người dùng và trình duyệt.
				5. **Tương tác với máy chủ:**
				- Nếu cần, JavaScript có thể sử dụng các yêu cầu HTTP (GET, POST, PUT, DELETE) để giao tiếp với máy chủ thông qua các API. Trình duyệt sẽ gửi yêu cầu và nhận phản hồi từ máy chủ, nhưng tất cả diễn ra trong nền tảng trình duyệt.
				6. **Cập nhật nội dung:**
				- JavaScript có khả năng cập nhật nội dung trang mà không cần tải lại trang hoàn toàn. Điều này giúp tạo ra trải nghiệm tương tác mượt mà và đáp ứng nhanh chóng cho người dùng.
				7. **Quản lý trạng thái:**
				- Thư viện và framework JavaScript như React, Angular và VueJS giúp quản lý trạng thái ứng dụng một cách hiệu quả hơn. Trạng thái là các dữ liệu được lưu trữ và cập nhật mà ứng dụng cần để hoạt động.
	- ### Server-side (phía máy chủ)
		- Là phần của ứng dụng web chạy trên máy chủ, nơi lưu trữ, xử lý và quản lý dữ liệu.
		- Xử lý các yêu cầu từ máy khách, tạo và cung cấp dữ liệu, thực hiện logic kinh doanh và tương tác với cơ sở dữ liệu.
		- Chịu trách nhiệm về bảo mật, kiểm tra dữ liệu và đảm bảo tính nhất quán của hệ thống.
		- Sử dụng các ngôn ngữ như Python, Ruby, Java, PHP để xây dựng logic ứng dụng, kết nối với cơ sở dữ liệu và cung cấp dịch vụ cho máy khách.
		- #### cách hoạt động
			- trong phát triển ứng dụng web **server-side** đóng vai trò quan trọng trong việc xử lý logic kinh doanh, quản lý dữ liệu và cung cấp dữ liệu cho phía máy khách. 
			- **các bước hoạt động cơ bản của server-side**
			1. **Nhận yêu cầu từ máy khách:**
			- Khi người dùng tương tác với ứng dụng web bằng cách nhấp chuột, gửi biểu mẫu hoặc thực hiện các hoạt động khác, trình duyệt sẽ gửi yêu cầu HTTP tới máy chủ.
			2. **Xử lý yêu cầu:**
			- Máy chủ nhận yêu cầu và xử lý nó theo các logic và quy tắc kinh doanh đã được định nghĩa trước. Điều này có thể bao gồm truy vấn cơ sở dữ liệu, tính toán, kiểm tra xác thực người dùng và thực hiện các hoạt động khác.
			3. **Truy vấn dữ liệu:**
			- Nếu cần, máy chủ sẽ truy vấn cơ sở dữ liệu để lấy thông tin cần thiết. Dữ liệu này có thể là thông tin người dùng, dữ liệu sản phẩm, thông tin đơn hàng và nhiều loại dữ liệu khác.
			4. **Xử lý logic kinh doanh:**
			- Máy chủ thực hiện các phép tính, so sánh, kiểm tra hợp lệ và xử lý logic kinh doanh theo yêu cầu từ người dùng. Ví dụ, tính toán giá sản phẩm, tính tổng đơn hàng, áp dụng chiết khấu, v.v.
			5. **Tạo và trả về phản hồi:**
			- Sau khi xử lý yêu cầu và thu thập dữ liệu cần thiết, máy chủ tạo ra một phản hồi HTTP. Phản hồi này chứa thông tin, dữ liệu hoặc trạng thái mà máy khách cần để hiển thị cho người dùng.
			6. **Gửi phản hồi tới máy khách:**
			- Máy chủ gửi phản hồi tới trình duyệt của người dùng thông qua giao thức HTTP. Phản hồi này có thể chứa HTML, JSON, XML hoặc các loại dữ liệu khác tùy thuộc vào yêu cầu và kiểu dữ liệu mong muốn.
			7. **Hiển thị dữ liệu cho người dùng:**
			- Trình duyệt nhận phản hồi từ máy chủ và hiển thị dữ liệu hoặc trạng thái mới trên giao diện người dùng. Điều này có thể là hiển thị trang mới, cập nhật dữ liệu trên trang hiện tại hoặc thực hiện các thay đổi khác.
- ***client-side và server-side** đều cần hoạt động cùng nhau để tạo ra một trải nghiệm hoàn chỉnh cho người dùng. Client-side xử lý giao diện người dùng và tương tác người dùng, trong khi server-side quản lý logic kinh doanh, dữ liệu và bảo mật.*
- ## Phân biệt giữa Client-side và Server-side
| | Client-side      | Server-side      |
| ------------|------------|------------|
|Mục đích chính| Đảm nhiệm hiển thị giao diện người dùng và tương tác trực tiếp với người dùng. | Xử lý logic kinh doanh, quản lý dữ liệu và cung cấp dữ liệu cho máy khách. |
|Ngôn ngữ| HTML, CSS, JS | PHP, RUBY, PYTHON |
|xử lý| Tự xử lý trên trình duyệt của người dùng | Xử lý trên máy chủ, thực hiện các tác vụ phức tạp như truy vấn cơ sở dữ liệu, tính toán logic kinh doanh. |
|Tính tương tác| Thực hiện tương tác nhanh, không cần tải lại trang, tạo hiệu ứng động và cảm giác phản hồi ngay lập tức. | Cần tải lại trang hoặc thực hiện yêu cầu mới từ người dùng để cập nhật dữ liệu. | 
|Trạng thái| Thường không lưu trạng thái lâu dài, sử dụng trạng thái tạm thời để hiển thị thông tin cho người dùng. | Lưu trữ trạng thái lâu dài, quản lý dữ liệu và trạng thái ứng dụng một cách an toàn. | 
|Bảo mật| Dữ liệu và logic thực thi trên máy khách có thể dễ dàng truy cập và xem bởi người dùng. | Dữ liệu và logic thực thi trên máy chủ được bảo mật hơn, không thể truy cập trực tiếp bởi người dùng. | 
|sự cần thiết của máy chủ| Thường yêu cầu kết nối máy chủ để lấy dữ liệu hoặc thực hiện hành động cần thông qua API. | Cung cấp dữ liệu hoặc trang được tạo sẵn để máy khách hiển thị. | 
