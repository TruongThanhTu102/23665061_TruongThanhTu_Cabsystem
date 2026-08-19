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

# Vẽ ma trận stackholder mandit thể hiện mức độ ảnh hưởng của các vai trò
                    STAKEHOLDER MATRIX
                  Mức độ ảnh hưởng (POWER)
                         CAO
                          │
        ┌─────────────────┼─────────────────┐
        │                 │                 │
        │  QUẢN LÝ CHẶT   │  QUẢN LÝ CHẶT   │
        │                 │                 │
        │  Ban giám đốc   │  Ban giám đốc   │
        │                 │  Nhân viên      │
        │                 │  vận hành       │
        │                 │                 │
        ├─────────────────┼─────────────────┤
        │                 │                 │
        │  THEO DÕI       │  GIỮ HÀI LÒNG   │
        │                 │                 │
        │  Nhà cung cấp   │  Khách hàng     │
        │  thông báo      │  Tài xế         │
        │                 │                 │
        │  Nhà cung cấp   │                 │
        │  thanh toán     │                 │
        │                 │                 │
        └─────────────────┴─────────────────┘
                          │
                         THẤP
             THẤP                         CAO
                    Mức độ quan tâm

# Business Goals

## Business Goals 1. Tự động hóa hoạt động đặt xe

- Tự động hóa quy trình từ khi khách hàng tạo yêu cầu đến khi chuyến xe hoàn thành.
- Giảm sự phụ thuộc vào việc phân công tài xế thủ công.
- Tự động tìm kiếm và phân công tài xế phù hợp cho khách hàng.

## Business Goals 2. Nâng cao chất lượng dịch vụ khách hàng

- Cho phép khách hàng dễ dàng đặt xe.
- Cho phép khách hàng theo dõi trạng thái chuyến đi.
- Cung cấp thông tin về tài xế và thời gian dự kiến đến.
- Hỗ trợ khách hàng thanh toán và đánh giá tài xế sau chuyến.

## Business Goals 3. Nâng cao hiệu quả vận hành

- Hỗ trợ nhân viên vận hành quản lý khách hàng, tài xế, phương tiện và chuyến đi.
- Theo dõi các chuyến đang diễn ra và trạng thái tài xế.
- Hỗ trợ xử lý các trường hợp chuyến đi bị lỗi.
- Cung cấp dữ liệu và báo cáo để theo dõi hoạt động kinh doanh.

## Business Goals 4. Hỗ trợ mở rộng quy mô kinh doanh

- Xây dựng hệ thống có khả năng phục vụ số lượng lớn khách hàng và tài xế.
- Cho phép các thành phần của hệ thống mở rộng độc lập khi nhu cầu tăng cao.
- Đảm bảo hệ thống hoạt động ổn định trong thời điểm nhu cầu tăng cao.

## Business Goals 5. Xây dựng nền tảng có khả năng phát triển lâu dài

- Cho phép bổ sung các loại dịch vụ mới.
- Cho phép thêm các phương thức thanh toán mới.
- Cho phép tích hợp thêm các nhà cung cấp dịch vụ thông báo.
- Có thể thay đổi một số thành phần kỹ thuật mà không phải xây dựng lại toàn bộ hệ thống.
- Cho phép triển khai các chức năng mới từng phần và hạn chế ảnh hưởng đến các chức năng đang hoạt động.

## Business Goals 6. Đảm bảo an toàn và bảo mật dữ liệu

- Bảo vệ thông tin cá nhân của khách hàng và tài xế.
- Bảo vệ thông tin phương tiện, dữ liệu vị trí và dữ liệu giao dịch.
- Kiểm soát quyền truy cập đối với các chức năng quản trị.
- Lưu vết các thao tác quan trọng để phục vụ kiểm tra và xử lý sự cố.

## Business Goals 7. Nâng cao hiệu quả quản lý và ra quyết định

- Cung cấp báo cáo về số lượng chuyến.
- Theo dõi doanh thu.
- Theo dõi tỷ lệ chuyến hoàn thành và tỷ lệ hủy.
- Đánh giá hiệu quả hoạt động của tài xế.
- Cung cấp dữ liệu để ban lãnh đạo theo dõi tình hình hoạt động của doanh nghiệp.

# Scope – Phạm vi của hệ thống CAB

## 1. In Scope – Phạm vi thuộc hệ thống

### 1.1. Quản lý khách hàng

- Đăng ký tài khoản.
- Đăng nhập.
- Cập nhật thông tin cá nhân.
- Quản lý thông tin tài khoản khách hàng.

### 1.2. Quản lý tài xế

- Đăng ký tài khoản hoặc được nhân viên vận hành tạo tài khoản.
- Cập nhật hồ sơ tài xế.
- Quản lý trạng thái hoạt động của tài xế.
- Chuyển sang trạng thái sẵn sàng nhận chuyến.
- Quản lý thông tin vị trí của tài xế.

### 1.3. Quản lý phương tiện

- Quản lý thông tin phương tiện của tài xế.
- Cho phép nhân viên vận hành quản lý thông tin phương tiện.

### 1.4. Đặt và quản lý chuyến xe

- Khách hàng nhập điểm đón và điểm đến.
- Khách hàng lựa chọn loại xe.
- Khách hàng gửi yêu cầu đặt xe.
- Hệ thống tiếp nhận và xử lý yêu cầu đặt xe.
- Theo dõi trạng thái chuyến đi.
- Lưu lịch sử chuyến đi.

### 1.5. Tìm kiếm và phân công tài xế

- Xác định tài xế phù hợp dựa trên:
  - Vị trí.
  - Trạng thái sẵn sàng.
  - Các tiêu chí vận hành khác.
- Ưu tiên tài xế phù hợp và gần khách hàng.
- Gửi yêu cầu chuyến đến tài xế.
- Cho phép tài xế chấp nhận hoặc từ chối chuyến.
- Nếu tài xế không phản hồi hoặc từ chối, hệ thống tiếp tục tìm tài xế khác.
- Thông báo cho khách hàng nếu không tìm được tài xế.

### 1.6. Theo dõi và cập nhật chuyến đi

Tài xế có thể cập nhật các trạng thái:

- Đã đến điểm đón.
- Đã đón khách.
- Đang di chuyển.
- Hoàn thành chuyến.

Khách hàng có thể theo dõi trạng thái hiện tại của chuyến đi.

### 1.7. Tính cước và thanh toán

- Tính số tiền khách hàng phải trả dựa trên loại dịch vụ và thông tin chuyến đi.
- Hỗ trợ thanh toán bằng tiền mặt.
- Hỗ trợ thanh toán điện tử.
- Tích hợp với nhà cung cấp thanh toán bên ngoài.
- Không lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán.
- Xử lý trường hợp thanh toán điện tử thất bại.
- Cho phép xử lý lại thanh toán theo chính sách của doanh nghiệp.
- Lưu và tra cứu thông tin giao dịch.

### 1.8. Thông báo

Hệ thống gửi thông báo cho khách hàng khi:

- Yêu cầu đặt xe được tiếp nhận.
- Có tài xế nhận chuyến.
- Tài xế đến điểm đón.
- Chuyến đi hoàn thành.
- Thanh toán có kết quả.

Tài xế nhận thông báo khi:

- Có chuyến mới.
- Có thay đổi liên quan đến chuyến đang thực hiện.

Hệ thống có khả năng mở rộng thêm các kênh thông báo trong tương lai.

### 1.9. Quản trị và vận hành

Nhân viên vận hành có thể:

- Quản lý khách hàng.
- Quản lý tài xế.
- Quản lý phương tiện.
- Quản lý chuyến đi.
- Xem các chuyến đang diễn ra.
- Kiểm tra trạng thái tài xế.
- Hỗ trợ xử lý các chuyến bị lỗi.
- Tra cứu lịch sử giao dịch.
- Phân quyền các chức năng quản trị.

### 1.10. Báo cáo

Hệ thống hỗ trợ báo cáo:

- Số lượng chuyến.
- Doanh thu.
- Tỷ lệ chuyến hoàn thành.
- Tỷ lệ hủy.
- Hiệu quả hoạt động của tài xế.

### 1.11. Bảo mật và kiểm soát

- Xác thực khách hàng và tài xế trước khi sử dụng các chức năng yêu cầu tài khoản.
- Kiểm soát quyền truy cập đối với chức năng quản trị.
- Bảo vệ thông tin cá nhân.
- Bảo vệ thông tin phương tiện.
- Bảo vệ dữ liệu vị trí.
- Bảo vệ dữ liệu giao dịch.
- Lưu vết các thao tác quan trọng để phục vụ kiểm tra khi có sự cố.

### 1.12. Khả năng mở rộng

- Hệ thống có khả năng phục vụ số lượng lớn khách hàng và tài xế.
- Các thành phần có khả năng mở rộng độc lập khi tải tăng.
- Có thể triển khai chức năng mới từng phần.
- Hạn chế ảnh hưởng đến các chức năng đang hoạt động khi bổ sung chức năng mới.
- Có khả năng bổ sung loại dịch vụ mới.
- Có khả năng bổ sung phương thức thanh toán mới.
- Có khả năng tích hợp thêm nhà cung cấp thông báo.
- Có thể thay đổi một số thành phần kỹ thuật mà không phải xây dựng lại toàn bộ ứng dụng.

