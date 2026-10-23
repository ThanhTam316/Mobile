1. Tìm hiểu về các components của Android, bao gồm những gì, tác dụng là gì? hãy code example để đưa ra dẫn chứng.
   Gồm 4 thành phần cốt lõi:
   - Activity: Đại diện cho một màn hình duy nhất có giao diện người dùng (UI) tương tác với người dùng. (Ví dụ: Màn hình đăng nhập, màn hình danh sách sản phẩm).
   - Service: Chạy ngầm để thực hiện các tác vụ dài hạn mà không cần giao diện người dùng (Ví dụ: Phát nhạc ngầm, tải file lớn từ server, đồng bộ dữ liệu)
   - Broadcast Receiver: Cho phép ứng dụng nhận các thông báo (broadcasts) từ hệ thống hoặc từ các ứng dụng khác (Ví dụ: Thông báo pin yếu, kết nối mạng thay đổi, khởi động xong máy).
   - Content Provider: Quản lý và chia sẻ tập dữ liệu của ứng dụng một cách bảo mật với các ứng dụng khác (Ví dụ: Truy cập danh bạ, thư viện ảnh của thiết bị).

// EM KHÔNG BIẾT CODE HUHU 😭😭
     
2. 1 bộ khung xương của Android Studio gồm những thành phần nào, tác dụng của từng thành phần
- Project Window (Cửa sổ quản lý dự án): Cây thư mục hiển thị toàn bộ cấu trúc file của project (java/kotlin, res/layout, AndroidManifest.xml, build.gradle...)
- Editor Window (Khu vực soạn thảo):
  + Khi viết code (Kotlin/Java): Nơi gõ mã nguồn, có hỗ trợ gợi ý code (AutoComplete) và báo lỗi.
  + Khi thiết kế XML/Compose: Hỗ trợ 3 chế độ xem chính là Code (chỉ hiện code XML), Split (vừa hiện code vừa hiện giao diện preview thực tế), và Design (kéo-thả giao diện).
- Toolbar & Navigation Bar (Thanh công cụ & Thanh điều hướng)
   + Chứa các nút bấm thao tác nhanh như Run (chạy app), Debug (sửa lỗi), chọn máy ảo/máy thật để chạy app.
   + Cho biết vị trí đường dẫn file bạn đang làm việc
- Tool Window Bar (Thanh công cụ phụ xung quanh): Chứa các công cụ bổ trợ chuyên sâu như:
  + Build Variant: Chuyển đổi giữa các môi trường (Debug / Release).
  + Device Manager: Quản lý và tạo máy ảo Android (AVD).
  + Gradle Tab: Đồng bộ (Sync) và kiểm tra các tác vụ build project.
- Bottom Tool Windows (Khu vực thông tin & kiểm thử bên dưới):
  + Logcat: Nơi in ra toàn bộ log, thông báo lỗi (Crash logs) khi app đang chạy.
  + Terminal: Dòng lệnh tích hợp sẵn (chạy các lệnh Git, Gradle...).
  + Build / Problems: Hiển thị tiến trình biên dịch code và danh sách các lỗi cú pháp trong project


3. Vòng đời của 1 app Android, bao gồm các state nào, tìm hiểu về các state đó.
  - Trạng thái Created (onCreat()): Activity vừa được khởi tạo lần đầu tiên
     + dùng hàm này để giao diện (setContentView), khởi tạo các biến, kết nối cơ sở dữ liệu hoặc thiết lập ViewModel         ban đầu. Sau bước này, app chuyển sang onStart().
  - Trạng thái Started (onStart()): Activity chuẩn bị xuất hiện trên màn hình, người dùng đã có thể nhìn thấy nó           nhưng chưa thể tương tác
      + Chuẩn bị các tài nguyên hiển thị lên màn hình.
  - Trạng thái Resumed: Activity nằm ở lớp trên cùng (foreground) và người dùng đang tương tác trực tiếp với nó
    + Đây là trạng thái hoạt động chính của app (ví dụ: đang lướt danh sách, đang gõ tin nhắn). App sẽ giữ nguyên            trạng thái này cho đến khi có sự kiện ngắt xảy ra (như có cuộc gọi đến hoặc người dùng bấm nút về Home)
  - Trạng thái Paused: Activity bắt đầu mất tiêu điểm (focus)
    + Lưu lại dữ liệu tạm thời (như đang gõ dở văn bản) hoặc tạm dừng các tác vụ nặng (như tạm dừng camera hoặc game)       để tiết kiệm pin.
  - Trạng thái Stopped: Activity hoàn toàn bị che khuất và không còn hiển thị trên màn hình nữa
    + Giải phóng các tài nguyên không cần thiết khi app đang ẩn (như ngắt kết nối mạng hoặc dừng cập nhật giao diện           ngầm).
  - Trạng thái Destroyed: Đây là trạng thái cuối cùng trước khi Activity bị hủy hoàn toàn khỏi bộ nhớ RAM
    + Dọn dẹp sạch sẽ (hủy các luồng chạy ngầm, đóng kết nối database) để tránh rò rỉ bộ nhớ (Memory Leak)
    
