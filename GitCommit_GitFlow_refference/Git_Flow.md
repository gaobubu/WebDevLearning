# Khái niệm
- Là mô hình quản lý nhánh của git, sử dụng để phân nhánh cụ thể giúp quản lý quy trình phát triền phần mềm dễ dàng hơn bằng cách sử dụng nhiều nhánh khác nhau  để quản lý tính năng, sửa lỗi và quá trình phát hành
- Git Flow báo gồm các nhánh chính như sau : 
	1. **Main Branch**: là nơi chứa production code
	2. **Develop Branch**: là nơi phát triển chính của quá trình. Tất cả cá tính năng và sửa lỗi được tích hợp trước khi kiểm tra và triển khai lên main branch
	3. **Feature Branch**: được tạo từ Develop để thực hiện các tính năng cụ thể. Mỗi tính năng sẽ có một nhánh riêng để tránh ảnh hưởng đến các thành viên khác
	4. **Release Branch**: được tạo ra từ develop để chuẩn bị cho việc phát hành các phiên bản mới. các chỉnh sửa và kiểm tra cuối được thực hiện ở đây trước khi merge với main và develop
	5. **Hotfix Branch**: được tạo ra từ main để sửa lỗi trực tiếp. Sau khi sửa xong, nó sẽ được merge  vào nhánh master và develop
![[Pasted image 20230811115418.png]]

## GitHub flow
- Như Git-flow nhưng được phân nhánh nhẹ nhàng phù hợp với các nhóm thực hiện triển khai liên tục và hoạt động tốt nhất cho các nhóm và dự án nhỏ
![[github-flow.png]]
- Main Branch là nơi chứa mã nguồn sản xuất
- Được phát triển trong nhánh riêng biệt tạo ra từ nhánh feature nơi mà sẽ được gộp với main khi sẵn sàng
- **Pull request** là nơi để xem xét mã nguồn và đáp ứng nhu cầu bảo vệ nhánh trước khi được gộp với nhánh main
# The Space Git Flow
- là quy trình quán lý nhánh tương tự như github-flow nhưng tập trung vào an toàn khi thực hiện các thay đổi vào nhánh main và khả năng mở rộng đối với các dự án và nhóm lớn hơn.
![[jetbrains-space-git-flow-1.png]]
- **Main branch** là nhánh sẵn sàng cho việ sản xuất, tất cả thay đổi được xác minh. Nhánh chính được bảo vệ , có nghĩa là ko cho phép commit trực tiếp
- **Feature branch**: các thay đổi nào mã nguồn được thực hiện vào 1 nhánh riêng biệt và được tạo trực tiếp từ nhánh main
- **Merge request** những thay đổi được gộp từ nhánh feature và nhánh main. Merge request này thường đi kèm với mô tả về những thay đổi bạn đã thực hiện  và lý do bạn muốn merge. Mọi người có thể thảo luận  về ác thay đổi  trước khi chúng được hợp nhất.
- **Safe merge**: bước bảo mật bổ sung trước khi merge nhánh feature và nhánh main. Space tạo một commit merge tạm thời chứa các thay đổi mới nhất từ cả hai nhánh và sử dụng nỏ để thực hiện kiểm tra chất lượng
- **Release branch**: được tạo ra từ nhánh chính và những thay đổi cuối cùng sẽ được chọn từ nhánh chính vào một nhánh cụ thể