---

# 2. Out of Scope – Ngoài phạm vi hiện tại

Tài liệu **chưa xác định rõ** một số nội dung. Vì vậy, các nội dung này cần được BA làm rõ với các bên liên quan trước khi đưa vào phạm vi chính thức:

- Chi tiết công thức tính cước.
- Tiêu chí cụ thể để ưu tiên tài xế.
- Thời gian tài xế phải phản hồi yêu cầu chuyến.
- Chính sách hủy chuyến.
- Cách xử lý cụ thể khi mất kết nối mạng.
- Thời gian lưu trữ dữ liệu.

> Lưu ý: Đây không nhất thiết là các chức năng bị loại khỏi dự án. Đây là **các vấn đề chưa được xác định rõ trong tài liệu và cần xác nhận thêm với khách hàng**.

---

# 3. Tóm tắt phạm vi

Hệ thống CAB tập trung hỗ trợ toàn bộ quy trình:

**Đặt xe → Tìm tài xế → Phân công tài xế → Thực hiện chuyến → Tính cước → Thanh toán → Thông báo → Đánh giá → Lưu trữ và quản lý dữ liệu**

Hệ thống phục vụ 3 nhóm người dùng chính:

- **Khách hàng**
- **Tài xế**
- **Nhân viên vận hành**

Ngoài ra, hệ thống tích hợp với các **nhà cung cấp dịch vụ bên ngoài**, đặc biệt là nhà cung cấp thanh toán và các kênh thông báo.

# Business Requirements

## BR01 – Xây dựng nền tảng đặt xe tập trung

Hệ thống CAB phải cung cấp một nền tảng đặt xe trực tuyến tập trung, hỗ trợ toàn bộ quy trình từ khi khách hàng tạo yêu cầu đặt xe đến khi chuyến đi hoàn thành, thanh toán và đánh giá.

## BR02 – Hỗ trợ quản lý khách hàng

Hệ thống phải cho phép doanh nghiệp quản lý thông tin khách hàng và hỗ trợ khách hàng thực hiện các hoạt động liên quan đến dịch vụ đặt xe.

Hệ thống phải hỗ trợ:

- Đăng ký tài khoản.
- Đăng nhập.
- Cập nhật thông tin cá nhân.
- Quản lý lịch sử chuyến đi.

## BR03 – Hỗ trợ quản lý tài xế

Hệ thống phải cho phép doanh nghiệp quản lý thông tin và trạng thái hoạt động của tài xế.

Hệ thống phải hỗ trợ:

- Tạo hoặc đăng ký tài khoản tài xế.
- Quản lý hồ sơ tài xế.
- Quản lý thông tin phương tiện.
- Theo dõi trạng thái sẵn sàng của tài xế.
- Theo dõi thông tin vị trí của tài xế.

## BR04 – Tự động hóa quy trình đặt xe và tìm tài xế

Hệ thống phải tự động tiếp nhận yêu cầu đặt xe và tìm tài xế phù hợp dựa trên vị trí, trạng thái sẵn sàng và các tiêu chí vận hành.

Nếu tài xế được đề xuất không phản hồi hoặc từ chối chuyến, hệ thống phải tiếp tục tìm tài xế khác mà không yêu cầu khách hàng tạo lại yêu cầu.

Nếu không tìm được tài xế, hệ thống phải thông báo rõ ràng cho khách hàng.

## BR05 – Hỗ trợ theo dõi và quản lý chuyến đi

Hệ thống phải cho phép khách hàng và nhân viên vận hành theo dõi trạng thái chuyến đi.

Tài xế phải có khả năng cập nhật trạng thái:

- Đã đến điểm đón.
- Đã đón khách.
- Đang di chuyển.
- Hoàn thành chuyến.

Khách hàng phải có thể biết:

- Hệ thống đang tìm tài xế.
- Tài xế đã nhận chuyến.
- Thời gian dự kiến tài xế đến.
- Trạng thái hiện tại của chuyến đi.

## BR06 – Hỗ trợ tính cước và thanh toán

Hệ thống phải hỗ trợ xác định số tiền khách hàng cần thanh toán sau khi chuyến đi hoàn thành.

Hệ thống phải hỗ trợ:

- Thanh toán bằng tiền mặt.
- Thanh toán điện tử.
- Tích hợp với nhà cung cấp thanh toán bên ngoài.
- Xử lý trường hợp thanh toán điện tử thất bại.
- Thông báo kết quả thanh toán cho khách hàng.

Hệ thống không được lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán.

## BR07 – Cung cấp hệ thống thông báo

Hệ thống phải cung cấp cơ chế thông báo cho khách hàng và tài xế trong các sự kiện quan trọng.

Khách hàng cần được thông báo khi:

- Yêu cầu đặt xe được tiếp nhận.
- Có tài xế nhận chuyến.
- Tài xế đến điểm đón.
- Chuyến đi hoàn thành.
- Thanh toán có kết quả.

Tài xế cần được thông báo khi:

- Có chuyến mới.
- Có thay đổi liên quan đến chuyến đang thực hiện.

## BR08 – Hỗ trợ quản lý và vận hành

Hệ thống phải cung cấp giao diện quản trị cho nhân viên vận hành.

Nhân viên vận hành phải có khả năng:

- Quản lý khách hàng.
- Quản lý tài xế.
- Quản lý phương tiện.
- Quản lý chuyến đi.
- Theo dõi các chuyến đang diễn ra.
- Kiểm tra trạng thái tài xế.
- Xử lý các trường hợp chuyến bị lỗi.
- Tra cứu lịch sử giao dịch.

## BR09 – Hỗ trợ báo cáo hoạt động kinh doanh

Hệ thống phải cung cấp dữ liệu và báo cáo phục vụ công tác quản lý của doanh nghiệp.

Các thông tin cần theo dõi gồm:

- Số lượng chuyến.
- Doanh thu.
- Tỷ lệ chuyến hoàn thành.
- Tỷ lệ chuyến hủy.
- Hiệu quả hoạt động của tài xế.

## BR10 – Đảm bảo phân quyền và bảo mật

Hệ thống phải đảm bảo người dùng được xác thực trước khi sử dụng các chức năng yêu cầu tài khoản.

Các chức năng quản trị phải được phân quyền để hạn chế nhân viên thông thường thực hiện các thao tác nhạy cảm.

Hệ thống phải bảo vệ:

- Thông tin cá nhân.
- Thông tin phương tiện.
- Dữ liệu vị trí.
- Dữ liệu giao dịch.

Hệ thống phải lưu vết các thao tác quan trọng để phục vụ kiểm tra khi xảy ra sự cố.

## BR11 – Đảm bảo khả năng mở rộng

Hệ thống phải có khả năng phục vụ số lượng lớn khách hàng và tài xế.

Các thành phần của hệ thống phải có khả năng mở rộng độc lập khi tải tăng.

Việc bổ sung chức năng mới phải hạn chế ảnh hưởng đến các chức năng đang hoạt động.

## BR12 – Hỗ trợ phát triển hệ thống trong tương lai

Hệ thống phải có kiến trúc đủ linh hoạt để doanh nghiệp có thể:

- Bổ sung loại dịch vụ mới.
- Thêm phương thức thanh toán mới.
- Thêm nhà cung cấp dịch vụ thông báo.
- Thay đổi một số thành phần kỹ thuật.
- Triển khai chức năng mới từng phần.

Các thay đổi trong tương lai không được yêu cầu xây dựng lại toàn bộ ứng dụng.

---

# Các yêu cầu cần làm rõ

Một số yêu cầu nghiệp vụ hiện chưa được doanh nghiệp xác định cụ thể và cần Business Analyst làm rõ với các bên liên quan:

- Công thức tính cước.
- Tiêu chí ưu tiên và lựa chọn tài xế.
- Thời gian tài xế phải phản hồi yêu cầu.
- Chính sách hủy chuyến.
- Cách xử lý khi mất kết nối mạng.
- Thời gian lưu trữ dữ liệu.


# Business Process – Quy trình nghiệp vụ đặt xe

## 1. Tổng quan quy trình

Quy trình nghiệp vụ chính của hệ thống CAB:

**Khách hàng tạo yêu cầu**
→ **Hệ thống tiếp nhận yêu cầu**
→ **Tìm tài xế phù hợp**
→ **Tài xế nhận / từ chối chuyến**
→ **Thực hiện chuyến**
→ **Hoàn thành chuyến**
→ **Tính cước**
→ **Thanh toán**
→ **Đánh giá tài xế**

---

# 2. Chi tiết Business Process

## Bước 1: Khách hàng tạo yêu cầu đặt xe

**Actor:** Khách hàng

Khách hàng:

- Đăng nhập vào hệ thống.
- Nhập điểm đón.
- Nhập điểm đến.
- Lựa chọn loại xe.
- Gửi yêu cầu đặt xe.

**Kết quả:** Hệ thống tiếp nhận yêu cầu đặt xe và thông báo cho khách hàng rằng yêu cầu đã được tiếp nhận.

---

## Bước 2: Hệ thống tìm tài xế

**Actor:** Hệ thống

Hệ thống xác định các tài xế phù hợp dựa trên:

- Vị trí của tài xế.
- Trạng thái sẵn sàng nhận chuyến.
- Các tiêu chí vận hành khác.

