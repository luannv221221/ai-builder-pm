# AI BUILDER
### Từ người *dùng* AI đến người *xây* hệ thống AI cho công việc thật

> **Bản syllabus v1.0** — Chương trình đào tạo 12 tuần dành cho người đi làm không có nền tảng kỹ thuật.

---

## 1. TỔNG QUAN CHƯƠNG TRÌNH

| Hạng mục | Thông tin |
|---|---|
| **Tên chương trình** | AI Builder — Xây hệ thống AI Agent cho công việc thật |
| **Đối tượng** | Người đi làm non-tech: Marketing, Sales, Business, Operations, HR, Admin, Finance; chủ doanh nghiệp & founder |
| **Yêu cầu đầu vào** | Không cần biết lập trình. Cần: dùng thành thạo Excel/Google Sheets, có ít nhất 1 quy trình công việc lặp lại muốn tự động hoá |
| **Thời lượng** | 12 tuần · 24 buổi · 2 buổi/tuần · 2,5h/buổi |
| **Tổng giờ học** | 60h live + ~40h bài tập & lab có hướng dẫn = **~100h** |
| **Hình thức** | Online trực tiếp (live) + lab thực hành + mentoring capstone 1-1 |
| **Sĩ số** | Tối đa 25 học viên/lớp (đảm bảo chấm eval và mentor capstone) |
| **Đầu ra** | 1 sản phẩm agent chạy thật + bộ đánh giá (eval set) + hồ sơ ROI để trình bày nội bộ |

### Triết lý thiết kế

Phần lớn khoá học AI trên thị trường dừng ở **"làm cho nó chạy được một lần"**. Chương trình này dạy ba thứ mà việc đó thiếu:

1. **Context Engineering** — vì sao agent trả lời sai không phải lỗi model, mà là lỗi context người dùng đưa vào.
2. **Evaluation** — cách chứng minh agent đúng bao nhiêu phần trăm, thay vì "cảm thấy nó ổn".
3. **Tích hợp hệ thống thật qua MCP** — nối agent vào Jira, Slack, Notion, Google Workspace, database nội bộ, chứ không dừng ở demo với file Excel mẫu.

**Nguyên tắc học:** *No-code first, code-assisted.* Học viên không học lập trình. Học viên học cách **điều khiển một Coding Agent viết code thay mình**, và cách kiểm tra kết quả đó đúng hay sai.

---

## 2. KẾT QUẢ HỌC TẬP (Learning Outcomes)

Kết thúc chương trình, học viên có thể:

- **LO1.** Giải thích đúng cơ chế hoạt động của LLM và agent, dự đoán được khi nào AI sẽ sai và vì sao.
- **LO2.** Thiết kế context (tài liệu, system prompt, cấu trúc dữ liệu) để agent đạt chất lượng ổn định, lặp lại được.
- **LO3.** Xây bộ test và rubric để đo chất lượng đầu ra AI bằng số, so sánh được giữa các phương án.
- **LO4.** Xây agent tự động hoá một quy trình công việc thật, có xử lý lỗi và điểm phê duyệt của con người.
- **LO5.** Kết nối agent vào hệ thống nội bộ của tổ chức qua MCP và n8n, có kiểm soát quyền và dữ liệu nhạy cảm.
- **LO6.** Đánh giá rủi ro (chi phí, bảo mật, prompt injection, tuân thủ) và lập checklist đưa agent vào vận hành.
- **LO7.** Lượng hoá ROI và trình bày business case để xin ngân sách/phê duyệt triển khai trong tổ chức.

---

## 3. CẤU TRÚC 4 MODULE

```
Tuần 1-3    MODULE 1 — NỀN TẢNG      Điều khiển AI cho ra kết quả dùng được
Tuần 4-6    MODULE 2 — AGENT         Từ chat sang tự làm việc
Tuần 7-9    MODULE 3 — TÍCH HỢP      Nối agent vào hệ thống thật
Tuần 10-12  MODULE 4 — SẢN XUẤT      Đo lường, vận hành, Capstone
```

---

