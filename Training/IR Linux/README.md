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


# Users và Groups

Người dùng phải có trong một hệ điều hành. Hệ thống người dùng có mặt trong tất cả hệ điều hành để đảm bảo an toàn cho hệ thống, để xác minh dữ liệu, và cung cấp trải nghiệm người dùng tốt hơn.

Trong chủ đề này, chúng ta sẽ xem xét hệ thống người dùng có trong hệ điều hành Linux.

Khi chúng ta xem xét báo cáo tấn công APT, chúng ta quan sát được tội phạm mạng mục đích để lấy được người dùng có quyền để hoạn toàn kiểm soát. Trong tấn công ransomware rất phổ biến trên thế giới, tội phạm mạng chiếm được tài khoản admin và tải xuống mã hóa tống tiền lên toàn bộ thiết bị trong miền.

![image1](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image1.jpg)

Hầu hết những người quản trị hệ thống sẽ không định kỳ tiến hành kiểm tra các thiết bị do mình phụ trách. Do đó, khi một người dùng bị chiếm hoặc một người dùng mới được thêm vào hệ điều hành, nó hiếm khi bị phát hiện. Vì khả năng bị phát hiện là thấp, kẻ tấn công thường chọn phương pháp này để duy trì bên bỉ.

Ngoài ra, vì mật khẩu của người dùng được để mặc đinh và không thay dổi trong quá trình thiết lập, kẻ tấn công có thể dễ dàng truy cập hệ điều hành.

Nếu pháp chứng của một cuộc tấn công mạng được kiểm tra, những kẻ tấn công sẽ truy cập vào hệ thống do khái thác lỗ hổng bảo mật trên một dịch vụ được mở trên Internet, và vì các dịch vụ này hầu hết đều chạy dưới người dùng không có quyền, kẻ tấn công lợi dụng người dùng này để tăng quyền hạn trên hệ thống.

Như là một người ứng cứu sự cố, chúng ta phải có khả năng phát hiện người dùng bị chiếm, thêm hoặc xóa khỏi hệ điều hành bởi tội phạm mạng.

"Everything is file"

Miêu tả một trong những tính năng xác định của Unix, và các dẫn xuất của nó - một loạt các tài nguyên đầu vào/đầu ra như tài liệu, thư mục, ổ cứng, modems, bàn phím, máy in và thậm chí một số liên tiến trình (inter-process) và giao tiếp mạng là các dòng byte đơn giản được hiển thị thông qua không gian tên hệ thống tệp.

Hệ thống tập tin UNIX chứ một số file quan trọng chứa thông tin về người dùng và nhóm. Như là một người ứng cứu sự cố, cần thiết phải có khả năng phát hiện sự tồn tại của các tệp này, cấu trúc tệp chung, và sự bất thường của các file này.

File chứa thông tin của người dùng và nhóm được thấy như bên dưới:
/etc/passwd

Chắc chắn, một trong những file quan trọng nhất của UNIX là /etc/passwd/ File này chứa username, password của người dùng (không còn nữa), UID/GID. thư mục home của người dùng và thông tin shell của người dùng.

![image2](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image2.png)

File *passwd* đi kèm với người dùng root và mọi người có quyền đọc nó. Vì lý này, thậm chí nếu kẻ tấn công lấy được người dùng có quyền thấp trong hệ thống, chúng vẫn có thể thu thập thông tin về người dùng trên thiết bị.

Bạn có thể đọc nội dung file *passwd* như bất kỳ file khác với lệnh cat.

```
cat /etc/passwd
```

![image3](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image3.png)

Cái nhìn đầu tiền, file /etc/passwd có thể rối mắt. Tuy nhiên, mỗi dòng trong file này có một định dạng cụ thể.

![image4](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image4.png)

Khi phân tích định dạng file này, chúng ta thấy:
* Username được viết ở nơi bắt đầu của mỗi lần trước dấu hai chấm đầu tiên,
* Password được viết giữad dâu hai chấm đầu và hai (phần này không còn sử dụng nữa)
* UID được viết giữa 2 và 3
* GID được viết giữa 3 và 4
* Comment được viết giữa 4 và 5
* Thư mục chính của người dùng được viết giữa 5 và 6
* Shell được sử dụng bởi người dùng được viết giữa 6 và 7

Nếu shell của người dùng là "/usr/sbin/nologin" trong file passwd, có nghĩa là người dùng sẽ không thể đăng nhập vào hệ điều hành.

![image5](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image5.png)

