# TÀI LIỆU PROBLEM STATEMENT - CÁC GIAI ĐOẠN PHÁT TRIỂN HỆ THỐNG AI

---

## PHASE 0 : KHỞI TẠO VÀ CHUẨN BỊ
*(Giai đoạn này hiện tại chưa có nội dung chi tiết từ hệ thống)*

---

## PHASE 1 : KHẢO SÁT VÀ XÁC ĐỊNH BÀI TOÁN CỐT LÕI
Dưới đây là các vấn đề cốt lõi đã được khảo sát và ghi nhận trong quy trình hiện tại:

1. Chưa có cơ chế hiểu được trình độ, điểm mạnh của mỗi người khiến việc ghép đội (match team) chưa đồng nhất.
2. Chưa thống nhất các thông tin, hướng dẫn thành một line cụ thể, tài liệu bị phân tán nhiều nơi.
3. Lượng kiến thức có thể quá tải cho các bạn học viên không có nền tảng công nghệ (background tech).
4. Có quá ít trợ giảng so với nhu cầu hỏi đáp của học viên.
5. Quy trình điểm danh, nộp bài hoạt động chưa hiệu quả.

---

## PHASE 2 : ĐỊNH HƯỚNG GIẢI PHÁP AI (PROBLEM STATEMENT)

### 1. Vấn đề: Thiếu cơ sở đánh giá năng lực để ghép đội (Team Matching) đồng nhất
* **Actor (Đối tượng ảnh hưởng):** Học viên và Ban tổ chức (BTC) / Quản lý chương trình.
* **Workflow (Quy trình hiện tại):** Học viên cung cấp thông tin $
ightarrow$ Tự tìm nhóm hoặc BTC xếp nhóm ngẫu nhiên $
ightarrow$ Chốt danh sách.
* **Bottleneck (Nút thắt):** Thiếu dữ liệu phân tích kỹ năng, điểm mạnh/yếu của từng cá nhân; quá trình ghép nhóm thủ công, cảm tính và mất thời gian.
* **Impact (Tác động):** Chất lượng team không đồng đều, dễ xảy ra xung đột, hiệu suất làm việc nhóm kém, tỷ lệ rời nhóm cao.
* **Success Metric (Chỉ số thành công):** Giảm 80% thời gian ghép nhóm; tăng tỷ lệ hài lòng về đồng đội; giảm số lượng yêu cầu đổi nhóm.
* **Boundary (Ranh giới):** AI không bắt buộc/ép người dùng vào nhóm; quyền quyết định cuối cùng vẫn thuộc về học viên hoặc BTC.
* **Điểm AI can thiệp (Decision entry):** Giai đoạn ngay sau khi học viên hoàn thành hồ sơ/bài test: AI phân tích profile và gợi ý các thành viên bù trừ kỹ năng cho nhau.
* **Mức chọn (Decision level):** Rule / Workflow / Agent? $
ightarrow$ **Workflow / Agent**: Hệ thống tự động phân tích và đưa ra danh sách đề xuất phù hợp nhất.
* **Rủi ro & HITL (Decision safety):** AI gợi ý sai lệch do thông tin đầu vào không chuẩn $
ightarrow$ Học viên có quyền từ chối gợi ý và tìm kiếm thủ công.

---
Draft current workflow

CURRENT STATE - 115 phút

┌─────────────┐   ┌─────────────┐   ┌─────────────┐   ┌─────────────┐
│ 1 Nộp form  │──>│ 2 Tải & lọc │──>│ 3 Đọc &     │──>│ 4 Ghép nhóm │
│ data        │   │ file Excel  │   │ phân tích   │   │ thủ công    │
│ ⏱ 15'       │   │ ⏱ 20'       │   │ ⏱ 45' 🔴    │   │ ⏱ 20'       │
└─────────────┘   └─────────────┘   └─────────────┘   └─────────────┘
                                                             │
                                                             ▼
                                      ┌─────────────┐   ┌─────────────┐
                                      │ 6 Công bố   │<──│ 5 Review &  │
                                      │ & email     │   │ chốt ds     │
                                      │ ⏱ 5'        │   │ ⏱ 10'       │
                                      └─────────────┘   └─────────────┘

🔴 = Bottleneck (Phân tích hồ sơ và xếp nhóm thủ công tốn thời gian, cảm tính)


Draft future workflow

FUTURE STATE - 32 phút

