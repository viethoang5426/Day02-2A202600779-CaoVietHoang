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