Nhưng không có nghĩa người dùng đó sẽ không thể chạy lệnh trên hệ thống. Ví dụ, shell của www-data là "/usr/sbin/nologin", tuy nhiên khi một ứng dụng web bị xâm nhập, kẻ tấn công thường thực thi lệnh trên hệ thống với người dùng này.

/etc/shadow

Trong file shadow, đây là phiên bản đã mã hóa của mật khẩu người dùng. Do đó, nó trở thành một trong những tệp phổ biến nhất của những kẻ tấn công.

![image6](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image6.png)

Bạn đang nghĩ bao gồm mật khẩu người dùng sẽ dẫn đến mối đe dọa bảo mật. File shadow chỉ đọc bởi root và những người dùng trong group shadow và những mật khẩu đã được mã hóa. Đọc file này không có ý nghĩa của nó. Một kẻ tấn công muốn khám phá mật khẩu của người dùng phải vét cạn nó để tìm được password.

![image7](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image7.png)

Xem qua định dạng của file shadow.

![image8](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image8.png)

Phân tích định dạng:
* Người dùng được viết đầu tiên
* Mật khẩu đã mã hóa được viết giữa 1 và 2
* Thời gian thay đổi password được viết giữa 2 và 3
* Thông tin về thời gian cần thiết để người dùng thay đổi mật khẩu được viết ở giữa 3 và 4
* Thông tin về thời gian thay đổi bắt buộc được viết giữa 4 và 5
* Thông tin về thời gian khi nào người dùng được thông báo trước khi passowrd hết hạn được viết giữa 5 và 6
* Thông tin về số ngày sẽ được cung cấp cho người dùng để thay đổi mật khẩu đã hêt hạn trước khi bị vô hiệu hóa được viết giữa 6 và 7
* Thông tin khi nào người dùng sẽ hết hạn được viết giữa 7 và 8
* Phần phía sau 8 được tạo việc sử dụng trong tương lai nhưng bỏ trống vì hiện tại không cần sử dụng.

/etc/group

File /etc/group chứa group và thông tin về người dùng nào trong griup nào.

Xác minh người dùng bị hại là không đủ để hiểu về mối nguy trong sự cố an toàn mạng. Nhóm người dùng cũng nên được kiểm tra.

Nếu một cấu hình đặc biệt không được thực hiện, người dùng www-data là một người dùng có quyền thấp. Tuy nhiên, khi xác định rủi ro của một sự cố mạng, sẽ là sai lầm nếu áp dụng một quan điểm như "Người dùng www-data đã bị xâm phạm, nhưng rủi ro là thấp vì quyền của người dùng này thấp". Nếu kẻ tán công nhóm www-data và nhóm có đặc quyền, www-data có thể có đầy đủ quyền như là root.

![image9](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image9.png)

File *group* đi kèm với root và những người dùng có quyền đọc. Vì lý do này, thậm chí kẻ tấn công truy cập vào hệ thống thông qua người dùng thấp nhất, chúng có thể thu thập thông tin về người dùng trên thiết bị.

![image10](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image10.png)

Xem định dạng của file *group*

![image11](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image11.png)

Khi phân tích định dạng:
* Tên group được viết ở đầu
* Mật khẩu được viết thứ hai (không còn nữa)
* GID được viết thứ 3
* Người dùng và username được viết sau dấu hai chấm thứ ba

/etc/sudoers

File *sudoers* chứa thông tin về ai có thể chạy lệnh sudo dưới những điều kiện nào.

![image12](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image12.png)

Không giống như những file khác, file *sudoers* chứa comment về định dạng file theo mặc định.

![image13](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image13.png)

* User List: xác định ai sẽ có các ủy quyền nhất định
* Host List: xác định các host nào sẽ có những quyền nhất định
* Operation List: xác định người dùng nào mà người dùng trong <user list> sẽ chạy các lệnh thay mặt.
* Tag List: có thể là "PASSWD", "NOPASSWD" và "NOEXEC" và xác định có cần phải có password để chạy lệnh hay không
* Command List: Chứa các lệnh

![image14](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image14.png)

**Các file quan trọng khác**

Ngoài những file trên, còn có nhiều file khác chứa thông tin về tiếng trình đăng nhập của người dùng.

* var/run/utmp: duy trì kế toán đầy đủ về tình trạng hiện tại của hệ thống, thời gian khởi động, ghi lại thông tin đăng nhập của người dùng tại các thiết bị đầu cuối, đăng xuất, sự kiện hệ thống.
* var/log/wtmp: hoạt động như là lịch sử của utmp
* var/log/btmp: ghi lại thông tin đăng nhập sai


