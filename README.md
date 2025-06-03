# GoFilm

Một trang web xem phim trực tuyến dựa trên vue và gin

Hiển thị hiệu ứng: <a href="https://m.mubai.link/" target="_blank">Nhấp để truy cập trang web demo</a>

Trang web truy cập thử nghiệm phiên bản mới: [Trang web nội dung thử nghiệm](http://113.44.5.201/index)

## Giới thiệu

**GoFilm**

Dự án sử dụng vite + vue làm ngăn xếp công nghệ front-end và ElementPlus làm khung UI để phát triển

Chương trình back-end sử dụng Gin + gorm + go-redis và các khung liên quan khác để cung cấp các dịch vụ giao diện và sử dụng gocolly và robfig/cron để thu thập tài nguyên phim và truyền hình công cộng và các chức năng cập nhật theo lịch trình

## Triển khai dự án

**Phương pháp triển khai**

- [Triển khai Docker](https://github.com/ProudMuBai/GoFilm/blob/main/film/README.md)
- [Triển khai 1Panel (bảng điều khiển trực quan hoạt động)](https://blog.mubai.link/2024/04/21/Docs/gofilm/)

**Hướng dẫn sử dụng**

- Đường dẫn dự án phụ trợ `GoFilm/server`, bao gồm mô tả cấu trúc dự án, mã nguồn chương trình phụ trợ, mô tả giao diện API, biện pháp phòng ngừa khởi động cục bộ [Xem](https://github.com/ProudMuBai/GoFilm/tree/main/server)
- Đường dẫn dự án phụ trợ `GoFilm/client`, bao gồm mô tả cấu trúc dự án, mã nguồn dự án phụ trợ, mô tả tệp cấu hình, phương pháp khởi động cục bộ [Xem](https://github.com/ProudMuBai/GoFilm/tree/main/client)
- Tệp triển khai `GoFilm/film`, bao gồm tất cả các tệp cần thiết để triển khai dự án và các tệp mô tả tương ứng [Xem](https://github.com/ProudMuBai/GoFilm/tree/main/film)
- Tài liệu hướng dẫn sử dụng chương trình: Cung cấp cài đặt và triển khai dự án cũng như các bước sử dụng khởi tạo tương ứng [Nhấp để go](https://blog.mubai.link/2024/04/21/Docs/gofilm/)

## Mô tả phiên bản mới

**Giao diện trang web**

- Nếu bạn cần cải thiện hoặc bổ sung các tính năng mới hoặc hiện có, vui lòng để lại tin nhắn dưới số #71. Chúng tôi sẽ nghỉ vào giữa tháng 1 để có thể tập trung vào việc xử lý

- Phần frontend liên kết một số thông tin như tên trang web và nguồn phát lại với dữ liệu backend, có thể được sửa đổi thông qua backend
- Cấu trúc dữ liệu của chi tiết video và điều hướng trang chủ đã thay đổi, nhưng kiểu vẫn giữ nguyên
- Địa chỉ truy cập mặc định: `IP máy chủ: cổng mặc định [http://127.0.0.1/index]`

**Backend quản trị**

- Đã thêm nhóm chức năng backend quản trị mới, chủ yếu được sử dụng để quản lý `trang web thu thập`, `cập nhật thường xuyên`, `thông tin trang web cơ bản`, `đồng bộ hóa hình ảnh`, `phân loại video`, `thông tin video`, v.v. (một số chức năng đang được cải thiện và sẽ không ảnh hưởng đến việc sử dụng các chức năng hiện có)
- Cần phải đăng nhập để truy cập vào backend quản trị, tài khoản/mật khẩu mặc định: `admin admin` (Thay đổi mật khẩu bằng cách kéo xuống cửa sổ bật lên bên phải sau khi đăng nhập thành công)
- Vui lòng tự xây dựng quyền truy cập cho các tình huống cụ thể
- Địa chỉ truy cập mặc định: `Máy chủ IP: cổng mặc định/quản lý [http://127.0.0.1:3600/manage]`

**Ghi chú cập nhật**

- Trang demo sẽ không được cập nhật đồng bộ trong giai đoạn cải thiện chức năng phụ trợ. Bạn cần sử dụng máy chủ để tự xây dựng trải nghiệm
- Các vấn đề gặp phải trong quá trình sử dụng có thể được mô tả trong mục Sự cố của dự án. Các tính năng mới và gợi ý hay cần bổ sung cũng có thể được cung cấp
- Đối với phương pháp cài đặt và hướng dẫn sử dụng phiên bản mới, vui lòng tham khảo tệp mô tả trong thư mục phim của dự án này

>Nội dung mới:
>
>- Đã thêm lịch sử xem trên thiết bị di động
>- Đã thêm chức năng ghi lại lỗi thu thập && Thu thập lại dựa trên việc thu thập không thành công
>- Đã thêm xử lý thường xuyên chức năng thu thập không thành công vào tác vụ theo lịch trình mặc định
>- Đã khắc phục sự cố gửi bất thường của sửa đổi tham số biểu ngữ băng chuyền trang chủ Banner
>- Đã khắc phục sự cố không có dữ liệu trong điều hướng phân loại cấp một trên trang chủ
>- Đã khắc phục sự cố hiển thị bất thường của thẻ thông tin phim trên giao diện trang chủ
>- Tối ưu hóa sự cố hiển thị nền thành phần của chi tiết phim và trang phát lại
>
>Kế hoạch tiếp theo:
>
>- Kiểm tra chức năng mới && sửa chữa buf
>- Cải thiện chức năng giao diện xem lịch sử && Tối ưu hóa các thành phần UI tương ứng
>- Tối ưu hóa trình phát hoặc thay thế thành phần trình phát
>- Chi tiết phương pháp thu thập để đạt được thu thập theo hướng và cập nhật thủ công theo thời gian thực của một bộ phim duy nhất

## Cấu trúc thư mục

- máy khách máy khách dự án thư mục [Giới thiệu về máy khách](./client/README.md)
- máy chủ giao diện máy chủ thư mục dự án [Giới thiệu về máy chủ](./client/README.md)
- triển khai dự án phim liên quan đến cấu hình thư mục [cài đặt dự án phim](./film/README.md)
- Để biết hướng dẫn chi tiết, vui lòng tham khảo tệp README trong thư mục cụ thể
```text
GoFilm-main                            
├─ client                              
│  ├─ public                           
│  │  └─ favicon.ico                   
│  ├─ src                              
│  │  ├─ assets                        
│  │  │  ├─ css                        
│  │  │  │  ├─ classify.css            
│  │  │  │  ├─ film.css                
│  │  │  │  └─ pagination.css          
│  │  │  └─ image                      
│  │  │     ├─ 404.png                 
│  │  │     └─ play.png                
│  │  ├─ components                    
│  │  │  ├─ Loading                    
│  │  │  │  ├─ index.ts                
│  │  │  │  └─ Loading.vue             
│  │  │  ├─ FilmList.vue               
│  │  │  ├─ Footer.vue                 
│  │  │  ├─ Header.vue                 
│  │  │  ├─ RelateList.vue             
│  │  │  └─ Util.vue                   
│  │  ├─ router                        
│  │  │  └─ router.ts                  
│  │  ├─ utils                         
│  │  │  ├─ cookie.ts                  
│  │  │  └─ request.ts                 
│  │  ├─ views                         
│  │  │  ├─ error                      
│  │  │  │  └─ Error404.vue            
│  │  │  ├─ index                      
│  │  │  │  ├─ FilmClassify.vue        
│  │  │  │  ├─ FilmClassifySearch.vue  
│  │  │  │  ├─ FilmDetails.vue         
│  │  │  │  ├─ Home.vue                
│  │  │  │  ├─ Play.vue                
│  │  │  │  └─ SearchFilm.vue          
│  │  │  └─ IndexHome.vue              
│  │  ├─ App.vue                       
│  │  ├─ main.ts                       
│  │  ├─ style.css                     
│  │  └─ vite-env.d.ts                 
│  ├─ auto-imports.d.ts                
│  ├─ components.d.ts                  
│  ├─ index.html                       
│  ├─ package.json                     
│  ├─ README.md                        
│  ├─ tsconfig.json                    
│  ├─ tsconfig.node.json               
│  └─ vite.config.ts                   
├─ film                                
│  ├─ data                             
│  │  ├─ nginx                         
│  │  │  ├─ html                       
│  │  │  │  ├─ assets                  
│  │  │  │  │  ├─ 404-b813c94a.png     
│  │  │  │  │  ├─ index-984712d6.js    
│  │  │  │  │  ├─ index-de4c7ff5.css   
│  │  │  │  │  └─ play-bb9c8990.png    
│  │  │  │  ├─ favicon.ico             
│  │  │  │  └─ index.html              
│  │  │  └─ nginx.conf                 
│  │  └─ redis                         
│  │     └─ redis.conf                 
│  ├─ server                           
│  │  ├─ config                        
│  │  │  └─ DataConfig.go              
│  │  ├─ controller                    
│  │  │  ├─ IndexController.go         
│  │  │  └─ SpiderController.go        
│  │  ├─ logic                         
│  │  │  ├─ IndexLogic.go              
│  │  │  └─ SpiderLogic.go             
│  │  ├─ model                         
│  │  │  ├─ Categories.go              
│  │  │  ├─ Movies.go                  
│  │  │  ├─ RequestParams.go           
│  │  │  ├─ ResponseJson.go            
│  │  │  └─ Search.go                  
│  │  ├─ plugin                        
│  │  │  ├─ common                     
│  │  │  │  ├─ dp                      
│  │  │  │  │  ├─ ProcessCategory.go   
│  │  │  │  │  └─ ProcessMovies.go     
│  │  │  │  └─ param                   
│  │  │  │     └─ SimpleParam.go       
│  │  │  ├─ db                         
│  │  │  │  ├─ mysql.go                
│  │  │  │  └─ redis.go                
│  │  │  └─ spider                     
│  │  │     ├─ Spider.go               
│  │  │     ├─ SpiderCron.go           
│  │  │     └─ SpiderRequest.go        
│  │  ├─ router                        
│  │  │  └─ router.go                  
│  │  ├─ go.mod                        
│  │  ├─ go.sum                        
│  │  ├─ main.go                       
│  │  └─ README.md                     
│  ├─ docker-compose.yml               
│  ├─ Dockerfile                       
│  └─ README.md                        
├─ server                              
│  ├─ config                           
│  │  └─ DataConfig.go                 
│  ├─ controller                       
│  │  ├─ IndexController.go            
│  │  └─ SpiderController.go           
│  ├─ logic                            
│  │  ├─ IndexLogic.go                 
│  │  └─ SpiderLogic.go                
│  ├─ model                            
│  │  ├─ Categories.go                 
│  │  ├─ Movies.go                     
│  │  ├─ RequestParams.go              
│  │  ├─ ResponseJson.go               
│  │  └─ Search.go                     
│  ├─ plugin                           
│  │  ├─ common                        
│  │  │  ├─ dp                         
│  │  │  │  ├─ ProcessCategory.go      
│  │  │  │  └─ ProcessMovies.go        
│  │  │  ├─ param                      
│  │  │  │  └─ SimpleParam.go          
│  │  │  └─ util                       
│  │  │     ├─ FileDownload.go         
│  │  │     └─ Request.go              
│  │  ├─ db                            
│  │  │  ├─ mysql.go                   
│  │  │  └─ redis.go                   
│  │  └─ spider                        
│  │     ├─ Spider.go                  
│  │     └─ SpiderCron.go              
│  ├─ router                           
│  │  └─ router.go                     
│  ├─ go.mod                           
│  ├─ go.sum                           
│  ├─ main.go                          
│  └─ README.md                        
├─ LICENSE                             
└─ README.md                           
```



## Nguồn gốc

Từ khi chính thức tiếp xúc với ngôn ngữ lập trình cho đến lần đầu tiên viết code, tôi đã có ý tưởng làm một cái gì đó. Cũng vào thời điểm đó, tôi thích theo dõi anime và chiều không gian thứ hai, và tôi đã nghĩ đến việc tạo trang web anime của riêng mình.

Nhưng vì thiếu kiến ​​thức, tôi luôn gặp phải một số điểm mù khi đạt đến một bước nhất định. Từ trang tĩnh lúc đầu đến dữ liệu giả sau này, tôi cũng nhận ra một số phần mà mình có thể làm vào thời điểm đó.

Trong quá trình học chậm rãi sau này, tôi dần quên mất ý tưởng này, nhưng vì một số yếu tố ngẫu nhiên, tôi muốn tạo ra dự án nguồn mở của riêng mình, vì vậy tôi bắt đầu từ đầu và dần nhận ra và cải thiện

Video và trạm video. Trong thời gian này, tôi cũng đã sửa đổi một số ý tưởng ban đầu một chút, nhưng hiện tại các chức năng chính về cơ bản đã hoàn thành và một số bản sửa lỗi và cập nhật chức năng mới sẽ được thực hiện thường xuyên trong tương lai

Nếu bạn tìm thấy lỗi hoặc có đề xuất hay, bạn có thể phản hồi. Chào mừng bạn đến để cho tôi một số lời khuyên

## Kế hoạch cập nhật và lặp lại

- Hiện tại, một số chức năng của giao diện người dùng cần được phát triển và cải thiện, và mọi người có thể tiếp tục cung cấp một số gợi ý hay

- Hiện tại, một phiên bản thử nghiệm đơn giản của bản ghi lịch sử trên PC đã được viết, Sau đó, chúng tôi sẽ cải thiện bản ghi lịch sử và các chức năng thu thập của PC và Wrap cùng một lúc.
- Chức năng front-end hiện tại về cơ bản đáp ứng được nhu cầu xem. Chúng tôi sẽ xem xét thêm một số chức năng đăng nhập và tài khoản và quản lý back-end trong tương lai để dần cải thiện dự án này.