┌─────────────┐   ┌─────────────┐   ┌─────────────┐
│ 1 Nộp form  │──>│ 2 AI phân   │──>│ 3 AI draft  │
│ data        │   │ tích data   │   │ team list   │
│ ⏱ 15'       │   │ ⏱ 2'        │   │ ⏱ 3'        │
└─────────────┘   └─────────────┘   └─────────────┘
                                           │
                                           ▼
                          ┌─────────────┐   ┌─────────────┐
                          │ 4 User/BTC  │──>│ 5 Công bố   │
                          │ review chốt │   │ & email     │
                          │ ⏱ 10' 🟢    │   │ ⏱ 2'        │
                          └─────────────┘   └─────────────┘

🟢 = Human boundary
Fallback: Nếu AI gợi ý không phù hợp -> Học viên tự tìm nhóm thủ công.


--- 

### 2. Vấn đề: Thông tin và hướng dẫn bị phân tán, thiếu đồng nhất
* **Actor (Đối tượng ảnh hưởng):** Người dùng nội bộ / Học viên (Người cần tra cứu thông tin).
* **Workflow (Quy trình hiện tại):** Phát sinh thắc mắc $
ightarrow$ Tra cứu trên nhiều kênh (Discord, Zalo, Handbook, Facebook) $
ightarrow$ Hỏi người hỗ trợ $
ightarrow$ Nhận đáp án.
* **Bottleneck (Nút thắt):** Không có nguồn thông tin tập trung, người dùng không biết tìm ở đâu, hỏi lặp lại nhiều câu hỏi cũ.
* **Impact (Tác động):** Tốn thời gian tra cứu, quá tải cho bộ phận Support/Admin, rủi ro làm sai quy trình do đọc tài liệu cũ.
* **Success Metric (Chỉ số thành công):** Giảm tỷ lệ câu hỏi lặp lại cho Support; rút ngắn thời gian trung bình để tìm thấy câu trả lời chính xác.
* **Boundary (Ranh giới):** AI không tự sáng tạo ra quy trình/chính sách mới; chỉ được phép truy xuất từ nguồn dữ liệu đã được phê duyệt.
* **Điểm AI can thiệp (Decision entry):** Cổng thông tin/Chat nội bộ: AI tiếp nhận câu hỏi, tổng hợp thông tin và trả lời ngay lập tức kèm link tài liệu gốc.
* **Mức chọn (Decision level):** Rule / Workflow / Agent? $
ightarrow$ **Agent (RAG)**: Trợ lý ảo truy xuất dữ liệu từ các nguồn đã được định dạng và trả lời tự động.
* **Rủi ro & HITL (Decision safety):** AI trả lời sai ngữ cảnh hoặc bịa thông tin (Hallucination) $
ightarrow$ Có nút chuyển tiếp (Escalate) câu hỏi cho nhân sự hỗ trợ con người xử lý.

---

Draft current workflow

CURRENT STATE - 60 phút

┌─────────────┐   ┌─────────────┐   ┌─────────────┐   ┌─────────────┐
│ 1 Phát sinh │──>│ 2 Tìm Drive/│──>│ 3 Nhắn hỏi  │──>│ 4 Support   │
│ câu hỏi     │   │ Wiki        │   │ Support     │   │ tra cứu     │
│ ⏱ 2'        │   │ ⏱ 15'       │   │ ⏱ 5'        │   │ ⏱ 20' 🔴    │
└─────────────┘   └─────────────┘   └─────────────┘   └─────────────┘
                                                             │
                                                             ▼
                                      ┌─────────────┐   ┌─────────────┐
                                      │ 6 User đọc  │<──│ 5 Text &    │
                                      │ & áp dụng   │   │ gửi trả lời │
                                      │ ⏱ 3'        │   │ ⏱ 15'       │
                                      └─────────────┘   └─────────────┘

🔴 = Bottleneck (Phụ thuộc vào sức người, tra cứu rải rác mất thời gian)


Draft future workflow

FUTURE STATE - 5 phút

┌─────────────┐   ┌─────────────┐   ┌─────────────┐
│ 1 Gửi câu   │──>│ 2 AI query  │──>│ 3 AI trả lời│
│ hỏi AI Bot  │   │ data (RAG)  │   │ + gắn link  │
│ ⏱ 1'        │   │ ⏱ 1'        │   │ ⏱ 1'        │
└─────────────┘   └─────────────┘   └─────────────┘
                                           │
                                           ▼
                          ┌─────────────┐   ┌─────────────┐
                          │ 4 User đọc  │──>│ 5 Áp dụng   │
                          │ & đánh giá  │   │ làm việc    │
                          │ ⏱ 2' 🟢     │   │ ⏱ 0'        │
                          └─────────────┘   └─────────────┘

