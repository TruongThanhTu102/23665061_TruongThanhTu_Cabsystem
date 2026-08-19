# 1. Ngữ cảnh của nghiệp vụ

Công ty ABC là doanh nghiệp cung cấp dịch vụ đặt xe trực tuyến. Hiện tại, khách hàng có thể liên hệ với tổng đài hoặc sử dụng một ứng dụng đơn giản để yêu cầu xe.

Quy trình nghiệp vụ chính của hệ thống bao gồm:

- Khách hàng tạo yêu cầu đặt xe.
- Hệ thống tiếp nhận yêu cầu và tìm kiếm tài xế phù hợp.
- Tài xế nhận hoặc từ chối chuyến.
- Nếu tài xế từ chối hoặc không phản hồi, hệ thống tiếp tục tìm tài xế khác.
- Tài xế thực hiện chuyến và cập nhật trạng thái.
- Khi chuyến hoàn thành, hệ thống tính cước.
- Khách hàng thực hiện thanh toán.
- Khách hàng có thể đánh giá tài xế sau chuyến.
- Hệ thống lưu trữ thông tin chuyến đi và giao dịch để phục vụ quản lý và tra cứu.

Doanh nghiệp mong muốn xây dựng một nền tảng CAB mới có khả năng phục vụ số lượng lớn khách hàng và tài xế, đồng thời có khả năng mở rộng và bổ sung các chức năng trong tương lai.

---

# 2. Vấn đề của nghiệp vụ hiện tại

Hệ thống hiện tại của Công ty ABC đang tồn tại một số vấn đề:

- Việc phân công tài xế chủ yếu được thực hiện thủ công.
- Khách hàng khó theo dõi trạng thái chuyến đi.
- Khách hàng khó biết hệ thống đang tìm tài xế nào hoặc tài xế nào đã nhận chuyến.
- Thông tin thanh toán chưa được quản lý tập trung.
- Bộ phận vận hành gặp khó khăn trong việc quản lý và giám sát hoạt động.
- Hệ thống khó mở rộng khi số lượng khách hàng và tài xế tăng.
- Việc xử lý trường hợp tài xế không phản hồi hoặc từ chối chuyến chưa được tự động hóa.
- Doanh nghiệp gặp khó khăn khi muốn bổ sung các tính năng mới trong tương lai.

---

# 3. Vì sao doanh nghiệp không thể đáp ứng tốt nhu cầu hiện tại?

Do hệ thống hiện tại còn phụ thuộc nhiều vào các thao tác thủ công và chưa có khả năng tự động hóa đầy đủ quy trình đặt xe.

Cụ thể:

- Việc phân công tài xế thủ công gây khó khăn khi số lượng khách hàng và tài xế tăng.
- Hệ thống chưa hỗ trợ tốt việc theo dõi trạng thái chuyến đi theo thời gian thực.
- Thông tin thanh toán chưa được quản lý tập trung.
- Các bộ phận vận hành gặp khó khăn khi cần theo dõi và xử lý các chuyến đi.
- Kiến trúc hiện tại chưa đủ linh hoạt để mở rộng từng thành phần độc lập.
- Khi xảy ra lỗi ở một chức năng như thanh toán hoặc thông báo, doanh nghiệp muốn tránh việc lỗi đó ảnh hưởng đến toàn bộ hệ thống.
- Doanh nghiệp muốn có thể thêm loại dịch vụ, phương thức thanh toán hoặc nhà cung cấp thông báo mới mà không phải xây dựng lại toàn bộ ứng dụng.

Vì vậy, Công ty ABC cần xây dựng một hệ thống CAB mới có khả năng tự động hóa, mở rộng và phát triển lâu dài.

---

# 4. Người sử dụng hệ thống

Hệ thống có 3 nhóm người dùng chính:

## 4.1. Khách hàng

Khách hàng sử dụng hệ thống để:

- Đăng ký tài khoản.
- Đăng nhập.
- Cập nhật thông tin cá nhân.
- Nhập điểm đón và điểm đến.
- Lựa chọn loại xe.
- Gửi yêu cầu đặt xe.
- Theo dõi trạng thái chuyến đi.
- Xem tài xế đã nhận chuyến.
- Xem thời gian dự kiến tài xế đến.
- Xem lịch sử chuyến đi.
- Xem số tiền phải trả.
- Thanh toán.
- Đánh giá tài xế sau khi hoàn thành chuyến.

## 4.2. Tài xế

Tài xế sử dụng hệ thống để:

- Đăng ký tài khoản hoặc được nhân viên vận hành tạo tài khoản.
- Cập nhật thông tin cá nhân.
- Cập nhật thông tin phương tiện.
- Chuyển sang trạng thái sẵn sàng nhận chuyến.
- Nhận thông báo về chuyến mới.
- Chấp nhận hoặc từ chối chuyến.
- Cập nhật trạng thái chuyến:
  - Đã đến điểm đón.
  - Đã đón khách.
  - Đang di chuyển.
  - Hoàn thành chuyến.
- Cung cấp thông tin vị trí để hệ thống hỗ trợ tìm tài xế gần khách hàng.

## 4.3. Nhân viên vận hành