## BUỔI 0 — ONBOARDING (tự học, trước khai giảng)

Không tính vào 24 buổi. Học viên hoàn thành trước Buổi 1:

- Tạo tài khoản: ChatGPT Plus / Claude Pro, Google Workspace, n8n Cloud (trial), GitHub
- Cài đặt môi trường: Claude Desktop, Node.js, OpenClaw (có script cài tự động kèm hướng dẫn hình ảnh)
- Xem video tiền học 40 phút: giao diện n8n cơ bản
- Nộp **"1 quy trình công việc đau nhất của tôi"** — mô tả 1 trang. Đây là hạt giống của capstone.

---

## MODULE 1 — NỀN TẢNG (Tuần 1–3 · Buổi 1–6)

> *Mục tiêu module: chuyển từ "hỏi AI cho vui" sang "giao việc cho AI và tin được kết quả".*

### Buổi 1 — AI thực sự làm gì bên trong
- LLM đoán chữ tiếp theo: hệ quả thực tế của việc này với công việc của bạn
- Token, context window, cut-off date — ba giới hạn giải thích 80% lỗi thường gặp
- Vì sao AI "bịa" (hallucination): cơ chế, dấu hiệu nhận biết, cách phòng
- Bản đồ công cụ 2026: ChatGPT · Claude · Gemini · công cụ chuyên biệt — chọn cái nào cho việc gì
- **Lab:** Bài test 10 câu hỏi bẫy — tự tay bắt AI nói sai, ghi lại pattern

### Buổi 2 — Prompt Engineering: từ may rủi sang có hệ thống
- Khung prompt 5 thành phần: Vai trò · Nhiệm vụ · Bối cảnh · Ràng buộc · Định dạng đầu ra
- Few-shot: dạy AI bằng ví dụ thay vì bằng mô tả
- Chain-of-thought và khi nào nó phản tác dụng
- Phản mẫu: những kiểu prompt phổ biến nhưng làm kết quả tệ đi
- **Lab:** Viết lại 3 prompt công việc của chính mình theo khung; đo mức cải thiện
- **Giao nộp:** Prompt Library cá nhân v1 (10 prompt cho vai trò của bạn)

### Buổi 3 — Context Engineering I: Context quyết định trần năng lực ⭐
- **Nguyên lý cốt lõi:** Chất lượng đầu ra bị chặn trên bởi chất lượng context, không phải bởi model
- System prompt vs. user prompt vs. tài liệu đính kèm — ba tầng, ba vai trò khác nhau
- Chuẩn bị tài liệu cho AI đọc: cấu trúc file, đặt tên, tách nhỏ, metadata
- Projects (Claude) / Custom GPTs / Gems: dựng không gian làm việc có context thường trực
- **Lab:** Cùng một câu hỏi, ba mức context khác nhau — quan sát chênh lệch kết quả

### Buổi 4 — Context Engineering II: Chọn lọc, nén và duy trì ⭐
- *Context rot*: vì sao hội thoại càng dài AI càng kém, và cách xử lý
- Kỹ thuật nén: tóm tắt trung gian, checkpoint, khởi động lại có chọn lọc
- Tách nhiệm vụ dài thành chuỗi bước ngắn có bàn giao rõ ràng
- **Agent Skills / Custom Instructions:** đóng gói know-how thành năng lực dùng lại được
- **Lab:** Xây 1 Skill đóng gói quy trình riêng của bạn (VD: chuẩn SEO nội bộ, template báo cáo tuần)

### Buổi 5 — Evaluation I: Làm sao biết AI trả lời đúng? ⭐⭐

> *Buổi tạo khác biệt lớn nhất của chương trình.*

- Vì sao "tôi thấy nó ổn" là cách đánh giá không dùng được trong tổ chức
- Xây **Golden Set**: 20 câu hỏi/tình huống có đáp án chuẩn cho công việc của bạn
- Rubric chấm điểm: tiêu chí, thang điểm, ai chấm
- A/B testing prompt: so sánh hai phương án bằng số, không bằng cảm giác
- **Lab:** Chấm 2 phiên bản prompt trên golden set của mình, ra bảng điểm
- **Giao nộp:** Eval Set v1 (20 case + rubric)

