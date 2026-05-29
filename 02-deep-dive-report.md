# Tên nhóm: bàn D1 + cháu bác Vượng:
| Họ và tên | MSV | 
|---|---|
| Trần Hoàng Hà | 2A202600612 |
| Hoàng Đức Trường | 2A202600552 |
| Nguyễn Hồ Diệu Linh | 2A202600567|
| Nguyễn Thị Bích Duyên | 2A202600752 |
| Nguyễn Thị Hiểu | 2A202600545 |
| Nguyễn Hoàng Tùng | 2A202600628 |

| Field | Nội dung |
|---|---|
| **1. Actor / Operator** | Bác sĩ, Bệnh nhân, Điều dưỡng điều phối. |
| **2. Current Workflow** | Bệnh nhân đặt lịch trước qua App/Kiosk tại viện $\rightarrow$ Hệ thống tự động phân luồng vào phòng khám phù hợp dựa trên cây quyết định triệu chứng $\rightarrow$ Bệnh nhân đến thẳng phòng khám $\rightarrow$ Bác sĩ khám (hệ thống tự động hiển thị lịch sử bệnh án điện tử - EMR) $\rightarrow$ Bác sĩ dùng Giọng nói để AI Text-to-Speech điền nhanh vào form bệnh án (thay vì gõ tay). |
| **3. Bottleneck** | 1. Thời gian chờ đợi xếp hàng làm thủ tục tại quầy lễ tân trực tiếp; 2. Thời gian bác sĩ phải gõ bàn phím để nhập liệu bệnh án điện tử sau khi khám. |
| **4. Business Impact** | 1-Giới hạn năng lực tiếp nhận bệnh nhân của bệnh viện (lãng phí công suất phòng khám); 2-Trải nghiệm khách hàng thấp dẫn đến tỷ lệ khách hàng không quay lại là 25%. |
| **5. Success Metric** | 1-TAT (Turnaround Time): Giảm thời gian chờ đợi trung bình của bệnh nhân từ lúc vào viện đến lúc gặp bác sĩ từ 45 phút xuống còn < 15 phút; 2-Throughput: Tăng số lượng bệnh nhân bác sĩ khám được trong 1 ngày lên 20% nhờ giảm thời gian gõ nhập liệu; 3-Cost per Visit: Giảm chi phí vận hành nhân sự điều phối tại quầy xuống 30%; 4-Accuracy: Tỷ lệ phân luồng chính xác của hệ thống Rule-based đạt 98%.|
| **6. Operational Boundary** | Toàn bộ dữ liệu lưu trữ tại Server nội bộ (On-premise). AI chỉ được ứng dụng ở dạng Offline Speech-to-Text để chuyển giọng nói của bác sĩ thành văn bản nhập vào form có sẵn, tuyệt đối không gửi dữ liệu lên Cloud của bên thứ ba (OpenAI, Google). Hệ thống phân luồng chạy bằng Rule-based (Cây quyết định y khoa) được kiểm duyệt bởi Hội đồng Y khoa. **CẤM:** AI không được tự động gửi thông tin của bệnh nhân ra ngoài hoặc gửi cho bên thứ 3. |