Nhân viên vận hành sử dụng hệ thống để:

- Quản lý khách hàng.
- Quản lý tài xế.
- Quản lý phương tiện.
- Theo dõi các chuyến đang diễn ra.
- Kiểm tra trạng thái tài xế.
- Hỗ trợ xử lý các trường hợp chuyến bị lỗi.
- Tra cứu lịch sử giao dịch.
- Thực hiện các chức năng quản trị theo quyền được cấp.
- Theo dõi các báo cáo về:
  - Số lượng chuyến.
  - Doanh thu.
  - Tỷ lệ chuyến hoàn thành.
  - Tỷ lệ hủy.
  - Hiệu quả hoạt động của tài xế.

---

# 5. Các bên liên quan (Stakeholder)

Các stakeholder chính của hệ thống gồm:

| Stakeholder | Vai trò |
|---|---|
| **Ban giám đốc / Ban lãnh đạo** | Đưa ra định hướng, yêu cầu và kỳ vọng của dự án; quan tâm đến doanh thu, số lượng chuyến, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả hoạt động. |
| **Khách hàng** | Sử dụng dịch vụ đặt xe, theo dõi chuyến đi, thanh toán và đánh giá tài xế. |
| **Tài xế** | Nhận và thực hiện chuyến, cập nhật trạng thái và thông tin vị trí. |
| **Nhân viên vận hành** | Quản lý khách hàng, tài xế, phương tiện, chuyến đi và hỗ trợ xử lý sự cố. |
| **Nhà cung cấp thanh toán** | Cung cấp dịch vụ thanh toán điện tử cho hệ thống. |
| **Nhà cung cấp dịch vụ thông báo** | Cung cấp các kênh gửi thông báo cho khách hàng và tài xế. |

---

# 6. Mục tiêu của hệ thống mới

Công ty ABC mong muốn xây dựng CAB System nhằm:

- Tự động hóa quy trình đặt xe và tìm kiếm tài xế.
- Hỗ trợ phân công tài xế phù hợp và gần khách hàng.
- Cho phép khách hàng theo dõi trạng thái chuyến đi.
- Hỗ trợ tài xế tiếp nhận và thực hiện chuyến.
- Quản lý thông tin thanh toán tập trung.
- Tích hợp với nhà cung cấp thanh toán bên ngoài.
- Cung cấp hệ thống thông báo cho khách hàng và tài xế.
- Hỗ trợ nhân viên vận hành quản lý và giám sát hoạt động.
- Bảo vệ thông tin cá nhân, dữ liệu vị trí và dữ liệu giao dịch.
- Có khả năng mở rộng khi số lượng người dùng tăng.
- Cho phép bổ sung các loại dịch vụ, phương thức thanh toán và nhà cung cấp mới trong tương lai.
- Có thể triển khai các chức năng mới từng phần và hạn chế ảnh hưởng đến các chức năng đang hoạt động.

---

# 7. Tóm tắt vấn đề nghiệp vụ

**Vấn đề:**  
Hệ thống đặt xe hiện tại còn phụ thuộc vào thao tác thủ công, khó theo dõi chuyến đi, quản lý thanh toán chưa tập trung và khó mở rộng khi quy mô khách hàng, tài xế tăng.

**Nguyên nhân:**  
Hệ thống hiện tại chưa tự động hóa đầy đủ quy trình đặt xe và chưa có kiến trúc đủ linh hoạt để các thành phần có thể mở rộng hoặc thay đổi độc lập.

**Nhu cầu:**  
Công ty ABC cần một nền tảng CAB mới có khả năng tự động hóa quy trình từ đặt xe, tìm tài xế, thực hiện chuyến, tính cước, thanh toán, thông báo đến đánh giá sau chuyến.

**Người sử dụng chính:**  
- Khách hàng.
- Tài xế.
- Nhân viên vận hành.

**Mục tiêu cuối cùng:**  
Xây dựng một nền tảng đặt xe có khả năng hoạt động ổn định, bảo mật, mở rộng và dễ dàng bổ sung các chức năng mới trong tương lai.
# 7. Vẽ ma trận stackholder mandit thể hiện mức độ ảnh hưởng của các vai trò
                    STAKEHOLDER MATRIX
                  Mức độ ảnh hưởng (POWER)
                         CAO
                          │
        ┌─────────────────┼─────────────────┐
        │                 │                 │
        │  QUẢN LÝ CHẶT   │  QUẢN LÝ CHẶT   │
        │                 │                 │
        │  Ban giám đốc    │  Ban giám đốc   │
        │                 │  Nhân viên       │
        │                 │  vận hành        │
        │                 │                 │
        ├─────────────────┼─────────────────┤
        │                 │                 │
        │  THEO DÕI       │  GIỮ HÀI LÒNG   │
        │                 │                 │
        │  Nhà cung cấp    │  Khách hàng     │
        │  thông báo       │  Tài xế         │
        │                 │                 │
        │  Nhà cung cấp    │                 │
        │  thanh toán      │                 │
        │                 │                 │
        └─────────────────┴─────────────────┘
                          │
                         THẤP
             THẤP                         CAO
                    Mức độ quan tâm
