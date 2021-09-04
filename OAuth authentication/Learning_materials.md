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
3. Khi nó đã nhận được dữ liệu, ứng dụng khách sẽ sử dụng nó thay cho tên người dùng để đăng nhập người dùng.
   Mã thông báo truy cập mà nó nhận được từ máy chủ ủy quyền thường được sử dụng thay vì mật khẩu truyền thống.

## 4. Lab: Authentication bypass via OAuth implicit flow

người dùng đăng nhập bằng tài khoản mạng xã hội của họ. Việc xác thực sai quy định của ứng dụng khách khiến kẻ tấn công có thể đăng nhập vào tài khoản của người dùng khác mà không biết mật khẩu của họ.

![image](https://user-images.githubusercontent.com/76999751/132077936-0e587769-d4c6-48de-a540-ca8f1c93abd1.png)

- http history:

![image](https://user-images.githubusercontent.com/76999751/132078393-d99ad5c7-5302-40e0-9f87-bf6367048f60.png)

- thay đổi object email 

![image](https://user-images.githubusercontent.com/76999751/132078520-985cd023-86c7-481c-9e5a-0c824d6f0f8c.png)

- Request browser 

![image](https://user-images.githubusercontent.com/76999751/132078547-6fb430d2-5448-491b-a59d-1e1751055f4a.png)

- Với session mới của user carlot ta dễ dàng đăng nhập được

![image](https://user-images.githubusercontent.com/76999751/132078590-e7f31c81-a6a5-47da-8e66-ef2a607281dd.png)



  
  
  
  
  
  
  
  
  