### Buổi 6 — WORKSHOP 1 + CHECKPOINT
- Build tại lớp: **Trợ lý AI cá nhân theo đúng vai trò công việc** (context + skills + eval set đi kèm)
- Peer review chéo: mỗi người chạy eval set của bạn học khác
- **Checkpoint 1 (10% điểm):** Trợ lý AI + Eval Set + báo cáo cải thiện có số liệu

---

## MODULE 2 — AGENT (Tuần 4–6 · Buổi 7–12)

> *Mục tiêu module: từ "AI trả lời" sang "AI tự thực hiện chuỗi hành động".*

### Buổi 7 — Agent là gì và khi nào cần agent
- **Công thức nền tảng: Agent = LLM + Context + Tools**
- Vòng lặp hành động: Suy nghĩ → Chọn công cụ → Thực thi → Quan sát → Lặp
- Ba mức tự động hoá: Prompt → Workflow cố định → Agent tự quyết. Chọn mức nào?
- Chi phí thật của agent: token, thời gian chờ, tỉ lệ thất bại
- **Lab:** Phân loại 10 công việc của bạn vào 3 mức tự động hoá

### Buổi 8 — Research Agent: từ câu hỏi đến bộ slide
- Công cụ có sẵn: tìm kiếm web, đọc/ghi file, chạy code, duyệt trình duyệt
- Deep Research: giao đề tài nghiên cứu, thu thập đa nguồn, kiểm chứng chéo, phát hiện nguồn rác
- **Từ nghiên cứu ra sản phẩm trình bày:** báo cáo có trích dẫn → outline → bộ slide hoàn chỉnh
- Đọc "dấu vết thực thi" (trace) để biết agent đã làm gì và sai ở bước nào
- **Lab:** Báo cáo nghiên cứu thị trường/đối thủ + bộ slide trình bày, có nguồn kiểm chứng được

### Buổi 9 — Data Agent: phân tích dữ liệu bằng ngôn ngữ tự nhiên
- Nạp Excel/CSV/Sheets cho agent; làm sạch dữ liệu bẩn
- Sinh biểu đồ và dashboard từ mô tả bằng lời
- **Chống ảo giác số:** quy tắc bắt agent trưng ra phép tính để kiểm chứng
- Giới hạn: khi nào phải tự tay làm thay vì tin agent
- **Lab:** Từ file dữ liệu thô → báo cáo phân tích có biểu đồ + bước kiểm chứng

### Buổi 10 — Coding Agent cho người không biết code ⭐
- **Tool tạo ra tool:** để agent tự viết script làm việc thay bạn
- Claude Code / Cursor cho non-tech: nói việc bằng tiếng Việt, agent viết và chạy code
- Cách kiểm tra kết quả khi bạn không đọc được code: test bằng dữ liệu mẫu, đối chiếu thủ công
- Ranh giới an toàn: những gì tuyệt đối không để agent tự chạy
- **Lab:** Tự động hoá 1 tác vụ file/dữ liệu lặp lại bằng script do agent viết

### Buổi 11 — Knowledge & Memory: cấp kho tri thức cho agent
- Vì sao AI không biết tài liệu nội bộ của công ty bạn
- **RAG giải thích trực quan:** cắt tài liệu → đánh chỉ mục → tìm → đưa vào context
- Chuẩn bị kho tài liệu: cái gì nên đưa vào, cái gì không, cách cấu trúc
- Memory: agent nhớ gì giữa các phiên làm việc, và rủi ro nhớ sai
- **Lab:** Trợ lý tra cứu tài liệu nội bộ (chính sách, quy trình, sản phẩm) + eval độ chính xác

