# Mô hình TCP/IP
- Nó chủ yếu là một tập hợp các giao thức mạng và tổ chức của các giao thức này thành các lớp khác nhau để mô hình hóa mạng
- Một trong những mục tiêu chính của nó là đảm bảo rằng dữ liệu được gửi từ người gửi đến người nhận một cách an toàn và chính xác. Để làm được điều này, dữ liệu được chia thành các phần nhỏ hơn gọi là gói (packets) trước khi gửi đi. Các gói này di chuyển riêng lẻ và được lắp ráp lại theo đúng thứ tự khi chúng đến đích, giúp ngăn ngừa lỗi và đảm bảo tin nhắn hoàn chỉnh và chính xác

# Các lớp mô hình TCP/IP
- Đối với mô hình TCP/IP được chia thành 4 lớp thay vì 7 lớp như OSI
- Các lớp này là: Application (Ứng dụng), Transport (Giao vận), Network/Internet (Mạng/Internet) và Network Access (Truy cập Mạng)

# Các chức năng chính của từng lớp
- Lớp ứng dụng (Application Layer):
    - Đây là lớp trên cùng và gần với người dùng nhất
    - Đây là nơi các ứng dụng như trình duyệt web, ứng dụng email, hoặc công cụ chia sẻ tệp kết nối với mạng
    - Nó hoạt động như một cầu nối giữa phần mềm của bạn (ví dụ: Chrome, Gmail) và các lớp thấp hơn của mạng để thực sự gửi và nhận dữ liệu
    - Hỗ trợ các giao thức khác nhau như HTTP, FTP, SMTP và DNS
    - Quản lý các vấn đề như định dạng dữ liệu (để cả người gửi và người nhận hiểu dữ liệu), mã hóa (để giữ an toàn dữ liệu) và quản lý phiên (để theo dõi các kết nối đang diễn ra)

- Lớp giao vận (Transport Layer):
    - **Chịu trách nhiệm đảm bảo dữ liệu được gửi một cách đáng tin cậy và theo đúng thứ tự giữa các thiết** bị
    - Kiểm tra xem dữ liệu bạn gửi (tin nhắn, tệp, video) có đến an toàn và đầy đủ không
    - Sử dụng hai giao thức chính: TCP (Transmission Control Protocol) và UDP (User Datagram Protocol), tùy thuộc vào việc giao tiếp cần độ tin cậy hay tốc độ nhanh hơn
    - TCP được sử dụng khi dữ liệu phải chính xác và đầy đủ (ví dụ: tải trang web, tải tệp). Nó kiểm tra lỗi, gửi lại các phần bị thiếu và giữ mọi thứ theo đúng thứ tự
    - UDP nhanh hơn nhưng không đảm bảo việc gửi dữ liệu, hữu ích cho các ứng dụng như video trực tiếp hoặc trò chơi trực tuyến, nơi tốc độ quan trọng hơn độ chính xác hoàn hảo

- Lớp internet (Internet Layer):
    - **Được sử dụng để tìm đường dẫn tốt nhất cho dữ liệu di chuyển qua các mạng khác nhau để đến đúng đích**
    - Hoạt động như một bộ điều khiển giao thông, giúp các gói dữ liệu di chuyển từ mạng này sang mạng khác cho đến khi chúng đến đúng thiết bị
    - **Sử dụng Giao thức Internet (IP) để gán cho mỗi thiết bị một địa chỉ IP duy nhất, giúp xác định nơi dữ liệu cần đến**
    - Công việc chính của lớp này là định tuyến (quyết định cách tốt nhất để dữ liệu di chuyển), chuyển tiếp gói (di chuyển dữ liệu từ điểm này sang điểm khác), phân mảnh (chia dữ liệu lớn thành các phần nhỏ hơn) và địa chỉ hóa

- Lớp truy cập mạng (Network Access Layer):
    - Là lớp dưới cùng của mô hình TCP/IP
    - Xử lý **kết nối vật lý thực tế giữa các thiết bị trên cùng một mạng cục bộ** (ví dụ: máy tính được kết nối bằng cáp hoặc Wi-Fi)
    - Đảm bảo dữ liệu có thể truyền qua phần cứng, chẳng hạn như dây, bộ chuyển mạch hoặc tín hiệu không dây
    - Xử lý các tác vụ quan trọng như sử dụng địa chỉ MAC để xác định thiết bị, tạo khung (định dạng được sử dụng để gửi dữ liệu qua liên kết vật lý) và kiểm tra lỗi cơ bản trong quá trình truyền