Hệ thống ưu tiên các tài xế phù hợp và gần khách hàng.

**Kết quả:** Một tài xế phù hợp được lựa chọn để gửi yêu cầu chuyến.

---

## Bước 3: Tài xế nhận hoặc từ chối chuyến

**Actor:** Tài xế

Hệ thống gửi thông báo về chuyến mới cho tài xế.

Tài xế có hai lựa chọn:

### Trường hợp 1: Tài xế chấp nhận

- Tài xế chấp nhận chuyến.
- Hệ thống cập nhật tài xế được phân công.
- Khách hàng nhận thông báo tài xế đã nhận chuyến.
- Hệ thống cung cấp thời gian dự kiến tài xế đến.

→ Chuyển sang **Bước 4: Thực hiện chuyến**.

### Trường hợp 2: Tài xế từ chối hoặc không phản hồi

- Hệ thống xác định tài xế không nhận chuyến.
- Hệ thống tiếp tục tìm tài xế khác.
- Khách hàng không cần tạo lại yêu cầu.

Nếu không tìm được tài xế:

- Hệ thống thông báo rõ ràng cho khách hàng.
- Quy trình đặt xe kết thúc.

---

## Bước 4: Tài xế thực hiện chuyến

**Actor:** Tài xế**

Tài xế cập nhật trạng thái chuyến theo quá trình thực hiện:

1. **Đã đến điểm đón**
2. **Đã đón khách**
3. **Đang di chuyển**
4. **Hoàn thành chuyến**

Trong quá trình thực hiện, hệ thống lưu thông tin vị trí của tài xế để hỗ trợ theo dõi và dự kiến thời gian đến.

Khách hàng có thể theo dõi trạng thái hiện tại của chuyến.

---

## Bước 5: Hoàn thành chuyến và tính cước

**Actor:** Hệ thống**

Sau khi tài xế cập nhật trạng thái **Hoàn thành chuyến**:

- Hệ thống xác định số tiền khách hàng phải trả.
- Số tiền được xác định dựa trên:
  - Loại dịch vụ.
  - Thông tin chuyến đi.

**Kết quả:** Hệ thống tạo thông tin cước cần thanh toán.

> Công thức tính cước cụ thể hiện chưa được doanh nghiệp xác định và cần Business Analyst làm rõ.

---

## Bước 6: Thanh toán

**Actor:** Khách hàng + Hệ thống + Nhà cung cấp thanh toán**

Khách hàng có thể lựa chọn:

- Thanh toán bằng tiền mặt.
- Thanh toán điện tử.

### Thanh toán tiền mặt

- Khách hàng thanh toán tiền mặt.
- Hệ thống ghi nhận kết quả thanh toán.

### Thanh toán điện tử

- Hệ thống gửi yêu cầu đến nhà cung cấp thanh toán bên ngoài.
- Nhà cung cấp xử lý giao dịch.
- Hệ thống nhận kết quả thanh toán.

Nếu thanh toán thành công:

- Hệ thống ghi nhận giao dịch thành công.
- Thông báo kết quả cho khách hàng.

Nếu thanh toán thất bại:

- Hệ thống thông báo cho khách hàng.
- Cho phép xử lý lại theo chính sách của doanh nghiệp.

---

## Bước 7: Đánh giá tài xế

**Actor:** Khách hàng

Sau khi chuyến đi hoàn thành:

- Khách hàng xem thông tin chuyến đi.
- Khách hàng có thể đánh giá tài xế.
- Hệ thống lưu kết quả đánh giá.

---

# 3. Business Process Flow

```text
[Khách hàng]
     |
     v
[Nhập điểm đón, điểm đến, loại xe]
     |
     v
[Gửi yêu cầu đặt xe]
     |
     v
[Hệ thống tiếp nhận yêu cầu]
     |
     v
[Tìm tài xế phù hợp]
     |
     v
[Gửi yêu cầu cho tài xế]
     |
     v
[Tài xế phản hồi]
     |
     +----------------------+
     |                      |
   Nhận                  Từ chối /
     |                   Không phản hồi
     v                      |
[Phân công tài xế]          v
     |                [Tìm tài xế khác]
     |                      |
     |                +-----+-----+
     |                |           |
     |             Tìm thấy    Không tìm thấy
     |                |           |
     |                |           v
     |                |      [Thông báo KH]
     |                |           |
     |                |         [Kết thúc]
     |                |
     +<---------------+
     |
     v
[Thực hiện chuyến]
     |
     v
[Đã đến điểm đón]
     |
     v
[Đã đón khách]
     |
     v
[Đang di chuyển]
     |
     v
[Hoàn thành chuyến]
     |
     v
[Tính cước]
     |
     v
[Thanh toán]
     |
     +-------------------+
     |                   |
   Thành công         Thất bại
     |                   |
     v                   v
[Ghi nhận]       [Thông báo + xử lý lại]
     |                   |
     +---------+---------+
               |
               v
       [Đánh giá tài xế]
               |
               v
            [Kết thúc]
```
# Phân rã yêu cầu chức năng – CAB System

## FR01. Quản lý tài khoản và người dùng

### FR01.1. Quản lý khách hàng
- FR01.1.1. Đăng ký tài khoản
- FR01.1.2. Đăng nhập
- FR01.1.3. Cập nhật thông tin cá nhân
- FR01.1.4. Xem lịch sử chuyến đi

### FR01.2. Quản lý tài xế
- FR01.2.1. Đăng ký tài khoản tài xế
- FR01.2.2. Tạo tài khoản tài xế bởi nhân viên vận hành
- FR01.2.3. Cập nhật hồ sơ tài xế
- FR01.2.4. Cập nhật thông tin phương tiện
- FR01.2.5. Cập nhật trạng thái hoạt động
- FR01.2.6. Cập nhật trạng thái sẵn sàng nhận chuyến
- FR01.2.7. Cập nhật vị trí tài xế

---

## FR02. Quản lý đặt xe

### FR02.1. Tạo yêu cầu đặt xe
- FR02.1.1. Nhập điểm đón
- FR02.1.2. Nhập điểm đến
- FR02.1.3. Lựa chọn loại xe
- FR02.1.4. Gửi yêu cầu đặt xe

### FR02.2. Theo dõi yêu cầu đặt xe
- FR02.2.1. Theo dõi trạng thái tìm tài xế
- FR02.2.2. Xem tài xế đã nhận chuyến
- FR02.2.3. Xem thời gian dự kiến tài xế đến
- FR02.2.4. Theo dõi trạng thái hiện tại của chuyến

---

## FR03. Tìm kiếm và phân công tài xế

### FR03.1. Xác định tài xế phù hợp
- FR03.1.1. Kiểm tra vị trí tài xế
- FR03.1.2. Kiểm tra trạng thái sẵn sàng
- FR03.1.3. Kiểm tra các tiêu chí vận hành
- FR03.1.4. Ưu tiên tài xế phù hợp và gần khách hàng

### FR03.2. Gửi và xử lý yêu cầu chuyến
- FR03.2.1. Gửi thông báo chuyến đến tài xế
- FR03.2.2. Tiếp nhận phản hồi của tài xế
- FR03.2.3. Xử lý tài xế chấp nhận chuyến
- FR03.2.4. Xử lý tài xế từ chối chuyến
- FR03.2.5. Xử lý tài xế không phản hồi

### FR03.3. Tìm tài xế thay thế
- FR03.3.1. Tiếp tục tìm tài xế khác
- FR03.3.2. Phân công tài xế mới
- FR03.3.3. Thông báo không tìm được tài xế

---

## FR04. Quản lý chuyến đi

### FR04.1. Quản lý trạng thái chuyến
- FR04.1.1. Đã nhận chuyến
- FR04.1.2. Đã đến điểm đón
- FR04.1.3. Đã đón khách
- FR04.1.4. Đang di chuyển
- FR04.1.5. Hoàn thành chuyến

### FR04.2. Theo dõi chuyến đi
- FR04.2.1. Khách hàng theo dõi trạng thái chuyến
- FR04.2.2. Lưu thông tin chuyến đi
- FR04.2.3. Xem lịch sử chuyến đi

---

## FR05. Tính cước và thanh toán

### FR05.1. Tính cước
- FR05.1.1. Xác định loại dịch vụ
- FR05.1.2. Sử dụng thông tin chuyến đi
- FR05.1.3. Xác định số tiền khách hàng phải trả

### FR05.2. Thanh toán
- FR05.2.1. Thanh toán bằng tiền mặt
- FR05.2.2. Thanh toán điện tử
- FR05.2.3. Gửi yêu cầu đến nhà cung cấp thanh toán
- FR05.2.4. Nhận kết quả giao dịch

### FR05.3. Xử lý thanh toán thất bại
- FR05.3.1. Thông báo thanh toán thất bại
- FR05.3.2. Cho phép xử lý lại thanh toán
- FR05.3.3. Lưu kết quả giao dịch

---

## FR06. Quản lý thông báo

### FR06.1. Thông báo cho khách hàng
- FR06.1.1. Thông báo yêu cầu đặt xe được tiếp nhận
- FR06.1.2. Thông báo tài xế đã nhận chuyến
- FR06.1.3. Thông báo tài xế đến điểm đón
- FR06.1.4. Thông báo chuyến hoàn thành
- FR06.1.5. Thông báo kết quả thanh toán

