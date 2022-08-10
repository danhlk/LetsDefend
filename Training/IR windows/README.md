# How to Create Incident Response Plan? (cách tạo một kết hoạch ứng cứu sự cố)

## What is incident response? (ứng cứu sự cố là gì)
Ứng cứu sự cố là một tiếp cận để quản lý một quy trình sự cố bảo mật. Cần có kế hoạch ứng cứu sự cố để tiếp cận các sự cố an ninh một cách có hệ thống. Một kế hoạch ứng cứu sự cố thành công bao gồm 6 giai đoạn:
1. Preparation
2. Identification
3. Scope
4. Eradication
5. Recovery
6. Lessons Learned

## 1 - Preparation
### Tạo một hệ thống đăng ký trung tâm 
Đây là một điều kiện quan trong cho việc tiết kiệm thời gian khi tất cả dữ liệu có thể được xem xét từ một điểm đơn với một trung tâm lưu trữ có thể quản lý lượng lớn files.

### Đồng bộ thời gian
Bật NTP trên tất cả thiết bị trong mạng là quan trọng cho việc khớp thông tin thời gian của việc thu thập log.

### User Account Management
Việc tên người dùng của các tài khoản khác nhau thuộc về nhận sự giống nhau và khác với nhân sự khác giúp dễ dàng theo dõi sự kiện hoạt động của người dùng trong trường hợp có sự kiện.

### Quản lý tài khoản hệ thống và dịch vụ
Quản trị viên của các dịch vụ và hệ thống được sử dụng nên được chỉ định và phải tạo một tài liệu về cách tiếp cận những người quản lý này nếu cần.

### Quản lý tài sản
Cần có quyền truy cập tức thì vào thông tin như thiết bị, hệ điều hành, phiên bản vá lỗi và trạng thái quan trọng.

### Giao tiếp an toàn
Nếu cần, nhóm có thể cần giao tiếp độc lập với mạng nội bộ, đối với những trường hợp như vậy có thể sử dụng điện thoại di động hoặc email phụ.

### Giao dịch hợp pháp (Legal Transaction)
Phương pháp ai sẽ bắt đầu quá trình đánh giá và trong các tình huống cần được xác định trước khi sự cố xảy ra. 


## 2 - Identification
### Review
Đối với sự cố đáng ngờ tiềm năng, thông tin sơ bộ về sự cố cần được thu thập. Sau đó nó phải được xác định liệu tình huống đó là đáng nghi hay không.

### Assignment
Người đầu tiên xem xét sự cố phải được chỉ định. Người này nên ghi chú về review.

### Using the Checklist
Cần phải có các mốc cho việc phân tích để đảm bảo có phản ứng nhất quán đối với sự cố.

## 3 - Scope
### Đặc trưng sự kiện
Vì xác định sự kiện sẽ xác định các hành động sẽ được thực hiện, nó quan trọng để xác định loại sự kiện sắp tới, Ví dụ: DDoS, nhiễm mã độc, lộ dữ liệu ...

### Taking Action
Hành động nên được thực hiện theo kỹ thuật được sử dụng chặn phương pháp của kẻ tấn công một cách nhanh chóng. Nếu có một tài khoản bị bắt, biện pháp đơn giản là vô hiệu hóa và khóa IP.

### Data Collecting
Image của bộ nhớ RAM cùng với logs của firewall, lưu lượng mạng các những cái khác sẽ được yêu cầu cho việc điều tra.

### Isolation (cô lập)
Ngắt nguồn hệ thống bị nhiễm có thể làm biện pháp, cô lập nó là một giải pháp khả thi hơn.
Sau khi hệ thống bị ảnh hưởng với sự cố được xác định, khả năng kẻ tấn công sẽ lây lan ra mạng và thu thập thông tin, bước tiếp theo có thể được thông qua

