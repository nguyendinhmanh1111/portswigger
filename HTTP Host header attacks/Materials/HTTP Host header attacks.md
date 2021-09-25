## HTTP Host header attacks

![image](https://user-images.githubusercontent.com/76999751/134766233-27bc9d14-59eb-4ef6-812d-1a9d223ec584.png)

- Tiêu đề Máy chủ HTTP là tiêu đề request từ HTTP / 1.1
- chỉ định tên miền mà client muốn truy cập
-  Ví dụ: khi người dùng truy cập `https://portswigger.net/web-security`, trình duyệt của họ sẽ soạn một yêu cầu có chứa tiêu đề Máy chủ lưu trữ như sau:
```http
GET /web-security HTTP/1.1
Host: portswigger.net
```
- Host có thể bị thay đổi khi đến back-end

### the purpose of the HTTP Host header

- Mục đích của tiêu đề Máy chủ HTTP là giúp xác định thành phần back-end nào mà máy khách muốn giao tiếp.
- Nếu các yêu cầu không chứa tiêu đề Máy chủ lưu trữ hoặc nếu tiêu đề Máy chủ lưu trữ không đúng định dạng theo một cách nào đó, điều này có thể dẫn đến sự cố khi định tuyến các yêu cầu đến ứng dụng dự kiến.

### Virtual hosting
- mỗi trang web riêng biệt này sẽ có một tên miền khác nhau, nhưng tất cả chúng đều chia sẻ một địa chỉ IP chung với máy chủ. Các trang web được lưu trữ theo cách này trên một máy chủ duy nhất được gọi là "máy chủ ảo".

### Routing traffic via an intermediary
- khi các trang web được lưu trữ trên các máy chủ back-end riêng biệt, nhưng tất cả lưu lượng truy cập giữa máy khách và máy chủ được định tuyến thông qua một hệ thống trung gian
- Trong trường hợp này, mặc dù các trang web được lưu trữ trên các máy chủ back-end riêng biệt, tất cả các tên miền của chúng đều phân giải thành một địa chỉ IP của thành phần trung gian.

===> Dẫn đến việc sử dụng HTTP header là cần thiết giống như cùng 1 địa chỉ chung cư mà lại có rất nhiều phòng, HTTP header sẽ xác định chính xác request đến địa chỉ nào

### What is an HTTP Host header attack?
- handle the value of the Host header in an unsafe way.
- kẻ tấn công có thể sử dụng đầu vào này để đưa các tải trọng có hại vào thao tác hành vi phía máy chủ.
- Attacks that involve injecting a payload directly into the Host header are often known as "Host header injection" attacks.
