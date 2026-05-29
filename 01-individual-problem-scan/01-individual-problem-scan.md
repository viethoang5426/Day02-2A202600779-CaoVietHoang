# 01 — Individual Problem Scan

## Scan rộng

Lan scan 10 problems từ nhiều góc nhìn khác nhau xoay quanh việc học viên bị quá tải thông tin.

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Lặp lại | Gom thông báo từ Zalo, FB, Discord, Teams để làm Weekly Digest (Bản tin tuần) | Quản lý học viên, TA | Mất khoảng 120 phút mỗi chiều thứ Sáu |
| 2 | Phân mảnh | Học viên lỡ deadline bài tập vì thông báo trôi quá nhanh trên Zalo/Discord | Học viên, Giảng viên | Tỉ lệ nộp bài muộn/quên bài chiếm 15-20% |
| 3 | Tốn thời gian | Tìm kiếm và copy quy định (hoàn phí, bảo lưu) từ Web/Handbook PDF để trả lời Q&A | Quản lý học viên | Mất 10-15 phút lục lọi tài liệu cho mỗi tin nhắn hỏi |
| 4 | Lặp lại | Học viên mới onboard không biết tìm tài liệu cũ ở đâu, liên tục hỏi lại câu cũ | Học viên mới, TA | 1 câu hỏi về "link record buổi 1" bị hỏi đi hỏi lại 5 lần/tuần |
| 5 | Khó tra cứu | Giảng viên post tài liệu lên Teams, nhưng học viên quen dùng FB Group nên không thấy | Học viên | Thường xuyên nhắn tin: "Cô ơi em không thấy file bài tập" |
| 6 | AI có thể tốt hơn | Lọc các câu hỏi học thuật từ Discord để gom thành bộ FAQ cho khóa sau | TA, Academic Team | Cứ hết khóa là thông tin trôi mất, không ai rảnh để ngồi copy từng dòng |
| 7 | Tốn thời gian | Nhắc nhở từng học viên lỡ buổi học đọc lại recap trên các group khác nhau | TA | Mất 30 phút nhắn tin riêng cho từng người sau mỗi buổi |
| 8 | Pain từ người khác | Ban đào tạo gửi policy mới qua email, nhưng học viên chỉ check Zalo nên bỏ lỡ | Học viên, Ban đào tạo | Sinh viên phàn nàn "em chưa được thông báo" khi có sự cố |
| 9 | Chờ đợi | Học viên nhắn tin hỏi tìm link nộp bài lúc 10h tối, không ai trực | Học viên | Phải chờ đến 9h sáng hôm sau mới được phản hồi |
| 10 | AI có thể tốt hơn | Tóm tắt các luồng tranh luận dài về kỹ thuật trên Discord để cho vào Newsletter | Quản lý học viên | Đọc hiểu và tóm tắt lại đoạn chat dài tốn 20-30 phút |

Vì sao phần scan này mạnh:
- Phản ánh đúng thực trạng "thừa kênh giao tiếp" của các cộng đồng học tập hiện nay (Zalo để chat nhanh, FB để chia sẻ, Discord/Teams để học thuật, Web để lưu trữ).
- Xác định rõ nỗi đau đến từ cả hai phía: Học viên (bị ngợp, lỡ thông tin) và Nhân sự (mất thời gian gom nhặt, nhắc nhở).
- Có metric thời gian và dấu hiệu rõ ràng.

## Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Tổng hợp Bản tin tuần (Weekly Digest) từ 5 kênh | Workflow quá rõ, tốn nhiều công sức gom nhặt văn bản thô, metric cải thiện dễ đo lường | Khả năng AI kết nối (API/Export) với các kênh như Zalo có dễ không |
| 2 | Trả lời Q&A quy định từ Web/Handbook | Có pain thật, lặp đi lặp lại nhiều lần trong ngày | Rủi ro AI (Hallucination) bịa ra chính sách học phí, bảo lưu |
| 3 | Gom câu hỏi kỹ thuật từ Discord thành FAQ | Tái sử dụng được kiến thức cho khóa sau, impact tốt | Phải biết cách đánh giá câu trả lời nào của học viên/TA trên Discord là đúng nhất |

## Problem Card #1 — Tổng hợp Weekly Digest cho học viên

**Problem 1 câu:**
Mỗi chiều thứ Sáu, Quản lý học viên mất khoảng 120 phút đi gom nhặt thông báo, link bài tập, update từ 5 nguồn (Zalo, FB, Discord, Teams, Web) để viết bản tin tổng hợp (Weekly Digest) nhằm giúp học viên không bị lỡ thông tin.