<h2 align="center">Incident Response</h2>

## Analyze
### Xác định những người dùng trên hệ thống
Kẻ tấn công thêm người dùng mới và chỉnh sửa người dùng hiện tại để đảm bảo sự duy trì. Như là một người ứng cứu sự cố, cần phải xác định những người dùng này và xóa/sửa theo cách không gây rủi ro trong bước diệt trừ (eradication).

Trong khi kiểm soát người dùng trên hệ thống trong suốt quá trình ứng cứu, có thể cần thiết để so sánh máy bị nhiễm với máy bình thường để lấy danh sách người dùng nên ở trong hệ thống của người sỡ hữu. Sẽ chính xác hơn nếu có một bản snapshot trước khi tấn công xảy ra khi lấy danh sách người dùng.

Để đảm bảo việc phân tích cụ thể cho người dùng trên hệ thống, trước hết cần phải xác định người dùng trên hệ thống.

Bằng cách đọc /etc/passwd, các người dùng được định nghĩa trên hệ thống có thể được xác định ở đây.

```
cat /etc/passwd
```

![image15](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image15.png)

Kẻ tấn công thường ưu tiên các tên như *support, service, dev, admin và sysadmin* cho những người dùng mà chúng tạo ra để ngăn bị phát hiện. Chúng ta nên tập trung vào những người dùng có tên này.

Nếu file *passwd* có quyền sai, những người dùng có độc hại có thể chỉnh sửa nội dung nó. Kẻ tấn công có thể chính người dùng bằng cách bỏ dấy "x" kế bên username với mật khẩu mà chúng tạo. Vì lý do này, thông tin trong trường password trong file *passwd* nên được kiểm tra cẩn thận trong suốt quá trình ứng cứu sự cố.

Ngoài ra, thông tin shell của người dùng nên được kiểm tra. Thông tin shell của người dùng không nên có shell nên được kiểm tra.

Nếu kẻ tấn công không làm sạch file *auth.log*, nó có thể phát hiện người dùng mới được thêm htoong tin file auth.log.

```shell
tail /var/log/auth.log
```

![image16](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image16.png)

Bạn có thể tìm người dùng mới bằng cách tìm kiếm cụm "useradd" trong file auth.log.


```shell
grep useradd /var/log/auth.log
```

![image17](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image17.png)

Bạn có thể xác minh người dùng có password bị thay đổi bằng cách tìm kiếm từ khóa "passwd" trong auth.log

```shell
grep passwd /var/log/auth.log
```

![image18](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image18.png)

### Xác minh quyền của người dùng
Như đã đề cập trước đó, phát hiện người dùng đọc hại là không đủ để xác đinh rủi ro. Sau khi xác định người dùng, group của những người dùng này, và quyền được chỉ định cho học cũng phải được xác đinh.

Điểm bắt đầu tốt là xem xét nhóm mà người dùng đi kèm và kiểm tra quyền của họ.

Chúng ta phải xem xét nhóm và những người dùng trong nhóm thông qua file */etc/group*. Nội dung trong file group có thể xem sử dụng lệnh cat.

```shell
cat /etc/group
```

![image19](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image19.png)

Trong khi tiến hành xem xét, chúng ta phải tập trung và vào nhóm quan trọng nhát và những người dùng trong nhóm này. Người dùng không nên ở trong nhóm này nên được xác định. Ví dụ, *www-data* mà ở trong nhóm sudo sẽ là bất thường. Một số nhóm quan trọng được liệt kê bên dưới:
* root
* adm
* shadow
* sudo

File khác cũng được kiểm tra để hiểu về ủy quyền của người dùng hoặc nhóm là *"/etc/sudoers"*. Có thông tin về người dùng và nhóm có thể sử dụng quyền sudo ở mức độ nào trên tệp này.

```shell
cat /etc/sudoers
```

![image20](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image20.png)

Trong file sudoers, người dùng không được ủy quyền và quyền sudo có thể dẫn đến hệ thông bị xâm phạm không được xác định. Ngoài ra, cấu hình không đúng trên file này nên được xác định.

Bạn có thể liệt kê tiếnh trình group bằng cách tìm kiếm *"groupadd"* và *"usermod"* trong auth.log. Liệt kệ thay đổi group trong ngày bị tấn công sẽ dễ hơn để theo dõi hành động được thực hiện bởi kẻ tấn công.

```shell
grep groupadd /var/log/auth.log
```

![image21](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image21.png)

