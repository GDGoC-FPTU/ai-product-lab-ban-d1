# 🔍 Phase 1 — SCAN (Cá nhân, 20 min)

Hãy sử dụng **4 lenses** dưới đây để quét hoạt động vận hành của các công ty thành viên Vingroup. Ghi lại **ít nhất 5 bài toán / bottleneck** thực tế.

### 4 lenses để tìm bài toán AI cho Vingroup
1. **Lặp lại (Repetitive)** — Tác vụ lặp đi lặp lại hàng ngày (ví dụ: so khớp hóa đơn sạc điện tại VinFast, route lại chuyến taxi tại Xanh SM).
2. **Tốn thời gian (Time-consuming)** — Tác vụ thủ công ngốn nhiều thời gian của nhân viên (ví dụ: soạn phản hồi đánh giá 1-star của cư dân Vinhomes).
3. **AI có thể tốt hơn (AI-upgrade)** — Dịch vụ còn chậm hoặc phản hồi rập khuôn (ví dụ: chatbot CSKH Vinpearl hỗ trợ đặt vé).
4. **Pain từ stakeholder (Stakeholder Pain)** — Bottleneck gây phàn nàn từ khách hàng hoặc nhân viên (ví dụ: tài xế Xanh SM phàn nàn hệ thống gợi ý điểm đón không chính xác).

> **🤖 AI Prompts — Partner brainstorm**
>
> Sử dụng prompt này để brainstorm nếu cần ý tưởng:
>
> "Tôi là AI Engineer tại Vin Smart Future (Vingroup). Tôi đang tìm kiếm các pain point vận hành cụ thể có thể tối ưu bằng AI cho mảng [Chọn một: VinFast / Xanh SM / Vinhomes / Vinmec]. Hãy gợi ý cho tôi 5 quy trình nghiệp vụ thủ công, tốn nhiều thời gian và gây rò rỉ hiệu suất kèm con số thống kê ước tính về tổn thất."

### 📝 Danh sách bài toán (ví dụ)

| # | Subsidiary | Lens | Mô tả ngắn |
|---:|:-----------|:-----|:-----------|
| 1 | VinFast | Time-consuming | Phân tích lỗi bảo hành và khiếu nại khách hàng (Warranty Claim Analysis) |
| 2 | Xanh SM | Stakeholder Pain | AI Energy Optimization: chọn trạm sạc phù hợp, dự báo tắc nghẽn, tối ưu tuyến đường + sạc |
| 3 | Vinhomes | AI-upgrade | Tiếp nhận và xử lý yêu cầu cư dân (Resident Service Request): tạo yêu cầu, hỏi đáp, thủ tục, nhắc đóng phí |
| 4 | Vinmec | AI-upgrade | Customer Assistant: tư vấn sức khỏe, tự động đặt lịch khám, nhắc nhở lịch |
| 5 | Vinmec | AI-upgrade | Điều phối lịch khám và giảm tỷ lệ No-Show |


# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** (khoảng 10 phút / card). Dưới đây là hai ví dụ đã được làm mịn và chuẩn Markdown — copy, sửa hoặc bổ sung card thứ 3.

---

### QUICK PROBLEM CARD #1 — Resident Service Request

- **Bài toán (1 câu):** Resident Service Request
- **Công ty thành viên:** Vinhomes
- **Ai đang đau (Actor):** Cư dân
- **Workflow thủ công hiện tại (3–5 bước):**
    1. Cư dân gặp vấn đề hoặc cần dịch vụ.
    2. Cư dân không rõ quy trình, liên hệ ban quản lý.
    3. Ban quản lý tiếp nhận, nhân viên đọc từng yêu cầu, phân loại và điều phối thủ công.
    4. (nếu có) Thực hiện xử lý và thông báo kết quả.
- **Bước tốn thời gian / lỗi nhất:** Bước 3 (⏱ ~8 phút / lượt)
- **AI có thể hỗ trợ ở đâu:** Tự động phân loại yêu cầu, routing đến bộ phận đúng chuyên môn, trợ lý ảo hướng dẫn cư dân làm thủ tục.
- **Đo thành công (metric):** Giảm 60–80% effort điều phối; giảm thời gian xử lý trung bình; tăng tỉ lệ xử lý đúng chuyên môn ngay lần đầu.
- **Quick architecture (gợi ý):** Agent (NLU for classification) + Routing API + Dashboard cho ban quản lý.

