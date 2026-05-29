# 🔍 Phase 1 — SCAN (Cá nhân, 20 min)

### 📝 List bài toán của tôi:
| # | Subsidiary (VinFast/Xanh SM...) | Lens | Mô tả ngắn bài toán |
|---|----------------------------------|------|---------------------|
| 1 |Vinmec |Tốn thời gian |Xây dựng AI system giúp bệnh nhân có thể tìm bác sĩ phù hợp và đặt trước lịch khám |
| 2 |Vinmec |Tốn thời gian, lặp lại |Xây dựng AI system giúp tổng hợp thông tin, triệu chứng của bệnh nhân và lịch sử bệnh cho bác sĩ đọc trước lúc khám cho bệnh nhân |
| 3 |Vinmec |Tốn thời gian |Xây dựng AI system giúp tổng hợp nhanh thông tin của bệnh nhân cấp cứu và phân tích nhanh ảnh hưởng của các bệnh nền liên quan đến hình thức phẫu thuật giúp các bác sĩ tiết kiệm thời gian, tăng cơ hội cứu sống bệnh nhân |
| 4 |Vinmec |Tốn thời gian, lặp lại |Xây dựng chatbot hỗ trợ truy vấn nhanh giúp y tá tra cứu, tìm kiếm hồ sơ của các bệnh nhân, hồ sơ thiết bị y tế|
| 5 |Vinhomes |Tốn thời gian |Xây dựng chatbot giúp khách hàng tìm kiếm thông tin về những thủ tục hoặc thông tin trong quá trình sinh sống ở Vinhomes, ví dụ muốn xin giấy phép sửa nhà ở đâu, như thế nào, ... |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #1                                     │
│                                                             │
│ Bài toán (1 câu): Xây dựng AI system giúp tổng hợp nhanh thông tin của bệnh nhân bệnh nhân và phân tích nhanh ảnh hưởng của các bệnh nền liên quan đến hình thức phẫu thuật giúp các bác sĩ tiết kiệm thời gian, tăng cơ hội cứu sống bệnh nhân
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [x] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Bác sĩ │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Bệnh viện tiếp nhận bệnh nhân ──> 2. Làm các xét nghiệm nhanh, tìm hồ sơ tiền sử bệnh ──> 3. Xác định các bệnh nền và triệu tập các bác sĩ liên quan ──> 4. Các bác sĩ họp để đưa ra phương án phẫu thuật hiệu quả                  │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? 4 (⏱ - phút/lượt)      │
│ AI có thể nhảy vào hỗ trợ ở bước nào?Bước 4 │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? Giảm thời gian tổng hợp thông tin => Giảm thời gian họp của các bác sĩ => Tăng cơ hội cứu sống bệnh nhân│
│   VD: "Giảm thời gian soạn phản hồi từ 10 min ──> under 2 min"│
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [x] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #2                                     │
│                                                             │
│ Bài toán (1 câu): Xây dựng AI system giúp bệnh nhân có thể tìm bác sĩ phù hợp và đặt trước lịch khám
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [x] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Bệnh nhân │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Bệnh nhân bị đau đến bệnh viện ──> 2. Tìm tới lễ tân để mô tả triệu chứng và được hướng dẫn đến khoa tương ứng ──> 3. Xếp hàng chờ đến lượt khám ──> 4. Khám bệnh│
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? 3 (⏱ - phút/lượt)      │
│ AI có thể nhảy vào hỗ trợ ở bước nào?Bước 2,3 │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? Giảm thời gian tìm lễ tân, mô tả triệu chứng và chờ xếp hàng│
│   VD: "Giảm thời gian soạn phản hồi từ 10 min ──> under 2 min"│
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #3                                     │
│                                                             │
│ Bài toán (1 câu): Xây dựng AI system giúp khách ở Vinhomes dễ dàng tra cứu các thông tin, thủ tục
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [x] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Cư dân │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Cư dân cần tra cứu 1 thủ tục, thông tin ──> 2. Tìm kiếm nơi có thể hỏi thông tin ──> 3. Tiếp nhận thông tin và thực hiện │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? 2 (⏱ - phút/lượt)      │
│ AI có thể nhảy vào hỗ trợ ở bước nào?Bước 2 │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? Giảm thời gian tìm kiếm thông tin│
│   VD: "Giảm thời gian soạn phản hồi từ 10 min ──> under 2 min"│
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [x] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