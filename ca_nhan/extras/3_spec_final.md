## 3. Eval metrics + threshold

**Optimize precision hay recall?** ☑ Precision · ☐ Recall

**Tại sao?** Nếu bệnh nhân nảy sinh tâm lý ỷ lại và tin tưởng AI 100% mà không đối chiếu đơn thuốc gốc, việc AI nhắc sai tên thuốc hoặc sai liều lượng (False Positive) sẽ dẫn đến tình trạng ngộ độc thuốc, đe dọa trực tiếp tính mạng. Trong y khoa, "Thà không nhắc, còn hơn hướng dẫn sai".

**Nếu sai ngược lại thì chuyện gì xảy ra?** Nếu ưu tiên Recall (cố gắng không bỏ sót bất kỳ liều nào), AI có thể "ảo giác" (hallucinate) và tự bịa ra các cữ thuốc không tồn tại hoặc trích xuất nhầm đơn của người khác. Hệ quả là bệnh nhân có nguy cơ uống quá liều. Dù quên liều (False Negative) cũng làm giảm hiệu quả điều trị, nhưng hướng xử lý khi quên liều thường an toàn hơn (bỏ qua liều đã quên nếu sát giờ uống tiếp theo).

| Metric | Threshold | Red flag (dừng khi) |
|--------|-----------|---------------------|
| **Độ chính xác thông tin lâm sàng (Clinical Precision):** Tỷ lệ thông báo nhắc thuốc chứa thông tin chính xác tuyệt đối 100% (đúng tên thuốc, đúng hàm lượng, đúng số viên/ml) so với đơn thuốc gốc. | ≥ 99.9% | < 98% (Hoặc dừng toàn bộ hệ thống ngay lập tức nếu phát hiện dù chỉ 1 ca AI nhắc sai liều lượng hoặc sai tên thuốc gây nguy hiểm lâm sàng). |
| **Tỷ lệ "Từ chối tự động" (Low-confidence reject rate):** Khi AI trích xuất chữ viết tay mờ hoặc đơn thuốc có cấu trúc phức tạp mà độ tự tin thấp, AI phải tự động "báo lỗi" và yêu cầu Điều dưỡng/Dược sĩ kiểm tra tay, thay vì cố gắng đoán bừa. | ≥ 95% | Tỷ lệ AI đoán sai nhưng lại báo độ tự tin cao (High-confidence failures) xuất hiện > 0.5%. |
| **Tỷ lệ xác nhận đối chiếu chéo (Cross-check Adherence):** Số lượt bệnh nhân xác nhận "Đã kiểm tra lại với đơn thuốc vật lý" trước khi bấm "Đã uống" trên ứng dụng. | ≥ 80% | < 60% (Cảnh báo người dùng đang bắt đầu auto nhấn "đã kiểm tra" và tin tưởng AI một cách mù quáng. Cần thay đổi UI/UX để ép người dùng phải nhìn lại đơn). |
