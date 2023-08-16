# GIT (nơi lưu trữ phiên bản)
- ## Khái niệm
	- Git là một hệ thống quản lý phiên bản phân tán **(DVCS - Distributed Version Control System)**. Nó được sử dụng rộng rãi trong quản lý mã nguồn và dự án phát triển phần mềm để theo dõi, quản lý và hợp nhất mã nguồn từ nhiều người tham gia.
	- Dưới đây là 1 số khái niệm quan trọng nằm trong GIT
		1. **Repository (Repo):** Là nơi lưu trữ toàn bộ lịch sử, mã nguồn và các thông tin về dự án. Repository có thể là local (trên máy cá nhân) hoặc remote (trên máy chủ xa).
		    
		2. **Commit:** Là một "snapshot" của mã nguồn tại một thời điểm cụ thể. Mỗi commit bao gồm các thay đổi trong mã nguồn và thông tin về người thực hiện commit và thời gian.
		    
		3. **Branch:** Là một nhánh riêng biệt của dự án, cho phép phát triển đồng thời các tính năng, sửa lỗi hoặc thay đổi mà không ảnh hưởng đến nhánh chính.
		    
		4. **Merge:** Là quá trình kết hợp nội dung từ một nhánh vào nhánh khác, thường được thực hiện để tích hợp các tính năng hoặc sửa lỗi vào nhánh chính.
		    
		5. **Pull Request (PR):** Là một yêu cầu để hợp nhất thay đổi từ một nhánh vào nhánh khác (thường từ nhánh con vào nhánh chính). Điều này thường được sử dụng trong quy trình làm việc đội.
		    
		6. **Clone:** Là quá trình sao chép toàn bộ repository từ remote xuống local, cho phép bạn làm việc với dự án trên máy tính cá nhân.
		    
		7. **Push:** Là quá trình đẩy các thay đổi từ máy tính local lên remote repository, cập nhật các thay đổi của bạn trên dự án chia sẻ.
		    
		8. **Pull:** Là quá trình kéo các thay đổi từ remote repository xuống máy tính local của bạn.
		    
		9. **Conflict:** Xảy ra khi Git không thể tự động hợp nhất các thay đổi do có xung đột giữa các phiên bản. Người dùng phải giải quyết xung đột bằng cách sửa mã nguồn thủ công.
