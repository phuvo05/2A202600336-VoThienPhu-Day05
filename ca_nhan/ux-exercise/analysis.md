# V-AI Product Experience Analysis & Improvement Proposal

**Author:** Võ Thiên Phú
**Student ID:** 24202600336
**Scope:** V-app / V-AI Ecosystem Experience Review

---

# 1) Executive Summary

Tài liệu này tổng hợp trải nghiệm thực tế khi khám phá **V-AI trong hệ sinh thái V-app**, phân tích các tình huống AI hoạt động tốt, chưa chắc chắn, hoặc cần escalation sang human support. Đồng thời, tài liệu đề xuất một **to-be flow theo hướng AI Agent có khả năng hành động (action-taking)** thay vì chỉ trả lời hội thoại.

Mục tiêu chính:

* Đánh giá trải nghiệm hiện tại của chatbot
* Xác định pain points trong user journey
* Đề xuất flow AI Agent nâng cao
* Mở rộng khả năng automation đa ứng dụng trong hệ sinh thái Vingroup

---

# 2) First Impression & Product Promise

## 2.1 Marketing Promise

Những kỳ vọng ban đầu mà sản phẩm truyền tải:

* Trợ lý thông minh có khả năng **thấu hiểu ngữ cảnh người Việt**
* Tốc độ phản hồi nhanh, hội thoại tự nhiên
* Có khả năng **cá nhân hóa trải nghiệm và lộ trình di chuyển**
* Kết nối nhiều dịch vụ trong cùng hệ sinh thái

## 2.2 First Impression

Trải nghiệm ban đầu tương đối tích cực:

* Giao diện hiện đại, dễ tiếp cận
* Icon và entry points rõ ràng
* Tốc độ phản hồi nhanh
* Có tích hợp **tool search** khi truy vấn dữ liệu có sẵn trong hệ thống

---

# 3) Current Experience Analysis (4 Paths)

## 3.1 Path 1 — When AI Performs Well

Các trường hợp AI cho trải nghiệm tốt:

* Hiểu ý định người dùng nhanh
* Bắt đúng context ngay từ câu hỏi đầu tiên
* Có khả năng bao phủ scope rộng như xe, thương hiệu và dịch vụ trong hệ sinh thái
* Đưa ra quick suggestions giúp người dùng ra quyết định nhanh
* Chat flow mượt, ít phải hỏi lại

### Key Strengths

* Strong contextual understanding
* Fast response time
* Good intent mapping
* Smooth multi-turn conversation

---

## 3.2 Path 2 — When AI Is Uncertain

Một số tình huống AI chưa chắc chắn:

* Phản hồi còn chung chung
* Thiếu chiều sâu ở các câu hỏi đặc thù
* Dẫn link hoặc search result dài làm tăng cognitive load
* Chưa tối ưu phần summarize kết quả từ tool

### Pain Point

Người dùng phải đọc nhiều thông tin trung gian trước khi đạt mục tiêu cuối.

---

## 3.3 Path 3 — When AI Is Wrong

Một số điểm còn hạn chế:

* Chưa gặp nhiều case sai nghiêm trọng, nhưng có thể xảy ra ở câu hỏi mơ hồ
* Thiếu khả năng **edit lại message sau khi gửi**
* Chưa hỗ trợ recovery flow tốt khi user muốn sửa ý định

### UX Risk

Nếu AI hiểu sai intent ở early step, người dùng phải restart conversation.

---

## 3.4 Path 4 — When User Needs Human Support

Điểm tốt hiện tại:

* Có hướng chuyển sang người thật
* Có thể điều hướng sang hotline / website / kênh hệ sinh thái khác
* Có fallback flow tương đối rõ

### Opportunity

Escalation nên được contextualized tốt hơn để tránh người dùng phải lặp lại thông tin.

---

# 4) Current Pain Points

## UX Pain Points

* Chưa hỗ trợ đa ngôn ngữ mạnh
* Chưa có voice-native interaction
* Khả năng xử lý hình ảnh/video còn hạn chế
* Automation còn yếu, chủ yếu dừng ở trả lời thông tin
* Chưa đủ mạnh ở task completion end-to-end

## Product Pain Points

* Chưa khai thác sâu sức mạnh ecosystem orchestration
* Chưa tận dụng AI Agent để thao tác liên app
* Thiếu proactive clarification flow

---

# 5) To-Be Experience Vision (AI Agent)

## Vision

Chuyển từ **chatbot hỏi-đáp** sang **AI Agent có khả năng thực thi hành động xuyên ứng dụng**.

### Example User Request

> “Đặt cho tôi 1 ly cà phê sữa nóng vào buổi sáng.”

## Proposed Flow

### Step 1 — User Input

Người dùng nhập text, voice hoặc wake-word.

### Step 2 — Intent Clarification

AI chủ động hỏi thêm:

> “Bạn muốn đặt ở chi nhánh gần vị trí hiện tại hay địa chỉ đã lưu?”

### Step 3 — Tool Execution

AI Agent tự động:

* Mở app Food trong hệ sinh thái
* Chọn cửa hàng gần nhất
* Tìm đúng món theo lịch sử cá nhân
* Tự động điền địa chỉ giao hàng
* Chọn phương thức thanh toán mặc định

### Step 4 — Confirmation

AI chỉ yêu cầu xác nhận cuối:

> “Đơn cà phê sữa nóng sẽ được giao trong 15 phút. Xác nhận thanh toán?”

### Step 5 — Completion

Sau khi xác nhận:

* Thanh toán
* Theo dõi đơn
* Gửi ETA
* Gợi ý reorder cho hôm sau

---

# 6) Strategic Improvement Recommendations

## 6.1 Multimodal Expansion

Nên bổ sung:

* Voice interaction
* Image understanding
* Video-based support
* OCR từ ảnh hóa đơn / địa điểm
* Browser tool mở web trong hệ sinh thái

## 6.2 Cross-App Agent Automation

AI nên orchestration được:

* Food
* VinFast services
* VinHomes tiện ích
* Booking / travel
* Customer support

## 6.3 Personalization Layer

* Dựa trên lịch sử đặt hàng
* Theo vị trí thường xuyên
* Theo thời gian trong ngày
* Theo thói quen di chuyển

---

# 7) Final Product Direction

Hướng phát triển phù hợp nhất là:

> **Ecosystem AI Agent Platform**

Trong đó V-AI đóng vai trò:

* Universal interface cho toàn hệ sinh thái
* Personal assistant đa phương thức
* Action engine có tool calling
* Cross-app workflow automation layer

Điểm khác biệt cạnh tranh nằm ở:

* dữ liệu hệ sinh thái mạnh
* khả năng cá nhân hóa sâu
* AI không chỉ trả lời mà còn **thực hiện công việc thay người dùng**

---

# 8) Conclusion

Sản phẩm hiện tại đã có nền tảng tốt về:

* UI
* tốc độ phản hồi
* contextual QA
* ecosystem integration

Bước nâng cấp chiến lược tiếp theo nên tập trung vào:

> **AI Agent + Multimodal + Cross-App Automation**

để chuyển trải nghiệm từ **chat support → intell