**Actor:**
Lan, Quản lý học viên (Student Success Coordinator) chịu trách nhiệm vận hành lớp và giao tiếp với học viên.

**Thời điểm / bối cảnh:**
Chiều thứ Sáu hằng tuần, chuẩn bị bản tin gửi học viên trước cuối tuần để họ có thời gian làm bài tập.

**Current workflow:**
```text
1. Lướt Zalo: Tìm và copy các tin nhắn đã ghim (nhắc lịch, sự kiện).
2. Lướt FB Group: Lấy link các bài post chia sẻ tài liệu hay trong tuần.
3. Check Discord/Teams: Gom link bài tập, thông báo từ Giảng viên.
4. Check Website/Handbook: Xem có chính sách/cập nhật hệ thống nào mới không.
5. Paste tất cả vào Google Docs (Raw text).
6. Viết và cấu trúc lại Digest: Phân loại theo (1) Cần làm ngay, (2) Sự kiện sắp tới, (3) Tài liệu hữu ích. Lược bỏ văn phong chat mạng.
7. Gửi email cho học viên & quăng link vào nhóm chat.
```

**Bottleneck:**
Bước 6 — Cấu trúc và viết lại nội dung từ các văn phong lộn xộn (chat cụt lủn trên Zalo, post dài trên FB, text kỹ thuật trên Discord) mất khoảng 60 phút và rất mệt mỏi.

**Impact:**
120 phút/tuần cho 1 lớp. Nếu Lan quản lý 4 lớp, mất trọn 1 ngày làm việc (8 tiếng) chỉ để làm việc "copy - dán - dịch lại". Nếu Lan không làm, học viên sẽ ngợp thông tin, lỡ deadline, dẫn đến rớt môn và phản hồi xấu.

**Success metric:**
Giảm thời gian làm 1 bản Weekly Digest từ 120 phút xuống dưới 20 phút. Format bản tin mạch lạc hơn, giảm 50% tin nhắn hỏi "tuần này có bài tập gì không chị".

**Non-AI alternative:**
Quy định "Bàn tay sắt": Cấm mọi giao tiếp công việc trên Zalo/FB, ép 100% Giảng viên và Học viên dùng duy nhất 1 hệ thống LMS (Canvas/Moodle). Tuy nhiên, khó áp dụng vì thói quen dùng mạng xã hội của học viên Việt Nam quá lớn.

**AI hypothesis:**
AI tự động cấu trúc dữ liệu thô (được Lan export/copy từ các kênh) và chuyển sang văn phong bản tin (Digest) theo đúng template. Quản lý học viên chỉ cần duyệt và tinh chỉnh.

**Quick gut:**
Workflow.

### Draft current workflow

CURRENT STATE — 120 phút

[1 Lướt lấy tin Zalo: 10']
→ [2 Lấy link FB Group: 10']
→ [3 Gom update Discord/Teams: 20']
→ [4 Check web policy: 10']
→ [5 Tổng hợp thô vào Docs: 5']
→ [6 Cấu trúc & Viết lại thành Bản tin: 60']  <-- bottleneck
→ [7 Gửi mail & post thông báo: 5']
```

### Draft future workflow

FUTURE STATE — 22 phút

[1 Lan copy/paste raw data từ các kênh: 5']
→ [2 AI phân loại thông tin (Deadline, Sự kiện, Tài liệu): 1']
→ [3 AI viết lại văn phong Bản tin: 1']
→ [4 Lan review + edit độ chính xác: 10']  <-- human boundary
→ [5 Lan duyệt template và gửi: 5']

Fallback: AI cấu trúc lộn xộn hoặc thiếu thông tin quan trọng → Lan tự chỉnh sửa thủ công trên Docs.
```

## Problem Cards #2 và #3 — tóm tắt

| Card | Actor | Bottleneck | Metric | Quick gut | Vì sao chưa chọn làm #1 |
|---|---|---|---|---|---|
| Trả lời Q&A Handbook | Quản lý học viên | Lục tìm đúng trang PDF chứa chính sách học viên đang hỏi | 15 phút/câu → 2 phút/câu | RAG / Agent | Rủi ro AI bịa (hallucinate) chính sách tài chính rất nguy hiểm |
| Gom FAQ từ Discord | TA (Trợ giảng) | Đọc toàn bộ lịch sử chat để lọc ra luồng kiến thức có giá trị | 3 tiếng/cuối khóa → 30 phút | Workflow | Cần đánh giá đúng/sai từ ngữ chuyên ngành, không làm thường xuyên bằng Weekly Digest |
