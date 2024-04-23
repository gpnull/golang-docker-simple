# golang-docker-simple

- FROM 1.22.0-alpine3.19: Chọn image base là golang:1.22.0-alpine3.19. Đây là image có sẵn của golang trên nền tảng Alpine Linux.
- RUN mkdir /app: Tạo thư mục /app để chứa source code Go trong quá trình build.
- ADD . /app: Thêm toàn bộ source code Go hiện tại (dấu chấm .) vào thư mục /app vừa tạo.
- WORKDIR /app: Thiết lập thư mục làm việc hiện tại là /app, nơi chứa source code.
- RUN go build -o main .: Trong thư mục /app, dùng lệnh go build để biên dịch source code thành file binary main và lưu tại /app.
- CMD ["/app/main"]: Định nghĩa lệnh mặc định khi chạy container là thực thi file binary main nằm trong thư mục /app.