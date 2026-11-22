# Danh sách lớp v0 — G03

## DMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng DMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | `face` | Có / không thấy rõ | Xác định vị trí mặt tài xế để phân tích trạng thái | Thường có; bị che hoặc ngoài khung thì không |
| 2 | `eye_left`, `eye_right` | open / closed / unknown | Phát hiện mắt nhắm kéo dài, hỗ trợ cảnh báo buồn ngủ | Có thể; phản xạ kính làm khó thấy |
| 3 | `gaze_zone` | road / mirror / cluster / center / lap / other | Phát hiện tài xế nhìn lệch khỏi đường | Hướng nhìn thường thấy; vùng đích có thể khó phân biệt |
| 4 | `glasses` | none / clear / sun / unknown | Giúp diễn giải độ tin cậy của quan sát mắt | Thường thấy hình kính; loại kính có thể không rõ trên NIR |
| 5 | `hand.on_wheel` | yes / no / unknown | Phát hiện tay rời vô lăng hoặc tư thế lái bất thường | Tay thường thấy; vùng tối hoặc che khuất gây khó |
| 6 | `phone.state` | held / mounted / lap | Phát hiện dùng điện thoại gây mất tập trung | Hình dạng thường thấy; màu sắc không đáng tin trên IR |

## OMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng OMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | `person.seat` | driver / front_passenger / rear_left / rear_middle / rear_right | Xác định người đang ngồi ở ghế nào | Thường thấy dáng người và vị trí ghế |
| 2 | `person.seatbelt` | worn_correct / worn_incorrect / not_worn / unknown | Phát hiện dây an toàn chưa cài hoặc cài sai | Dải dây có thể thấy; bóng tối hoặc che khuất làm giảm độ chắc chắn |
| 3 | `child_seat.occupied` | yes / no / unknown | Xác định ghế trẻ em có người hay trống để hỗ trợ cảnh báo an toàn | Hình dạng ghế thấy được; tình trạng bên trong có thể bị che |
| 4 | `infant_seat.facing` | rear / front | Kiểm tra hướng quay của ghế em bé | Thường nhận ra theo hình dáng và hướng ghế |
| 5 | `object.type` | bag / box / cup / other | Nhận diện đồ vật rời trong cabin để hỗ trợ quản lý và cảnh báo vật cản | Hình dạng thường thấy; không dựa vào màu trên IR |
| 6 | `frame_meta.camera_blocked` | yes / no | Nhận biết camera bị che để tránh tin cậy kết quả nhận diện | Có thể thấy vật che; cần đánh giá theo khung hình |

## 2 câu hỏi leo thang

1. Câu hỏi: Nếu ảnh SVIRO có hình giống em bé nằm trong ghế, có được gán nhãn ghế không dù guideline nói SVIRO không có trẻ em?
   Khung ví dụ: `G03 S05_ir.png`
   Bạn tạm gán thế nào và vì sao: gán tạm `infant_seat` để có thể sau này cập nhật thêm occupied.
2. Câu hỏi: Khi tài xế nhìn vào vật cầm gần mặt, lúc nào chọn `center` và lúc nào chọn `other`?
   Khung ví dụ: `G03 D03.png`
   Bạn tạm gán thế nào và vì sao: Chọn `other` nếu hướng nhìn không khớp chắc chắn với một vùng được định nghĩa; không suy ra `center` chỉ vì vật ở gần giữa ảnh.
