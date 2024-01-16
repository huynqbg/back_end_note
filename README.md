## JWT

1. Secret key:

   - Nên sử dụng crypto để tạo. Vì nếu bị lộ secret Key thì dễ gây vấn đề bảo mật.

2. Refesh Token (RT):

   - Tại sao cần?
     - Khi access token hết hạn thì RT tạo ra access token mới (đồng thời cũng tạo thêm refresh token mới)
     - Refresh token có exprire lâu hơn access token(AT) rất nhiều.
   - Lưu token ở phía server (Database) (có thể lưu ở redis). Cần lưu trữ RT vào 1 blackList để quản lý RT.
   - Khi Logout thì cần verify RT và xóa RT của user
