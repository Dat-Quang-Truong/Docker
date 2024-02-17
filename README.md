# Docker
Bài tập tìm hiểu về Docker.

## Mục lục
   - [Docker và docker-composer là gì](#docker-và-docker-composer-là-gì)
   - [Linux vs Unix vs BSD hay *nix? macOS thuộc loại nào](#linux-vs-unix-vs-bsd-hay-nix-macos-thuộc-loại-nào)
   - [Alpine vs Ubuntu?](#alpine-vs-ubuntu)
   - [VNC](#vnc)

---

## Lý thuyết
### Docker và docker-composer là gì
   - Docker là một nền tảng để cung cấp cách để building, deploying và running ứng dụng dễ dàng nhanh chóng. Docker đóng gói phần mềm vào các đơn vị tiêu chuẩn hóa được gọi là container có mọi thứ mà phần mềm cần để chạy, trong đó có thư viện, công cụ hệ thống, mã và thời gian chạy. Bằng cách sử dụng Docker, người dùng có thể nhanh chóng triển khai và thay đổi quy mô ứng dụng vào bất kỳ môi trường nào và biết chắc rằng mã của bạn sẽ chạy được.
   - Các containers cho phép lập trình viên đóng gói một ứng dụng với tất cả các phần cần thiết, chẳng hạn như thư viện và các phụ thuộc khác, và gói tất cả ra dưới dạng một package.
   - Lợi ích của docker: Không như máy ảo, Docker start và stop chỉ trong vài giây. Container có thể build và loại bỏ nhanh hơn máy ảo, dễ dàng thiết lập môi trường làm việc. Chỉ cần config 1 lần duy nhất và không bao giờ phải cài đặt lại các dependencies. Nếu thay đổi máy hoặc có người mới tham gia vào project thì chỉ cần lấy config đó và đưa cho họ.
   - Docker Compose là một công cụ hỗ trợ xác định và chạy các ứng dụng Docker multi-container. Nó giúp bạn quản lý nhiều container cùng một lúc trong các môi trường như sản xuất, staging, phát triển, thử nghiệm và CI. Với docker-composer có thể sử dụng file YAML để config các services cho ứng dụng. Sau đó dùng command để create và run từ những config đó.
---
### Linux vs Unix vs BSD hay *nix? macOS thuộc loại nào
Linux: Linux là hệ điều hành mã nguồn mở, được phát triển bởi Linus Torvalds. Nó sử dụng kernel Linux và GNU Tools để tạo thành một hệ điều hành hoàn chỉnh. GNU/Linux là kết hợp giữa các công cụ GNU và kernel Linux.  
Unix: Unix là hệ điều hành gốc, phát triển từ lâu và có nhiều phiên bản khác nhau. Unix là một hệ thống ổn định, đa người dùng, đa tác vụ cho máy chủ, máy tính để bàn và máy tính xách tay. Hệ điều hành Unix được tạo thành từ ba phần: Kernel, Shell và Program.  
BSD: BSD là hệ điều hành nguồn mở tương tự Unix, có kernel riêng và userland riêng (không sử dụng kernel Linux hoặc GNU). BSD bao gồm các phiên bản như FreeBSD, OpenBSD và NetBSD.  
*nix: *nix thường được sử dụng để đề cập đến họ các hệ điều hành có họ từ UNIX. Một số ví dụ bao gồm Linux, FreeBSD.

MacOS thuộc loại Unix vì MacOS sử dụng nhân Darwin là sự kết hợp của Mach, BSD, XNU,... tất cả đều là dẫn xuất của UNIX gốc.

---
### Alpine vs Ubuntu?
Alpine Linux và Ubuntu là hai hệ điều hành phổ biến trong việc xây dựng các container. Alpine Linux thích hợp cho môi trường container hạn chế tài nguyên, trong khi Ubuntu phù hợp cho các trường hợp sử dụng đa dạng. Alpine Linux có một số điểm quan trọng:  
- Kích thước nhỏ: Alpine là một bản phân phối Linux nhẹ và tối giản, chỉ khoảng 133 MB cho phương tiện cài đặt mặc định, được tạo ra đặc biệt cho việc sử dụng trong môi trường container.
- Bảo mật cao hơn: Alpine sử dụng kỹ thuật các tệp thực thi độc lập với vị trí (position-independent executables) để ngẫu nhiên hóa vị trí của các chương trình trong bộ nhớ. Điều này làm cho việc khai thác lỗ hổng trong bộ nhớ trở nên khó khăn hơn và tăng tính bảo mật.
- Cấu hình tối giản: Alpine sử dụng BusyBox để cung cấp hầu hết các tiện ích trong một tệp thực thi, giúp giảm kích thước hệ thống.
- Phù hợp cho container: Kích thước nhỏ của Alpine làm cho nó phù hợp cho việc sử dụng trong các container, đặc biệt là Docker.

Ubuntu là một hệ điều hành trên máy tính, và nó được phát triển dựa trên Linux/Debian GNU:
- Ubuntu không cần cấu hình quá mạnh để chạy nhưng giao diện không thân thiện với người dùng. Đòi hỏi người dùng phải có hiểu biết về công nghệ và thường xuyên dùng lệnh để tương tác với thiết bị.
- Có độ tùy biến cao, hỗ trợ nhiều môi trường GUI (Giao diện đồ họa người dùng).
- Số lượng ứng dụng miễn phí nhiều với số lượng malware hay virus rất ít. Thế nên, việc bảo mật sẽ trở nên an toàn hơn.
- Tốc độ vá lỗi về bảo mật thường nhanh hơn nhờ cộng đồng hỗ trợ lớn, phần lớn là lập trình viên.

---

### VNC
VNC, viết tắt của "Virtual Network Computing", là một hệ thống được sử dụng để chia sẻ màn hình giữa các thiết bị khác nhau với mục đích điều khiển từ xa. Điều này cho phép người dùng từ xa có thể xem và điều khiển màn hình, bàn phím và chuột của một máy tính khác như thể họ đang ngồi trước máy tính đó. VNC hoạt động dựa trên mô hình client/server. Máy tính cần được cài đặt thành một máy chủ VNC, trong khi máy tính khác muốn điều khiển từ xa cần cài đặt một trình xem VNC, hoặc còn gọi là client. Khi hai thành phần này được kết nối, máy chủ VNC sẽ chuyển gửi hình ảnh màn hình từ xa đến trình xem VNC.

VNC có các tính năng nổi bật như giao thức đơn giản, hoạt động độc lập, chia sẻ màn hình giữa người dùng trên nhiều nền tảng và bảo mật quản lý dễ dàng.
