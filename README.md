# Docker
Bài tập tìm hiểu về Docker

## Mục lục
   - [Docker và docker-composer là gì](#docker-và-docker-composer-là-gì)
   - [Linux vs Unix vs BSD hay *nix? macOS thuộc loại nào](#linux-vs-unix-vs-bsd-hay-nix-macos-thuộc-loại-nào)
   - [Alpine vs Ubuntu?](#alpine-vs-ubuntu)
   - [VNC](#vnc)

---

## Lý thuyết
### Docker và docker-composer là gì
 ![image](https://github.com/Dat-Quang-Truong/Docker/assets/113848415/be09cc2c-3dec-4ccf-b82c-649d2ede95ea)

   - Docker là một nền tảng để cung cấp cách để building, deploying và running ứng dụng dễ dàng nhanh chóng. Docker đóng gói phần mềm vào các đơn vị tiêu chuẩn hóa được gọi là container có mọi thứ mà phần mềm cần để chạy, trong đó có thư viện, công cụ hệ thống, mã và thời gian chạy. Bằng cách sử dụng Docker, bạn có thể nhanh chóng triển khai và thay đổi quy mô ứng dụng vào bất kỳ môi trường nào và biết chắc rằng mã của bạn sẽ chạy được.
   - Các containers cho phép lập trình viên đóng gói một ứng dụng với tất cả các phần cần thiết, chẳng hạn như thư viện và các phụ thuộc khác, và gói tất cả ra dưới dạng một package.
   - Lợi ích của docker: Không như máy ảo, Docker start và stop chỉ trong vài giây. Container có thể build và loại bỏ nhanh hơn máy ảo, dễ dàng thiết lập môi trường làm việc. Chỉ cần config 1 lần duy nhất và không bao giờ phải cài đặt lại các dependencies. Nếu thay đổi máy hoặc có người mới tham gia vào project thì chỉ cần lấy config đó và đưa cho họ.
   - Docker Compose là một công cụ hỗ trợ xác định và chạy các ứng dụng Docker multi-container. Nó giúp bạn quản lý nhiều container cùng một lúc trong các môi trường như sản xuất, staging, phát triển, thử nghiệm và CI. Với docker-composer có thể sử dụng file YAML để config các services cho ứng dụng. Sau đó dùng command để create và run từ những config đó.
---
### Linux vs Unix vs BSD hay *nix? macOS thuộc loại nào
Linux: Linux là hệ điều hành mã nguồn mở, được phát triển bởi Linus Torvalds. Nó sử dụng kernel Linux và GNU Tools để tạo thành một hệ điều hành hoàn chỉnh. GNU/Linux là kết hợp giữa các công cụ GNU và kernel Linux.  
Unix: Unix là hệ điều hành gốc, phát triển từ lâu và có nhiều phiên bản khác nhau. Unix là một hệ thống ổn định, đa người dùng, đa tác vụ cho máy chủ, máy tính để bàn và máy tính xách tay. Hệ điều hành Unix được tạo thành từ ba phần: Kernel, Shell và Program.  
BSD: BSD là hệ điều hành nguồn mở tương tự Unix, có kernel riêng và userland riêng (không sử dụng kernel Linux hoặc GNU). BSD bao gồm các phiên bản như FreeBSD, OpenBSD và NetBSD.  
*nix: *nix thường được sử dụng để đề cập đến họ các hệ điều hành có họ từ UNIX. Một số ví dụ bao gồm Linux, FreeBSD.

MacOS thuộc loại Unix vì MacOS sử dụng nhân Darwin là sự kết hợp của Mach, BSD, XNU, ...; tất cả đều là dẫn xuất của UNIX gốc.

---
### Alpine vs Ubuntu?
Alpine Linux và Ubuntu là hai hệ điều hành phổ biến trong việc xây dựng các container.
Alpine Linux là một bản phân phối Linux nhẹ và tối giản, được thiết kế với sự bảo mật cao và hiệu quả về tài nguyên. Alpine Linux có một số điểm quan trọng:  
- Kích thước nhỏ: Alpine là một hệ điều hành nhẹ và tối giản, chỉ khoảng 133 MB cho phương tiện cài đặt mặc định, được tạo ra đặc biệt cho việc sử dụng trong môi trường container.
- Bảo mật cao hơn: Alpine sử dụng kỹ thuật các tệp thực thi độc lập với vị trí (position-independent executables) để ngẫu nhiên hóa vị trí của các chương trình trong bộ nhớ. Điều này làm cho việc khai thác lỗ hổng trong bộ nhớ trở nên khó khăn hơn và tăng tính bảo mật.
- Cấu hình tối giản: Alpine sử dụng BusyBox để cung cấp hầu hết các tiện ích trong một tệp thực thi, giúp giảm kích thước hệ thống.
- Phù hợp cho container: Kích thước nhỏ của Alpine làm cho nó phù hợp cho việc sử dụng trong các container, đặc biệt là Docker.

Ubuntu là một hệ điều hành trên máy tính, và nó được phát triển dựa trên Linux/Debian GNU:
- Ubuntu không cần cấu hình quá mạnh để chạy nhưng giao diện không thân thiện với người dùng. Đòi hỏi người dùng phải có hiểu biết về công nghệ và thường xuyên dùng lệnh để tương tác với thiết bị.
- Có độ tùy biến cao, hỗ trợ nhiều môi trường GUI (Giao diện đồ họa người dùng).
- Số lượng ứng dụng miễn phí nhiều với số lượng malware hay virus rất ít. Thế nên, việc bảo mật sẽ trở nên an toàn hơn.
- Tốc độ vá lỗi về bảo mật thường nhanh hơn nhờ cộng đồng hỗ trợ lớn, phần lớn là lập trình viên.

Tóm lại, Alpine Linux thích hợp cho môi trường container hạn chế tài nguyên, trong khi Ubuntu phù hợp cho các trường hợp sử dụng đa dạng

---

### VNC
VNC, viết tắt của "Virtual Network Computing", là một hệ thống được sử dụng để chia sẻ màn hình giữa các thiết bị khác nhau với mục đích điều khiển từ xa. Điều này cho phép người dùng từ xa có thể xem và điều khiển màn hình, bàn phím và chuột của một máy tính khác như thể họ đang ngồi trước máy tính đó. VNC hoạt động dựa trên mô hình client/server. Máy tính cần được cài đặt thành một máy chủ VNC, trong khi máy tính khác muốn điều khiển từ xa cần cài đặt một trình xem VNC, hoặc còn gọi là client. Khi hai thành phần này được kết nối, máy chủ VNC sẽ chuyển gửi hình ảnh màn hình từ xa đến trình xem VNC.

![image](https://github.com/Dat-Quang-Truong/Docker/assets/113848415/4c1c1b3c-57f2-4326-bbe1-b720be21af68)

VNC có các tính năng nổi bật:
- Giao thức đơn giản: VNC sử dụng giao thức RFB (remote framebuffer) đơn giản và mạnh mẽ. Vì VNC không sử dụng nhiều tài nguyên như CPU và bộ nhớ, nên nó có thể chạy trên phần cứng có công suất thấp.
- Hoạt động độc lập: Giao thức RFB không cần biết rõ về hệ điều hành mà nó đang chạy mà chỉ cần gửi dữ liệu chuột và bàn phím từ máy người dùng đến máy từ xa và gửi dữ liệu hình ảnh từ máy từ xa đến máy người dùng nên việc viết phần mềm VNC cho máy từ xa và máy người dùng trên các hệ điều hành mới là khá dễ dàng.
- Chia sẻ màn hình giữa người dùng và sử dụng trên nhiều nền tảng: Giao thức đơn giản của VNC cho phép nó hoạt động trên nhiều nền tảng. Mặc dù một số giải pháp máy tính từ xa khác có khả năng tương tác trực tiếp với hệ điều hành cơ bản nên có khả năng hoạt động nhanh hơn so với các giải pháp máy tính từ xa dựa trên VNC. Nhưng các công cụ máy tính từ xa dựa trên VNC vẫn có thể được sử dụng để kết nối giữa các nền tảng khác nhau.
- Bảo mật và quản lý dễ dàng: VNC cung cấp các tính năng bảo mật và quản lý cho người dùng. Bạn có thể thiết lập mật khẩu và các cơ chế xác thực để bảo vệ kết nối VNC.