🟢 = Human boundary
Fallback: Trợ lý ảo AI không trả lời được -> Chuyển tiếp (Escalate) cho con người.

---

### 3. Vấn đề: Quá tải kiến thức đối với người học không có nền tảng Tech
* **Actor (Đối tượng ảnh hưởng):** Học viên thuộc khối Non-tech (Không có nền tảng công nghệ).
* **Workflow (Quy trình hiện tại):** Đọc tài liệu / Nghe giảng $
ightarrow$ Gặp thuật ngữ chuyên ngành $
ightarrow$ Tự tìm hiểu hoặc hỏi chuyên gia $
ightarrow$ Áp dụng.
* **Bottleneck (Nút thắt):** Tài liệu dùng nhiều thuật ngữ kỹ thuật phức tạp; học viên mất nhiều thời gian để hiểu khái niệm cơ bản, dễ nản chí.
* **Impact (Tác động):** Tỷ lệ hoàn thành thấp, tiến độ học tập chậm, giảng viên tốn nhiều thời gian giải thích lại khái niệm nền.
* **Success Metric (Chỉ số thành công):** Giảm thời gian đọc hiểu tài liệu của nhóm Non-tech; tăng điểm bài kiểm tra kiến thức nền; tăng tỷ lệ hoàn thành khóa học.
* **Boundary (Ranh giới):** AI không làm thay bài tập/dự án của học viên; chỉ đóng vai trò "gia sư" giải thích từ vựng và khái niệm.
* **Điểm AI can thiệp (Decision entry):** Ngay khi học viên bôi đen/chọn một thuật ngữ khó trong tài liệu hoặc khi đặt câu hỏi yêu cầu giải thích đơn giản hóa.
* **Mức chọn (Decision level):** Rule / Workflow / Agent? $
ightarrow$ **Workflow / Agent**: AI tự động tạo tooltip giải nghĩa bằng ngôn ngữ đời thường hoặc hội thoại 1:1 giải thích ví dụ thực tế.
* **Rủi ro & HITL (Decision safety):** AI giải thích quá bình dân làm sai lệch bản chất kỹ thuật $
ightarrow$ Cho phép người dùng Vote (Up/Down) và Giảng viên (Coach) định kỳ rà soát các định nghĩa bị vote down.

---

Draft current workflow

CURRENT STATE - 45 phút

┌─────────────┐   ┌─────────────┐   ┌─────────────┐   ┌─────────────┐
│ 1 Đọc/Nghe  │──>│ 2 Gặp thuật │──>│ 3 Tự search │──>│ 4 Lọc & hiểu│
│ tài liệu    │   │ ngữ khó     │   │ Google/Wiki │   │ khái niệm   │
│ ⏱ 10'       │   │ ⏱ 2'        │   │ ⏱ 15'       │   │ ⏱ 15' 🔴    │
└─────────────┘   └─────────────┘   └─────────────┘   └─────────────┘
                                                             │
                                                             ▼
                                      ┌─────────────┐
                                      │ 5 Quay lại  │
                                      │ học tiếp    │
                                      │ ⏱ 3'        │
                                      └─────────────┘

🔴 = Bottleneck (Lượng kiến thức bị dồn ứ, tự chắt lọc thông tin dễ nản)


Draft future workflow

FUTURE STATE - 15 phút

┌─────────────┐   ┌─────────────┐   ┌─────────────┐
│ 1 Đọc/Nghe  │──>│ 2 Bôi đen / │──>│ 3 AI dịch & │
│ tài liệu    │   │ hỏi từ khó  │   │ tóm tắt gọn │
│ ⏱ 10'       │   │ ⏱ 1'        │   │ ⏱ 2'        │
└─────────────┘   └─────────────┘   └─────────────┘
                                           │
                                           ▼
                          ┌─────────────┐   ┌─────────────┐
                          │ 4 User đọc  │──>│ 5 Quay lại  │
                          │ hiểu & Vote │   │ học tiếp    │
                          │ ⏱ 2' 🟢     │   │ ⏱ 0'        │
                          └─────────────┘   └─────────────┘

🟢 = Human boundary
Fallback: AI giải thích sai ngữ cảnh -> User downvote -> Giáo viên rà soát lại.