### Buổi 12 — AI Chatbot: đưa kho tri thức thành trợ lý trả lời 24/7 + CHECKPOINT
- Từ kho tri thức (Buổi 11) sang chatbot: kiến trúc một con bot dùng được
- Thiết kế hội thoại: phạm vi trả lời, câu hỏi ngoài phạm vi, giọng thương hiệu
- **Đường thoát cho con người:** khi nào bot phải dừng và chuyển cho nhân viên
- Đưa bot lên kênh thật: web widget · Facebook Messenger · Zalo OA · Slack nội bộ
- Tối ưu bằng dữ liệu: đọc log hội thoại, tìm câu bot trả sai, vá kho tri thức
- **Checkpoint 2 (15% điểm):** Chatbot chạy trên 1 kênh thật + trace + kết quả eval độ chính xác trên golden set

---

## MODULE 3 — TÍCH HỢP (Tuần 7–9 · Buổi 13–18)

> *Mục tiêu module: agent chạy trong hệ thống thật của tổ chức, không chỉ trong cửa sổ chat.*

### Buổi 13 — n8n: workflow tự động biết suy nghĩ
> Có video tiền học 40 phút về giao diện n8n để buổi live tập trung vào phần khó.
- Tư duy workflow: Trigger → Node → Điều kiện → Hành động; đọc JSON không cần biết code
- Kết nối tài khoản (credentials) an toàn; nối Gmail, Sheets, Slack, Calendar, Drive
- AI Agent node: chèn khả năng suy luận vào giữa workflow
- **Xử lý lỗi nghiêm túc:** retry, fallback, cảnh báo khi hỏng, tránh vòng lặp vô hạn
- **Lab:** Email/yêu cầu đến → AI phân loại → định tuyến → ghi log, có nhánh xử lý lỗi

### Buổi 14 — Agent chạy nền & chọn tầng điều phối ⭐
> *Buổi này chưa khoá nào ở Việt Nam dạy — và doanh nghiệp đã bắt đầu tuyển đúng bộ kỹ năng này.*
- **Chuyển dịch của ngành:** từ *process-centric* (vẽ flowchart) sang *goal-centric* (giao mục tiêu + đăng ký tool). Automation cũ không bị thay thế — nó bị bọc lại thành tool bên trong agent
- **OpenClaw:** agent mã nguồn mở chạy trên máy bạn — cài đặt, skills có sẵn, chạy theo lịch, nhớ ngữ cảnh giữa các phiên
- **Ranh giới an toàn khi agent chạy trên máy thật:** quyền truy cập file, thư mục cấm, thao tác cần xác nhận, tách máy làm việc và máy thử nghiệm
- **Khung quyết định tầng điều phối:** khi nào n8n, khi nào agent chạy nền, khi nào Zapier/Make/Power Automate — theo tần suất, độ phức tạp, ai bảo trì
- **Lab:** Cùng một công việc, dựng bằng n8n và bằng agent chạy nền — so chi phí, độ ổn định, công sức bảo trì

### Buổi 15 — MCP I: chuẩn kết nối agent với hệ thống ⭐
- Vấn đề trước MCP: mỗi tích hợp là một lần làm lại từ đầu
- MCP là gì, giải thích bằng ngôn ngữ đời thường; MCP vs. n8n — dùng cái nào khi nào
- Cài và dùng MCP server có sẵn: Notion · Slack · GitHub · Google Drive · Postgres · Filesystem
- **Lab:** Agent truy vấn trực tiếp Notion/Slack của bạn và tổng hợp báo cáo

### Buổi 16 — MCP II: nối vào hệ thống nội bộ & kiểm soát ⭐
- Kết nối database/API nội bộ: quy trình xin quyền và làm việc với IT
- **Phân quyền & bảo mật:** nguyên tắc quyền tối thiểu, chỉ-đọc vs. ghi, dữ liệu nhạy cảm & PII
- Tự tạo MCP server đơn giản cho hệ thống riêng — bằng Coding Agent, không tự viết code
- **Lab:** Dựng 1 MCP server cho nguồn dữ liệu của chính bạn

### Buổi 17 — Nhiều agent và điều phối
- Chia việc cho nhiều agent: khi nào có lợi, khi nào làm mọi thứ tệ hơn
- Mẫu điều phối: tuần tự · song song · agent điều phối + agent chuyên môn
- **Human-in-the-loop:** đặt cổng phê duyệt ở đâu để vừa nhanh vừa an toàn
- Chia sẻ vs. cô lập context giữa các agent
- **Lab:** Thiết kế sơ đồ hệ thống multi-agent cho quy trình liên phòng ban