### FR06.2. Thông báo cho tài xế
- FR06.2.1. Thông báo chuyến mới
- FR06.2.2. Thông báo thay đổi liên quan đến chuyến

### FR06.3. Quản lý kênh thông báo
- FR06.3.1. Hỗ trợ các kênh thông báo hiện tại
- FR06.3.2. Cho phép mở rộng thêm kênh thông báo

---

## FR07. Quản lý vận hành

### FR07.1. Quản lý dữ liệu
- FR07.1.1. Quản lý khách hàng
- FR07.1.2. Quản lý tài xế
- FR07.1.3. Quản lý phương tiện
- FR07.1.4. Quản lý chuyến đi

### FR07.2. Giám sát hoạt động
- FR07.2.1. Xem các chuyến đang diễn ra
- FR07.2.2. Kiểm tra trạng thái tài xế
- FR07.2.3. Hỗ trợ xử lý chuyến bị lỗi
- FR07.2.4. Tra cứu lịch sử giao dịch

### FR07.3. Quản trị và phân quyền
- FR07.3.1. Phân quyền nhân viên
- FR07.3.2. Kiểm soát các thao tác quản trị
- FR07.3.3. Hạn chế thao tác nhạy cảm theo quyền

---

## FR08. Báo cáo

### FR08.1. Báo cáo hoạt động
- FR08.1.1. Báo cáo số lượng chuyến
- FR08.1.2. Báo cáo doanh thu
- FR08.1.3. Báo cáo tỷ lệ chuyến hoàn thành
- FR08.1.4. Báo cáo tỷ lệ hủy

### FR08.2. Báo cáo tài xế
- FR08.2.1. Theo dõi hiệu quả hoạt động của tài xế

---

## FR09. Đánh giá tài xế

### FR09.1. Đánh giá sau chuyến
- FR09.1.1. Cho phép khách hàng đánh giá tài xế
- FR09.1.2. Lưu kết quả đánh giá

---

# Tổng quan phân rã

CAB System
│
├── FR01. Quản lý tài khoản và người dùng
│   ├── Quản lý khách hàng
│   └── Quản lý tài xế
│
├── FR02. Quản lý đặt xe
│   ├── Tạo yêu cầu đặt xe
│   └── Theo dõi yêu cầu
│
├── FR03. Tìm kiếm và phân công tài xế
│   ├── Xác định tài xế
│   ├── Xử lý phản hồi
│   └── Tìm tài xế thay thế
│
├── FR04. Quản lý chuyến đi
│   ├── Quản lý trạng thái
│   └── Theo dõi chuyến
│
├── FR05. Tính cước và thanh toán
│   ├── Tính cước
│   ├── Thanh toán
│   └── Xử lý thanh toán thất bại
│
├── FR06. Quản lý thông báo
│   ├── Thông báo khách hàng
│   ├── Thông báo tài xế
│   └── Quản lý kênh thông báo
│
├── FR07. Quản lý vận hành
│   ├── Quản lý dữ liệu
│   ├── Giám sát hoạt động
│   └── Quản trị và phân quyền
│
├── FR08. Báo cáo
│   ├── Báo cáo hoạt động
│   └── Báo cáo tài xế
│
└── FR09. Đánh giá tài xế
    └── Đánh giá sau chuyến

# Business Rules – Quy tắc nghiệp vụ

## BR01 – Chỉ tài xế sẵn sàng mới được nhận chuyến

- Hệ thống chỉ xem xét các tài xế đang ở trạng thái **sẵn sàng nhận chuyến**.
- Việc lựa chọn tài xế còn dựa trên vị trí và các tiêu chí vận hành khác.

## BR02 – Ưu tiên tài xế phù hợp và gần khách hàng

- Hệ thống phải ưu tiên các tài xế phù hợp và gần vị trí khách hàng.
- Tiêu chí ưu tiên cụ thể hiện chưa được doanh nghiệp xác định.

## BR03 – Tài xế có quyền chấp nhận hoặc từ chối chuyến

- Khi nhận được yêu cầu chuyến, tài xế có thể:
  - Chấp nhận chuyến.
  - Từ chối chuyến.

## BR04 – Tự động tìm tài xế thay thế

- Nếu tài xế được đề xuất không nhận chuyến hoặc không phản hồi, hệ thống phải tiếp tục tìm tài xế khác.
- Khách hàng không cần tạo lại yêu cầu đặt xe.

## BR05 – Thông báo khi không tìm được tài xế

- Nếu hệ thống không tìm được tài xế phù hợp, khách hàng phải được thông báo rõ ràng.

## BR06 – Cập nhật trạng thái chuyến theo quá trình thực hiện

Tài xế phải cập nhật trạng thái chuyến theo quá trình:

1. Đã đến điểm đón.
2. Đã đón khách.
3. Đang di chuyển.
4. Hoàn thành chuyến.

## BR07 – Tính cước sau khi chuyến hoàn thành

- Sau khi chuyến đi hoàn thành, hệ thống xác định số tiền khách hàng phải trả.
- Số tiền dựa trên loại dịch vụ và thông tin chuyến đi.
- Công thức tính cước cụ thể chưa được xác định.

## BR08 – Hỗ trợ hai hình thức thanh toán

Khách hàng có thể thanh toán bằng:

- Tiền mặt.
- Phương thức thanh toán điện tử.

## BR09 – Không lưu thông tin thanh toán nhạy cảm

- Hệ thống CAB không được lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán.
- Thanh toán điện tử phải thông qua nhà cung cấp thanh toán bên ngoài.

## BR10 – Phân quyền chức năng quản trị

- Các chức năng quản trị phải được phân quyền.
- Nhân viên thông thường không được thực hiện các thao tác nhạy cảm nếu không có quyền.

## BR11 – Xác thực người dùng

- Khách hàng và tài xế phải được xác thực trước khi sử dụng các chức năng yêu cầu tài khoản.

## BR12 – Bảo vệ dữ liệu

Hệ thống phải bảo vệ:

- Thông tin cá nhân.
- Thông tin phương tiện.
- Dữ liệu vị trí.
- Dữ liệu giao dịch.

## BR13 – Lưu vết thao tác quan trọng

- Hệ thống phải lưu vết các thao tác quan trọng.
- Dữ liệu này phục vụ kiểm tra khi xảy ra sự cố.

## BR14 – Thành phần hệ thống phải có khả năng mở rộng độc lập

- Các thành phần cần có khả năng mở rộng độc lập khi tải tăng.
- Một lỗi ở chức năng thanh toán hoặc thông báo không được làm toàn bộ hệ thống đặt xe ngừng hoạt động.

## BR15 – Hệ thống phải hỗ trợ mở rộng trong tương lai

Doanh nghiệp phải có khả năng:

- Bổ sung loại dịch vụ mới.
- Thêm phương thức thanh toán.
- Thêm nhà cung cấp thông báo.
- Thay đổi một số thành phần kỹ thuật.
- Triển khai chức năng mới từng phần.

# Business Exceptions – Các ngoại lệ

## EX01 – Tài xế từ chối chuyến

**Điều kiện:**
- Tài xế được hệ thống đề xuất nhưng từ chối chuyến.

**Xử lý:**
- Hệ thống tiếp tục tìm tài xế khác.
- Khách hàng không cần tạo lại yêu cầu.

---

## EX02 – Tài xế không phản hồi

**Điều kiện:**
- Tài xế được đề xuất nhưng không phản hồi.

**Xử lý:**
- Hệ thống tiếp tục tìm tài xế khác.

**Lưu ý:**
- Thời gian tài xế phải phản hồi hiện chưa được doanh nghiệp xác định.

---

## EX03 – Không tìm được tài xế

**Điều kiện:**
- Hệ thống không tìm được tài xế phù hợp.

**Xử lý:**
- Thông báo rõ ràng cho khách hàng.
- Không yêu cầu khách hàng tạo lại yêu cầu một cách tự động.

---

## EX04 – Thanh toán điện tử thất bại

**Điều kiện:**
- Giao dịch thanh toán điện tử không thành công.

**Xử lý:**
- Thông báo kết quả thất bại cho khách hàng.
- Cho phép xử lý lại theo chính sách của doanh nghiệp.

---

## EX05 – Lỗi chức năng thanh toán

**Điều kiện:**
- Thành phần thanh toán xảy ra lỗi.

**Yêu cầu nghiệp vụ:**
- Lỗi thanh toán không được làm toàn bộ hệ thống đặt xe ngừng hoạt động.

---

## EX06 – Lỗi chức năng thông báo

**Điều kiện:**
- Thành phần thông báo xảy ra lỗi.

**Yêu cầu nghiệp vụ:**
- Lỗi thông báo không được làm toàn bộ hệ thống đặt xe ngừng hoạt động.

---

## EX07 – Thao tác quản trị không có quyền

**Điều kiện:**
- Nhân viên thực hiện chức năng quản trị nhạy cảm nhưng không có quyền.

**Xử lý:**
- Hệ thống phải kiểm soát quyền truy cập và không cho phép thực hiện thao tác trái quyền.

---

## EX08 – Người dùng chưa xác thực

**Điều kiện:**
- Khách hàng hoặc tài xế chưa được xác thực nhưng cố gắng sử dụng chức năng yêu cầu tài khoản.

