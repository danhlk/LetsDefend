# Tấn công Phishing

Tấn công lừa đảo là một loại tấn công mục đích là đánh cắp thông tin cá nhân của người dùng thông thường bằng cách nhấn vào các liên kết độc hại thông qua email hoặc chạy các file độc hại trên máy tính của họ.

Tấn công lừa đảo tương ứng với giai đoạn "Delivery" trong Cyber Kill Chain (chuỗi tấn công) mô hình được tạo ra để phân tích tấn công mạng. Nơi đây là là nơi các kẻ tấn công truyền nội dung độc hại đã được chuẩn bị trước đến hệ thống nạn nhân.

![image1](https://umuttosun.com/wp-content/uploads/2020/06/Intrusion_Kill_Chain_-_v2-1.png)

Kẻ tấn công thường lừa nạn nhân nhấn vào các đường link độc hại đính kèm trong mail, như "Bạn vừa chiến thắng món quà", "Đừng bỏ lỡ đợt giảm giá lớn này", "Nếu không click vào link này tài khoản của bạn sẽ bị khóa tạm thời" trực tiếp đến người dùng.

![images2](https://letsdefend.io/blog/wp-content/uploads/2020/08/Screen-Shot-2020-08-22-at-10.43.37-1024x916.png)

```
**__NOTE__**
Tấn công phishing là dạng tấn công phổ biến nhất để khởi tạo truy cập.
```

Tất nhiên, mục đích không chỉ là để đánh cắp thông tin người dùng như mật khẩu. Nó còn dùng để khai thác khía cạnh con người, liên kết yếu nhất trong chuỗi. Kẻ tấn công sử dụng tấn công lừa đảo như là bước đầu tiên để xâm nhập vào hệ thống.


# Information Gathering (thu thập thông tin)

## Spoofing (giả mạo)
Kẻ tấn công có thể gửi emails thay mặt một ai đó, vì email không nhất thiết phải có cơ chế xác thực

Kẻ tấn công có thể gủi email thay mặt người khác sử dụng kỹ thuật gọi là "giải mạp" để làm cho người dùng tin rằng đó là cụôc gọi đáng tin tưởng.

Một số giao thức được tạỏa để ngăn chặn kỹ thuật Email Spoofing (giả mạo emails).

Với sự hỗ trợ của giao thức SPF, DKIM và DMARC, nó có thể nhận biết được liệu địa chỉ nguwoifg gửi email là giả hay thật. Một số ứng dụng mail thực hiện những việc kiểm tra này tự động. Tuy nhiên, việc sử dụng các giao thức này không bắt buộc và trong một số trường hợp có thể dẫn đến vấn đề.

* Sender Policy Framework (SPF)
* DomainKeys Identified Mail (DKIM)

Để tìm kiếm thủ công liệu rằng mail này có phải là giả mạo hay không, địa SMTP của mail phải được học trước.

Bản  ghi SPF, DKIM, DMARC và MX của tên miền có thể được học sử dụng các công cụ như Mxtoolbox. Bằng cách so sánh thông tin ở đây, nó có thể học liệu rằng mail này là giả hay thật.

![image3](https://umuttosun.com/wp-content/uploads/2020/05/Screen-Shot-2020-05-10-at-15.21.06-1-1024x291.png)

Vì địa chỉ IP của một tổ chức lớn sử dụng mail server của chính họ sẽ thuộc về họ, có thể kiểm tra liệu địa SMTP với tổ chức đó bằng cách tìm kiếm trong bản ghi whois của địa chỉ IP SMTP.

Điểm quan trọng ở đây là nếu địa chỉ người gửi không phải là giả mạo, chưng ta cũng không thể nói đó là an toàn. Mail độc hại có thể được gửi bới chính người được tin tưởng do họ đã bị hack. Loại tấn công này đã xảy ra, vì vậy khả năng này cũng cần phải xem xét.

## E-mail Traffic Analysis 
Một số tham số cần thiết khi phân tích tấn công lừa đảo. Chúng ta có thể tìm hiểu quy mô của cuộc tấn công và đối tượng mục tiêu trong kết quả tìm kiếm được thực hiện trên cổng thư theo các thông số sau.
* Địa chỉ nguwoifg gửi (info@letsdefend.io)
* Địa chỉ IP SMTP (127.0.0.1)
* @letsdefend.io (tên miền)
* letsdefend (Bên cạnh tài khoản gmail, kẻ tấn công có thể gửi từ tài khoản hotmail)
* Chủ đề (địa chỉ người gửi và địa chỉ SMTP có thể liên tục thay đổi)

Trong kết quả tìm kiếm, cần thiết phải tìm hiểu địa chỉ người nhận và thông tin thời gian bên canh số mail. Nếu một e-mails độc hại liên tục gửi đến cùng một người dùng, địa chỉ email của họ có thể đã bị lộ trong một cách nào đó và được shared trên các trang như PasteBin.

Kẻ tấn công có thể tìm địa chỉ email với công cụ theHarvester có sẵn trong Kali Linux. Khuyến cáo rằng thông tin đó không nên được chia sẻ rõ ràng, vì việc lưu giữ các địa chỉ mail cá nhân trên các trang web sẽ là một phương tiện tấn công tiềm ẩn cho những kẻ tấn công.

```
**__NOTE__**
Nếu những mail được gửi ngoài giờ làm việc, kẻ tấn công có thể ở trong múi giờ khác. Bằng cách thu thập thông tin, chúng ta có thể bắt đầu hiểu về cuộc tấn công.
```


# Static Analysis (phân tích tĩnh)

Có một sự thật là những email viết bằng văn bản thuần túy rất dễ nhàm chán. Vì lí do này, ứng dụng mail cung cấp hỗ trợ HTML, cho phép tạo nội dung email có thể thu hút người dùng hơn. Tất nhiên, tính năng này cũng có bất lợi. Lẻ tấn công có thể tạo e-mail với HTML, ẩn địa chỉ URL độc hai phía sau nút nhấn/đọan text trong có vẻ vô dụng.

![image4](https://letsdefend.io/blog/wp-content/uploads/2020/08/Screen-Shot-2020-08-22-at-10.45.13-1024x242.png)

Như bạn thấy trên hình, địa chỉ mà người dùng thấy khác với khi nhấn vào (địa chỉ thật sẽ hiện ra khi ta để con chuột phía trên).

```
**__NOTE__**
Kẻ tấn công sẽ tạo một tên miền mới trong hầu hết các tấn công lừa đảo và thực hiện tấn công trong vòng vài ngày và kết thúc nó. Vì lý do này, nếu tên miền trong mail là mới, nó có thể là tấn công lừa đảo.
```

Ta có thể kiểm tra liệu chương trình antivirus có thể phát hiện địa chỉ là độc hại bằng cách tìm kiếm nó trên VirusTotal. Nếu một ai đó đã gửi lên phân tích trước đó thì VirusTotal sẽ không phân tích từ đầu, nó sẽ hiển thị kết quả đã phân tích trước đó. Chúng ta có thể sử dụng tính năng này với cả ưu và nhược điểm.

![image5](https://umuttosun.com/wp-content/uploads/2020/05/Screen-Shot-2020-05-04-at-05.07.11-1024x156.png)

Nếu kẻ tấn công tìm kiếm địa chỉ miền trên VirusTotal mà không chức nội dung độc hại trên đó, địa chỉ này sẽ xuất hiện vô hại trên VirusTotal, và nó sẽ không được chú ý. Trong ảnh trên, bạn có thể thấy địa chỉ xuất hiện vô hại, nhưng nếu nhìn kỹ hơn trong vùng trỏ đỏ, địa chỉ này đã được quét 9 tháng trước. Để phân tích lại, nút nhấn với mũi tên xanh cần được nhấn.

Nếu trang đã được tìm kiếm trước đây trên VirusTotal, nó có thể nghĩa là kẻ tấn công muốn xem tỷ lệ phát hiện của trang trong suốt quá trình chuẩn bị. Nếu chúng ta phân tích lại, chương trình antivirus phát hiện nó là lừa đảo, có nghĩa kẻ tấn công có động thánh đánh lừa các nhà phân tích.

Thực hiện phân tích tĩnh của files trong mail có thể kích hoạt khả năng học về khả năng của tệp đó. Tuy nhiên, vì phân tích tĩnh tốn nhiều thời gian, bạn có thể lấy được kết quả nhanh hơn với phân tích động.

Cisco Talos Intellingence có các phần tìm kiếm nơi chúng ta có thể tìm hiểu độ danh tiếng của các địa chỉ IP. Bằng cách tìm kiếm địa chỉ SMTP của mail chúng phát hiện trên Talos, chúng ta có thể thấy độ danh tiếng của địa chỉ IP và tìm kiếm liệu nó được bao gồm trong danh sách đen hay không. Nếu địa chỉ SMTP nằm trong danh sách đen, nó có thể được hiểu là một kẻ tấn công đã tạo nó trên một server bị xâm nhập.

![image6](https://umuttosun.com/wp-content/uploads/2020/05/Screen-Shot-2020-05-10-at-15.26.00-1-1024x453.png)

Tương tự, địa chỉ SMTP có thể được tìm kiếm trên VirusTotal và AbuseIPDB để xác định liệu địa chỉ IP trước đó có liên quan đến hành vi đọc hịa hay không.


# Dynamic Analysis (phân tích động)

URLs và files có thể được tìm thất trong mail. Các files này và URLs cần được kiểm tra. Bạn không muốn dữ liệu của bạn bị đánh cắp bới kẻ tấn công bởi việc chạy các files này trên máy tính cá nhân của bạn. Vì lý đó này, các trang wweb và files đính kèm trong mail nên được chạy trong một sandbox (hộp cát) và những thay đổi thực hiện trong hệ thống sẽ được kiểm tra, và nó nên được kiểm tra liệu chúng có gây hại hay không.

![image7](https://letsdefend.io/blog/wp-content/uploads/2020/08/Screen-Shot-2020-08-22-at-10.52.32-1024x498.png)

Nếu bạn muốn nhanh chóng kiểm trên địa chỉ trong mail, bạn có thể xem nội dung web sử dụng trình duyệt online như Broserling. Điểm tốt của các dịch vụ này là bạn sẽ không bị ảnh hưởng bởi khai thác 0-day gây ảnh hưởng đến trình duyệt, vì không phải trực tiếp truy cập web từ máy của bạn. Bất lợi của Broserling là nếu files độc hại được tải về, bạn không thể chạy nó. việc phân tích của bạn sẽ bị gián đoạn.

![image8](https://letsdefend.io/blog/wp-content/uploads/2020/08/Screen-Shot-2020-08-22-at-10.45.13-1024x242.png)

Trước khi đi đến trang wweb trong mail, cần phải kiểm tra liệu có thông tin quan trọng trong địa chỉ đó. Khi chúng ta xem xét ví dụ trong ảnh trên, khi người dùng nhấn vào [populeralisverissitesi.com](http://populeralisverissitesi.com), ta thấy được địa chỉ thật, và địa chỉ email của người dùng được sử dụng trong tham số. Thậm chí nếu người dùng không nhập mật khẩu trong trang lừa đảo, có nghĩa là liên kết trong mail được truy cập khi đến địa chỉ này và kẻ tấn công hiểu rằng người dùng này hợp lệ. Nó có thể làm tăng tỉ lệ thành công của cuộc tấn công mà nó sẽ thực hiện bằng cách thực hiện các cuộc tán công kỹ thuật xã hội đối với những ngườ dùng hợp lệ trong các cuộc tấn công sẽ thực hiện sau này. Vì lí do này, cần thiết phải thay đổi thông tin như địa chỉ e-mail khi truy cập trang này.
![image9](https://letsdefend.io/blog/wp-content/uploads/2020/08/Screen-Shot-2020-08-22-at-10.48.01.png)

Bạn có thể xem xét file đáng nghi và website trong sandbox. Khi bạn xem xét files trong môi trường này, bạn loại bỏ các mối đe dọa của việc lây nhiễm đến máy tính với mã độc. Nhiều dịch vụ/sản phẩm sandbox khả dụng. Các sản phẩm/dịch vụ này khả dụng cho trả phí và miễn phí. Bạn có thể chọn một/nhiều tùy theo nhu cầu.

Một số sandbox phổ biến:
* VMEay
* Cuckoo Sandbox
* Joe Sandbox
* AnyRun
* Hybrid Analysis (Falcon Sandbox)

```
**__NOTE__**
Mã độc có thể một khoản thời gian mà không thực hiện bất kỳ hành động nào. Bạn phải chờ cho mã độc hoạt động trước khi quyết định việc xem xét file có độc hại hay không.
```

Sự thật là không có URLs và files trong mail không nghĩa là nó không độc hại. Kẻ tấn công cũng có thể gửi nó như là một bức ảnh để không bị bắt trong các sản phẩm phân tích.


# Additional Techniques

Kỹ thuật khác mà kẻ tấn công sử dụng là thực hiện tấn công lừa đảo sử dụng các trang hợp pháp. Một số chúng như sau
* Sử dụng các dịch vụ cung cấp kho lưu trữ đám mây như Google hay Microsoft
  * Kẻ tấn công thử nhấn vào Google/Microsoft có vẻ vô hại với người dùng bằng cách tải một tập tin độc hại lên drive đó.
* Sử dụng dịch vụ ho phép tạo một tên miền con như Microsoft, Wordpress, Blogspot, Wix
  * Kẻ tấn công cố gắng đánh lừa các sản phẩm bảo mật bằng cách tạo một tên miền con từ các dịch vụ này. Vì thông tin whois không thể tifm kiếm một tên miền con, nó có thể hiểu rằng những địa chỉ này được tạo trong quá khứ và thuộc về các tổ chức như Microsoft, Wordpress.
* Từ ứng dụng
  * Các dịch vụ khả dụng cho phép tạo nội dung miễn phí. Kẻ tấn công có thể sử dụng các dịch vụ này thay vì tạo một trang lửa đảo cho riêng mình. Vì tên miền là vô hại trong điều kiện bình thường, nó có thể được chuyển sang người dùng mà không bị dính phần mềm antivirus. Google Form là một ví dụ của các dịch vụ này. Khi tìm kiếm thông tin whois, tên miền sẽ được thấy là Google, nên kẻ tấn công có thể làm phân tích sai.