---

### QUICK PROBLEM CARD #2 — Điều phối lịch khám và giảm No-Show

- **Bài toán (1 câu):** Điều phối lịch khám và giảm No-Show
- **Công ty thành viên:** Vinmec
- **Ai đang đau (Actor):** Bác sỹ / Bộ phận điều phối lịch
- **Workflow thủ công hiện tại (3–5 bước):**
    1. Bệnh nhân đặt lịch, một số hủy hoặc không đến sát giờ.
    2. Khó sắp xếp, dẫn đến quá tải cho bác sỹ giỏi và tình trạng phòng khám mất cân bằng.
    3. Bệnh nhân đến phải đợi lâu hoặc lịch bị trống.
    4. Điều phối thủ công để fill slot khi có hủy.
- **Bước tốn thời gian / lỗi nhất:** Bước 2 (tỷ lệ No-Show ~8%)
- **AI có thể hỗ trợ ở đâu:** Mô hình dự báo No-Show; tự động nhắc, đề xuất xác nhận, tự động fill slot từ danh sách chờ.
- **Đo thành công (metric):** Giảm 20–40% No-Show; giảm thời gian chờ; tăng sử dụng công suất phòng khám.
- **Quick architecture (gợi ý):** Predictive model + Reminder service (SMS/Push) + Waitlist management + Scheduling agent.

---

### QUICK PROBLEM CARD #3 — (Thêm card của bạn)

- **Bài toán (1 câu):** Customer Assistant
- **Công ty thành viên:** Vinmec
- **Ai đang đau (Actor):** Bệnh nhân
- **Workflow thủ công hiện tại (3–5 bước):**
    1. Bệnh nhân đến khám bệnh, tình trạng đang rất tệ.
    2. phải làm thủ tục lấy số, đợi thăm khám rất lâu.
    3. phải đợi bất kể bệnh nặng, nhẹ.
    4. chẳng may không mang đủ tiền, thiếu kinh phí.
- **Bước tốn thời gian / lỗi nhất:**  2. phải làm thủ tục lấy số, đợi thăm khám rất lâu.
- **AI có thể hỗ trợ ở đâu:** bước 2 và 3. Agent sẽ giúp bệnh nhân lấy số thăm khám, tự động ghi hồ sơ bệnh án.
- **Đo thành công (metric):** Giảm được ít nhất 30 phút chờ đợi và làm thủ tục, đồng thời rút ngắn thời gian xử lý ban đầu.
- **Quick architecture (gợi ý):**
    - **Giao diện cho bệnh nhân:** web/app/kiosk để check-in tự động và điền phiếu tiếp nhận (có thể gửi link SMS/Push).
    - **Agent tiếp nhận:** NLU hội thoại hướng dẫn bệnh nhân, tự động điền form, thu thập triệu chứng và quét/tải lên giấy tờ (OCR).
    - **Dịch vụ lịch hẹn & xếp hàng:** tích hợp với hệ thống đặt lịch để giữ số, quản lý hàng đợi, ưu tiên sơ tuyển.
    - **Kết nối hồ sơ bệnh án:** lưu chuyến khám, tạo ghi chú ban đầu, liên kết với hồ sơ bệnh nhân (nếu có FHIR/HL7).
    - **Kiểm tra thanh toán / bảo hiểm:** dịch vụ nhỏ tùy chọn để xác minh đóng góp chi phí và kiểm tra trước hóa đơn.
    - **Thông báo & nhắc nhở:** SMS/push/email xác nhận, cập nhật trạng thái hàng đợi và nhắc lịch.
    - **Bảng điều khiển nhân viên:** hiển thị hàng đợi theo thời gian thực, cho phép điều phối và xem nhanh thông tin bệnh nhân.
    - **Hệ thống ML chính:** phân loại intent NLU, OCR xử lý tài liệu, mô hình đánh giá ưu tiên/nhóm nguy cơ (no-show / độ nặng).

---