**Xử lý:**
- Hệ thống yêu cầu người dùng xác thực trước khi sử dụng chức năng.

---

# Các ngoại lệ chưa được xác định đầy đủ

Tài liệu yêu cầu doanh nghiệp cần làm rõ thêm:

- Cách xử lý khi **mất kết nối mạng**.
- **Chính sách hủy chuyến**.
- **Thời gian tài xế phải phản hồi**.
- **Tiêu chí ưu tiên tài xế**.
- **Công thức tính cước**.
- **Thời gian lưu trữ dữ liệu**.

Các nội dung này chưa nên tự đặt ra quy tắc cụ thể vì tài liệu xác định đây là những vấn đề cần Business Analyst làm rõ với các bên liên quan trước khi phát triển. 

# Mô hình hóa dữ liệu – CAB System

## 1. Các thực thể chính

### 1.1. Customer – Khách hàng

Lưu thông tin người sử dụng dịch vụ đặt xe.

**Thuộc tính chính:**
- CustomerID
- FullName
- Phone
- Email
- Password
- Address
- CreatedAt

**Chức năng liên quan:**
- Đăng ký / đăng nhập.
- Cập nhật thông tin cá nhân.
- Tạo yêu cầu đặt xe.
- Xem lịch sử chuyến đi.
- Thanh toán.
- Đánh giá tài xế.

---

### 1.2. Driver – Tài xế

Lưu thông tin tài xế sử dụng hệ thống.

**Thuộc tính chính:**
- DriverID
- FullName
- Phone
- Email
- Password
- Status
- IsAvailable
- CurrentLocation

**Chức năng liên quan:**
- Đăng ký / đăng nhập.
- Cập nhật hồ sơ.
- Cập nhật trạng thái hoạt động.
- Bật / tắt trạng thái sẵn sàng.
- Nhận / từ chối chuyến.
- Cập nhật trạng thái chuyến.
- Cập nhật vị trí.

---

### 1.3. Vehicle – Phương tiện

Lưu thông tin phương tiện của tài xế.

**Thuộc tính chính:**
- VehicleID
- DriverID
- VehicleType
- LicensePlate
- VehicleStatus

**Mối quan hệ:**
- Một tài xế có thể quản lý phương tiện.
- Phương tiện được sử dụng để thực hiện chuyến đi.

---

### 1.4. Booking / Trip – Chuyến đặt xe

Lưu thông tin yêu cầu và chuyến đi của khách hàng.

**Thuộc tính chính:**
- TripID
- CustomerID
- DriverID
- VehicleID
- PickupLocation
- Destination
- VehicleType
- Status
- RequestedAt
- StartedAt
- CompletedAt

**Trạng thái chuyến có thể gồm:**
- Searching
- DriverAssigned
- DriverArrived
- PassengerPickedUp
- InProgress
- Completed

**Mối quan hệ:**
- Một khách hàng có thể tạo nhiều chuyến.
- Một tài xế có thể thực hiện nhiều chuyến.
- Một chuyến thuộc về một khách hàng.
- Một chuyến có thể được phân công cho một tài xế.

---

### 1.5. DriverAssignment – Phân công tài xế

Lưu thông tin quá trình hệ thống tìm và phân công tài xế.

**Thuộc tính chính:**
- AssignmentID
- TripID
- DriverID
- AssignmentStatus
- ResponseTime
- AssignedAt

**Mục đích:**
- Theo dõi tài xế được đề xuất.
- Ghi nhận tài xế chấp nhận hoặc từ chối.
- Hỗ trợ trường hợp tài xế không phản hồi.
- Cho phép hệ thống tiếp tục tìm tài xế khác.

---

### 1.6. Payment – Thanh toán

Lưu thông tin giao dịch thanh toán.

**Thuộc tính chính:**
- PaymentID
- TripID
- Amount
- PaymentMethod
- PaymentStatus
- TransactionTime

**PaymentMethod:**
- Cash
- Electronic

**PaymentStatus:**
- Pending
- Success
- Failed

> Không lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán trong hệ thống CAB.

---

### 1.7. Rating – Đánh giá

Lưu đánh giá của khách hàng đối với tài xế sau chuyến đi.

**Thuộc tính chính:**
- RatingID
- TripID
- CustomerID
- DriverID
- Rating
- Comment
- CreatedAt

**Mối quan hệ:**
- Khách hàng đánh giá tài xế sau khi chuyến hoàn thành.

---

### 1.8. Notification – Thông báo

Lưu thông tin các thông báo được gửi đến khách hàng hoặc tài xế.

**Thuộc tính chính:**
- NotificationID
- UserID
- TripID
- NotificationType
- Message
- Status
- CreatedAt

**Các loại thông báo:**
- Yêu cầu đặt xe được tiếp nhận.
- Tài xế nhận chuyến.
- Tài xế đến điểm đón.
- Chuyến hoàn thành.
- Kết quả thanh toán.
- Chuyến mới cho tài xế.
- Thay đổi liên quan đến chuyến.

---

### 1.9. User / Staff – Nhân viên vận hành

Lưu thông tin nhân viên sử dụng chức năng quản trị.

**Thuộc tính chính:**
- StaffID
- FullName
- Username
- Password
- Role
- Status

**Chức năng:**
- Quản lý khách hàng.
- Quản lý tài xế.
- Quản lý phương tiện.
- Quản lý chuyến đi.
- Tra cứu giao dịch.
- Xử lý chuyến bị lỗi.
- Thực hiện chức năng theo quyền được cấp.

---

# 2. Mối quan hệ giữa các thực thể

| Quan hệ | Cardinality | Ý nghĩa |
|---|---|---|
| Customer → Trip | 1 : N | Một khách hàng có thể tạo nhiều chuyến |
| Driver → Trip | 1 : N | Một tài xế có thể thực hiện nhiều chuyến |
| Driver → Vehicle | 1 : N | Một tài xế có thể có/quản lý phương tiện |
| Trip → Payment | 1 : 1 | Một chuyến có thông tin thanh toán |
| Trip → Rating | 1 : 0..1 | Một chuyến có thể có đánh giá sau khi hoàn thành |
| Trip → DriverAssignment | 1 : N | Một chuyến có thể có nhiều lần đề xuất tài xế |
| Driver → DriverAssignment | 1 : N | Một tài xế có thể được đề xuất cho nhiều chuyến |
| Trip → Notification | 1 : N | Một chuyến có thể phát sinh nhiều thông báo |
| Customer → Notification | 1 : N | Khách hàng có thể nhận nhiều thông báo |
| Driver → Notification | 1 : N | Tài xế có thể nhận nhiều thông báo |

---

# 3. Mô hình dữ liệu tổng quát

```text
                    ┌──────────────┐
                    │   CUSTOMER   │
                    └──────┬───────┘
                           │ 1
                           │
                           │ N
                    ┌──────▼───────┐
                    │     TRIP     │
                    └──┬───┬───┬───┘
                       │   │   │
              1:N      │   │   │ 1:1
                       │   │   └──────────────┐
                       │   │                  │
                       │   │             ┌────▼─────┐
                       │   │             │  PAYMENT  │
                       │   │             └──────────┘
                       │   │
                       │   │
                       │   └──────────────┐
                       │                  │
                       │             ┌────▼─────┐
                       │             │  RATING   │
                       │             └──────────┘
                       │
                       │ 1:N
                ┌──────▼──────────┐
                │ DRIVER ASSIGNMENT│
                └──────┬──────────┘
                       │ N
                       │
                       │ 1
                ┌──────▼───────┐
                │    DRIVER    │
                └──────┬───────┘
                       │
                       │ 1:N
                ┌──────▼───────┐
                │   VEHICLE    │
                └──────────────┘

                    TRIP
                     │
                     │ 1:N
                     ▼
               ┌──────────────┐
               │ NOTIFICATION │
               └──────────────┘
```
# Non-Functional Requirements – Yêu cầu phi chức năng

## NFR01 – Hiệu năng (Performance)

- Hệ thống phải có khả năng phục vụ số lượng lớn khách hàng và tài xế.
- Hệ thống phải duy trì khả năng hoạt động ổn định khi số lượng người dùng và yêu cầu đặt xe tăng cao.
- Các thành phần của hệ thống cần có khả năng mở rộng độc lập khi tải tăng.

> Chưa có yêu cầu cụ thể về thời gian phản hồi hoặc số request/giây trong tài liệu.

---

## NFR02 – Khả năng mở rộng (Scalability)

- Hệ thống phải có khả năng mở rộng khi số lượng khách hàng và tài xế tăng.
- Các thành phần có thể được mở rộng độc lập theo nhu cầu.
- Việc mở rộng một thành phần không được yêu cầu mở rộng toàn bộ hệ thống.

---

## NFR03 – Tính sẵn sàng và ổn định (Availability & Reliability)

- Hệ thống phải hoạt động ổn định trong thời điểm nhu cầu đặt xe tăng cao.
- Lỗi của một thành phần như thanh toán hoặc thông báo không được làm toàn bộ hệ thống đặt xe ngừng hoạt động.
- Hệ thống cần có khả năng tiếp tục phục vụ các chức năng chính khi một thành phần gặp sự cố.

---

## NFR04 – Bảo mật (Security)