### Buổi 18 — WORKSHOP 3 + CHECKPOINT
- Build tại lớp: **Workflow vận hành liên phòng ban** có ít nhất 1 kết nối MCP + 1 cổng phê duyệt
- **Checkpoint 3 (15% điểm):** Workflow chạy được + sơ đồ kiến trúc + bảng phân tích rủi ro

---

## MODULE 4 — SẢN XUẤT & CAPSTONE (Tuần 10–12 · Buổi 19–24)

> *Mục tiêu module: biến prototype thành thứ tổ chức dám dùng.*

### Buổi 19 — Evaluation II: đánh giá agent, không chỉ đánh giá câu trả lời ⭐⭐
- Khác biệt giữa đánh giá 1 câu trả lời và đánh giá 1 chuỗi hành động
- Bộ chỉ số vận hành: **tỉ lệ hoàn thành · độ chính xác · chi phí/lượt · độ trễ · tỉ lệ cần người can thiệp**
- **LLM-as-judge:** dùng AI chấm AI — cách làm và cách nó đánh lừa bạn
- Vì sao chạy 1 lần thấy đúng không có nghĩa là đúng: tính ngẫu nhiên và cỡ mẫu tối thiểu
- **Lab:** Chạy eval trên agent capstone của bạn, ra bảng chỉ số

### Buổi 20 — Vận hành & rủi ro
- Kiểm soát chi phí: ước tính token, đặt hạn mức, chọn model theo bài toán
- Giám sát: log, cảnh báo, phát hiện khi agent âm thầm hỏng
- **Prompt injection & rò rỉ dữ liệu:** cách tấn công thật, cách phòng thủ
- **Tuân thủ Luật Trí tuệ nhân tạo** (Luật số 134/2025/QH15, hiệu lực 01/3/2026): ba mức phân loại rủi ro; doanh nghiệp bạn là *nhà cung cấp*, *bên triển khai* hay *người sử dụng* — mỗi vai một nghĩa vụ khác nhau. Nghị định 142/2026/NĐ-CP hướng dẫn thi hành từ 01/5/2026
- Quyền riêng tư: dữ liệu nào không được đưa lên cloud, chính sách nội bộ
- **Giao nộp:** Checklist đưa agent vào vận hành, có mục tự phân loại rủi ro theo luật

### Buổi 21 — ROI & thuyết phục tổ chức
- Đo lường trước/sau: giờ tiết kiệm, tỉ lệ lỗi, thời gian xử lý
- Dựng business case: chi phí công cụ vs. giá trị tạo ra
- Lộ trình pilot → mở rộng: chọn phòng ban thí điểm, tiêu chí dừng
- Quản trị thay đổi: xử lý nỗi lo "AI thay thế tôi" trong đội
- **Lab:** Viết đề xuất 1 trang xin phê duyệt triển khai

### Buổi 22 — CAPSTONE LAB 1 (có mentor)
- Xây dựng có hướng dẫn 1-1; chốt phạm vi, gỡ vướng kỹ thuật

### Buổi 23 — CAPSTONE LAB 2 (có mentor)
- Chạy eval, sửa theo kết quả đo, đóng gói tài liệu & portfolio

### Buổi 24 — DEMO DAY & TỐT NGHIỆP
- Trình bày 8 phút + phản biện 5 phút trước hội đồng (giảng viên + khách mời doanh nghiệp)
- Trao chứng nhận · công bố portfolio · định hướng lộ trình tiếp theo

---

## 4. THƯ VIỆN CASE STUDY

Mỗi buổi học gắn với case công việc thật. Học viên chọn case gần nhất với vai trò của mình; chương trình cấp sẵn dữ liệu mẫu, template và lời giải tham khảo cho toàn bộ 19 case dưới đây.

### Marketing & Content

