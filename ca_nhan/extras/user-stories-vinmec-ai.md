# User Stories — AI Chăm Sóc Sức Khỏe (Vinmec)

Mỗi feature AI chính = 1 bảng. AI trả lời xong → chuyện gì xảy ra? Viết cả 4 trường hợp.

---

## Feature 1: Nhắc nhở uống thuốc (Spam Notification)

**Trigger:** Đến giờ uống thuốc theo đơn → AI gửi thông báo lên Web/App mỗi 5 phút → Chờ user nhấn "Đã uống".

| Path | Câu hỏi thiết kế | Mô tả |
|------|-------------------|-------|
| **Happy** — AI đúng, tự tin | User thấy gì? Flow kết thúc ra sao? | 08:00 hiện Pop-up: *"Đã đến giờ uống 1 viên Kháng sinh A"*. User nhấn **"Đã uống"** → Hệ thống dừng gửi tin, ghi chú vào lịch sử: *"Hoàn thành lúc 08:02"*. |
| **Low-confidence** — AI không chắc | System báo "không chắc" bằng cách nào? User quyết thế nào? | User nhấn **"Bỏ qua"** hoặc im lặng sau 3 lần nhắc. AI gửi tin nhắn: *"Bạn có gặp khó khăn gì (buồn nôn, quên mang thuốc...) không?"* kèm nút **"Trợ giúp"**. Ngoài ra, mỗi thông báo có nút **"Trì hoãn 15 phút"** (Snooze) để tránh gây ức chế khi user đang họp hoặc lái xe. |
| **Failure** — AI sai | User biết AI sai bằng cách nào? Recover ra sao? | Thông báo hiện *"Uống 2 viên"* trong khi vỏ thuốc ghi *"1 viên"*. User thấy mâu thuẫn → Nhấn nút **"Sai liều lượng"** ngay trên thông báo nhắc nhở. |
| **Correction** — user sửa | User sửa bằng cách nào? Data đó đi vào đâu? | User chụp ảnh đơn giấy để AI quét lại hoặc chọn **"Sửa lịch"**. Data gửi về bộ phận CSKH để kiểm tra đơn gốc trên hệ thống Vinmec. ⚠️ Mọi sửa đổi liều lượng phải được **bác sĩ hoặc dược sĩ duyệt** trước khi lịch nhắc mới có hiệu lực. |

---

## Feature 2: Hỏi thăm triệu chứng hằng ngày

**Trigger:** 20:00 hằng ngày, Chatbot chủ động nhắn: *"Hôm nay sức khỏe của bạn sau khi dùng thuốc thế nào?"*

| Path | Câu hỏi thiết kế | Mô tả |
|------|-------------------|-------|
| **Happy** — AI đúng, tự tin | User thấy gì? Flow kết thúc ra sao? | User chọn **"Bình thường"**. AI phản hồi: *"Rất tốt, hãy tiếp tục duy trì!"*. Flow kết thúc, dữ liệu được lưu vào báo cáo theo dõi sức khỏe tuần. |
| **Low-confidence** — AI không chắc | System báo "không chắc" bằng cách nào? User quyết thế nào? | User nhập: *"Cũng hơi mệt"*. AI không rõ mức độ nguy hiểm → Hiện **thang điểm 1–10** để user đánh giá mức độ mệt và liệt kê thêm các biểu hiện đi kèm để user xác nhận. |
| **Failure** — AI sai | User biết AI sai bằng cách nào? Recover ra sao? | User báo *"Đau bụng dữ dội"*, AI lại phản hồi *"Hãy nghỉ ngơi thêm"*. User thấy tình trạng tệ hơn → Nhấn nút **"Kết nối nhân viên y tế khẩn cấp" (SOS)**. Các triệu chứng AI bỏ lỡ được gắn tag để đào tạo lại NLP hằng tuần. |
| **Correction** — user sửa | User sửa bằng cách nào? Data đó đi vào đâu? | User đính chính: *"Không phải mệt bình thường mà là phát ban"*. AI cập nhật lại trạng thái thành **"Phản ứng phụ"** và log vào hồ sơ bệnh án điện tử của bệnh nhân. |

---

## Feature 3: Đề cử bệnh viện gần nhất (khi có triệu chứng đặc biệt)

**Trigger:** AI nhận diện từ khóa nguy hiểm (co giật, khó thở, sốt cao >40°C) từ câu trả lời của user.

| Path | Câu hỏi thiết kế | Mô tả |
|------|-------------------|-------|
| **Happy** — AI đúng, tự tin | User thấy gì? Flow kết thúc ra sao? | AI báo: *"Triệu chứng của bạn cần xử lý y tế ngay"*. Hiện **bản đồ 3 bệnh viện/phòng khám gần nhất** (ưu tiên Vinmec) kèm nút **"Gọi cấp cứu"**. |
| **Low-confidence** — AI không chắc | System báo "không chắc" bằng cách nào? User quyết thế nào? | Triệu chứng cần chuyên khoa sâu (ví dụ: đau mắt đột ngột). AI báo: *"Chúng tôi tìm thấy các phòng khám đa khoa, nhưng **khuyên bạn nên đến bệnh viện có khoa Mắt**"*. |
| **Failure** — AI sai | User biết AI sai bằng cách nào? Recover ra sao? | AI đề xuất phòng khám đã đóng cửa hoặc quá xa. User xem bản đồ thấy thời gian di chuyển >1 tiếng → Nhấn **"Tìm địa điểm khác"** hoặc **"Cập nhật vị trí"**. |
| **Correction** — user sửa | User sửa bằng cách nào? Data đó đi vào đâu? | User chọn **"Vị trí hiện tại không đúng"** và định vị lại trên bản đồ. Data GPS này được dùng để **tối ưu thuật toán gợi ý** cơ sở y tế theo bán kính thực tế. |

---

## Lưu ý chung cho dự án

- **Snooze notification:** Nút "Trì hoãn 15 phút" là bắt buộc để tránh gây ức chế khi user đang bận.
- **Duyệt liều lượng:** Mọi Correction về thuốc (Feature 1) phải qua bác sĩ/dược sĩ trước khi có hiệu lực — không tự động áp dụng.
- **Feedback Loop:** Các triệu chứng "đặc biệt" mà AI bỏ lỡ phải được gắn tag và đưa vào pipeline **retrain NLP hằng tuần**.
- **Path "Failure" là quan trọng nhất:** Nếu user không biết AI sai → nguy hiểm, đặc biệt trong bối cảnh y tế.