Hệ thống phải bảo vệ các loại dữ liệu:

- Thông tin cá nhân của khách hàng.
- Thông tin cá nhân của tài xế.
- Thông tin phương tiện.
- Dữ liệu vị trí.
- Dữ liệu giao dịch.

Ngoài ra:

- Người dùng phải được xác thực trước khi sử dụng các chức năng yêu cầu tài khoản.
- Chức năng quản trị phải được phân quyền.
- Các thao tác quan trọng phải được lưu vết.
- Hệ thống không được lưu trực tiếp thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán.

---

## NFR05 – Khả năng bảo trì (Maintainability)

- Hệ thống phải cho phép thay đổi một số thành phần kỹ thuật mà không phải xây dựng lại toàn bộ ứng dụng.
- Các chức năng mới có thể được triển khai từng phần.
- Việc thay đổi hoặc bổ sung một chức năng không nên gây ảnh hưởng lớn đến các chức năng đang hoạt động.

---

## NFR06 – Khả năng mở rộng chức năng (Extensibility)

Hệ thống phải có khả năng mở rộng để:

- Bổ sung loại dịch vụ mới.
- Bổ sung phương thức thanh toán mới.
- Tích hợp thêm nhà cung cấp dịch vụ thông báo.
- Thay đổi hoặc thay thế một số thành phần kỹ thuật.

---

## NFR07 – Khả năng tích hợp (Interoperability)

- Hệ thống phải có khả năng tích hợp với nhà cung cấp thanh toán bên ngoài.
- Hệ thống phải có khả năng tích hợp với các nhà cung cấp dịch vụ thông báo.
- Có thể bổ sung thêm các nhà cung cấp hoặc kênh dịch vụ mới trong tương lai.

---

## NFR08 – Khả năng triển khai (Deployability)

- Các chức năng mới phải có khả năng được triển khai từng phần.
- Việc triển khai chức năng mới phải hạn chế ảnh hưởng đến các chức năng đang hoạt động.

---

## NFR09 – Khả năng kiểm tra và truy vết (Auditability)

- Hệ thống phải lưu vết các thao tác quan trọng.
- Thông tin lưu vết được sử dụng để kiểm tra và xử lý khi xảy ra sự cố.

# Vẽ các Use Case
flowchart LR

    %% Actors
    Customer([Khách hàng])
    Driver([Tài xế])
    Staff([Nhân viên vận hành])
    Payment([Nhà cung cấp thanh toán])
    Notification([Nhà cung cấp dịch vụ thông báo])

    %% System
    subgraph CAB["CAB System"]

        UC1((Quản lý tài khoản))
        UC2((Đặt xe))
        UC3((Theo dõi chuyến đi))
        UC4((Thanh toán))
        UC5((Đánh giá tài xế))

        UC6((Quản lý tài xế))
        UC7((Quản lý phương tiện))
        UC8((Nhận / từ chối chuyến))
        UC9((Cập nhật trạng thái chuyến))
        UC10((Cập nhật vị trí))

        UC11((Tìm kiếm tài xế))
        UC12((Phân công tài xế))

        UC13((Quản lý chuyến đi))
        UC14((Quản lý khách hàng))
        UC15((Tra cứu giao dịch))
        UC16((Xử lý chuyến bị lỗi))
        UC17((Báo cáo))

        UC18((Gửi thông báo))
    end

    %% Customer
    Customer --> UC1
    Customer --> UC2
    Customer --> UC3
    Customer --> UC4
    Customer --> UC5

    %% Driver
    Driver --> UC1
    Driver --> UC8
    Driver --> UC9
    Driver --> UC10

    %% Staff
    Staff --> UC6
    Staff --> UC7
    Staff --> UC13
    Staff --> UC14
    Staff --> UC15
    Staff --> UC16
    Staff --> UC17

    %% External systems
    Payment --> UC4
    Notification --> UC18

    %% Booking process
    UC2 --> UC11
    UC11 --> UC12
    UC12 --> UC8

    %% Trip
    UC8 --> UC13
    UC9 --> UC13

    %% Notification
    UC2 --> UC18
    UC8 --> UC18
    UC9 --> UC18
    UC4 --> UC18
``
# ĐẶC TẢ USE CASE

## UC01 – Đăng ký tài khoản

| Thành phần | Nội dung |
|---|---|
| **Tên Use Case** | Đăng ký tài khoản |
| **Mã** | UC01 |
| **Actor** | Khách hàng |
| **Mục tiêu** | Tạo tài khoản để sử dụng các chức năng của hệ thống CAB |
| **Tiền điều kiện** | Khách hàng chưa có tài khoản |
| **Hậu điều kiện** | Tài khoản khách hàng được tạo thành công |
| **Kích hoạt** | Khách hàng chọn chức năng đăng ký |

### Luồng chính

1. Khách hàng chọn **Đăng ký**.
2. Hệ thống yêu cầu nhập thông tin tài khoản.
3. Khách hàng nhập thông tin cá nhân.
4. Khách hàng gửi thông tin đăng ký.
5. Hệ thống kiểm tra thông tin.
6. Hệ thống tạo tài khoản.
7. Hệ thống thông báo đăng ký thành công.

### Luồng ngoại lệ

- **E1:** Thông tin đăng ký không hợp lệ → Hệ thống yêu cầu khách hàng nhập lại.
- **E2:** Tài khoản đã tồn tại → Hệ thống thông báo và yêu cầu sử dụng thông tin khác.

---

# UC02 – Đặt xe

| Thành phần | Nội dung |
|---|---|
| **Tên Use Case** | Đặt xe |
| **Mã** | UC02 |
| **Actor** | Khách hàng |
| **Mục tiêu** | Tạo yêu cầu đặt xe và tìm được tài xế phù hợp |
| **Tiền điều kiện** | Khách hàng đã đăng nhập |
| **Hậu điều kiện** | Chuyến được tạo và tài xế được phân công hoặc khách hàng được thông báo không tìm được tài xế |
| **Kích hoạt** | Khách hàng gửi yêu cầu đặt xe |

### Luồng chính

1. Khách hàng nhập **điểm đón**.
2. Khách hàng nhập **điểm đến**.
3. Khách hàng lựa chọn **loại xe**.
4. Khách hàng gửi yêu cầu đặt xe.
5. Hệ thống tiếp nhận yêu cầu.
6. Hệ thống tìm kiếm tài xế phù hợp.
7. Hệ thống gửi yêu cầu chuyến đến tài xế.
8. Tài xế chấp nhận chuyến.
9. Hệ thống phân công tài xế.
10. Hệ thống thông báo cho khách hàng.
11. Khách hàng theo dõi trạng thái chuyến.

### Luồng ngoại lệ

- **E1:** Tài xế từ chối chuyến → Hệ thống tiếp tục tìm tài xế khác.
- **E2:** Tài xế không phản hồi → Hệ thống tiếp tục tìm tài xế khác.
- **E3:** Không tìm được tài xế → Hệ thống thông báo cho khách hàng.
- **E4:** Thông tin đặt xe không hợp lệ → Hệ thống yêu cầu khách hàng nhập lại.

---

# UC03 – Theo dõi chuyến đi

| Thành phần | Nội dung |
|---|---|
| **Tên Use Case** | Theo dõi chuyến đi |
| **Mã** | UC03 |
| **Actor** | Khách hàng |
| **Mục tiêu** | Cho phép khách hàng theo dõi trạng thái chuyến |
| **Tiền điều kiện** | Khách hàng đã có chuyến được phân công |
| **Hậu điều kiện** | Khách hàng xem được trạng thái hiện tại của chuyến |
| **Kích hoạt** | Khách hàng mở thông tin chuyến |

### Luồng chính

1. Khách hàng mở chuyến đang thực hiện.
2. Hệ thống lấy thông tin chuyến.
3. Hệ thống hiển thị tài xế đã nhận chuyến.
4. Hệ thống hiển thị thời gian dự kiến tài xế đến.
5. Hệ thống hiển thị trạng thái hiện tại của chuyến.
6. Khách hàng tiếp tục theo dõi cho đến khi chuyến hoàn thành.

### Luồng ngoại lệ

- **E1:** Không lấy được thông tin chuyến → Hệ thống thông báo lỗi.
- **E2:** Không có dữ liệu vị trí mới → Hệ thống hiển thị thông tin vị trí gần nhất.

---

# UC04 – Nhận / từ chối chuyến

| Thành phần | Nội dung |
|---|---|
| **Tên Use Case** | Nhận / từ chối chuyến |
| **Mã** | UC04 |
| **Actor** | Tài xế |
| **Mục tiêu** | Cho phép tài xế phản hồi yêu cầu chuyến |
| **Tiền điều kiện** | Tài xế đang ở trạng thái sẵn sàng nhận chuyến |
| **Hậu điều kiện** | Chuyến được tài xế chấp nhận hoặc hệ thống tiếp tục tìm tài xế khác |
| **Kích hoạt** | Tài xế nhận được yêu cầu chuyến |

### Luồng chính

1. Hệ thống gửi thông báo chuyến mới cho tài xế.
2. Tài xế xem thông tin chuyến.
3. Tài xế chọn **Chấp nhận**.
4. Hệ thống ghi nhận tài xế nhận chuyến.
5. Hệ thống phân công tài xế.
6. Hệ thống thông báo cho khách hàng.