| # | Case | Kết quả cụ thể | Học ở buổi |
|---|---|---|---|
| 1 | **Content Engine đa kênh** | 1 brief → 10 bài Facebook/LinkedIn/TikTok đúng brand voice, không phải viết lại từ đầu | 3, 4, 6 |
| 2 | **Radar đối thủ** | Sáng thứ Hai tự có báo cáo giá & campaign đối thủ gửi vào Slack | 8, 14 |
| 3 | **Máy đọc review khách hàng** | 500 comment/review → bảng insight phân nhóm theo chủ đề và cảm xúc | 9 |
| 4 | **SEO brief tự động** | Từ keyword → outline + brief giao cho writer, theo đúng chuẩn nội bộ | 4, 10 |

### Sales & CRM

| # | Case | Kết quả cụ thể | Học ở buổi |
|---|---|---|---|
| 5 | **Chấm điểm lead inbound** | Form/email đến → chấm điểm → định tuyến đúng sale, ghi thẳng vào CRM | 14, 15 |
| 6 | **Email follow-up cá nhân hoá** | Từ lịch sử hội thoại sinh email đúng giai đoạn của deal | 3, 8 |
| 7 | **Cuộc gọi → CRM** | Recording → tóm tắt → hành động tiếp theo → cập nhật deal, không gõ tay | 10, 15 |

### Operations & Admin

| # | Case | Kết quả cụ thể | Học ở buổi |
|---|---|---|---|
| 8 | **Xử lý chứng từ** | Ảnh/PDF hoá đơn → trích xuất số liệu → Sheets → cổng duyệt của kế toán | 9, 14, 17 |
| 9 | **Trợ lý họp** | Biên bản → tách đầu việc → giao người → nhắc deadline qua Slack | 14, 15 |
| 10 | **Báo cáo tuần liên phòng ban** | Gom số liệu từ nhiều nguồn thành một báo cáo chuẩn, không cần đi xin từng nơi | 15, 18 |
| 11 | **Trực ca yêu cầu nội bộ** | Yêu cầu nội bộ → phân loại → định tuyến → theo dõi tồn đọng | 14, 18 |

### Nhân sự

| # | Case | Kết quả cụ thể | Học ở buổi |
|---|---|---|---|
| 12 | **Sàng lọc CV** | CV đối chiếu JD → xếp hạng có lý do + sinh bộ câu hỏi phỏng vấn riêng cho từng ứng viên | 9, 11 |
| 13 | **Chatbot chính sách nhân sự** | Nhân viên tự hỏi về nghỉ phép, bảo hiểm, quy trình — HR không phải trả lời lặp lại | 11, 12 |

### Tài chính

| # | Case | Kết quả cụ thể | Học ở buổi |
|---|---|---|---|
| 14 | **Đối soát hai nguồn số liệu** | Tìm sai lệch giữa hai bảng và giải thích nguyên nhân từng dòng | 9, 10 |
| 15 | **Cảnh báo chi phí bất thường** | Dashboard chi phí + tự động báo động khi vượt ngưỡng | 9, 14 |

### Chăm sóc khách hàng

| # | Case | Kết quả cụ thể | Học ở buổi |
|---|---|---|---|
| 16 | **Chatbot hỗ trợ khách 24/7** | Trả lời trên tài liệu sản phẩm thật, biết chuyển người khi gặp câu khó | 11, 12 |
| 17 | **Trợ lý cho nhân viên CSKH** | Gợi ý câu trả lời và tra cứu chính sách ngay trong lúc đang chat với khách | 12, 15 |

### Founder & Điều hành

| # | Case | Kết quả cụ thể | Học ở buổi |
|---|---|---|---|
| 18 | **Nghiên cứu thị trường → bộ slide** | Từ một câu hỏi kinh doanh đến deck trình bày có trích dẫn nguồn | 8 |
| 19 | **Daily briefing** | Mỗi sáng có bản tóm tắt số liệu kinh doanh + tin ngành trong hộp thư | 8, 14 |

> **Cách dùng:** Buổi 0 học viên chọn 1 case làm hướng capstone. Các case còn lại đi kèm lời giải mẫu để tự làm lại sau khoá.

