# Lab 02 — Worksheet: AI Product Scoping (Vin Smart Future)

---

## 🏛️ 1. Bối cảnh thực tế: Vin Smart Future (Vingroup)

**Vingroup** — Tập đoàn tư nhân lớn nhất Việt Nam — vừa sáp nhập toàn bộ các phòng ban công nghệ thuộc các công ty thành viên thành một đơn vị công nghệ thống nhất mang tên **Vin Smart Future**. 

Nhiệm vụ của **Vin Smart Future** là xây dựng các giải pháp AI, số hóa, và tự động hóa cốt lõi để nâng cao hiệu suất vận hành và trải nghiệm khách hàng xuyên suốt các công ty thành viên:
* 🚗 **VinFast:** Hệ thống xe điện thông minh (EV), trợ lý AI ảo trong xe, dự đoán bảo trì pin, và quản lý chuỗi cung ứng sản xuất.
* 🚕 **Xanh SM (GSM):** Vận hành đội xe taxi/xe máy điện thông minh, điều vận thông minh (Smart Dispatching), tối ưu hóa lộ trình di chuyển.
* 🏢 **Vinhomes:** Quản lý đô thị thông minh (Smart Cities), trợ lý cư dân thông minh, tối ưu hóa mức tiêu thụ năng lượng.
* 🏥 **Vinmec:** Y tế thông minh, chẩn đoán hình ảnh bằng AI, tối ưu hóa quản lý hồ sơ bệnh án.
* 🎢 **Vinpearl / VinWonders:** Trải nghiệm du lịch số hóa, quản lý phòng và luồng khách thông minh tại các khu vui chơi.

Trong buổi Lab hôm nay, nhóm của bạn sẽ đóng vai trò là **AI Product Engineer** tại **Vin Smart Future**, tiến hành tìm kiếm, scoping, phân tích độ khả thi, thiết lập ranh giới vận hành, và xây dựng một **bản mẫu kỹ thuật (prompt prototype)** cho một bài toán cụ thể thuộc một trong những mảng kinh doanh trên.

---

## 📊 2. Cơ cấu tính điểm bài lab

### 👥 Điểm nhóm (60 điểm)

| Gate | Điểm | Deliverable | Tiêu chí chấm |
|---|---:|---|---|
| **G1. Workflow Mapping** | 20 | Problem Deep-Dive | Vẽ chi tiết quy trình hiện tại: các bước, handoff, thời gian, bottleneck |
| **G2. Problem Statement** | 20 | Problem Deep-Dive | Problem Statement 6-field bám sát thực tế, metric có số và ranh giới rõ ràng |
| **G3. AI Fit & Future Flow** | 10 | Problem Deep-Dive | So sánh Rule vs LLM vs Agent, future flow có bước AI, ranh giới và Fallback |
| **G4. Decision Quality** | 10 | Problem Deep-Dive | Quyết định Go/Not Yet/No-Go trung thực và có chứng cứ rõ ràng |

### 👤 Điểm cá nhân (40 điểm)

| Gate | Điểm | Deliverable | Tiêu chí chấm |
|---|---:|---|---|
| **I1. Scan & Cards** | 15 | Quick Cards | Liệt kê 5 problems sử dụng 3 lenses, hoàn thiện 3 quick cards chất lượng |
| **I2. Prototyping** | 10 | 02-lab/ | Chạy thử nghiệm programmatic prompt prototype thành công |
| **I3. AI Log & Reflection** | 15 | 03-ai-log.md | Phản ánh trung thực về việc dùng AI làm thought-partner (giúp gì, sai gì, sửa gì) |

---

# 🚀 Phase 0 — worked Example: Xanh SM Intelligent Dispatcher (15 min)

*Giảng viên walk-through ví dụ thực tế từ Vin Smart Future để bạn hiểu rõ cách scoping một bài toán AI.*
Đọc chi tiết worked example tại file [02-deliverable-example.md](02-deliverable-example.md).
yes, đã đọc ạ
---

# 🔍 Phase 1 — SCAN (Cá nhân, 20 min)

Hãy sử dụng **4 Lenses** dưới đây để quét qua hoạt động vận hành của các công ty thành viên Vingroup. Ghi lại **ít nhất 5 bài toán/bottleneck** thực tế.