### Luồng thay thế

**Tài xế từ chối:**

1. Tài xế chọn **Từ chối**.
2. Hệ thống ghi nhận tài xế từ chối.
3. Hệ thống tiếp tục tìm tài xế khác.

**Tài xế không phản hồi:**

1. Tài xế không phản hồi yêu cầu.
2. Hệ thống xác định yêu cầu không được phản hồi.
3. Hệ thống tiếp tục tìm tài xế khác.

### Luồng ngoại lệ

- **E1:** Tài xế không còn ở trạng thái sẵn sàng → Không cho phép nhận chuyến.
- **E2:** Hệ thống không thể xử lý phản hồi → Thông báo lỗi và ghi nhận sự cố.

---

# UC05 – Cập nhật trạng thái chuyến

| Thành phần | Nội dung |
|---|---|
| **Tên Use Case** | Cập nhật trạng thái chuyến |
| **Mã** | UC05 |
| **Actor** | Tài xế |
| **Mục tiêu** | Cập nhật trạng thái chuyến trong quá trình thực hiện |
| **Tiền điều kiện** | Tài xế đã được phân công chuyến |
| **Hậu điều kiện** | Trạng thái chuyến được cập nhật |
| **Kích hoạt** | Tài xế thực hiện một giai đoạn của chuyến |

### Luồng chính

1. Tài xế bắt đầu thực hiện chuyến.
2. Tài xế cập nhật **Đã đến điểm đón**.
3. Tài xế cập nhật **Đã đón khách**.
4. Tài xế cập nhật **Đang di chuyển**.
5. Tài xế cập nhật **Hoàn thành chuyến**.
6. Hệ thống lưu trạng thái.
7. Hệ thống thông báo trạng thái phù hợp cho khách hàng.

### Luồng ngoại lệ

- **E1:** Không thể cập nhật trạng thái → Hệ thống thông báo lỗi.
- **E2:** Trạng thái không hợp lệ → Hệ thống từ chối cập nhật.

---

# UC06 – Thanh toán

| Thành phần | Nội dung |
|---|---|
| **Tên Use Case** | Thanh toán |
| **Mã** | UC06 |
| **Actor** | Khách hàng |
| **Actor phụ** | Nhà cung cấp thanh toán |
| **Mục tiêu** | Thanh toán số tiền của chuyến đi |
| **Tiền điều kiện** | Chuyến đi đã hoàn thành và hệ thống đã xác định số tiền phải trả |
| **Hậu điều kiện** | Giao dịch được ghi nhận thành công hoặc thất bại |
| **Kích hoạt** | Khách hàng thực hiện thanh toán |

### Luồng chính – Thanh toán điện tử

1. Hệ thống hiển thị số tiền cần thanh toán.
2. Khách hàng chọn thanh toán điện tử.
3. Hệ thống gửi yêu cầu đến nhà cung cấp thanh toán.
4. Nhà cung cấp xử lý giao dịch.
5. Nhà cung cấp trả kết quả.
6. Hệ thống ghi nhận kết quả giao dịch.
7. Hệ thống thông báo kết quả cho khách hàng.

### Luồng thay thế – Thanh toán tiền mặt

1. Khách hàng chọn thanh toán tiền mặt.
2. Khách hàng thanh toán cho tài xế.
3. Hệ thống ghi nhận kết quả thanh toán.

### Luồng ngoại lệ

- **E1:** Thanh toán điện tử thất bại → Hệ thống thông báo cho khách hàng.
- **E2:** Khách hàng cần thực hiện lại thanh toán → Hệ thống cho phép xử lý lại theo chính sách doanh nghiệp.
- **E3:** Nhà cung cấp thanh toán không phản hồi → Hệ thống ghi nhận giao dịch ở trạng thái phù hợp và xử lý theo quy định.

---

# UC07 – Đánh giá tài xế

| Thành phần | Nội dung |
|---|---|
| **Tên Use Case** | Đánh giá tài xế |
| **Mã** | UC07 |
| **Actor** | Khách hàng |
| **Mục tiêu** | Cho phép khách hàng đánh giá tài xế sau chuyến đi |
| **Tiền điều kiện** | Chuyến đi đã hoàn thành |
| **Hậu điều kiện** | Đánh giá được lưu vào hệ thống |
| **Kích hoạt** | Khách hàng chọn chức năng đánh giá |

### Luồng chính

1. Khách hàng mở thông tin chuyến đã hoàn thành.
2. Hệ thống hiển thị chức năng đánh giá.
3. Khách hàng nhập đánh giá.
4. Khách hàng gửi đánh giá.
5. Hệ thống kiểm tra thông tin.
6. Hệ thống lưu đánh giá.
7. Hệ thống thông báo đánh giá thành công.

### Luồng ngoại lệ

- **E1:** Chuyến chưa hoàn thành → Không cho phép đánh giá.
- **E2:** Thông tin đánh giá không hợp lệ → Yêu cầu khách hàng nhập lại.

---

# UC08 – Quản lý khách hàng

| Thành phần | Nội dung |
|---|---|
| **Tên Use Case** | Quản lý khách hàng |
| **Mã** | UC08 |
| **Actor** | Nhân viên vận hành |
| **Mục tiêu** | Quản lý thông tin khách hàng |
| **Tiền điều kiện** | Nhân viên đã đăng nhập và có quyền quản lý |
| **Hậu điều kiện** | Thông tin khách hàng được cập nhật |
| **Kích hoạt** | Nhân viên chọn chức năng quản lý khách hàng |

### Luồng chính

1. Nhân viên mở danh sách khách hàng.
2. Hệ thống hiển thị thông tin khách hàng.
3. Nhân viên thực hiện thao tác quản lý.
4. Hệ thống kiểm tra quyền.
5. Hệ thống thực hiện thao tác.
6. Hệ thống lưu thay đổi.

### Luồng ngoại lệ

- **E1:** Nhân viên không có quyền → Từ chối thao tác.
- **E2:** Dữ liệu không hợp lệ → Hệ thống yêu cầu nhập lại.

---

# UC09 – Quản lý tài xế

| Thành phần | Nội dung |
|---|---|
| **Tên Use Case** | Quản lý tài xế |
| **Mã** | UC09 |
| **Actor** | Nhân viên vận hành |
| **Mục tiêu** | Quản lý thông tin và trạng thái tài xế |
| **Tiền điều kiện** | Nhân viên đã đăng nhập và có quyền |
| **Hậu điều kiện** | Thông tin tài xế được cập nhật |
| **Kích hoạt** | Nhân viên chọn chức năng quản lý tài xế |

### Luồng chính

1. Nhân viên mở danh sách tài xế.
2. Hệ thống hiển thị thông tin tài xế.
3. Nhân viên chọn tài xế.
4. Nhân viên xem hoặc cập nhật thông tin.
5. Hệ thống kiểm tra quyền.
6. Hệ thống lưu thay đổi.

### Luồng ngoại lệ

- **E1:** Không có quyền → Từ chối thao tác.
- **E2:** Dữ liệu không hợp lệ → Yêu cầu nhập lại.

---

# UC10 – Theo dõi và quản lý chuyến đi

| Thành phần | Nội dung |
|---|---|
| **Tên Use Case** | Theo dõi và quản lý chuyến đi |
| **Mã** | UC10 |
| **Actor** | Nhân viên vận hành |
| **Mục tiêu** | Theo dõi và hỗ trợ xử lý các chuyến đang diễn ra |
| **Tiền điều kiện** | Nhân viên đã đăng nhập và có quyền |
| **Hậu điều kiện** | Nhân viên xem được trạng thái chuyến hoặc xử lý sự cố |
| **Kích hoạt** | Nhân viên mở chức năng quản lý chuyến |

### Luồng chính

1. Nhân viên mở danh sách chuyến.
2. Hệ thống hiển thị các chuyến đang diễn ra.
3. Nhân viên chọn một chuyến.
4. Hệ thống hiển thị thông tin chuyến.
5. Nhân viên kiểm tra trạng thái.
6. Nếu có sự cố, nhân viên thực hiện xử lý theo quyền được cấp.
7. Hệ thống lưu vết thao tác.

### Luồng ngoại lệ

- **E1:** Nhân viên không có quyền → Từ chối thao tác.
- **E2:** Không tìm thấy thông tin chuyến → Hệ thống thông báo lỗi.
# 3. Tiêu chí chấp nhận (Acceptance Criteria - AC)

Các tiêu chí chấp nhận dưới đây được xây dựng dựa trên các yêu cầu nghiệp vụ và Use Case đã xác định, đảm bảo hệ thống đáp ứng đúng kỳ vọng của khách hàng và doanh nghiệp.

---

##  AC cho Quy trình Đặt xe (Booking Flow)

