# BAO CAO GIT VA GITHUB
============================

## I. Tìm hiểu về Github .

**1.Github là gì ?**
  
  >+ Github, còn được gọi là social network dành cho developer đi vào hoạt động tháng 2 năm 2008, là một dịch vụ sử dụng hệ thống quản 
lý phân tán giúp người dùng lưu trữ source code cho các dự án.Git là một mô hình quản lý source phân tán, nó có mọi tính năng của một
source control như SVN và hơn thế nữa.

  >+ Github được viết bằng Ruby on Rails. GitHub cung cấp dịch vụ thương mại và cả tài khoản miễn phí cho các dự án nguồn mở. Theo khảo
sát của người sử dụng Git vào năm 2009, Github hiện đang là server Git lưu trữ source code phổ biến nhất hiện nay.Có hơn 439000 developer
tạo hơn 1 triệu 350 ngàn repositories là một con số khá ấn tượng, cùng với một số khách hàng lớn của github như Twitter, Facebook,
Yahoo ... cho thấy tính phổ biến của Github, cũng như cộng đồng lập trình thế giới tín nhiệm nó như thế nào.

  **2. Cách thức làm việc của Github.**
  
  > + Làm việc với GitHub nói riêng hay hệ thống GIT nói chung có 2 workflow chính là local workflow và server workflow.
    
  > + Có thể làm mọi chuyện thay đổi source code ở local, sau khi đã thay đổi xong, bạn sẽ commit những thay đổi đó lên 
server và bản lên server phải là bản hoàn chỉnh một tính năng nào đó, hoặc fix bug xong, test xong hoặc ít nhất bản đó phải chạy được.
Không được commit code dở dang, chưa qua test lên repository server sẽ làm ảnh hưởng đến các thành viên khác, ngược lại bạn có thể làm 
điều đó ở repository local (Bạn cũng có thể tạo một branch ở server cho việc commit code dở dang hay tính năng chưa hoàn thành như từng
làm với SVN, nó sẽ chiếm space ở server cũng như làm mất thời gian của bạn vào việc tương tác kết nối với server.

  > + Từ repository của **Github** ta có thể theo phương thức của Git tạo bản build cho production site bằng cách push thay đổi lên 
nó. Khi tương tác với repository server (cập nhật hay thay đổi) **GITHUB** đòi hỏi mã chứng nhận "Bạn là ai" thông qua so sánh SSH key 
ở local của bạn và SSH key trên server tương ứng với account mà bạn đã đăng ký với **GITHUB** trước đó.

### II. Các khái niệm: Add, Remove, Commit, Push, Pull, Fetch, Clone, Fork, Star, Watch.

  **1. Add:** lưu file thay đổi (mang tính cục bộ) - tương ứng với câu lệnh `git add` .

  **2. Commit :** Ghi lại trạng thái thay đổi tại máy local (ví dụ như có thể ấn Save nhiều lần với file README.md nhưng chỉ khi commit 
thì trạng thái của lần ấn Save cuối cùng trước đó mới được lưu lại) - tương ứng với câu lệnh `git commit`.

  **3. Push:** Đẩy những thay đổi từ máy trạm lên server - tương đương lệnh `git push`.

  **4. Pull:** đồng bộ trạng thái từ server về máy trạm - tương đương lệnh `git pull`.
  
  **5. Clone:** sao chép một repository - tương đương lệnh `github clone`.
  
  **6. Fetch:** hủy tất cả thay đổi và commit cục bộ, lấy về (fetch) lịch sử gần đây nhất từ máy chủ và trỏ nhánh master cục bộ vào nó-
tương đương lệnh `github fetch`

  **7. Fork:** một người dùng khác copy một bản sao của repo về kho của họ
  
  
#### III. Setting up Git.

+ **Cài đặt** : Download tại địa chỉ  https://windows.github.com/.
 
+ Cài đặt bình thường, yêu cầu phải có .NET 4.5

+ Giao diện chương trình :


<img src="https://scontent-hkg3-1.xx.fbcdn.net/v/t1.0-9/15391033_748683355283486_8837167856515556284_n.jpg?oh=1c9b1423f5e817a52c26510cd88c2eed&oe=58B52573">

+Thêm tài khoản Github:

  > + Click vào tool and options (hình bánh răng cạnh biểu tượng Sync) chọn options, Add account.
Khai báo username và password trên github.

  > + Tại mục Configure git thêm Tên và email của mình
  
<img src="https://scontent-hkg3-1.xx.fbcdn.net/v/t1.0-9/15283957_748683351950153_3638764291318842082_n.jpg?oh=120938a1399693cc53f69ad26450b4a7&oe=58F7465E">



##### IV. Generate and add SSH key.

+ Mở chương trình Git Shell trên desktop.
+ Nhập : **ssh-keygen -t rsa**

        Enter file in which to save the key (/root/.ssh/id_rsa): [Press enter]
        Enter passphrase (empty for no passphrase): [Press enter]
        Enter same passphrase again: [Press enter]
        Your identification has been saved in /root/.ssh/id_rsa.
        Your public key has been saved in /root/.ssh/id_rsa.pub.
        
+ Nếu nhập passphrase thì hãy nhớ pass này!
+ Kết quả:
>**ls ~/.ssh/**

        id_rsa       id_rsa.pub   known_hosts
        
> ssh-agent -s

> ssh-add ~/.ssh/id_rsa

> cat ~/.ssh/id_rsa.pub

+Truy cập đường dẫn sau https://github.com/settings/ssh , chọn Add SSH key, đặt tên cho key này tại `Title` và paste 
nội dung vừa copy vào ô `Key` .

<img src="https://scontent-hkg3-1.xx.fbcdn.net/v/t1.0-9/15284029_748687575283064_7968826560727684595_n.jpg?oh=6f47c772dd5d983d5bcf7a1cc50b2cd9&oe=58B00DD3">

+ Lúc này đã có thể commit lên github tại máy local mà không cần nhập username và password.



                                                           ~~ HẾT ~~
  