### 4 Lenses tìm bài toán AI cho Vingroup:
1. **Lặp lại (Repetitive):** Tác vụ lặp đi lặp lại nhiều lần hằng ngày. (Ví dụ: So khớp hóa đơn sạc điện tại VinFast, route lại chuyến taxi tại Xanh SM).
2. **Tốn thời gian (Time-consuming):** Tác vụ ngốn thời gian xử lý thủ công của nhân viên. (Ví dụ: Soạn thảo phản hồi đánh giá 1-star của cư dân Vinhomes).
3. **AI có thể tốt hơn (AI-upgrade):** Dịch vụ khách hàng hiện tại còn chậm hoặc phản hồi rập khuôn. (Ví dụ: Chatbot CSKH Vinpearl hỗ trợ đặt vé vui chơi).
4. **Pain từ người khác (Stakeholder Pain):** Bottleneck khiến khách hàng hoặc nhân viên thực địa phàn nàn. (Ví dụ: Tài xế Xanh SM phàn nàn về việc hệ thống gợi ý điểm đón khách không chính xác).

> [!TIP]
> **🤖 AI Prompts — Partner brainstorm:**
> Hãy sử dụng prompt sau để brainstorm các bài toán thực tế nếu bạn chưa có ý tưởng:
> *"Tôi là AI Engineer tại Vin Smart Future (Vingroup). Tôi đang tìm kiếm các pain point vận hành cụ thể có thể tối ưu bằng AI cho mảng [Chọn một: VinFast / Xanh SM / Vinhomes / Vinmec]. Hãy gợi ý cho tôi 5 quy trình nghiệp vụ thủ công, tốn nhiều thời gian và gây rò rỉ hiệu suất kèm con số thống kê ước tính về tổn thất."*

