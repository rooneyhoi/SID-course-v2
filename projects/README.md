# SID Projects  
> Từ khai thác tri thức → xây sản phẩm & hệ thống thật

Thư mục `projects/` chứa **4 project thực tế**, dùng để nối từ **SID Core** (8 buổi) sang **Expert Builder Track**.

Mỗi project:

- Dùng lại artifact SID (Framing Brief, IA Pack, Framework, Workflow, Validation…).  
- Có:
  - **Bài toán & bối cảnh** (đặt vấn đề thật),
  - **Yêu cầu chất lượng / tính đúng đắn**,
  - **Yêu cầu & Output cụ thể**,
  - **Phần Thực thi**: hướng dẫn step-by-step + 1 “bài giải mẫu khung” để người học có thể hình dung thực tế và copy pattern.

Đây **không phải** bài tập chơi, mà là các đề bài để:

- xây **Gem / Custom GPT / Book / Tutor** thật,
- trên nền kiến trúc tư duy & kỹ thuật SID.

---

## 0. Yêu cầu nền tảng trước khi vào projects

Trước khi làm bất kỳ project nào, học viên nên đã:

- Hoàn thành **SID Core (8 buổi)** trên **ít nhất 1 domain** thật.  
- Có các artifact cơ bản:
  - Framing Brief,
  - Prompt Stack V1,
  - Decomposition Tree + Functional/Stakeholder map,
  - IA Pack (taxonomy, hierarchy, bảng/matrix),
  - Research Path v1,
  - Reasoning Pack,
  - Validation Report,
  - Framework + Workflow + Asset + Rubric.

Những project này **không dạy lại** SID Core;  
chúng buộc bạn **dùng những gì đã có**.

---

## 1. Project 1 — Gem chuyên gia cây ăn quả

### Tài liệu liên quan
- [SID-project-audit.md](SID-project-audit.md)
- [SID-implementation-note.md](SID-implementation-note.md)
- [SID-prompt-system-architecture.md](SID-prompt-system-architecture.md)
- [SID-techniques-project-mapping.md](SID-techniques-project-mapping.md)


**File:** `01-domain-gem-fruit-trees.md` (tên gợi ý)

### Bài toán & bối cảnh

Thiết kế 1 **Gem/assistant chuyên gia cây ăn quả**, có thể:

- Tư vấn cho:
  - nông dân,  
  - nhà vườn,  
  - người chơi cây ăn quả,
- Về:
  - giống, đất, nước, phân bón, sâu bệnh, mùa vụ, tỉa cành, thu hoạch,…

Mục tiêu:

- Dùng SID để xây **1 expert assistant domain-specific**, ở domain **kỹ thuật nhưng an toàn** (ít ethical risk nặng).

### Yêu cầu chất lượng

- **Scope rõ ràng**:  
  - chỉ về cây ăn quả (cam, bưởi, xoài, sầu riêng,…), không trôi sang mảng y tế, tài chính, phong thủy…
- **Tri thức đúng hướng**:
  - không phóng đại, không bịa “thuốc thần”,
  - nhấn mạnh giới hạn: điều kiện vùng miền, giống, khí hậu.
- **Hành vi tư vấn**:
  - luôn hỏi lại về:
    - điều kiện địa phương,
    - giống cụ thể,
    - mục tiêu (ăn gia đình / thương mại),
  - cảnh báo khi đề xuất dùng thuốc/hóa chất.
- **Output có cấu trúc**:
  - checklist, quy trình chăm sóc, bảng so sánh giống, kế hoạch mùa vụ.

### Output project

1. **Gem Spec** đầy đủ cho “Fruit Tree Expert”, gồm:
   - Mission & Audience,
   - Scope & boundaries,
   - Core behaviors (theo framework/ workflow),
   - Internal prompt stack logic,
   - Input/Output formats,
   - 3–5 đoạn hội thoại mẫu,
   - Failure modes & guardrails.

