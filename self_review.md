# Tự đánh giá — Nguyễn Việt Quân · G03

## 1. Tự rà soát 4 cảnh

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| S02_ir.png | child_seat | guess | Details để `unknown` dù ghế trống nhìn rõ; peer chọn `no`. | Đã sửa |
| S08_rgb.png | frame_meta | guess | Modality cần khớp tên file `_rgb`. | Đã sửa |
| D04.png | hand | guess | Details để `on_wheel=unknown` dù tay đang cầm vật, không chạm vô lăng. | Đã sửa |
| D06.png | face | guess | `eye_right=open` trong khi vùng mắt bị che; nên dùng `unknown`. | Đã sửa |

## 2. Lỗi mình lặp lại nhiều nhất hôm nay

Lỗi: Chưa kiểm tra kỹ thuộc tính trong **Details** sau khi vẽ.

Vì sao mình mắc: Tập trung vào box nên dễ bỏ qua thuộc tính hoặc giá trị mặc định.

Lần sau tránh bằng cách: Sau mỗi box/tag, mở Details và rà lại từng thuộc tính trước khi lưu.

## 3. Ghi chú về disagreement_log

Peer nhắc mình kiểm tra lại Details. Mình sẽ rà các thuộc tính ở đó trước khi chốt nhãn.