# Cách thức hoạt động của mô hình TCP/IP
- Khi gửi dữ liệu (Từ người gửi đến người nhận):
    - **Lớp Ứng dụng**: Chuẩn bị dữ liệu người dùng bằng cách sử dụng các giao thức như HTTP, FTP hoặc SMTP
    - **Lớp Giao vận** (TCP/UDP): Chia dữ liệu thành các phân đoạn và đảm bảo việc gửi đáng tin cậy (TCP) hoặc nhanh chóng (UDP)
    - **Lớp Internet** (IP): Thêm địa chỉ IP và quyết định đường đi tốt nhất cho mỗi gói
    - **Lớp Liên kết** (Network Access Layer): Chuyển đổi các gói thành khung và gửi chúng qua mạng vật lý
- Khi nhận dữ liệu (Tại đích):
    - **Lớp Liên kết**: Nhận các bit từ mạng và xây dựng lại các khung để chuyển lên lớp tiếp theo
    - **Lớp Internet**: Kiểm tra địa chỉ IP, loại bỏ tiêu đề IP và chuyển tiếp dữ liệu đến Lớp Giao vận
    - **Lớp Giao vận**: Lắp ráp lại các phân đoạn, kiểm tra lỗi và đảm bảo dữ liệu hoàn chỉnh
    - **Lớp Ứng dụng**: Cung cấp dữ liệu cuối cùng cho ứng dụng chính xác (ví dụ: hiển thị trang web trong trình duyệt)

# Ưu điểm của mô hình TCP/IP
- **Khả năng tương tác (Interoperability)**: Cho phép các loại máy tính và mạng khác nhau giao tiếp với nhau, thúc đẩy khả năng tương thích
- **Khả năng mở rộng (Scalability)**: Rất dễ mở rộng, phù hợp cho cả mạng nhỏ và lớn, từ LAN đến WAN như internet
- **Tiêu chuẩn hóa (Standardization)**: Dựa trên các tiêu chuẩn và giao thức mở, đảm bảo các thiết bị và phần mềm khác nhau có thể hoạt động cùng nhau
- **Linh hoạt (Flexibility)**: Hỗ trợ nhiều giao thức định tuyến, loại dữ liệu và phương thức giao tiếp khác nhau, làm cho nó dễ thích nghi với các nhu cầu mạng khác nhau
- **Độ tin cậy (Reliability)**: Bao gồm các tính năng kiểm tra lỗi và truyền lại để đảm bảo truyền dữ liệu đáng tin cậy, ngay cả trên khoảng cách xa và qua các điều kiện mạng khác nhau

# Nhược điểm của mô hình TCP/IP
- Mối lo ngại về bảo mật: TCP/IP ban đầu không được thiết kế với mục đích bảo mật. Mặc dù có nhiều giao thức bảo mật hiện có (như SSL/TLS), chúng đã được thêm vào trên mô hình TCP/IP cơ bản, điều này có thể dẫn đến các lỗ hổng
- Không hiệu quả cho các mạng nhỏ: Đối với các mạng rất nhỏ, sự phức tạp của mô hình TCP/IP có thể không cần thiết và kém hiệu quả so với các giao thức mạng đơn giản hơn
- Bị giới hạn bởi không gian địa chỉ: Hệ thống IPv4 cũ có không gian địa chỉ hạn chế, có thể dẫn đến các vấn đề cạn kiệt địa chỉ trong các mạng lớn hơn (mặc dù IPv6 đã khắc phục vấn đề này)
- Chi phí dữ liệu (Data Overhead): TCP, giao thức truyền tải, bao gồm một lượng đáng kể chi phí để đảm bảo truyền dẫn đáng tin cậy

# Lý do TCP/IP được sử dụng hơn Mô hình OSI:
- TCP/IP được sử dụng rộng rãi hơn mô hình OSI vì nó **đơn giản hơn, thực tế hơn và được chấp nhận rộng rãi cho mạng và Internet trong thế giới thực**
- **Cấu trúc đơn giản hơn**: TCP/IP chỉ có 4 lớp so với 7 lớp của OSI, giúp dễ triển khai và hiểu hơn trong các hệ thống thực tế
- **Thiết kế dựa trên giao thức**: TCP/IP được thiết kế dựa trên các giao thức hoạt động, trong khi mô hình OSI là một khuôn khổ lý thuyết hơn
- **Linh hoạt và Mạnh mẽ**: TCP/IP thích ứng tốt với các phần cứng và mạng khác nhau, bao gồm xử lý lỗi, định tuyến và kiểm soát tắc nghẽn
- **Tiêu chuẩn mở**: TCP/IP là một tiêu chuẩn mở, miễn phí sử dụng và không bị kiểm soát bởi bất kỳ tổ chức nào, giúp nó được chấp nhận rộng rãi
- **Sử dụng thực tế so với Mô hình khái niệm**: Mô hình OSI rất tốt cho giáo dục và các nguyên tắc thiết kế, nhưng TCP/IP là mô hình thực sự được sử dụng trong mạng thực tế