2. (Tuỳ chọn) 1 bản setup thử trong Gemini/GPT (nếu học viên có điều kiện).

---

## 2. Project 2 — Custom GPT: Content Engine cho video chủ đề gia đình / tài chính

**File:** `02-custom-gpt-content-engine.md`

### Bài toán & bối cảnh

Thiết kế 1 **Custom GPT** chuyên làm:

- **Content engine** cho video:
  - chủ đề **gia đình** (cha mẹ, hôn nhân, nuôi dạy con,…),  
  - hoặc chủ đề **tài chính cá nhân/cơ bản** (quản lý chi tiêu, tiết kiệm, tư duy tiền,…).

Nó không chỉ “viết script”, mà:

- giúp chủ kênh:
  - lên chủ đề,
  - thiết kế series,
  - outline tập,
  - key message,
  - call-to-action,
  - gợi ý visual/shot.

### Yêu cầu chất lượng

- **Tone & values rõ**:
  - không sensational, không giật gân,
  - không cho lời khuyên tài chính vượt scope (“mua mã này, bán mã kia”…),
  - bám giá trị: trách nhiệm, bền vững, tôn trọng người xem.

- **IA content rõ**:
  - biết phân tầng nội dung:
    - top-of-funnel, mid, deep dive,
    - trình độ người xem,
  - biết cấu trúc 1 tập video:
    - hook → core → example → recap → CTA.

- **Workflow content**:
  - từ **idea bank** → **series** → **episode outline** → **script gợi ý**.

### Output project

1. **Spec cho Custom GPT Content Engine**:
   - System instructions (mission, boundaries, tone, values),
   - Supported workflows (ideation, series design, episode outline, script skeleton),
   - Input/Output schemas (vd: bảng lịch đăng video, outline, script format),
   - 3–5 scenario mẫu (user prompt → GPT output),
   - Safety & ethics rules (đặc biệt với tiền/bạo lực gia đình/khủng hoảng…).

2. (Tuỳ chọn) 1 pipeline mini:
   - ví dụ 1 series 5 video, mỗi video có outline sinh ra từ GPT.

---

## 3. Project 3 — Deep Research & Book Design (5–8 chương, 150–200 trang)

**File:** `03-book-design-deep-research.md`

### Bài toán & bối cảnh

Dùng SID để:

- Nghiên cứu **sâu** 1 chủ đề chuyên ngành (theo nghề/nghiên cứu của học viên),
- Thiết kế 1 **cuốn sách phi hư cấu** (non-fiction / chuyên ngành), khoảng:
  - **5–8 chương**,
  - **150–200 trang** (tương đương 40k–60k từ, tùy layout).

Mục tiêu:

- Biến **SID pipeline** thành:
  - **book architecture pipeline**:
    - từ framing, decomposition, IA, reasoning, validation →  
    - tới: cấu trúc sách, outline chương, mạch lập luận, workflow viết.

### Yêu cầu chất lượng

- **Framing sách rõ**:
  - Độc giả mục tiêu (reader persona),
  - Mục tiêu đọc xong làm được gì / hiểu được gì,
  - Scope (in/out).

- **Kiến trúc sách logic**:
  - 5–8 chương, mỗi chương có:
    - vai trò rõ trong mạch tổng,
    - decomposition nội bộ (sections/sub-sections),
  - mạch đi từ:
    - nền → khung → case → ứng dụng → nâng cao/tương lai.

- **Reasoning & Validation được nhúng vào**:
  - mỗi chương thể hiện:
    - CoT/ToT/hypothesis/causal/comparative trong cách trình bày,
    - phần “cảnh báo”, “giới hạn”, “góc tranh luận”.

- **Kế hoạch viết thực tế**:
  - lộ trình 3–6 tháng,
  - cách dùng AI:
    - research co-pilot,
    - outline assistant,
    - style checker,
  - điểm cần con người làm (validation, trải nghiệm, ví dụ).

### Output project

