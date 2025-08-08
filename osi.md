# Mô hình mạng OSI

- Mô hình osi là một khuôn khổ 7 lớp. Nhằm tiêu chuẩn hóa các chức năng của hệ thống máy tính
- Osi còn là khuôn khổ mô tả cách các máy tính giao tiếp với nhau trong các mạng và môi trường đám mây

# Cấu trúc tổng thể của mô hình OSI
- Mô hình được chia làm 7 lớp và được trình bày từ trên xuống dưới (7 -> 1)
- Các lớp này có thể được chia thành 3 nhóm chính dựa vào vai trò của chúng

#### Các lớp phần mềm (Software Layers):
- Bao gồm các lớp 7,6,5
    - Lớp ứng dụng
    - Lớp trình bày
    - Lớp phiên
> Đây là nơi diễn ra hoạt động truyền dẫn liên quan đến các ứng dụng phần mềm, hệ điều hành, trình duyệt web

#### Lớp trái tim của OSI (Heart of OSI):
- Bao gồm một lớp là lớp 4
    - Lớp giao vận
> Đây là lớp quan trọng trong việc truyền dẫn đầu cuối thực tế giữa các hệ thống khác nhau

#### Các lớp phần cứng (Hardware Layers):
- Bao gồm các lớp còn lại 3,2,1
    - Lớp mạng
    - Lớp liên kết dữ liệu
    - Lớp vật lí
> Đây là hành trình dữ liệu đi qua các thành phần vật lý và hạ tầng mạng trên mỗi hệ thống khi nó được xử lý để truyền hoặc nhận

# Các chức năng chính của từng lớp
- Lớp 7: Lớp Ứng dụng (Application Layer)
    > Là lớp gần người dùng cuối nhất. Nó cung cấp các giao thức (như HTTP, HTTPS, FTP, DNS) cho phép phần mềm/ứng dụng truyền dữ liệu. Chức năng chính bao gồm xác định dịch vụ, kiểm soát truy cập an ninh và thương lượng tài nguyên

- Lớp 6: Lớp Trình bày (Presentation Layer)
    > Đảm bảo dữ liệu được chuẩn bị ở dạng có thể sử dụng được cho lớp ứng dụng (phía nhận) hoặc lớp mạng (phía gửi). Chịu trách nhiệm dịch dữ liệu, mã hóa & giải mã, nén và các mục chuẩn bị dữ liệu khác

- Lớp 5: Lớp Phiên (Session Layer)
    > Tạo và duy trì các phiên (kết nối) cần thiết để hai hệ thống giao tiếp, bao gồm khởi tạo, trao đổi và kết thúc dữ liệu. Nó cũng tạo các điểm kiểm tra để đảm bảo và đồng bộ hóa việc truyền dữ liệu

- Lớp 4: Lớp Giao vận (Transport Layer)
    > Sử dụng các giao thức như TCP và UDP để quản lý lưu lượng mạng, đảm bảo truyền dữ liệu chính xác. Nó phân đoạn dữ liệu từ lớp phiên và tập hợp lại các phân đoạn cho lớp phiên ở phía nhận. Lớp này cũng xử lý kiểm soát luồng và kiểm soát lỗi, điều chỉnh tốc độ truyền và yêu cầu truyền lại nếu cần

- Lớp 3: Lớp Mạng (Network Layer)
    > Quyết định đường dẫn vật lý mà dữ liệu sẽ đi qua nhiều mạng. Chịu trách nhiệm chia nhỏ các phân đoạn của lớp giao vận thành các gói mạng nhỏ hơn và tập hợp lại chúng ở hệ thống nhận, chủ yếu bằng cách sử dụng địa chỉ IP

- Lớp 2: Lớp Liên kết dữ liệu (Data Link Layer)
    > Xác định định dạng dữ liệu trên phân đoạn mạng cục bộ và cho phép truyền dữ liệu giữa hai nút hoặc hệ thống được kết nối trực tiếp trên cùng một mạng. Lớp này cũng sửa lỗi có thể xảy ra ở lớp vật lý và sử dụng xử lý kiểm soát truy cập phương tiện (MAC) cho kiểm soát luồng và đa kênh, cũng như kiểm soát liên kết logic (LLC) cho kiểm soát luồng và lỗi trong phân đoạn mạng cục bộ

- Lớp 1: Lớp Vật lý (Physical Layer)
    > Chuyển đổi và truyền dữ liệu luồng bit thô (1 và 0) qua phương tiện vật lý. Liên quan đến các kết nối vật lý và điện mà hệ thống sử dụng, bao gồm cáp mạng, tần số không dây, và các thông số kỹ thuật vật lý cho việc truyền dữ liệu. Lớp này cũng liên quan đến các thành phần mạng như hub, repeater, modem, NIC, v.v


