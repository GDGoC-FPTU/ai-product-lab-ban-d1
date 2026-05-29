# 🔍 Phase 1 — SCAN: Tìm kiếm cơ hội

Áp dụng **4 Lenses** để quét qua các vấn đề hiện tại của các công ty thành viên Vingroup.

| # | Subsidiary | Lens | Mô tả ngắn bài toán |
|---|------------|------|---------------------|
| 1 | **Xanh SM** | Pain từ người khác | Trên ứng dụng Xanh SM, khách hàng lựa chọn sử dụng vị trí hiện tại (current location) để đặt xe nhưng hệ thống định vị sai khiến tài xế không tìm được điểm đón chính xác, dẫn đến cả hai vấn đề: tốn thời gian cho cả khách hàng và tài xế (1) và tăng tỷ lệ khách hàng hủy chuyến khi chờ đợi quá lâu (2). Lưu ý: khách hàng đã cấp quyền cho Xanh SM truy cập cập vị trí |
| 2 | **VinMec** | Tốn thời gian | Điều phối viên tiếp nhận khối lượng lớn bệnh nhân, đăng ký thông tin người bệnh, nghe dấu hiệu bệnh và chỉ định khoa khám. Việc này vừa gây sự quá tải cho bệnh viện (1) vừa gây tốn thời gian xếp hàng chờ đợi cho bệnh nhân. Nguyên nhân có thể do: không bố trí các máy tiếp đón người bệnh để cho phép họ tự scan CCCD & khai báo dấu hiệu bệnh. Nếu các máy móc này được bố trí, chúng có thể giúp tự động hóa việc nhập liệu và chỉ định phòng khám |
| 3 | **Vinpearl** | Lặp lại | Khi nhận phòng, thủ tục checkin-checkout vẫn còn thực hiện thủ công (nhập liệu, đối chiếu giấy tờ, gán phòng thủ công, etc). Việc này dẫn đến sự tốn thời gian và kém hiệu quả. Nên có phương án bố máy các thiết bị giúp tự động hóa giấy tờ/thủ tục nhanh chóng giúp trải nghiệm khách hàng tốt hơn. |
| 4 | **Vinpearl** | Lặp lại | Xử lý yêu cầu khách hàng còn thủ công và rời rạc (call center, chat, Zalo, nhân viên ghi nhận trực tiếp, etc) và chưa có kênh tổng hợp thống nhất. Không có kênh xử lý tổng hợp dẫn đến việc có thể bỏ sót yêu cầu khách hàng, khiến khách hàng ngừng xử dụng dịch vụ, gây tổn thất doanh thu. |
| 5 | **VinFast** | AI-upgrade | Giám sát thủ công tại xưởng lắp ráp bởi con người, dễ dẫn đến việc thất bại trong phát hiện lỗi. Và một khi sản phẩm lỗi bị tung ra thị trường, có thể gây thiệt hại lớn về chi phí đền bù và uy tín |
| 6 | **VinFast** | AI-upgrade | Quản lý chuỗi cung ứng linh kiện & thiếu hụt phụ tùng. Các vấn đề hiện tại như: Không dự đoán failure rate theo từng model/region (1) hay Dự đoán phụ tùng dựa trên Excel + lịch sử đơn giản |
---


# 🃏 Phase 2 — QUICK-ASSESS: 3 Quick Problem Cards (Cá nhân)

## Thẻ bài toán tiêu biểu: Card #2 — Xanh SM Xử lý sự cố sạc pin thực địa

