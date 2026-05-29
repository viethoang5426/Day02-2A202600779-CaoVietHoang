


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





```