| ID | Tiêu chí chấp nhận | Điều kiện tiên quyết (Pre-condition) | Kết quả mong đợi (Post-condition) |
| :--- | :--- | :--- | :--- |
| **AC-01** | **Tìm kiếm xe thành công:** Hệ thống hiển thị danh sách các tài xế/xe đang hoạt động dựa trên vị trí hiện tại của khách hàng và các tiêu chí lọc (ví dụ: loại xe, khoảng cách). | Khách hàng đã đăng nhập và bật định vị GPS. | Danh sách xe hiển thị đúng vị trí, trạng thái sẵn sàng và được sắp xếp theo khoảng cách gần nhất. |
| **AC-02** | **Gửi yêu cầu đặt xe thành công:** Khi khách hàng chọn xe và bấm "Đặt xe", hệ thống gửi yêu cầu tới tài xế đã chọn (hoặc broadcast tới các tài xế gần nhất tùy cơ chế). | Khách hàng đã chọn được điểm đón, điểm đến và loại xe. | 1. Hệ thống hiển thị trạng thái "Đang tìm tài xế" trên app KH.<br>2. Tài xế nhận được thông báo yêu cầu chuyến mới. |
| **AC-03** | **Hệ thống tự động từ chối yêu cầu khi hết thời gian:** Sau khoảng thời gian hệ thống quy định (ví dụ: 60 giây) mà không có tài xế nhận đơn, hệ thống tự động thông báo "Không tìm thấy tài xế, vui lòng thử lại" cho khách hàng. | Yêu cầu đã được gửi nhưng chưa có tài xế nào chấp nhận. | 1. Trạng thái chuyến chuyển sang "Thất bại".<br>2. Khách hàng nhận được thông báo lỗi trên màn hình. |
| **AC-04** | **Tài xế chấp nhận chuyến thành công:** Tài xế bấm nút "Nhận chuyến", hệ thống cập nhật trạng thái. | Tài xế đang online và nhận được thông báo yêu cầu. | 1. Tài xế được gán vào chuyến.<br>2. Khách hàng nhận được thông báo "Đã tìm thấy tài xế" kèm theo thông tin tài xế (tên, biển số xe, đánh giá). |
| **AC-05** | **Hủy chuyến đi từ phía Khách hàng:** Khách hàng có thể hủy chuyến trước khi tài xế nhận đơn hoặc trong giai đoạn cho phép (ví dụ: trước khi tài xế đến đón). | Chuyến đang ở trạng thái "Đang tìm xe" hoặc "Đã có tài xế". | 1. Chuyến bị hủy trên hệ thống.<br>2. Tài xế nhận được thông báo chuyến đã bị khách hủy.<br>3. Ghi nhận lý do hủy (nếu có) vào lịch sử. |

---

##  AC cho Quy trình Tài xế thực hiện chuyến đi (Trip Execution)

| ID | Tiêu chí chấp nhận | Điều kiện tiên quyết (Pre-condition) | Kết quả mong đợi (Post-condition) |
| :--- | :--- | :--- | :--- |
| **AC-06** | **Cập nhật trạng thái di chuyển:** Tài xế có thể cập nhật các trạng thái: "Đã đón khách", "Bắt đầu di chuyển", "Kết thúc chuyến" trên App Tài xế. | Tài xế đã nhận chuyến thành công. | 1. Trạng thái chuyến được cập nhật trên hệ thống.<br>2. App Khách hàng cập nhật trạng thái tương ứng (ví dụ: "Đã đón khách", "Đang di chuyển"). |
| **AC-07** | **Tính năng hỗ trợ/hủy đơn từ phía Tài xế (Sự cố):** Tài xế gặp sự cố có thể yêu cầu hủy chuyến. Yêu cầu này phải được gửi đến nhân viên vận hành (System Admin) để duyệt, không tự động hủy ngay lập tức. | Tài xế đang thực hiện chuyến và bấm nút "Gặp sự cố/Hủy chuyến". | 1. Yêu cầu hủy được gửi vào hệ thống quản trị.<br>2. Nhân viên vận hành nhận được thông báo và yêu cầu xử lý.<br>3. Chuyến chỉ bị hủy sau khi Admin xác nhận. |
| **AC-08** | **Tính toán chi phí chuyến đi tự động:** Hệ thống tính toán chính xác cước phí dựa trên quãng đường và thời gian di chuyển thực tế khi Tài xế bấm "Kết thúc chuyến". | Tài xế đã bấm nút "Kết thúc chuyến". | 1. Hóa đơn chi tiết được tạo (Km, thời gian, phí cơ bản, phụ phí).<br>2. Hiển thị chi phí lên App Khách hàng để xác nhận thanh toán. |

---

## AC cho Quy trình Thanh toán (Payment)

| ID | Tiêu chí chấp nhận | Điều kiện tiên quyết (Pre-condition) | Kết quả mong đợi (Post-condition) |
| :--- | :--- | :--- | :--- |
| **AC-09** | **Thanh toán qua nhiều phương thức:** Khách hàng có thể chọn thanh toán bằng: (1) Tiền mặt, (2) Thẻ tín dụng/ghi nợ, (3) Ví điện tử (nếu hệ thống có tích hợp). | Chuyến đã kết thúc và hiển thị hóa đơn. | 1. Giao diện thanh toán hiển thị các tùy chọn.<br>2. Khách hàng chọn và thực hiện thành công. |
| **AC-10** | **Đồng bộ trạng thái thanh toán và dữ liệu tài chính:** Khi khách hàng thanh toán, trạng thái chuyến được chuyển sang "Đã thanh toán" hoặc "Thành công". Hệ thống ghi nhận doanh thu và cập nhật số dư (nếu ví nội bộ). | Giao dịch thanh toán thành công từ cổng thanh toán. | 1. Trạng thái chuyến cập nhật đúng.<br>2. Báo cáo tài chính/Doanh thu được cập nhật.<br>3. Gửi hóa đơn điện tử (receipt) đến email/SMS cho khách hàng. |
| **AC-11** | **Xử lý thanh toán thất bại:** Nếu cổng thanh toán (Ví dụ: thẻ hết tiền, lỗi kết nối) trả về thất bại, hệ thống phải hiển thị thông báo lỗi rõ ràng cho Khách hàng và cho phép thử lại hoặc chuyển sang thanh toán tiền mặt. | Khách hàng chọn thanh toán online nhưng gặp lỗi. | 1. Hiển thị popup thông báo lỗi (nêu rõ lý do).<br>2. Không đánh dấu chuyến là "Đã thanh toán".<br>3. Cho phép đổi phương thức thanh toán. |

---

## AC cho Hệ thống Quản lý & Báo cáo (Admin & Management)

| ID | Tiêu chí chấp nhận | Điều kiện tiên quyết (Pre-condition) | Kết quả mong đợi (Post-condition) |
| :--- | :--- | :--- | :--- |
| **AC-12** | **Phân quyền truy cập hệ thống (Role-Based):** Hệ thống phân quyền rõ ràng giữa Nhân viên vận hành và Ban lãnh đạo.<br>- Nhân viên vận hành: Được quyền duyệt hủy đơn, xem tình trạng xe trực tiếp.<br>- Ban lãnh đạo: Được quyền xem các báo cáo tài chính, thống kê. | Người dùng quản trị đăng nhập vào Admin Dashboard. | Menu/quyền truy cập hiển thị chính xác theo tài khoản (không hiển thị tính năng không có quyền). |
| **AC-13** | **Thống kê và Báo cáo thời gian thực (Dashboard):** Hệ thống cho phép Ban lãnh đạo/Nhân viên xem các số liệu: Số lượng chuyến đi thành công, Tổng doanh thu, Tỷ lệ hủy chuyến, Số lượng tài xế đang hoạt động theo các khoảng thời gian (ngày, tuần, tháng). | Ban lãnh đạo truy cập vào tab "Báo cáo". | Biểu đồ và bảng số liệu hiển thị chính xác, dữ liệu được lấy từ cơ sở dữ liệu thời gian thực (hoặc cache gần thời gian thực). |
| **AC-14** | **Quản lý trạng thái xe/Tài xế (Live Tracking):** Nhân viên vận hành có thể xem bản đồ (map view) hiển thị vị trí và trạng thái hoạt động (Online/Offline/Bận) của tất cả tài xế. | Nhân viên vận hành đăng nhập vào hệ thống Admin. | Bản đồ hiển thị biểu tượng tài xế có màu sắc/trạng thái khác nhau, cập nhật thông tin vị trí liên tục (độ trễ cho phép tối đa 5-10 giây). |

---

##  AC cho Bảo mật và Hiệu năng (Non-functional)

| ID | Tiêu chí chấp nhận | Mô tả chi tiết | Điều kiện đánh giá |
| :--- | :--- | :--- | :--- |
| **AC-15** | **Xác thực và Bảo mật dữ liệu:** Tất cả quy trình đăng nhập, giao dịch thanh toán, và truyền dữ liệu vị trí phải được mã hóa theo chuẩn bảo mật (ví dụ: SSL/HTTPS). | Dữ liệu khách hàng, tài xế, và lịch sử giao dịch phải được bảo vệ. | Không có lỗ hổng bảo mật SQL Injection, XSS (dựa trên kết quả quét bảo mật cơ bản). |
| **AC-16** | **Thời gian phản hồi hệ thống:** Hệ thống đáp ứng nhanh, thời gian xử lý yêu cầu đặt xe và tìm kiếm tài xế (từ khi KH bấm Đặt xe đến khi Tài xế nhận được thông báo) không quá **3 giây**. | Đảm bảo trải nghiệm người dùng mượt mà. | Dùng công cụ test hiệu năng (JMeter) với 100 yêu cầu đồng thời, thời gian phản hồi trung bình (Average Response Time) dưới 3s. |