## 4 - Eradication (diệt trừ)
### Xác định nguyên nhân nguồn
Với thông tin có được từ giai đoạn 2 và 3, nguyên nhân gốc rễ của sự kiện nên được xác định. Kẻ tấn công sau đó phải hoàn toàn bị loại bỏ.

### Xác định tiềm tàng Rootkit
Nếu rootkit bị nghi ngờ trong hệ thống, ổ đĩa nên được làm sạch và một bản backup sạch được cài đặt lại. Sau khi cài đặt, bản cập nhật mới nhát của ứng dụng có sẵn và hệ thống nên được cài đặt.

### Cải thiện phòng thủ
Hệ điều hành, ứng dụng được sử dụng, mạng, DMZ. Các thiếu sót phòng thủ trong vùng nên được xác định và công việc cần được hoàn thành để cải thiện.

### Quét lỗ hổng (Vulnerabilitiy Scan)
Các điểm tấn công tiềm tàng trong mạng và hệ thống nên được xác định và sửa chữa bằng cách quét lỗ hổng.

Khi các sắp xếp cần thiết được chuẩn bị để ngăn chặn sự kiện tái diễn, giai đoạn Recovery có thể được bắt đầu.

## 5 - Recovery
### Verification (xác minh)
Xác minh rằng việc ghi log, hệ thống, ứng dụng, cơ sở dữ liệu, và các hoạt động khác hoạt động chính xác.

### Restore (khôi phục)
Ở giai đoạn này, hành động phục hồi được phối hợp.

### Monitoring (giám sát)
Hệ thống nên được giám sát cho các sự kiện lặp lại.

Khi không có tính huống lặp đi lặp lại hoặc hành động bất thường, bước kế tiếp được thực hiện.

## 6 - Lessons Learned (bài học rút ra)
### Viết báo cáo tiếp theo
Báo cáo bao gồm sự xem xét với chuyên gia và người điều hành, các giai đoạn hoạt động tốt và xấu trong kế hoạch can thiệp, và các khuyến nghị liên quan đến quy trình. Báo cáo nên được viết theo cách mà người quản lý chắc chắn rằng sự kiện đã kết thúc.


# Live Memory Analysis - 1
Cách tốt nhất để nhận định một hành động độc hại đang chạy trên hệ thống là tiến hành phân tích bộ nhớ. Nếu kẻ tấn công đang truy cập hệ thống từ xa vào lúc này, và nếu hắn đang đánh cắp dữ liệu hoặc tương tác trong cách nào đó, sẽ có một tiến trình cho phép điều đó. Để nhạn định tiến trình cho phép điều đó, một cuộc phân tích bộ nhớ sẽ được tiến hành.

Trong khi giải thích chủ đề này, chũng ta sẽ được hưởng lợi từ các công cụ "Process Hacker". Như đã giải thích trước đó, có nhiều công cụ khác nhau. Điều quan trọng là để biết kiểm soát cái gì, chứ không phải là xài công cụ gì.

