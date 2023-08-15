# HTTP Request
- ## khái niệm
	- HTTP (*Hypertext Transfer Protocol*) request là một khái niệm trong lĩnh vực của mạng và web development
	- Cách mà các máy tính và các thành phần trong mạng giao tiếp với nhau để trao đổi thông tin, đặc biệt là trong việc truyền tải dữ liệu **máy chủ (server)** và **máy khách (client)**
	- Một HTTP request là một yêu cầu được gửi từ máy khách đến máy chủ thông qua một giao thức HTTP. Mỗi request bảo gồm các phần quan trọng sau:
		1. **Method (Phương thức):** Đây là tên của hành động mà máy khách muốn thực hiện trên máy chủ. Các phương thức thông thường bao gồm GET, POST, PUT, DELETE, và nhiều phương thức khác.
		2. **URL (Uniform Resource Locator):** Đây là địa chỉ chỉ đến tài nguyên trên máy chủ mà máy khách muốn tương tác. URL bao gồm giao thức (ví dụ: http, https), tên miền, đường dẫn tới tài nguyên cụ thể trên máy chủ.
		3. **Headers (Tiêu đề):** Đây là các thông tin bổ sung mà máy khách gửi kèm với yêu cầu. Các thông tin này có thể bao gồm User-Agent (cho biết trình duyệt hoặc ứng dụng nào đang gửi yêu cầu), Accept (cho biết định dạng dữ liệu mà máy khách có thể xử lý), và nhiều thông tin khác.
		4. **Body (Nội dung):** Đây là phần dữ liệu chứa thông tin cụ thể mà máy khách muốn gửi đến máy chủ. Thường thì các phương thức như POST và PUT sẽ có body để gửi dữ liệu, trong khi các phương thức như GET thường không có body.
	- máy chủ nhận đc HTTP request, sau đó xử lý và trả về một HTTP response tương ứng. Response cũng bao gồm các phần tử tương tự như request như **status code (mã tâm trạng), header, body**
	- **ví dụ**: trình duyệt web yêu cầu hiển thị nội dung của một trang web cụ thể
		1. **method (phương thức)**: GET
		2. **URL(Uniform Resource Locator)**: [https://www.example.com/index.html](https://www.example.com/index.html)
		3. **headers (Tiêu đề):**
			- User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.124 Safari/537.36
			- Accept: text/html,application/xhtml+xml
		4. **body (nội dung)**: không có vì đây là một request loại GET
	- trong ví dự này, trình duyệt web **(máy khách)** gửi một HTTP request đến máy chủ có tên miền "[www.example.com](http://www.example.com/)"
		- **request** yêu cầu hiển thị nội dung của trang "index.html". Trình duyệt gửi thông tin về trình duyệt và định dang dữ liệu mà nó có thể xử lý thống qua các tiêu đề User-Agent và Accept.
		- sau khi máy chủ nhận được request này, nó sẽ xử lý yêu cầu bằng cách tìm và trả về nội dung của trang "index.html". sau đó, máy chủ sẽ tạo một HTTP response gồm status code **(vd: 200 OK)**, header và nội dung của trang "index.html", và gửi lại cho trình duyệt
## Các phương thức thường sử dụng (GET, POST, PUT,…)
- Các phương thức chính trong giao thức HTTP mà các ứng dụng web thường sử dụng
	1. **GET** *(yêu cầu hiển thị thông tin)* Phương thức này được sử dụng để yêu cầu dữ liệu từ máy chủ. Một yêu cầu GET thông thường không có body, và các tham số yêu cầu thường được truyền qua URL.
		- **Ví dụ: Trình duyệt web yêu cầu hiển thị nội dung của một bài viết trên blog.**
			- Method: GET
			- URL: [https://www.example.com/posts/123](https://www.example.com/posts/123)
			- Headers: (Không có thông tin quan trọng cần truyền trong headers)
			- Body: (Không có body trong yêu cầu GET)
	2. **POST** *(tạo mới dữ liệu)* Phương thức này thường được sử dụng để gửi dữ liệu từ **máy khách (client)** lên **máy chủ(server)**. Dữ liệu này thường được đặt trong body của request và không hiển thị trực tiếp trên URL. POST thường được sử dụng trong việc đăng nhập, tạo mới dữ liệu, cập nhật thông tin.
		- **Ví dụ: Ứng dụng gửi dữ liệu để tạo một bài viết mới trên blog.**
			- Method: POST
			- URL: [https://www.example.com/posts](https://www.example.com/posts)
			- Headers:
			    - Content-Type: application/json
			- Body:
				```json
				{
				  "title": "Bài viết mới",
				  "content": "Nội dung bài viết..."
				}
				```
	3. **PUT** *(cập nhật thông tin)* Phương thức này được sử dụng để gửi dữ liệu mới hoặc cập nhật dữ liệu đã tồn tại từ máy khách lên máy chủ. Tương tự như POST, dữ liệu được đặt trong body của request. PUT thường được sử dụng trong việc cập nhật thông tin chi tiết của một tài nguyên
		- **Ví dụ: Ứng dụng cập nhật thông tin của một bài viết đã tồn tại.**
			- Method: PUT
			- URL: [https://www.example.com/posts/123](https://www.example.com/posts/123)
			- Headers:
			    - Content-Type: application/json
			- Body:
				```json
				{
				  "title": "Bài viết đã cập nhật",
				  "content": "Nội dung bài viết đã thay đổi..."
				}
				```
	1. **DELETE** *(xóa dữ liệu)* Phương thức này được sử dụng để xóa tài nguyên được chỉ định trên máy chủ. Không có body trong request DELETE, thông tin cần thiết thường được truyền qua URL.
		- Ví dụ: Ứng dụng yêu cầu xóa một bài viết khỏi blog.
			- Method: DELETE
			- URL: [https://www.example.com/posts/123](https://www.example.com/posts/123)
			- Headers: (Không có thông tin quan trọng cần truyền trong headers)
			- Body: (Không có body trong yêu cầu DELETE)
	1. **PATCH** *(cập nhật một phần tài nguyên)* Phương thức này tương tự như PUT, nhưng thường được sử dụng để cập nhật một phần của tài nguyên, thay vì thay đổi toàn bộ tài nguyên.
		- **Ví dụ: Ứng dụng cập nhật một phần nội dung của một bài viết trên blog.**
			- Method: PATCH
			- URL: [https://www.example.com/posts/123](https://www.example.com/posts/123)
			- Headers:
			    - Content-Type: application/json
			- Body:
				```json
				{
				  "content": "Nội dung bài viết đã được cập nhật..."
				}
				```
	1. **OPTIONS** *(lấy thông tin về tùy chọn hỗ trợ từ máy chủ)* Phương thức này được sử dụng để yêu cầu thông tin về các phương thức mà máy chủ hỗ trợ cho một tài nguyên cụ thể. Điều này có thể giúp cho việc xác định các tùy chọn có sẵn cho việc giao tiếp với máy chủ.
		- Ví dụ: Trình duyệt web lấy thông tin về các phương thức hỗ trợ cho một tài nguyên cụ thể.
			- Method: OPTIONS
			- URL: [https://www.example.com/posts/123](https://www.example.com/posts/123)
			- Headers: (Không có thông tin quan trọng cần truyền trong headers)
			- Body: (Không có body trong yêu cầu OPTIONS
- GET, POST, PUT, DELETE được sử dụng nhiều hơn PATCH và OPTION, nhưng PATCH VÀ OPTION có vai trò quan trọng hơn trong việc cập nhật dữ liệu một cách linh hoạt và xác định các tìu chọn hỗ trợ từ máy chủ
- ### phân biệt giữa các phương thức
	- sự khác nhau chính giữa các phương thức HTTP nằm trong mục đích sử dụng, cách truyền dữ liệu và tính bảo mật và các phương thức này thực hiện các tác vụ khác nhau trên ứng dụng web, từ yêu cầu thông tin đến tạo mới , cập nhật và xóa/sửa dữ liệu. Cụ thể như sau
		1. **GET**
			- **Mục đích:** Yêu cầu dữ liệu từ máy chủ để hiển thị cho người dùng.
			- **Dữ liệu:** Thông thường không có dữ liệu gửi cùng yêu cầu (được truyền qua URL).
			- **Bảo mật:** Dữ liệu gửi qua URL có thể dễ dàng nhìn thấy trong lịch sử trình duyệt.
			- **Cạnh tranh:** Thích hợp cho việc yêu cầu dữ liệu, tải trang, không thay đổi dữ liệu trên máy chủ.
		2. **POST:**
			- **Mục đích:** Gửi dữ liệu mới lên máy chủ để tạo mới hoặc cập nhật dữ liệu.
			- **Dữ liệu:** Dữ liệu được gửi trong phần body của yêu cầu.
			- **Bảo mật:** Dữ liệu được gửi trong body, không hiển thị trực tiếp trên URL.
			- **Cạnh tranh:** Thích hợp cho việc tạo mới dữ liệu, cập nhật dữ liệu, gửi dữ liệu quan trọng.
		3. **PUT:**
			- **Mục đích:** Gửi dữ liệu mới hoặc cập nhật dữ liệu đã tồn tại trên máy chủ.
			- **Dữ liệu:** Dữ liệu được gửi trong phần body của yêu cầu.
			- **Bảo mật:** Dữ liệu được gửi trong body, không hiển thị trực tiếp trên URL.
			- **Cạnh tranh:** Thích hợp cho việc cập nhật dữ liệu, thay thế dữ liệu cũ bằng dữ liệu mới.
		4. **DELETE:**
			- **Mục đích:** Yêu cầu xóa dữ liệu cụ thể trên máy chủ.
			- **Dữ liệu:** Thông thường không có dữ liệu gửi cùng yêu cầu (được truyền qua URL).
			- **Bảo mật:** Dữ liệu gửi qua URL có thể dễ dàng nhìn thấy trong lịch sử trình duyệt.
			- **Cạnh tranh:** Thích hợp cho việc xóa dữ liệu không cần thiết, hủy bỏ dữ liệu.


