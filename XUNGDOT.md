Khi làm việc với Git và nhiều người cùng làm việc trên một repository, xung đột (conflict) có thể xảy ra khi hai người sửa cùng một phần của tệp (hoặc các tệp khác nhau nhưng thay đổi liên quan) và sau đó cố gắng commit hoặc merge các thay đổi đó.

Để xử lý xung đột Git, bạn có thể làm theo các bước sau:

### 1. **Nhận diện xung đột**

* **Khi push**: Nếu bạn cố gắng push thay đổi lên remote repository nhưng Git báo lỗi về xung đột, điều này có nghĩa là đã có thay đổi từ người khác trên remote repository mà bạn chưa có trong local.
* **Khi merge**: Nếu bạn đang cố gắng merge một nhánh vào nhánh hiện tại và Git không thể tự động hợp nhất (merge), Git sẽ báo xung đột và yêu cầu bạn giải quyết.

### 2. **Lấy thay đổi từ remote**

Trước khi cố gắng commit, hãy luôn **pull** thay đổi từ remote repository về máy local của bạn. Điều này giúp tránh các xung đột khi bạn cố gắng **push** lên remote sau đó.

```bash
git pull origin <branch>
```

Nếu có xung đột, Git sẽ thông báo và bạn sẽ cần giải quyết.

### 3. **Giải quyết xung đột**

Sau khi Git báo có xung đột, bạn sẽ thấy các thay đổi trong các tệp bị xung đột được đánh dấu như sau:

```text
<<<<<<< HEAD
(Changes from your branch)
=======
(Changes from the branch you are merging)
>>>>>>> branch_name
```

* Phần giữa `<<<<<<< HEAD` và `=======` là các thay đổi của bạn (từ branch hiện tại).
* Phần giữa `=======` và `>>>>>>> branch_name` là các thay đổi từ branch mà bạn đang merge vào.

**Cách giải quyết**:

* Mở tệp có xung đột và chọn cách giải quyết. Bạn có thể:

  * **Giữ một bên**: Chỉ giữ các thay đổi của bạn hoặc chỉ giữ các thay đổi của người khác.
  * **Kết hợp**: Kết hợp các thay đổi của bạn và người khác một cách hợp lý.
* Sau khi giải quyết xong, xóa các dấu xung đột (`<<<<<<<`, `=======`, `>>>>>>>`).

### 4. **Thêm các tệp đã sửa vào staging**

Sau khi đã giải quyết xung đột trong tệp, bạn cần thêm lại các tệp vào staging để chuẩn bị commit:

```bash
git add <file>
```

Nếu bạn đã giải quyết xung đột trong tất cả các tệp, bạn có thể thêm tất cả các tệp đã thay đổi vào staging:

```bash
git add .
```

### 5. **Commit các thay đổi**

Sau khi đã thêm các tệp vào staging, hãy commit các thay đổi đã giải quyết xung đột:

```bash
git commit -m "Resolved merge conflict"
```

### 6. **Push thay đổi lên remote**

Sau khi commit thành công, bạn có thể push các thay đổi đã được giải quyết lên remote repository:

```bash
git push origin <branch>
```

### 7. **Kiểm tra lại**

Sau khi push, đảm bảo rằng các thay đổi đã được áp dụng và không còn xung đột nữa.

---

### Lưu ý:

* **Trước khi bắt đầu làm việc**: Hãy luôn thực hiện `git pull` để đảm bảo rằng bạn có những thay đổi mới nhất từ remote repository, tránh trường hợp khi push gặp phải xung đột.
* **Cẩn thận khi giải quyết xung đột**: Nếu bạn không chắc chắn về cách giải quyết, hãy trao đổi với nhóm của mình để thống nhất cách xử lý.

Chúc bạn thành công trong việc giải quyết xung đột Git!