### 📝 List bài toán của tôi:
| # | Subsidiary (VinFast/Xanh SM...) | Lens | Mô tả ngắn bài toán |
|---|----------------------------------|------|---------------------|
| 1 | Vinmec | Lặp lại & Tốn thời gian | tiếp nhận/mở hồ sơ nhập viện khám sức khoẻ, nhân viên làm hồ sơ nhập viện đều yêu cầu các giấy tờ tương đối giống nhau từ tất cả bệnh nhân mà có nhiều bệnh nhân không chuẩn bị đủ giấy tờ dù họ có tìm hiểu trên website hay V-app|
| 2 | Vinhomes | AI Upgrade | nhu cầu cho thuê/nhượng lại nhà/chung cư của chủ hộ và người thuê cao nhưng khó match được với nhau, khi qua nhân viên tư vấn hay dùng V-app thì chưa kết nối match được hai bên đối tượng này và phải qua nhiều bên trung gian |
| 3 | Vinmec | AI Upgrade | Cần tối ưu quản lý hồ sơ bệnh nhân check-out có muốn follow-up lần sau và khi nào dựa trên hồ sơ nhập viện và kết quả vừa khám trước check-out |
| 4 | Vinpearl/Vinwonders | Stakeholder pain | Chênh lệch khách đặt vé vui chơi tham quan vào ngày lễ lớn còn ngày thường lại vắng gây trống doanh thu, cần tạo gợi ý kèm promotion phù hợp để khách nắm bắt phòng đặt trong khu để tối ưu hơn|
| 5 | Xanh SM | Lặp lại & Tốn thời gian | Tài xế cần xác thực khách bằng cách gọi xác nhận nhưng nếu ở trong khu vực wifi mạnh còn sim đt kém thì khó liên lạc, có thể tích hợp cuộc gọi + nhắn tin ngay trên app để tiện lợi hơn|
| 6 | Vinhomes | AI Upgrade | Hệ thống chăm sóc khách hàng bị quá tải và chưa tối ưu, mức phàn nàn quá cao và chưa được xử lý hiệu quả |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #1                                      │
│                                                             │
│ Bài toán (1 câu): Thời gian làm nhập viện và xuất viện quá lâu │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [x] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Cả bệnh nhân và nhân viên hành chính BV │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Bệnh nhân chủ động nộp hồ sơ cần thiết trên hệ thống với support của chatbot |
|    ──> 2. Bệnh nhân đặt lịch hẹn với BV theo gợi ý của chatbot |
|    ──> 3. Agent xử lý các file bệnh nhân nộp để nhân viên hành chính chuẩn bị form |
|    ──> 4. Bệnh nhân tới và nhập viện theo giờ đã hẹn kèm xác nhận mã code       │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2+3 (⏱ 15 phút/lượt)      │
│ AI có thể nhảy vào hỗ trợ ở bước nào? bước 2+3 │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? Giảm thời gian xử lý hồ sơ bước 3 từ 15 phút xuống <3 phút/lượt, tiết kiệm 40% thời gian của nhân viên hành chính │
│   VD: "Giảm thời gian soạn phản hồi từ 10 min ──> under 2 min"│
│                                                             │
│ Quick Architecture: [ ] No AI  [x] Rule  [ ] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #2.                                      │
│                                                             │
│ Bài toán (1 câu): Tìm perfect match cho người thuê và chủ thuê │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [x] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Chủ nhà (mất thời gian lọc khách lẻ,   │
│ môi giới) và Người thuê (bị ngợp thông tin ảo, mất thời gian│
│ đi xem nhà không ưng ý)                                     │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Chủ nhà đăng tin và người thuê tự tìm kiếm thủ công trên các hội nhóm cư dân/chợ mạng phi chính thức.|
|    ──> 2. Hai bên nhắn tin, gọi điện để lọc các điều kiện cơ bản (Giá, nội thất, thời hạn hợp đồng, thú cưng...). |
|    ──> 3. Đặt lịch hẹn và đi xem nhà thực tế (mất nhiều buổi). |
|    ──> 4. Thỏa thuận giá và ký hợp đồng thuê qua BQL/Môi giới. │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2 + 3 (⏱ 7-14 ngày/lượt)     │
│ AI có thể nhảy vào hỗ trợ ở bước nào? không dùng AI │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?  │
│ 1. Giảm thời gian từ lúc đăng tin đến khi chốt cọc:          │
│    Từ 14 ngày ──> dưới 3 ngày.                               │
│ 2. Tăng tỷ lệ khớp nhu cầu ngay lần đầu xem nhà (Match rate):│
│    Từ 20% ──> trên 75% nhờ bộ lọc cứng chính xác.            │
│                                                             │
│ Quick Architecture: [ ] No AI  [x] Rule  [ ] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #6 (Nâng cấp hệ thống Agent)             │
│                                                             │
│ Bài toán (1 câu): Quá tải vận hành do các phản ánh phức tạp │
│ của cư dân đòi hỏi phối hợp liên phòng ban xử lý quá lâu.   │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [x] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Cư dân (bị đẩy qua đẩy lại giữa các   │
│ bộ phận) và Điều phối viên BQL (mất thời gian làm trung gian)│
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Cư dân gửi phản ánh phức tạp (ví dụ: thấm dột, va chạm │
│      xe trong hầm đỗ gây tranh chấp, tiếng ồn liên căn hộ). │
│   ──> 2. Điều phối viên tiếp nhận, đọc hiểu tình huống.      │
│   ──> 3. Điều phối viên tự tay phân rã thành các ticket nhỏ  │
│          chuyển cho Kỹ thuật, An ninh, Pháp chế, Bảo hiểm... │
│   ──> 4. Theo dõi tiến độ từng bên, tổng hợp kết quả để phản │
│          hồi lộ trình đền bù/sửa chữa cuối cùng cho cư dân.  │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 3 + 4 (⏱ 1-3 ngày/case) │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2, 3 và 4        │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                       │
│ 1. Giảm thời gian xử lý và điều phối liên phòng ban (SLA):   │
│    Từ 48 giờ ──> dưới 2 giờ (Agent tự phân rã và kích hoạt). │
│ 2. Giảm khối lượng công việc trung gian của Điều phối viên:  │
│    Giảm 70% số lượng cuộc gọi/email nội bộ nhắc việc.        │
│ 3. Trần chi phí vận hành AI (CFO Cap):                       │
│    Khống chế chi phí Token dưới 2,000đ / một case xử lý.     │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘
```

> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: [Dán nội dung]. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."*

---

# 🏗️ Phase 3 — DEEP-DIVE (Nhóm, 85 min)

## 3.1. Current-State Workflow Mapping (25 min)
**Vẽ quy trình hiện tại lên bảng/giấy A3.** Sử dụng các ký hiệu:
* 🔴 **Bottleneck:** Bước gây tắc nghẽn, tốn thời gian, hoặc sai sót nhiều nhất.
* 🔄 **Handoff:** Điểm chuyển giao thông tin giữa người và hệ thống, hoặc giữa các bộ phận.
* Ghi rõ thời gian vận hành trung bình: **Tổng cộng = ____ phút/lượt**.

## 3.2. Problem Statement (6-field) & Metrics (15 min)
Điền đầy đủ 6 trường thông tin của bài toán:

| Field | Nội dung chi tiết |
|---|---|
| **1. Actor / Operator** | Ai đang thực hiện tác vụ hằng ngày? |
| **2. Current Workflow** | Mô tả tóm tắt quy trình thủ công hiện tại và công cụ sử dụng. |
| **3. Bottleneck** | Bước nào chậm, lỗi, hoặc cần xử lý ngôn ngữ tự động nhiều nhất? |
| **4. Business Impact** | Tổn thất thực tế đo bằng thời gian, chi phí, hoặc SLA của Vingroup. |
| **5. Success Metric** | AI giải quyết được thì đạt ngưỡng số mấy? (Ví dụ: *"85% vé được phân loại dưới 10s"*). |
| **6. Operational Boundary** | AI được phép làm gì, TUYỆT ĐỐI không được làm gì, điểm nào cần duyệt? |

## 3.3. Future-State Flow & AI Fit (25 min)
* **Xác định mức AI Fit (AI-Fit Matrix):** Giải pháp thuộc nhóm nào? [ ] Rule / State-Machine [ ] LLM Feature [ ] Agentic Loop.
* **Vẽ Future-State Flow:** Đánh dấu rõ:
  * 🔵 **AI Step:** Tác vụ LLM xử lý.
  * 🟢 **Human Step (HITL):** Bước con người phê duyệt/review (Human-in-the-loop).
  * ↩️ **Fallback:** Kế hoạch dự phòng khi LLM trả về kết quả lỗi hoặc không tự tin.

---

# 💻 Phase 4 — TECHNICAL PROMPT PROTOTYPE (Nhóm, 30 min)

Để đảm bảo kỹ sư của Vin Smart Future luôn giữ vững năng lực lập trình, nhóm của bạn sẽ tiến hành **lập trình bản mẫu prompt** trực tiếp trên **Gemini 2.5 Flash** bằng Python để stress-test hệ thống.

### Hướng dẫn thực hiện:
1. Mở file [starter-code/prompt_prototype.py](starter-code/prompt_prototype.py) bằng VS Code/Cursor.
2. Hoàn thiện các nội dung sau:
   * **System Prompt:** Viết chỉ thị cực kỳ nghiêm ngặt quy định vai trò, nhiệm vụ, định dạng output và **Operational Boundary (Ranh giới cấm)** của mô hình.
   * **Structured Output:** Định nghĩa định dạng JSON output rõ ràng.
   * **Adversarial Test Cases:** Viết ít nhất 3 prompts "tấn công" (Adversarial inputs) cố tình dụ AI vượt ranh giới hoặc đưa ra câu trả lời không được phép để kiểm tra xem ranh giới của bạn có thực sự vững chắc.
3. Chạy file python:
   ```bash
   python3 prompt_prototype.py
   ```
4. Kiểm tra xem các ranh giới an toàn có bị LLM phá vỡ hay không và ghi lại kết quả vào worksheet.

---

# 🏁 Phase 5 — EVALUATE (Nhóm, 20 min)

### AI Readiness Checklist:
1. [ ] Chúng tôi có sẵn dữ liệu mẫu/logs sạch để test?
2. [ ] Rủi ro khi AI sai có nằm trong tầm kiểm soát (qua HITL hoặc Fallback)?
3. [ ] Stakeholders sẵn sàng thay đổi quy trình làm việc cũ?

### Quyết định cuối cùng của Ban Giám Đốc Vin Smart Future:
[ ] **GO (Bắt đầu xây dựng Prototype):** Bắt đầu phát triển với scope hẹp.
[ ] **NOT YET (Cần tích lũy thêm dữ liệu/xác lập baseline):** Trì hoãn để chuẩn bị thêm.
[ ] **NO-GO (Không khả thi / Rule-based tốt hơn):** Hủy bỏ dự án AI này.

**Justification (Lý giải quyết định dựa trên bằng chứng kỹ thuật và chi phí):**
> *Viết lý giải chi tiết tại đây*

---

# 📝 Phase 6 — REFLECTION (Cá nhân)
*Ghi nhận phản ánh của cá nhân bạn về việc phối hợp với AI trong buổi học hôm nay vào file `03-ai-log.md`.*
đã điền file.