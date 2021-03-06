## 1. What is OAuth?
- OAuth là khung ủy quyền thường được sử dụng cho phép các trang web và ứng dụng web yêu cầu quyền truy cập hạn chế vào tài khoản của người dùng trên một ứng dụng khác. 
- OAuth cho phép người dùng cấp quyền truy cập này mà không để lộ thông tin đăng nhập của họ vào ứng dụng yêu cầu

![image](https://user-images.githubusercontent.com/76999751/132077761-4255856b-8f7c-424e-84c0-2ed30607d5cf.png)

## 2. How does OAuth 2.0 work?
- Nó hoạt động bằng cách xác định một loạt các tương tác giữa ba bên riêng biệt, cụ thể là ứng dụng khách, chủ sở hữu tài nguyên và nhà cung cấp dịch vụ OAuth.

- Client application - Trang web hoặc ứng dụng web muốn truy cập dữ liệu của người dùng.
- Resource owner - Người dùng có dữ liệu mà ứng dụng khách muốn truy cập.
- OAuth service provider -  Trang web hoặc ứng dụng kiểm soát dữ liệu của người dùng và quyền truy cập vào nó. 
  Họ hỗ trợ OAuth bằng cách cung cấp API để tương tác với cả máy chủ ủy quyền và máy chủ tài nguyên
## 3. OAuth authentication
- Xác thực OAuth thường được triển khai như sau:
1. Người dùng chọn tùy chọn để đăng nhập bằng tài khoản mạng xã hội của họ. Sau đó, ứng dụng khách sử dụng dịch vụ OAuth của trang web truyền thông
xã hội để yêu cầu quyền truy cập vào một số dữ liệu mà nó có thể sử dụng để xác định người dùng. 
`Ví dụ: đây có thể là địa chỉ email được đăng ký với tài khoản của họ.`
2. Sau khi nhận được access token, client sẽ request dữ liệu từ source server 
3. Khi nó đã nhận được dữ liệu, ứng dụng client sẽ sử dụng nó thay cho tên người dùng để đăng nhập người dùng.
   Mã thông báo truy cập mà nó nhận được từ máy chủ ủy quyền thường được sử dụng thay vì mật khẩu truyền thống.



## 5. Nguyên nhân phát sinh lỗ hổng
- xác thực đầu vào yếu
- cấu hình bảo mật sai
- rò rỉ dữ liệu nhạy cảm

## 6. Identifying OAuth authentication
Nhận biết khi ứng dụng đang sử dụng xác thực OAuth tương đối đơn giản. Nếu bạn thấy tùy chọn đăng nhập bằng tài khoản của mình từ một trang web khác, thì đây là dấu hiệu mạnh mẽ cho thấy OAuth đang được sử dụng.

Cách đáng tin cậy nhất để xác định xác thực OAuth là proxy truy cập của bạn thông qua Burp và kiểm tra các thông báo HTTP luôn luôn request đến  `/authorization` endpoint

VD:
```http
GET /authorization?client_id=12345&redirect_uri=https://client-app.com/callback&response_type=token&scope=openid%20profile&state=ae13d489bd00e3c24 HTTP/1.1
Host: oauth-authorization-server.com
```

  
  
  
  
  
  
  
  
  
