# HTTP/HTTPS
- Giao thức dùng cho truyền tải tài liệu web. HTTPS thêm SSL/TLS để mã hóa, đảm bảo an toàn. HTTP hoạt động ở lớp ứng dụng

# TCP (Transmission Control Protocol)
- Về bộ giao thức này mình đã nói rất chi tiết ở folder **mo_hinh_mang** rồi nên sẽ không đề cập ở đây nữa

# UDP (User Datagram Protocol)
- Khác với TCP, UDP không yêu cầu bất kì hình thức giao tiếp trước nào giữa các thiết bị để bắt đầu gửi dữ liệu
- Chính vì không yêu cầu hình thức nào nên UDP trở thành một giao thức **không kết nối**
- UDP có lợi thế về mặt tốc độ trễ, nhưng đây cũng là con dao 2 lưỡi khi nó không thực hiện đủ các bước để đảm bảo tính bảo mật và toàn vẹn dữ liệu
- Thời gian chạy được rút ngắn này giúp UDP phù hợp hơn với các ứng dụng nhạy cảm về thời gian, trong đó tốc độ truyền tải quan trọng hơn việc đảm bảo dữ liệu được sắp xếp chính xác hoặc được nhận toàn bộ. Tra cứu Hệ thống Tên miền và kiểm tra thời gian mạng là hai ứng dụng phổ biến của UDP

# SSL/TLS
- Giao thức mã hóa ở lớp Presentation hoặc Application để bảo mật HTTP thành HTTPS, thiết lập kênh bảo mật

# VPN / IPSec
- VPN tạo kênh **mạng ảo bảo mật qua Internet**. IPSec là bộ giao thức bảo mật (mã hóa, xác thực) thường dùng cho VPN

# DNS (Domain Name System)
- Giao thức ứng dụng dùng UDP/TCP để dịch tên miền thành địa chỉ **IP**, là thành phần không thể thiếu của giao thức Internet

# IP
1. **Vai trò và định nghĩa**:
    - **Giao thức Internet (IP)** là giao thức giao tiếp lớp mạng trong bộ giao thức Internet (Internet protocol suite)
    - Nhiệm vụ chính của nó là **chuyển tiếp các gói dữ liệu (datagrams) qua các ranh giới mạng**
    - Chức năng định tuyến của IP cho phép kết nối liên mạng (internetworking) và về cơ bản đã hình thành nên Internet
    - IP có nhiệm vụ gửi gói dữ liệu từ máy chủ nguồn đến máy chủ đích chỉ dựa vào các địa chỉ IP trong tiêu đề gói

2. **Chức năng chính**:
    - Định địa chỉ giao diện máy chủ (addressing host interfaces)
    - Đóng gói dữ liệu vào các gói tin (datagrams), bao gồm việc phân mảnh (fragmentation) và lắp ráp lại (reassembly)
    - Định tuyến các gói tin từ một giao diện máy chủ nguồn đến một giao diện máy chủ đích qua một hoặc nhiều mạng IP
    - IP định nghĩa định dạng của các gói tin và cung cấp một hệ thống định địa chỉ
    - Mỗi gói tin IP có hai thành phần: tiêu đề (header) và dữ liệu (payload). Tiêu đề IP chứa địa chỉ IP nguồn, địa chỉ IP đích và các siêu dữ liệu khác cần thiết để định tuyến và chuyển giao gói tin. Dữ liệu là thông tin được truyền tải. Phương pháp này được gọi là đóng gói (encapsulation)

3. **Các phương thức định địa chỉ**:
    - Unicast: Gửi tin nhắn đến một nút cụ thể duy nhất (một-đến-một)
    - Broadcast: Gửi tin nhắn đến tất cả các nút trong mạng (một-đến-tất cả)
    - Multicast: Gửi tin nhắn đến một nhóm các nút đã bày tỏ sự quan tâm đến việc nhận tin nhắn (một-đến-nhiều-trong-số-nhiều)
    - Anycast: Gửi tin nhắn đến bất kỳ một nút nào trong một nhóm các nút, thường là nút gần nhất với nguồn (một-đến-một-trong-số-nhiều)