- ## Cách sử dụng GIT
	1. **Cài đặt Git:**
	    - Trước hết, bạn cần cài đặt Git trên máy tính của mình. Bạn có thể tải Git từ trang chính thức của nó: [https://git-scm.com/downloads](https://git-scm.com/downloads)
	2. **Tạo Repository (Repo):**
		- Để bắt đầu sử dụng Git, bạn cần tạo một thư mục để chứa dự án. Sau đó, mở Command Line hoặc Terminal và di chuyển đến thư mục dự án bằng lệnh `cd`.
	3. **Khởi tạo Repository:**
		- Sử dụng lệnh sau để khởi tạo một repository trong thư mục dự án: 
			```
			git init
			```
	4. **Thêm và Commit:**
		- Sử dụng lệnh `git add` để thêm các tệp và thay đổi vào vùng chờ (staging area) để chuẩn bị commit:
			```
			git add <tên_tệp>   # Thêm tệp cụ thể 
			git add .           # Thêm tất cả các tệp và thay đổi
			```
		- Sau đó, sử dụng lệnh `git commit` để tạo một commit:
			```
			git commit -m "Thông điệp commit"
			```
	5. **Tạo và Quản lý Nhánh:**
		- Để tạo một nhánh mới, sử dụng lệnh:
			```
			git branch <tên_nhánh>
			```
		- Để chuyển đổi sang một nhánh khác, sử dụng lệnh:
			```
			git checkout <tên_nhánh>
			```        
		- Sau khi hoàn thành công việc trên nhánh con, bạn có thể hợp nhất (merge) vào nhánh chính bằng cách:
			```
			git checkout <nhánh_chính> git merge <nhánh_con>
			```
	6. **Remote Repository:**
		- Nếu bạn muốn làm việc trên remote repository (trên máy chủ xa), bạn cần sao chép nó về local sử dụng lệnh:
			```
			git clone <url_remote_repo>
			```

		- Để đẩy (push) các commit từ local lên remote, sử dụng lệnh:
			```
			git push origin <tên_nhánh>
			```
        
	7. **Cập Nhật và Đồng Bộ:**
		- Để cập nhật dự án từ remote, sử dụng lệnh:
			```
			git pull origin <tên_nhánh>
			```
- ## Các câu lệnh thường dùng (create/delete branch, pull, push, stash, merge, check out,..)
	1. **Khởi tạo và Cấu hình:**
	    - `git init`: Khởi tạo một repository mới trong thư mục hiện tại.
	    - `git config`: Cấu hình Git (tên, email, cấu hình hệ thống, v.v.).
	2. **Cơ bản về Commit:**

	    - `git add`: Thêm tệp và thay đổi vào vùng chờ (staging area).
	    - `git commit`: Tạo một commit với các thay đổi đã thêm và ghi chú.
	    - `git commit -m "Thông điệp commit"`: Tạo commit với thông điệp ngắn.
	3. **Nhánh (Branch):**	    
	    - `git branch`: Liệt kê các nhánh hiện có.
	    - `git branch <tên_nhánh>`: Tạo một nhánh mới.
	    - `git checkout <tên_nhánh>`: Chuyển đổi sang một nhánh khác.
	    - `git merge <nhánh_khác>`: Hợp nhất các thay đổi từ một nhánh vào nhánh hiện tại.
	    - `git branch -d <tên_nhánh>`: Xóa một nhánh đã hợp nhất.
	4. **Đồng bộ với Remote:**	    
	    - `git clone <url_remote_repo>`: Sao chép một remote repository về local.
	    - `git pull`: Kéo các thay đổi mới nhất từ remote và hợp nhất vào nhánh hiện tại.
	    - `git push`: Đẩy các thay đổi từ local lên remote repository.
	5. **Xử lý Thay đổi Tạm thời:**	    
	    - `git stash`: Lưu trạng thái hiện tại của thay đổi tạm thời để làm việc khác.
	    - `git stash apply`: Áp dụng trạng thái tạm thời đã lưu trước đó.
	    - `git stash pop`: Áp dụng và xóa trạng thái tạm thời khỏi danh sách.
	6. **Thông tin và Lịch sử:**    
	    - `git log`: Hiển thị lịch sử commit.
	    - `git diff`: Hiển thị sự khác biệt giữa các thay đổi chưa được commit.
	    - `git status`: Hiển thị trạng thái của vùng chờ và thư mục làm việc hiện tại.
	7. **Xử lý Xung đột (Conflict):**	    
	    - Khi có xung đột, bạn cần giải quyết thủ công trong các tệp có xung đột sau đó thêm và commit lại.
	8. **Thông tin về Remote:**	    
	    - `git remote -v`: Liệt kê các remote repository đã cấu hình.
	    - `git remote add <tên_remote> <url_remote>`: Thêm một remote mới.
	9. **Undo và Amend:**    
	    - `git reset HEAD <tên_tệp>`: Hủy các thay đổi đã thêm vào vùng chờ.
	    - `git commit --amend`: Chỉnh sửa commit gần nhất hoặc kết hợp thay đổi vào commit đang hiệu chỉnh.


# Local repo and remote repo
- ### local repo (local repository)
	- phiên bản của dự án hoặc mã nguồn của bạn được lưu trữ trên máy tính cá nhân hoặc máy chủ cục bộ. 
	- Nó là nơi bạn thực hiện công việc phát triển, tạo và lưu trữ các thay đổi, quản lý lịch sử commit và thực hiện nhiều hoạt động khác liên quan đến quản lý phiên bản. 
	- Local repo không phụ thuộc vào internet hoặc máy chủ xa, và bạn có thể làm việc với nó mà không cần kết nối mạng.
	- ##### Cách sử dụng Local Repository:
		1. **Khởi tạo Local Repo:**
		    - Để bắt đầu, bạn cần khởi tạo một local repository trong thư mục dự án của bạn. Sử dụng lệnh `git init` để khởi tạo local repo.
		2. **Thêm và Commit Thay đổi:**
		    - Sau khi thực hiện các thay đổi trong mã nguồn của bạn, bạn sử dụng lệnh `git add` để thêm thay đổi vào vùng chờ (staging area), sau đó sử dụng `git commit` để tạo một commit chứa các thay đổi đã thêm.
		3. **Tạo và Quản lý Nhánh:**
		    - Sử dụng lệnh `git branch` để liệt kê, tạo, hoặc xóa các nhánh trong local repo. Bạn có thể sử dụng `git checkout` để chuyển đổi giữa các nhánh.
		4. **Xử lý Xung đột:**
		    - Trong trường hợp xảy ra xung đột giữa các thay đổi trong các nhánh khác nhau, bạn cần giải quyết xung đột thủ công bằng cách chỉnh sửa tệp có xung đột và sau đó commit lại.
		5. **Tạo Thay đổi Tạm thời (Stash):**
		    - Sử dụng `git stash` để lưu trạng thái hiện tại của thay đổi tạm thời khi bạn muốn chuyển sang một nhiệm vụ khác mà không muốn commit các thay đổi.
		6. **Xem Lịch sử và Sự khác biệt:**
		    - Sử dụng `git log` để xem lịch sử commit và `git diff` để xem sự khác biệt giữa các thay đổi chưa được commit.
		7. **Kết nối với Remote Repo:**
		    - Để chia sẻ và làm việc cộng tác với đồng đội, bạn có thể đẩy các thay đổi từ local repo lên remote repo sử dụng `git push` và kéo các thay đổi từ remote repo về local repo sử dụng `git pull`.

	>Local repository là nơi bạn làm việc chính trong quá trình phát triển và quản lý mã nguồn, cho phép bạn kiểm soát hoàn toàn quá trình làm việc và thử nghiệm thay đổi trước khi chia sẻ với đồng đội hoặc đẩy lên remote repository.
- ### remote repo (remote repository)
	- phiên bản của dự án hoặc mã nguồn của bạn được lưu trữ trên máy chủ xa, thường là một dịch vụ quản lý phiên bản như GitHub, GitLab, Bitbucket hoặc máy chủ riêng của bạn. 
	- Remote repo chứa toàn bộ lịch sử commit, các nhánh, tệp, và thông tin khác liên quan đến dự án.
	- Nó cho phép bạn chia sẻ mã nguồn với đồng đội, làm việc cộng tác, và triển khai dự án.
	- ##### Cách sử dụng Remote Repository
		1. **Tạo Remote Repo:**
		    - Trước tiên, bạn cần tạo một remote repository trên dịch vụ quản lý phiên bản như GitHub hoặc GitLab. Trong trường hợp bạn sử dụng máy chủ riêng, bạn cần cài đặt và cấu hình phần mềm quản lý phiên bản.
		2. **Kết nối Local Repo với Remote Repo:**
		    - Sử dụng lệnh `git remote add <tên_remote> <url_remote>` để kết nối local repo với remote repo. Tên remote thường là "origin".
		3. **Đẩy Thay đổi lên Remote Repo:**
		    - Khi bạn đã tạo các commit trong local repo và muốn chia sẻ thay đổi với đồng đội hoặc lưu trữ, bạn sử dụng lệnh `git push <tên_remote> <tên_nhánh>` để đẩy các commit lên remote repo.
		4. **Kéo Thay đổi từ Remote Repo:**
		    - Để cập nhật local repo với những thay đổi mới từ remote repo, bạn sử dụng lệnh `git pull <tên_remote> <tên_nhánh>`.
		5. **Fork và Pull Request:**
		    - Trên các dịch vụ quản lý phiên bản như GitHub, bạn có thể fork (bản sao) remote repo của người khác và sau đó tạo pull request để đề xuất các thay đổi vào repo gốc.
		6. **Làm việc Cộng tác:**
		    - Remote repo cho phép bạn và đồng đội làm việc cùng nhau trên cùng một dự án. Bạn có thể tạo và hợp nhất nhánh, thực hiện review code, giải quyết xung đột và thực hiện nhiều hoạt động khác.
		7. **Triển Khai Dự án:**
			- Khi dự án đã hoàn thành hoặc muốn triển khai, bạn có thể sử dụng remote repo để triển khai mã nguồn lên môi trường thực tế.
			
	>Remote repository giúp bạn tạo một nơi trung tâm để lưu trữ và quản lý mã nguồn của dự án, cho phép làm việc cộng tác và triển khai dự án một cách hiệu quả.
	
 - ***Tóm lại, local repo là nơi bạn làm việc và thực hiện thay đổi trong dự án cá nhân. Remote repo là nơi lưu trữ chính thức của dự án trên máy chủ xa, được sử dụng để chia sẻ và làm việc cộng tác.***