1. **Book Architecture Document**:
   - Framing sách,
   - Reader persona,
   - Mạch 5–8 chương (tên chương + 1–2 câu mô tả),
   - Outline chi tiết từng chương (sections),
   - IA (bản đồ khái niệm toàn sách).

2. **Sample content**:
   - 1 chương (hoặc 1 phần lớn của chương) được:
     - thiết kế bằng SID,
     - draft với AI,
     - validate lại theo Buổi 7.

3. **Writing Workflow**:
   - mô tả cách tác giả sẽ:
     - dùng AI trong từng giai đoạn (research, outline, draft, revise),
     - kiểm định & chỉnh sửa,
     - loop feedback (beta readers, expert review).

---

## 4. Project 4 — AI Tutor về tâm lý trẻ em

**File:** `04-ai-tutor-child-psychology.md`

*(Project này sẽ chi tiết hơn sau khi bạn cung cấp ví dụ master instruction; dưới đây là khung)*

### Bài toán & bối cảnh

Thiết kế 1 **AI Tutor** (hoặc Gem/Custom GPT) trong domain **tâm lý trẻ em**, có khả năng:

- Hỗ trợ phụ huynh/giáo viên:
  - hiểu phản ứng, cảm xúc, hành vi của trẻ,
  - tìm hướng **giao tiếp & giáo dục phù hợp**,
- Nhưng:
  - **không** đóng vai trò nhà trị liệu,
  - **không** đưa ra chẩn đoán lâm sàng,
  - biết **khi nào phải dừng và hướng người dùng tới chuyên gia/hotline**.

### Yêu cầu chất lượng

- **Master instruction rất sắc**:
  - giới hạn năng lực,
  - domain boundaries,
  - tránh overshoot (tự xem mình là chuyên gia lâm sàng).

- **Rules & checkpoint**:
  - nhận diện “red flags” (bạo lực, tự hại, lạm dụng, khủng hoảng),
  - định sẵn:
    - khi gặp red flag → không tiếp tục hướng dẫn chi tiết → đưa message chuẩn, khuyến nghị liên hệ chuyên gia/cơ quan chức năng.

- **Sư phạm & empathy**:
  - ngôn ngữ mềm, không phán xét,
  - biết hỏi lại nhiều để hiểu bối cảnh,
  - tránh gắn nhãn trẻ.

- **Epistemic humility**:
  - luôn ghi rõ:
    - đây không phải lời khuyên y khoa/clinical,
    - phạm vi hỗ trợ là hướng dẫn giao tiếp/giáo dục chung.

### Output project

1. **Tutor Spec**:
   - Master instruction,
   - Rules + red-flag detection logic,
   - Checkpoints & escalation flows,
   - Persona & tone,
   - Supported tasks (VD: phân tích tình huống, gợi ý cách trò chuyện, đề xuất hoạt động, hỗ trợ phản tư…),
   - Input/Output format (câu chuyện tình huống, phản hồi).

2. **Dialogue samples**:
   - 3–5 hội thoại, trong đó có:
     - 1–2 case bình thường,
     - 1 case red-flag (thể hiện cách Tutor dừng & escalate).

3. **Safety & ethics notes**:
   - phân tích các risk mode,
   - cách giảm thiểu.

*(Khi bạn gửi ví dụ master instruction thật, file này sẽ được “fill” chi tiết.)*

---

## 5. Cách dùng folder `projects/` trong chương trình

- Sau khi học xong **SID Core**:
  - học viên **chọn 1–2 project** trong `projects/` để làm.
- Với từng project:
  - đọc file `.md` tương ứng:
    - hiểu **bài toán, yêu cầu, output**,
    - follow phần **Thực thi**,
    - so sánh với **giải mẫu khung** để calibrate.
- Với level nâng cao:
  - hoàn thành **ít nhất 2 project**:
    - 1 project “an toàn” (P1 hoặc P3),
    - 1 project “nhạy cảm” (P2 hoặc P4).

---
