README – Kết quả kiểm thử hiệu năng bằng JMeter
1. Giới thiệu
Dự án sử dụng Apache JMeter để kiểm thử hiệu năng của các trang web bằng cách gửi nhiều request giả lập từ người dùng (threads).
Các request được kiểm thử gồm:
GET Homepage
GET Subpage
GET Page 1
GET Page 2
Kết quả được hiển thị trong Summary Report.

2. Kết quả kiểm thử
Test 1
Endpoint: GET Homepage
Samples	Average	Min	Max	Error	Throughput
50	120 ms	44 ms	769 ms	0%	37.5 request/sec
Nhận xét:
Trang Homepage phản hồi ổn định, không có lỗi.

Test 2
Endpoint: Homepage và Subpage
Request	Samples	Average	Error
GET Homepage	50	157 ms	0%
GET Subpage	50	51 ms	100%
Nhận xét:
Homepage hoạt động bình thường, nhưng Subpage bị lỗi toàn bộ request.
Test 3
Endpoint: Page 1 và Page 2
Request	Samples	Average	Error	Throughput
GET Page 1	11940	47 ms	100%	198.8/sec
GET Page 2	11933	47 ms	100%	199.2/sec
Nhận xét:
Hệ thống xử lý được nhiều request nhưng các request đều bị lỗi.

3. Kết luận
Thời gian phản hồi trung bình từ 47–157 ms.
Hệ thống có thể xử lý tối đa gần 400 request/giây.
Một số endpoint bị lỗi 100%, cần kiểm tra lại cấu hình hoặc server.