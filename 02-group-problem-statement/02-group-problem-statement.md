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



# 02 — Group Problem Statement

## Group convergence

Nhóm 4 người, mỗi người share top 3. Tổng cộng khoảng 12 candidates.

| Cluster | Candidate examples | Pattern chung |
|---|---|---|
| Phân tán thông tin & Hướng dẫn mơ hồ | Thông tin học vụ bị phân tán đa kênh; Lab nhiều yêu cầu mơ hồ; Thiếu luồng hướng dẫn chính thức; Tài liệu dài khó tách yêu cầu thật sự | Người học bị ngợp giữa "biển" tài liệu, không biết tập trung vào đâu, dẫn đến Quản lý/TA phải gom nhặt và giải đáp liên tục |
| Quá tải & Lệch nền tảng | Học 10-12h/ngày gây quá tải; Sinh viên no-tech khó theo kịp; Không biết trọng tâm bài trước khi học | Vấn đề thuộc về thiết kế chương trình và lượng kiến thức, AI khó giải quyết tận gốc mà chỉ hỗ trợ tóm tắt |
| Tooling & Kỹ thuật | Học viên kẹt ở quy trình GitHub/VS Code | Vấn đề thao tác công cụ. Có workflow rõ nhưng có thể giải quyết tốt bằng non-AI (video hướng dẫn, checklist) |
| Quy trình làm việc nhóm & Đánh giá | Thiếu checklist tự kiểm tra bài nộp; Feedback nhóm bị phân tán; Thiếu tiêu chí Team Matching; Viết Problem Card yếu | Khó khăn trong việc đối chiếu, đo lường chất lượng công việc và cộng tác nội bộ |

## Shortlist và score

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Tổng hợp thông tin phân tán (Weekly Digest) | 5 | 5 | 5 | 5 | 5 | 5 | 5 | 35 |
| Kẹt quy trình GitHub/VS Code | 5 | 5 | 4 | 4 | 5 | 4 | 4 | 31 |
| Thiếu checklist tự kiểm tra bài nộp | 4 | 4 | 4 | 4 | 4 | 4 | 4 | 28 |

Nhóm chọn: **Tổng hợp thông tin phân tán (Weekly Digest)**.

Vì sao chọn:
- Bao trùm được pain point lớn nhất ở cả hai phía: học viên (bị ngợp, lỡ thông tin) và Quản lý học viên/TA (mất thời gian tổng hợp).
- Workflow gom tin và viết báo cáo tuần rất rõ ràng, đo đếm được bằng metric thời gian (120 phút).
- Có thể so sánh Rule / Workflow / Agent rất rõ.
- Có thể vẽ before/after workflow mạch lạc.

Vì sao không chọn các bài khác:
- Kẹt quy trình GitHub: Vấn đề thao tác công cụ có thể giải quyết dứt điểm bằng Rule (Checklist chi tiết hoặc Video hướng dẫn) mà chưa chắc cần đến AI.
- Thiếu checklist bài nộp: Dễ trượt sang việc tạo template có sẵn thay vì xây dựng một workflow tích hợp AI thực thụ.

## Quick validation

Nhóm hỏi nhanh 3 Quản lý học viên (Student Success) và TA tại các trung tâm đào tạo.

| Nguồn | Số người | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Phỏng vấn nhanh | 3 | 3/3 người than phiền sinh viên hay hỏi lắt nhắt trên Zalo/Discord, tốn rất nhiều thời gian đi gom link bài tập mỗi cuối tuần | 1 người cho rằng "Nên rèn kỷ luật sinh viên, bắt lên LMS đọc thay vì tổng hợp hộ" | Thêm non-AI alternative: Rèn kỷ luật. Nhưng thực tế vận hành ngắn hạn vẫn cần Weekly Digest để đảm bảo tỉ lệ hoàn thành khóa |
| Quan sát lớp học thật | Nhiều | Sinh viên thường xuyên hỏi "link nộp bài chỗ nào", "nay có bài tập không" ở các kênh chat | Thông báo từ ban đào tạo đôi khi không có quy chuẩn format đầu vào | Gom chung các thông báo lộn xộn này làm Input thô cho AI xử lý cấu trúc |

Insight sau validation:

```text
Thói quen dùng đa kênh (Zalo, FB, Discord) của học viên rất khó bỏ ngay. Pain thật sự không chỉ là việc tìm kiếm, mà là khâu "đọc hiểu văn bản thô từ nhiều nguồn lộn xộn và viết lại cho ra dáng một bản tin chuyên nghiệp".
```