---

## 5. CAPSTONE PROJECT

Học viên chọn 1 quy trình công việc thật của mình (đã nộp ở Buổi 0) và xây thành hệ thống agent hoàn chỉnh.

**Bắt buộc có 5 thành phần:**

| # | Thành phần | Yêu cầu |
|---|---|---|
| 1 | **Agent chạy được** | Xử lý được quy trình thật, không phải dữ liệu giả |
| 2 | **Context được thiết kế** | System prompt, tài liệu, skill được cấu trúc có chủ đích |
| 3 | **Tích hợp thật** | Tối thiểu 1 kết nối MCP hoặc n8n vào hệ thống đang dùng |
| 4 | **Bộ đánh giá** | Golden set ≥ 20 case + bảng chỉ số vận hành |
| 5 | **Hồ sơ ROI** | Đo trước/sau + đề xuất triển khai 1 trang |

**Tiêu chí chấm (100 điểm):** Mức độ giải quyết vấn đề thật (25) · Chất lượng context engineering (20) · Độ chặt chẽ của eval (20) · Độ sâu tích hợp (15) · Xử lý rủi ro & vận hành (10) · Trình bày (10)

---

## 6. ĐÁNH GIÁ & ĐIỀU KIỆN TỐT NGHIỆP

| Hạng mục | Trọng số |
|---|---|
| Bài tập theo buổi (12 bài) | 20% |
| Checkpoint 1 — Trợ lý AI + Eval Set | 10% |
| Checkpoint 2 — AI Chatbot trên kho tri thức | 15% |
| Checkpoint 3 — Workflow tích hợp | 15% |
| Capstone Project | 30% |
| Demo Day & phản biện | 10% |

**Điều kiện tốt nghiệp:** Tham dự ≥ 80% số buổi · Hoàn thành cả 3 checkpoint · Capstone ≥ 60/100 điểm.

---

## 7. CÔNG CỤ SỬ DỤNG

| Nhóm | Công cụ |
|---|---|
| Mô hình & trợ lý | Claude · ChatGPT · Gemini |
| Coding Agent | Claude Code · Cursor |
| Agent chạy nền | OpenClaw (mã nguồn mở, chạy local) |
| Automation | n8n · Google Apps Script (do agent sinh) |
| Chatbot & kênh | Dify / Botpress · Web widget · Facebook Messenger · Zalo OA · Slack |
| Trình bày | Gamma · Google Slides (sinh tự động qua script) |
| Tích hợp | MCP servers: Notion, Slack, GitHub, Google Drive, Postgres, Filesystem |
| Dữ liệu | Google Sheets · Google Colab · Excel |
| Kho tri thức | Claude Projects · Custom GPTs · vector store no-code |
| Đánh giá | Bộ template eval của chương trình (Sheets) + LLM-as-judge |

*Chương trình cấp trước toàn bộ template: Prompt Library, Eval Template, Workflow Template, Production Checklist, ROI Calculator.*

---

## 8. HỌC VIÊN NHẬN ĐƯỢC

- Recording trọn đời toàn bộ 24 buổi
- Bộ template & tài liệu (Prompt Library · Eval Kit · Workflow Templates · Checklists)
- Mentoring 1-1 giai đoạn capstone
- Chứng nhận hoàn thành + portfolio sản phẩm công khai được
- Cộng đồng học viên & alumni; cập nhật nội dung khi công nghệ thay đổi
- Quyền học lại miễn phí 1 khoá kế tiếp

---

## 9. ĐỊNH VỊ & KHÁC BIỆT *(ghi chú nội bộ)*

### 9.1 Phủ đủ 6 buổi của đối thủ

Nguyên tắc: **không bỏ sót buổi nào của đối thủ**, và mỗi buổi đều được dạy sâu hơn.

