# arenahub-github.io
🎯 Đề Cương & Bài Tập Luyện Thi Thực Hành Git
Dựa trên các lệnh bạn đã ghi trong sổ, tôi chia thành 3 phần chính để luyện tập.

I. Thao Tác Cơ Bản & Quy Trình Phát Triển (Focus: clone, status, add, commit, push, pull)

Đây là quy trình làm việc hàng ngày của một lập trình viên. Bạn cần thực hiện nhanh và chính xác.

STT	Tên bài tập (Tình huống)	Các bước thực hiện (Lệnh cần dùng)
1.	Khởi tạo dự án & Commit lần đầu	1. Tạo thư mục web_ban_quan_ao và khởi tạo Git (git init). 2. Tạo file README.md với tiêu đề dự án. 3. Đưa file vào Staging và Commit lần đầu.
2.	Làm việc với tệp bị bỏ qua (.gitignore)	1. Tạo file .gitignore và thêm các dòng: *.log, temp/. 2. Tạo file debug.log và thư mục temp/ chứa file file_tam.txt. 3. Chạy git status và xác nhận các file này bị bỏ qua (không thấy).
3.	Tạo shortcut Commit nhanh	1. Sửa file README.md. 2. Sử dụng lệnh git commit -a -m "sua readme" để commit mà không cần dùng git add.
4.	Làm việc với Remote (Giả định)	1. Giả định bạn đã có Remote (GitHub). Thực hành đẩy code: git push origin main (hoặc master). 2. Giả định có thay đổi mới trên Remote, thực hành cập nhật code về máy: git pull origin main.
II. Quản Lý Nhánh & Hợp Nhất (Focus: checkout, merge, rebase)

Phần này là trọng tâm của việc kiểm soát phiên bản nâng cao, thường quyết định điểm cao trong bài thi.

STT	Tên bài tập (Tình huống)	Các bước thực hiện (Lệnh cần dùng)
5.	Tạo và chuyển đổi Branch	1. Đang ở main, tạo một branch mới cho tính năng: git branch feature/gio-hang. 2. Chuyển sang branch đó: git checkout feature/gio-hang (hoặc git switch feature/gio-hang). 3. Thêm file gio_hang.php và commit.
6.	Hợp nhất (Merge) thông thường	1. Chuyển về branch main. 2. Hợp nhất tính năng giỏ hàng: git merge feature/gio-hang. 3. Xóa branch cũ (sau khi merge xong): git branch -d feature/gio-hang.
7.	Giải quyết Xung đột (Conflict)	1. Trên branch main, sửa dòng 10 của file index.html. Commit. 2. Trên branch fix/header, sửa cùng dòng 10 của file index.html với nội dung khác. Commit. 3. Chuyển về main và chạy git merge fix/header. 4. Tự tay chỉnh sửa file index.html để giữ lại cả hai nội dung, sau đó git add và git commit để hoàn tất giải quyết xung đột.
8.	Tái cơ sở (Rebase)	1. Đang ở main, commit A. 2. Chuyển sang feature, commit B. 3. Quay về main, commit C. 4. Chạy git rebase main trên branch feature để di chuyển commit B lên sau commit C (làm cho lịch sử tuyến tính).
III. Hoàn Tác Lịch Sử (Focus: reset và cherry-pick)

Kỹ năng "hoàn tác" chứng minh bạn có thể sửa lỗi trong lịch sử commit.

STT	Tên bài tập (Tình huống)	Các bước thực hiện (Lệnh cần dùng)
9.	Hoàn tác mềm (Soft Reset)	1. Thực hiện 3 commit liên tiếp (Commit 1, Commit 2, Commit 3). 2. Quay về trạng thái sau Commit 1, nhưng giữ lại thay đổi của Commit 2 và 3 trong Staging Area: git reset --soft HEAD~2. 3. Chạy git status để kiểm tra.
10.	Hoàn tác hỗn hợp (Mixed Reset)	1. Thực hiện 2 commit (Commit A, Commit B). 2. Quay về trạng thái sau Commit A, giữ lại thay đổi của Commit B trong Working Directory: git reset --mixed HEAD~1 (hoặc chỉ git reset HEAD~1 vì mixed là mặc định). 3. Chạy git status để kiểm tra.
11.	Hoàn tác cứng (Hard Reset)	1. Thực hiện một commit lỗi. 2. Xóa commit đó hoàn toàn khỏi lịch sử và mọi thay đổi trên thư mục làm việc: git reset --hard HEAD~1. (Cảnh báo: Đây là lệnh nguy hiểm, chỉ dùng khi chắc chắn).
12.	Chọn lọc Commit (Cherry-pick)	1. Đang ở main, bạn cần một commit quan trọng từ branch hotfix/A mà không muốn merge cả branch. 2. Chạy git cherry-pick <ID_commit_quan_trong> để lấy riêng commit đó.
🔑 Luyện tập SSH Key (Theo ghi chú của bạn)

Tạo khóa SSH: Thực hành lệnh ssh-keygen -t rsa -C "email_git" để tạo cặp khóa công khai và riêng tư.

Thêm khóa: Biết cách sao chép khóa công khai (nằm trong file .pub) và dán vào phần cài đặt SSH Keys trên GitHub/GitLab. Điều này giúp bạn xác thực mà không cần dùng mật khẩu.