```shell
grep usermod /var/log/auth.log
```

![image22](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image22.png)

### Xác minh những người dùng đã đăng nhập vào hệ thống

Với sự hỗ trở của một số công cụ được cài sẵn trong hầu hết hệ thống Linux, người dùng với kết nối trực tiếp vào hệ điều hành có thể được liệt kê. Chúng tôi khuyến nghị cài tối thiểu công cụ để bảo tồm tính riêng tư của thiết bị trong suối tiến trình ứng cứu. Có một số công công cụ khác nhau có thể sủ dụng để phát hiện người dùng đăng nhập trên GNU/Linux.

Theo mặc đinh, w, who, users và lasts được bao gồm trong GNU/Linux. Với sự hỗ trợ của chúng, bạn có thể xác minh người dùng nào đã đăng nhập vào hệ thống.

Các công cụ này cũng có ưu và nhược. Tuy nhiên, việc lựa chọn "last" sẽ đẩy nhanh quá trình ứng cứu, vì nó cung cấp nhiều thông tin hơn và lịch sữ dữ liệu. Nếu không có tham số cho trước, nó sẽ đưa lịch sử đăng nhập của toàn bộ người dùng.

```shell
last
```

![image23](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image23.png)

Lệnh last lấy các thông tin này từ *"/var/log/wtmp"*. Bạn có thể lấy cùng thông bằng cách đọc file này, nhưng lệnh last cung cấp thông tin ở định dạng dễ đọc hơn.

```shell
cat /var/log/wtmp
```

![image24](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image24.png)

File /var/log/auth.log có thể được xem xét để phát hiện người dùng đã đăng nhập vào hệ thống thông qua SSH. File này bao gồm những lần đăng nhập thành công cũng như thất bại. Bằng cách này, chúng ta có thể phát hiện tân công vét cạn từ auth.log.

Bạn có thể lieejft kê các lần đăng nhập thất bịa với lệnh

```shell
grep "Failed password" /var/log/auth.log
```

![image25](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image25.png)

Một cách khác, đăng nhập SSH thất bại có thể xác định với lệnh jouralctl.

```shell
journalctl _SYSTEMD_UNIT=ssh.service | egrep "Failed|Failure"
```

### Xác minh những người dùng có thể thực hiện SSH
Trong quá trình ứng cứu có thể cần thiết phải phát hiện ai có thể điều kiển từ xa thiết bị sử dụng SSH. Bạn có thể tìm hiểu với ai có thê tiến hành RDP ở trên Windows bằng các liệt kê người dùng nằm trong group "Remote Desktop Users". Tuy nhiên, không có nhóm tương tự trong Linux. Các bước sau đây nên được làm theo để phát hiện ai có thể thực hiện SSH.

1. Bằng cách đọc */etc/passwd*, người dùng trên hệ thống được pahst hiện.
2. Người dùng không có một shell đúng bị loại bỏ khỏi danh sách.
3. Người dùng không có password đúng bị loại bỏ khỏi danh sách
4. Ngươi dùng có quyền SSH có thể phát hiện trong */etc/ssh/sshd_config*. Nếu "AllowUsser" được chỉ định trong file, có nghĩa là những người dùng khác sẽ không thể sử dụng dịch vụ SSH.

### Eradication (diệt trừ)
Giai đoạn cuooist ứng cứu, hệ thống phải được khooig phục về điều kiện hoạt động ban đầu giống nhwu chưa bị tấn công.

Những người dùng được thêm vào bởi kẻ tấn công nên bị xóa khỏi hệ thống. Bạn có thể xóa người dùng và thư mục chính với lệnh sau.

```shell
userdel -r USERNAME
```

![image26](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image26.png)

Người dùng không được ủy quyền nên bị xóa khỏi group quyền cao. Bạn có thể xóa người dùng khỏi group bằng lệnh

```shell
gpasswd -d USERNAME GROUP
```

![image27](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image27.png)

Quyền sudo cho người dùng nên được loại bỏ. Bạn có thể chỉnh quyền sudo thông qua lệnh visudo

```shell
visudo
```

![image28](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image28.png)

Password của người dùng phải được thay đổi và khóa SSH nên được tạo lại.

Bạn có thể dùng lệnh passwd để thay đổi password

```shell
passwd USERNAME
```

![image29](https://letsdefend.io/images/academy/linux-incident-response/users-and-groups/linux-users-and-groups-image29.png)

Để tạo lại khóa SSH mới, khóa cũ phải được xóa trức. Sau đó tạo một khóa SSH mới.