| Buổi của đối thủ | Nội dung họ dạy | AI Builder dạy ở buổi | Mình bổ sung gì |
|---|---|---|---|
| 1 · Trợ lý AI cá nhân | Prompt Engineering, AI Agent, tự động tìm kiếm | **1, 2, 3, 4, 6** | Context Engineering 2 buổi + eval set để đo chất lượng trợ lý |
| 2 · Agent phân tích dữ liệu | Phân tích, làm sạch, trực quan hoá | **9** | Quy tắc chống ảo giác số; biết khi nào không được tin agent |
| 3 · AI Research Agent | Thu thập đa nguồn, tạo slide | **8** | Kiểm chứng chéo nguồn, phát hiện nguồn rác, đọc trace |
| 4 · Workflow AI tự động | n8n, API, Google Forms/Sheets | **13** | Retry, fallback, cảnh báo khi hỏng — thứ quyết định workflow sống được; thêm buổi 14 về agent chạy nền là phần họ không có |
| 5 · Hệ thống vận hành | Đồng bộ dữ liệu, thông báo tự động | **15, 17, 18** | MCP thay cho tích hợp thủ công + cổng phê duyệt của con người |
| 6 · AI Chatbot | Xây, nối dữ liệu, tối ưu | **11, 12** | RAG trên tài liệu thật, đường thoát cho người, eval độ chính xác |

Sáu buổi của đối thủ nằm gọn trong 13 buổi đầu. Mười một buổi còn lại là phần đối thủ không có.

### 9.2 So sánh tổng thể

| Tiêu chí | Đối thủ (6 buổi) | AI Builder (24 buổi) |
|---|---|---|
| Thời lượng | 12h | 60h live + 40h lab |
| Prompt & công cụ AI | Có | Có |
| n8n automation | Có | Có (sâu hơn: xử lý lỗi, giám sát) |
| **Agent chạy nền (OpenClaw) & chọn tầng điều phối** | Không | 1 buổi |
| **Tuân thủ Luật TTNT 134/2025/QH15** | Không | Có, trong buổi 20 |
| **Context Engineering** | Không | 2 buổi chuyên sâu |
| **Evaluation / đo chất lượng** | Không | 2 buổi + xuyên suốt mọi checkpoint |
| **MCP & tích hợp hệ thống nội bộ** | Không | 2 buổi |
| AI Chatbot | Có | Có — thêm RAG, đường thoát cho người, eval |
| Research Agent → slide | Có | Có — thêm kiểm chứng nguồn |
| **Thư viện case theo vai trò** | Không | 19 case có dữ liệu mẫu & lời giải |
| **Coding Agent (tool tạo tool)** | Không | 1 buổi |
| Vận hành, bảo mật, prompt injection | Không | 1 buổi |
| ROI & business case | Không | 1 buổi |
| Capstone có mentor + Demo Day | Không | 3 buổi |

**Thông điệp định vị:** *"Khoá 6 buổi dạy bạn làm cho AI chạy được một lần. Khoá này dạy bạn xây hệ thống AI mà công ty bạn dám dùng thật — và bạn chứng minh được nó đúng bao nhiêu phần trăm."*

**Gợi ý khung giá:** với thời lượng gấp 4–5 lần và có mentoring 1-1, vùng giá hợp lý là **15,9 – 19,9 triệu đồng**, Early Bird 12,9 – 14,9 triệu. Cần khảo sát khả năng chi trả của nhóm non-tech trước khi chốt — đây là rủi ro lớn nhất của định vị này.

---

## 10. PHƯƠNG ÁN RÚT GỌN 10 TUẦN (20 buổi)

Nếu cần khớp mốc 2,5 tháng: giữ nguyên 4 module, cắt 4 buổi như sau — gộp Buổi 3+4 (Context Engineering) thành 1 buổi, gộp Buổi 9 (Data Agent) vào Buổi 8, chuyển Buổi 17 (Multi-agent) thành tài liệu tự học, gộp Buổi 22+23 (Capstone Lab) thành 1 buổi. **Không cắt Evaluation, MCP và Buổi 14 (agent chạy nền)** — đó là ba phần tạo khác biệt.

---

*Nguồn tham chiếu: Note.docx — khung chương trình đối thủ (tomorrowmarketers.org/generative-ai) và bộ kiến thức nền (github.com/bojieli/ai-agent-book).*