## Research giải pháp

Nhóm tìm các hướng đã có sẵn, không giả định phải tự build từ đầu.

| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Zapier / Make | [https://zapier.com](https://zapier.com) | Tự động kéo tin nhắn từ Discord/FB về Google Sheets | Pull data tự động rất nhanh | Không phân biệt được tin chat nhảm và tin quan trọng, văn phong vẫn lộn xộn | Dùng để thay thế Rule ở bước gom text thô, nhưng chưa giải quyết được narrative |
| Discord Auto-Summary | (Tính năng Discord) | Tóm tắt các thread chat dài | Nhanh, tích hợp sẵn | Chỉ hoạt động trên Discord, không gom được Zalo, Facebook, Website | Không giải quyết trọn vẹn được bài toán "Đa nguồn" |
| ChatGPT / Claude Pro | [https://chatgpt.com](https://chatgpt.com) | Cấu trúc lại dữ liệu thô thành bản tin | Văn phong mạch lạc, biết phân loại theo deadline/sự kiện | Có thể hallucinate (bịa sai ngày tháng, sai link) | Phải có Workflow rõ: Người cung cấp text thô → AI draft → Người soát lại link/ngày tháng |

Research takeaway:

```text
Không thể xây Agent tự động chui vào Zalo, FB, Discord đọc rồi tự động gửi email cho học viên vì rào cản API và rủi ro sai thông tin. Solution tốt nhất là Workflow: Người gom text thô → AI xử lý draft nội dung → Người Review và Gửi.
```

## Workflow before/after

File nhóm nộp kèm:

```text
02-group-problem-statement-workflow.png/pdf/md
```

Nội dung workflow:

```text
CURRENT STATE — 7 bước, 120 phút

[1 Lướt lấy tin Zalo: 10']
→ [2 Lấy link FB Group: 10']
→ [3 Gom update Discord/Teams: 20']
→ [4 Check web policy/Handbook: 10']
→ [5 Tổng hợp thô vào Docs: 5']
→ [6 Cấu trúc & Viết lại thành Bản tin: 60']  <-- bottleneck
→ [7 Gửi mail & post thông báo: 5']

FUTURE STATE — 5 bước, 22 phút

[1 Export/Copy text thô đa kênh: 5']         -- Rule/Manual
→ [2 AI phân loại (Deadline, Sự kiện, TL): 1'] -- Workflow step
→ [3 AI draft văn phong Bản tin: 1']           -- Workflow step
→ [4 Quản lý HV review + check link: 10']      -- Human boundary
→ [5 Gửi mail & post thông báo: 5']

Fallback:
AI tóm tắt sai hoặc bịa link → Quản lý HV tự copy link gốc chèn vào và sửa tay trên Docs.

Bottleneck mới:
Review độ chính xác của link và ngày tháng. Đây là bottleneck bắt buộc chấp nhận được để đảm bảo uy tín thông tin.
```

Before/after impact:

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Tổng thời gian làm Digest | 120 phút | Dưới 25 phút | Target chính |
| Công sức xử lý văn bản | Phải tự gõ/cấu trúc | Dùng AI prompt | Giảm stress cho nhân sự |
| Bước thủ công | 7/7 | 3/5 | Vẫn cần người gom thô và người review |
| Bottleneck chính | Viết cấu trúc lại tin | Dò chéo độ chính xác | Human boundary |
| Rủi ro mới | Trễ giờ gửi do viết lâu | AI hallucinate sai deadline | Check chéo thật kỹ ở bước review |

## Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | Quản lý học viên (Student Success) chịu trách nhiệm thông tin cho lớp. |
| **Workflow** | Mỗi thứ Sáu đi gom tin Zalo, FB, Discord, Web → dán vào Docs → cấu trúc lại nội dung → viết nháp → review → gửi. |
| **Bottleneck** | Bước phân loại tin thô và viết cấu trúc lại văn phong mất khoảng 60 phút, mệt mỏi và dễ sót ý. |
| **Impact** | Tốn 120 phút/tuần/lớp. Sinh viên dễ bị ngợp thông tin, lỡ deadline, phải hỏi đi hỏi lại. |
| **Success Metric** | Giảm tổng thời gian làm digest xuống dưới 25 phút; format dễ hiểu giúp giảm 50% tin nhắn hỏi lặt vặt. |
| **Boundary** | AI không được quyền tự động gửi email/chat cho học viên; không tự sáng tác thêm deadline/chính sách. |

## Rule / Workflow / Agent

| Mức | Phương án | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | Dùng template cố định, bắt sinh viên tự lên LMS coi, cấm chat Zalo. | Đủ nếu văn hóa học tập có tính tự giác cực cao. | Thực tế sinh viên lười, dễ rớt môn hàng loạt và phản hồi dịch vụ tệ. | Không chọn làm toàn bộ |
| **Workflow** | Người gom text → AI phân loại & viết draft → Người check link/ngày → Người gửi. | Hợp vì đầu vào là text lộn xộn cần ngôn ngữ tự nhiên, các bước đi theo đường thẳng. | AI bịa ngày tháng, sai link bài tập. | Chọn |
| **Agent** | Agent tự cắm API vào các kênh, tự theo dõi và tự động gửi tin nhắc nhở. | Chỉ cần nếu muốn cá nhân hóa nhắc nhở cho từng sinh viên theo thời gian thực. | Setup API phức tạp, không lấy được data từ Zalo cá nhân, rủi ro spam cao. | Chưa chọn |

Mức chọn:

```text
Workflow.
```

Vì sao:
- Bước gom thông tin có thể làm tay thật nhanh (copy-paste text thô).
- Cấu trúc, phân loại và viết lách là điểm mạnh nhất của AI ngôn ngữ.
- Vẫn cần Human Review để đảm bảo tính pháp lý/chính xác của deadline. Không được phép giao cho Agent tự chạy.

## Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** | Quản lý học viên (Student Success). |
| **Workflow** | Gom text thô đa kênh → tổng hợp vào Docs → AI phân loại → AI draft bản tin → người review link/ngày → gửi. |
| **Bottleneck** | Phân loại mớ text hỗn độn và cấu trúc lại mất khoảng 60 phút mỗi tuần. |
| **Impact** | Mất nhiều giờ làm việc lặp lại. Học viên lỡ thông tin, trải nghiệm học tập giảm sút. |
| **Success Metric** | Giảm tổng thời gian làm digest xuống dưới 25 phút; không tăng số lượng câu hỏi đính chính từ học viên. |
| **Boundary** | AI không tự gửi thông báo, không tự bịa thông tin tài chính/deadline, chỉ xử lý trên text đầu vào. |
| **AI intervention point** | Sau khi văn bản thô từ đa kênh được gom lại, trước bước Quản lý học viên duyệt bản tin cuối. |
| **Mức chọn** | Workflow: Người gom text thô → AI draft văn bản → Người kiểm duyệt. |
| **Rủi ro & người thật kiểm tra** | Rủi ro: Hallucination (sửa ngày, gắn nhầm link). Người thật review: Quản lý học viên phải đối chiếu text đầu ra với text gốc trước khi gửi. |

## Final decision

Decision:

```text
Go với scope nhỏ ở mức Workflow.
```

Pilot nhỏ nhất:
- Lấy text thô (chat Zalo, Discord, post FB) của 2 tuần học gần nhất.
- Chạy workflow bán thủ công: Dán toàn bộ text thô đó vào Prompt chứa Template Weekly Digest chuẩn.
- AI draft bản tin nháp.
- Quản lý học viên bấm giờ xem việc review và sửa lỗi sai của AI tốn bao nhiêu phút.

Exit / rollback:
- Nếu AI liên tục hiểu sai ý (ví dụ: gộp nhầm thông báo nghỉ học với thông báo nộp bài), mất nhiều công sửa hơn tự viết → Bỏ AI, quay về dùng Template và tự điền tay.
- Nếu không thể copy text Zalo nhanh gọn → Tạo Rule ép Giảng viên/TA chỉ chốt thông tin trên 1 kênh duy nhất rồi mới dùng AI tóm tắt kênh đó.

Decision rationale:
- Giao tiếp đa kênh là bài toán nhức nhối ở các cộng đồng học tập, impact rất cao.
- Chặn đúng chỗ AI mạnh nhất: Xử lý đống lộn xộn thành văn bản có cấu trúc.
- AI nằm ở một bước cụ thể, không ôm toàn bộ hệ thống.
- Boundary (Ranh giới) kiểm soát an toàn vì người gửi cuối cùng vẫn là con người.




# 03 — Individual Reflection Example

## Đóng góp của Hoàng trong nhóm

| Hoạt động | Hoàng đã làm gì? | Kết quả |
|---|---|---|
| Scan cá nhân | Đưa ra 10 problems về khó khăn trong việc quản lý học viên và tình trạng quá tải thông tin | Nhóm có nhiều candidate thực tế về mảng vận hành lớp học |
| Pitch | Pitch bài toán "Tổng hợp Bản tin tuần (Weekly Digest) từ đa kênh" | Bài toán được vào shortlist và cuối cùng được chọn làm bài nhóm |
| Challenge | Phản biện bài toán "Học viên kẹt quy trình GitHub" | Nhóm nhận ra đây là lỗi công cụ, có thể dùng Rule (Checklist/Video) thay vì AI |
| Workflow | Vẽ current/future workflow cho quy trình gom tin đa kênh | Nhóm dùng làm workflow bản cuối |
| Research | Tìm hiểu Zapier, Discord Auto-Summary và ChatGPT cho bài toán | Nhóm thấy rõ giới hạn: không thể dùng Agent tự động cắm API vào Zalo cá nhân |
| Rule / Workflow / Agent | Lập luận chọn Workflow (bán thủ công), phản đối dùng Agent tự động gửi tin | Nhóm thống nhất decision giữ ranh giới an toàn (Human review) |

## Bảng dùng AI trong reflection

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai/hời hợt ở đâu? | Tôi sửa gì |
|---|---|---|---|---|
| Scan | Gợi ý thêm problems trong việc quản lý cộng đồng học tập | Giúp nhớ ra các case như tóm tắt Discord, trả lời Q&A Handbook | AI hay gợi ý làm chatbot tự động trả lời 100% | Bỏ qua chatbot, chỉ chọn các vấn đề có workflow gom nhặt thông tin rõ ràng |
| Workflow | Nhờ AI chuyển các bước làm thủ công thành dạng text flow | Giúp định hình nhanh format và tính toán số phút | AI tự gộp bước gom tin thô và duyệt tin làm một | Tách rõ bước "người gom thô" và "người duyệt link" để thấy Human boundary |
| Research | Tìm các tool automation kết nối Zalo và nhóm chat | Gợi ý được Zapier, Make để xử lý luồng dữ liệu | AI ảo tưởng rằng có thể dễ dàng lấy API của Zalo cá nhân | Phải tự xác minh lại và chuyển hướng sang copy tay (Workflow bán thủ công) |
| Problem Statement | Nhờ AI cấu trúc lại câu Problem 1 câu cho gọn | Giúp câu văn mạch lạc, nhấn mạnh được bottleneck | AI quên mất yếu tố rủi ro sai lệch thông tin (Hallucination) | Tự bổ sung thêm rủi ro sai ngày tháng/link vào phần Rủi ro & Human kiểm tra |

## Bài học của Hoàng

- Problem tốt không phải là bài toán nghe có vẻ "tự động hóa 100%" (như Agent tự đọc tin nhắn rồi tự reply), mà là bài toán có workflow lặp lại rõ ràng và đo được bằng phút.
- Khi vẽ workflow ra, tôi mới thấy AI không cần thiết phải làm từ A-Z. Việc đi lướt Zalo copy tin cứ để người làm, gửi email cứ để người duyệt, AI chỉ nên đắp vào chỗ tốn công nhất: xử lý ngôn ngữ lộn xộn thành cấu trúc.
- Không phải lúc nào cũng cần API. Tích hợp tự động vào Zalo/Facebook rất khó và nhiều rủi ro bảo mật/spam. Làm bán thủ công (Workflow) kết hợp AI tóm tắt văn bản là phương án an toàn và khả thi hơn nhiều.
- Research các tool có sẵn giúp nhận ra giới hạn của công nghệ hiện tại (ví dụ: AI dễ bịa link), từ đó biết cách đặt ranh giới kiểm soát (Human boundary) cho hợp lý.

Nếu làm lại:

```text
Tôi sẽ phỏng vấn sâu thêm 3-5 bạn học viên để xem ngoài Zalo và Discord, họ còn hay bị lỡ thông tin ở những ngách nào nữa (email, web, hay truyền miệng), từ đó điều chỉnh template và metrics của Weekly Digest cho sát thực tế hơn là chỉ dựa vào góc nhìn của Quản lý học viên.
```