4. **Lịch sử phiên bản quan trọng**:
    - IP phiên bản 4 (IPv4) là giao thức chiếm ưu thế trên Internet hiện nay. Nó sử dụng địa chỉ 32-bit, cung cấp khoảng 4,3 tỷ địa chỉ. IPv4 được định nghĩa trong RFC791 (1981)
    - IPv6 là phiên bản kế nhiệm của IPv4. IPv6 sử dụng địa chỉ 128-bit, cung cấp khoảng 3.4 x 10^38 địa chỉ. Việc triển khai IPv6 trên Internet công cộng đã gia tăng kể từ khoảng năm 2006
    - Các phiên bản IP từ 1 đến 3 là các phiên bản thử nghiệm. Phiên bản 5 (Internet Stream Protocol) không được áp dụng

5. **Tính không đáng tin cậy và Best-Effort Delivery**:
    - Thiết kế của bộ giao thức Internet tuân thủ nguyên tắc "end-to-end", coi rằng hạ tầng mạng vốn không đáng tin cậy tại bất kỳ phần tử mạng hoặc phương tiện truyền dẫn nào, và là động về sự sẵn có của các liên kết và nút
    - IP chỉ cung cấp dịch vụ "best-effort delivery" (nỗ lực tốt nhất để gửi) và được đặc trưng là không đáng tin cậy (unreliable)
    - Đây là một giao thức không kết nối (connectionless protocol)
    - Các điều kiện lỗi như hỏng dữ liệu, mất gói và trùng lặp gói có thể xảy ra. Do định tuyến là động, các gói khác nhau có thể được định tuyến đến cùng một đích thông qua các đường dẫn khác nhau, dẫn đến việc gói tin đến không đúng thứ tự tại phía nhận
    - Các giao thức lớp trên của bộ giao thức Internet (như TCP) chịu trách nhiệm phát hiện và bù đắp các điều kiện lỗi và giải quyết các vấn đề về độ tin cậy
    - IPv4 cung cấp kiểm tra tổng kiểm tra tiêu đề (header checksums) để đảm bảo tiêu đề không bị lỗi, và các nút định tuyến sẽ loại bỏ các gói tin không vượt qua kiểm tra này. Ngược lại, IPv6 hoạt động không có tổng kiểm tra tiêu đề, vì công nghệ lớp liên kết hiện tại được cho là cung cấp đủ khả năng phát hiện lỗi

6. **Khả năng liên kết và Dung lượng**:
    - Không có sự đảm bảo rằng bất kỳ đường dẫn cụ thể nào thực sự có khả năng hoặc phù hợp để thực hiện việc truyền dữ liệu
    - IP có khả năng kiểm tra kích thước đơn vị truyền tối đa (MTU) của liên kết cục bộ. "Path MTU Discovery" có thể được sử dụng cho toàn bộ đường dẫn đến đích
    - IPv4 tự động phân mảnh một gói tin lớn thành các đơn vị nhỏ hơn để truyền khi MTU bị vượt quá. IP cũng cung cấp khả năng sắp xếp lại các mảnh nhận được không đúng thứ tự
    - Mạng IPv6 không thực hiện phân mảnh tại các phần tử mạng, nhưng yêu cầu các máy chủ cuối và các giao thức lớp cao hơn phải tránh vượt quá MTU đường dẫn

7. **Bảo mật**:
    - Trong giai đoạn thiết kế ARPANET và Internet ban đầu, các khía cạnh và nhu cầu bảo mật của một mạng công cộng, quốc tế đã không được lường trước đầy đủ
    - Do đó, nhiều giao thức Internet đã bộc lộ các lỗ hổng. Các đánh giá bảo mật kỹ lưỡng và đề xuất giảm thiểu vấn đề đã được công bố vào năm 2008