![image1](https://letsdefend.io/images/academy/memory/mem1.PNG)

Công cụ Process Hascker hiển thị rất chi tiết liên quan đến tiến trifng trong hệ thống. Ở trên, bạn có thể thấy các tiến trình liên quan, chỉ số PID, và thông tin người dùng chạy nó.

Trở về vìệc phân tích. Có 3 điểm quan trọng chứng ta phải tập trung trong khi tiến hành phân tích bộ nhớ:
* Cây tiến trình (Process Tree)
* Network Connections 
* Signature Status 

## Process Tree
Điều quan trọng phải biết đâu là trạng thái bình thường khi phân tích bộ nhớ. Ví dụ, tiến trình "chrome.exe" sẽ bình thường khi có tiến trình con cũng là "chrome.exe" vì nó có thể tạo ra nhiều tiến trình dựa vào các tab khác nhau.

![image2](https://letsdefend.io/images/academy/memory/mem2.PNG)

Nhưng nếu chúng ta thấy "powershall.exe" được tạo phía dưới "chrome.exe". Chúng thấy sự bất thường ở đây. Chúng ta phải nghi ngờ có một tình huống khai thác và xem xét powershell đã làm gì và những lệnh nào được chạy.

### Example 1 - Phát hiện WebShell
Nhìn hình bên dưới, một tiến trình con powershell.exe được tạo phía dưới tiến trình sở hữu bởi máy chủ web. Nó thể là "cmd.exe" thay vì PowerShell. Theo sau đó, lệnh "whoami" và "net user" được thực thi. Chúng ta không mong muốn một powershell chạy dưới tiến trình của máy chủ web hơn là các trường hợp bất thường. Thêm vào đó, chúng ta chắc chắn không mong muốn bất kỳ lệnh liệt kê nào chạy như vậy.

![image3](https://letsdefend.io/images/academy/memory/mem3.PNG)

Kết quả: nếu một tiến trình cmd hoặc PowerShell được tạo phía dưới tiếnh trình máy chủ web, chúng phải nghi ngờ nó và điều tra nó.

### Example 2 - Phát hiện Macro đọc hại
Nghĩ về tiến trình "Winword.exe". Chúng ta biết nó được tạo ra khi một tài liệu word được mở. Có bình thường không khi mà PowerShell được mở phía dưới Windword.exe? Điều gì xảy ra nếu trên thực tế; PowerShell này đạng được chạy bằng một lệnh được mã hóa bằng base64. Tình huống này là không bình thường và hâu hết có thể là do một file với một marco độc hại được nhúng vào nó đang được mở.

![image4](https://letsdefend.io/images/academy/memory/mem4.PNG)

## Kiểm tra với Process Hacker
Chúng ta đã đề cập lý thuyết cách để nhận định hành vị độc hại lấy được từ cây tiến trình với các ví dụ. Làm thế nào chúng ta có thể kiểm tra ngay trên máy thật?

![image5](https://letsdefend.io/images/academy/memory/mem5.PNG)

Khi ta xem xét tình huống ở trên, chúng ta có thể thấy python.exe được tạo phía dưới cmd.exe. Điều này có thể là hợp pháp nhưng cũng có thể là lệnh python độc hại. Để hiểu điều này, chúng ta phải double-click vào "python.exe" và kiểm tra file/lệnh nào được chạy.

![image6](https://letsdefend.io/images/academy/memory/mem6.PNG)

Khi ta xem Command Line, chúng ta thấy file manage.py được chạy với tham số là "runserver" và trong "thự mục hiện tại", chúng ta thấy nới điều này xảy ra. Chúng ta chưa thể kết luận đây là tình huống đáng nghi. Để hiểu đây là tình huống đáng nghi hay độc hại, chúng ta phải phân tích file "manager.py". Như đã thấy, file này nằm ở đường dẫn "C:\Users\gunal\Documents\Github\LetsDefend\letsdefend\"

Kết nối mạng và trạng thái signature phải được kiểm tra trong suốt một phân tích bộ nhớ sẽ được giải thích trong phần tới.


# User 
Một phương pháp phổ biến được sử dụng bởi các kẻ tấn công để duy trì sự bền bì (maintain persistence) là tạo users. Trong thực tế, không phải chỉ để duy tr sự bên bỉ, chúng tối quan sát rằng khi một kẻ tấn công điều khiển tài khoản "quản trị viên", họ tạo một user mới. Bì đây là user quan trọng, mà hoạt động của nó sẽ được lưu lại. Do đó, họ tạo một người dùng mới để tránh gây sự chú ý, và nếu có thể, chúng tăng quyền hạn của người dùng này ngang với quản trị viên.

Người dùng được tạo thường bao gồm các từ khóa như "support", "sysadmin", "admin". Trong hầu hết các doanh nghiệp, người dùng với tên như vậy sẽ không thu hút nhiều suwk chú ý.

Trong suốt quá trình ứng cưu sự cố, có 2 thứ phải nhanh chóng đánh giá. 
* Liệu hiện tại có người dùng nào trong hệ thống mà nên không có ở đây?
* Có người dùng nào được tạo trong cuộc tấn công và đã được xóa sau đó chưa?

## Phát hiện người dùng đáng nghi
Để hiển thị người dùng hiện tại trong hệ thống, chúng ta có thể sử dụng lệnh "net user" thông qua cmd.

![image7](https://letsdefend.io/images/academy/user/user1.PNG)

Như kết quả, nếu có một người dùng không nên có ở đây và cần nhiều thông tin chi tiến hơn liên quan đến người dùng này, sử dụng lệnh "net user $USERNAME".

![image8](https://letsdefend.io/images/academy/user/user2.PNG)

Trong ví dụ trên, nếu giá trị "Last logon" và "Password last set" được ghéo nối với thời gian của cụộc tấn công, chúng ta có thể nghi ngờ tình huống này.

Một phương pháp khác để kiểm soát là thông qua "lusrmgr".

![image9](https://letsdefend.io/images/academy/user/user3.PNG)

Trong cửa sổ hiện lên, chúng ta chọn "Users" và danh sách người dùng.

![image10](https://letsdefend.io/images/academy/user/user4.PNG)

Nếu bạn nghi ngờ người dùng, bạn có thể tập trung vào hoạt động của người dùng đó trong kỳ phân tích sau.

## Người dùng được tạo trong quá khứ
Kẻ tấn công, sau khi tạo người dùng và tiến hành các thủ tục liên quan, có thể xóa người dùng đó khi đã thực hiện xong để giảm thiểu khả năng bị phát hiện. Trong trường hợp này, chúng ta sẽ không thể xem người dùng với 2 phương pháp trên. Chúng ta phải kiểm tra trong "Security" logs để quan sát liệu có người dùng nào được tạo trong quá khứ hay không. Để làm điều đó, chúng ta sử dụng "Event ID 4720 - Một người dùng được tạo".

Sau khi mở "Security" với "event Viewer", chúng ta có thể lọc với ID là "4720"

![image 11](https://letsdefend.io/images/academy/user/user5.PNG)

![iamge12](https://letsdefend.io/images/academy/user/user6.PNG)

Trong cửa sổ hiện lên, nhập "4720"

![image 13](https://letsdefend.io/images/academy/user/user7.PNG)

![image14](https://letsdefend.io/images/academy/user/user8.PNG)

Khi ta xem kết quả, chúng ta thấy người dùng "LetsDefend" đã tạo người dùng mới có tên "SupportUser" vào lúc "10/10/2021 10:07". Bài học mà chúng ta nhận được ở đây là' người dùng "LestDefend" đã bị chiếm hoặc một quyền truy cập có thể cho phép chạy các lệnh đã được thực hiện. Từ điểm này, cả hai người dùng "LetsDefend" và "SuportUser" phải được theo dõi.

## ADDITIONAL
Để bắt được hành vi đáng ngờ từ người dùng, bạn có thể giám sát những người dùng nào được thêm vào nhóm "administrator" trong suốt thời gian cuộc tấn công. Do đó, bạn sẽ ngay lập tức bắt được người dùng không nên được thêm vào. Bạn có thể sử dụng event ID bên dưới.
* Event ID 4732 - Một thành viên được thêm vào nhóm Security-enbale.

## Chúng ta đã học được gì?
* Kẻ tấn công có có thể sử dụng các tên thông thường như "Support" hoặc "Admin" sau khi chiếm được hệ thống.
* Hành động của người dùng đã tạo một người dùng mới cũng phải được theo dõi ngoài các hoạt động của người dùng mới.
* Trong khi theo dõi các hoạt động trước đó, các bản ghi ID 4720 và 4732 sẽ có lợi.

```
**__NOTE__**
TÀI KHOẢN FREE CHỈ ĐƯỢC ĐẾN ĐÂY THÔI =(((
```
