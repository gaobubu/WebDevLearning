# KHÁI NIỆM
- Là một bộ nguyên tắc viết commit message sinh ra với mục đinh để người đọc được và các công cụ máy tính có thể tim kiếm. Nó cung cấp một bộ quy tắc dễ dàng để tạo lịch sử commit
- Conventional commit áp dụng cho nhiều reponsitory, đặc biệt là các project open source khi có nhiều sự đóng góp contributors
# Cấu trúc Commit message
- Đây là cấu trúc chung của một commit message theo conventional
```
<type>[optional scope]: <description>

[optional body]

[optional footer]

```
- Trong đó 
	- `<type>` và `<descriptioon>` là bắt buộc cần có trong commit message
	- `<type>` : từ khóa để phân loại commit như feature, fixbug, refactor
	- Scope : dùng để xác đinh phạm vị của sự thay đổi. Thường thể hiện vùng hoặc thành phần của dự án mà commit liên quan đến. Ví dụ như:
		- `feat(user): add reset password functiionality`, "user" là scope. Thể hiện là commit liên quan đến sự thay đổi của phần "user", chẳng hạn như thêm chức năng đạt lại mật khẩu.
	- Description : là mô tả ngắn về những gì sửa đổi trong commit
	- Body : mô tả chi tiết hơn về sửa đổi trong commit, cần thiết khi description chưa thể hiện rõ
	- Footer : thoogn tin mở rộng như số ID của pull, reques, issue, ...
- Ví dụ cụ thể:
	```
	feat: add validate of A feature
	fix: fix die dashboard page
	feat(feature_a): add validate of A1 feature
	```
# Type theo conventional commit
- ### một số type phổ biến
	1. **`Feat`** : thêm một feature
	2. **`Fix`** : fixbug cho hệ thống, vá lỗi trong codebase
	3. **`Refactor`** : sửa code nhưng không fix bug cũng không thêm feature hoặc đôi khi bug cũng không fix từ việc refactors 
	4. **`Docs`**: thêm/thay đổi document
	5. **`Chore`**: những sửa lôi nhỏ nhặt không liên quan tới code
	6. **`Style`** : những thay đổi không làm thay đổi ý nghĩa của code như thay đổi css/ui
	7. **`Perf`** : code cải thiện về mặt hiệu năng xử lý
	8. **`Vendor`** : cập nhật các dependencies packages