```
┌─────────────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #1                                               │
│                                                                     │
│ Bài toán: Khách hàng Xanh SM chọn “current location” nhưng hệ thống │
│ định vị sai → tài xế không tìm được điểm đón chính xác.            │
│ Công ty thành viên: Xanh SM                                         │
│                                                                     │
│ Ai đang đau?                                                        │
│ - Khách hàng (chờ lâu, dễ hủy chuyến)                               │
│ - Tài xế (tốn thời gian tìm kiếm)                                   │
│                                                                     │
│ Workflow thủ công hiện tại:                                         │
│   1. Khách đặt xe và chọn vị trí hiện tại                          │
│   → 2. App gửi tọa độ GPS không chính xác / lệch thực tế            │
│   → 3. Tài xế di chuyển đến điểm pin → không thấy khách             │
│   → 4. Gọi điện qua lại để xác nhận vị trí                          │
│   → 5. Khách tự chỉnh pin / gửi mô tả thủ công                      │
│                                                                     │
│ Bước nào tốn nhất? Bước 4–5 (⏱ 5–10 phút/lượt)                      │
│ AI có thể nhảy vào ở đâu? Bước 2–4                                   │
│ (Auto-correction GPS + prompt hỏi ngữ cảnh + landmark matching)     │
│                                                                     │
│ Metric thành công:                                                   │
│ Giảm tỷ lệ “driver cannot find passenger” từ X% → <50%              │
│ Giảm thời gian xác nhận điểm đón từ 6 phút → <1 phút                │
│                                                                     │
│ Quick Architecture: [x] AI Geo-Validation + LLM hỗ trợ điều phối    │
└─────────────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #2                                               │
│                                                                     │
│ Bài toán: Điều phối viên Vinmec bị quá tải khi tiếp nhận bệnh nhân  │
│ → nhập liệu + hỏi triệu chứng + chỉ định khoa khám thủ công.        │
│ Công ty thành viên: Vinmec                                          │
│                                                                     │
│ Ai đang đau?                                                        │
│ - Bệnh nhân (xếp hàng lâu, trải nghiệm kém)                         │
│ - Điều phối viên (quá tải, dễ sai sót)                              │
│                                                                     │
│ Workflow thủ công hiện tại:                                         │
│   1. Bệnh nhân xếp hàng tại quầy                                    │
│   → 2. Điều phối viên hỏi triệu chứng trực tiếp                     │
│   → 3. Nhập thông tin vào hệ thống                                  │
│   → 4. Dựa kinh nghiệm để chỉ định khoa                              │
│   → 5. In phiếu & hướng dẫn đi khám                                 │
│                                                                     │
│ Bước nào tốn nhất? Bước 2–3 (⏱ 5–8 phút/bệnh nhân)                  │
│ AI có thể nhảy vào ở đâu? Bước 1–4                                   │
│ (Self check-in + symptom triage + auto routing khoa khám)          │
│                                                                     │
│ Metric thành công:                                                   │
│ Giảm thời gian check-in từ 10 phút → <2 phút                        │
│ Giảm tải điều phối viên ≥40%                                         │
│                                                                     │
│ Quick Architecture: [x] AI Kiosk + Triage LLM + OCR CCCD           │
└─────────────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #3                                               │
│                                                                     │
│ Bài toán: Quy trình check-in / check-out Vinpearl còn thủ công      │
│ → nhập liệu, đối chiếu giấy tờ, gán phòng thủ công.                │
│ Công ty thành viên: Vinpearl                                        │
│                                                                     │
│ Ai đang đau?                                                        │
│ - Khách hàng (chờ lâu khi nhận phòng)                               │
│ - Lễ tân (xử lý thủ tục lặp lại, dễ sai sót)                        │
│                                                                     │
│ Workflow thủ công hiện tại:                                         │
│   1. Khách đến quầy lễ tân                                         │
│   → 2. Xuất trình CCCD / booking                                    │
│   → 3. Nhân viên nhập thông tin thủ công                            │
│   → 4. Kiểm tra booking & tình trạng phòng                          │
│   → 5. Gán phòng + in thẻ phòng                                     │
│                                                                     │
│ Bước nào tốn nhất? Bước 2–4 (⏱ 7–12 phút/khách)                    │
│ AI có thể nhảy vào ở đâu? Bước 1–5                                   │
│ (Self check-in kiosk + OCR + auto room assignment)                 │
│                                                                     │
│ Metric thành công:                                                   │
│ Giảm thời gian check-in từ 10 phút → <2 phút                        │
│ Giảm queue tại quầy lễ tân ≥60%                                     │
│                                                                     │
│ Quick Architecture: [x] AI Kiosk + OCR + Rule-based Room Engine    │
└─────────────────────────────────────────────────────────────────────┘
```
---