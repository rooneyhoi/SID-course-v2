# Prompt System Architecture

Tài liệu này giúp bạn chuyển từ 1 master prompt dài, rối sang một hệ thống prompt có cấu trúc hơn, dễ bảo trì và dễ mở rộng.

> Phiên bản này đã được gộp và rút gọn để tập trung vào nguyên tắc chính, thay vì lặp lại nhiều chi tiết triển khai.

---

## 1. Mục tiêu

Một prompt system tốt nên giúp assistant:
- hiểu đúng audience và scope,
- xử lý workflow theo phase,
- tự kiểm tra trước khi trả lời,
- dễ mở rộng khi project lớn hơn.

---

## 2. Cấu trúc tối thiểu nên có

### Mức 1 — Single-file MVP
Dùng cho project nhỏ:
- 1 master instruction,
- 1 output format chuẩn,
- 3–5 test prompts.

### Mức 2 — Multi-file Prompt System
Dùng cho project trung bình và lớn:
- rules.md — mission, audience, scope, safety, epistemic rules,
- flow-main.md — các flow chính,
- stacks/frame.md — framing prompt,
- stacks/structure.md — structuring prompt,
- stacks/reason.md — reasoning prompt,
- stacks/validate.md — validation prompt,
- stacks/synthesize.md — synthesis prompt,
- checkpoint.md — checklist trước khi output.

### Mức 3 — Multi-file + Knowledge Architecture
Dùng cho project chuyên sâu:
- thêm taxonomy.md,
- facets.md,
- knowledge module phân theo chủ đề/chương.

---

## 3. Mapping với SID

| File / module | Vai trò | Liên hệ với SID |
|---|---|---|
| rules.md | Định nghĩa mission, audience, scope, safety | Buổi 1, 7, 8 |
| flow-main.md | Mô tả flow chính của hệ thống | Buổi 2, 5, 8 |
| stacks/frame.md | Hỏi lại context và tóm tắt bối cảnh | Buổi 1–2 |
| stacks/structure.md | Tổ chức information architecture | Buổi 3–4 |
| stacks/reason.md | Phân tích giả thuyết và reasoning | Buổi 6 |
| stacks/validate.md | Kiểm tra assumptions, gaps, contradictions | Buổi 7 |
| stacks/synthesize.md | Tổng hợp thành framework/workflow/lesson | Buổi 8 |
| checkpoint.md | Chốt kiểm trước khi output | Buổi 7 |

---

## 4. Nguyên tắc thiết kế

Khi thiết kế prompt system, hãy trả lời 5 câu hỏi sau:

1. Rules — AI này làm gì, phục vụ ai, không làm gì?
2. Flows — Assistant phải đi qua những phase nào?
3. Stacks — Mỗi phase dùng prompt nào để làm việc tốt nhất?
4. Checkpoints — Trước khi trả lời, hệ thống có tự kiểm tra gì không?
5. Knowledge — Domain có cần được cấu trúc thành taxonomy, chapter, module không?

---

## 5. Template cốt lõi

```text
You are [Assistant Name], helping [audience] with [domain/problem].

Mission:
- Help users with [core task].

Audience:
- [Who they are and what level they are at].

In scope:
- [What the assistant can do].

Out of scope:
- [What it must not do].

Rules:
- Always ask for enough context before giving a strong recommendation.
- Separate facts, interpretations, assumptions, and recommendations.
- Mark confidence when important conclusions are uncertain.
- Use a clear structure: summary, analysis, action plan, safety note.
```

---

## 6. Khuyến nghị thực hành

- Không bắt buộc mọi project đều dùng full architecture.
- Với project nhỏ, nên bắt đầu từ single-file master instruction trước.
- Với project lớn hoặc nhạy cảm, mới chuyển sang multi-file system.
- Luôn giữ một checkpoint và một evaluation rubric để biết hệ thống có thực sự tốt hay không.
     - Bối cảnh, ràng buộc chính (thời gian, tài nguyên, domain)?
  3. Tóm tắt lại bối cảnh & mục tiêu (Framing Summary).
  4. Nếu thiếu thông tin quan trọng (theo RULES), liệt kê câu hỏi cần hỏi thêm.

```

#### Prompt ví dụ (dùng trong chat)

```text
Bạn đang hoạt động theo RULES đã được thiết lập.

Hãy chỉ thực hiện PHASE FRAME cho tình huống sau:

[NGƯỜI DÙNG MÔ TẢ YÊU CẦU/CASE Ở ĐÂY]

Yêu cầu:
1. Hỏi lại để làm rõ:
   - mục tiêu thực sự của người dùng,
   - audience/bối cảnh,
   - input/triệu chứng hiện có.
2. Tạo Framing Summary 3–7 bullet.
3. Nếu thấy thiếu thông tin quan trọng (theo RULES), liệt kê 3–5 câu hỏi bổ sung.

Không phân tích nguyên nhân, không đưa lời khuyên ở bước này.

```

### 5.4. `stacks/structure.md` — phase Structuring / IA

```markdown
# STACK: STRUCTURE

> Stack này:
> - Tuân thủ RULES (rules.md),
> - Được gọi sau khi FRAME đã tạo Framing Summary,
> - Tổ chức thông tin theo IA (outline, bảng, matrix) đã thiết kế trong IA Pack.

## Mục tiêu
- Chuyển thông tin rời rạc thành 1 cấu trúc dễ hiểu, dễ dùng:
  - outline multi-level,
  - bảng so sánh,
  - matrix, v.v.

## Pattern
- Nhận:
  - Framing Summary,
  - nguyên liệu thô (mô tả, dữ kiện).
- Trả:
  - cấu trúc IA phù hợp (đã định nghĩa trong domain).
```

#### Prompt ví dụ

```text
Dựa trên Framing Summary sau:

[FRAMING SUMMARY]

Hãy tổ chức lại thông tin theo cấu trúc chuẩn cho domain này
(ví dụ: outline 3 tầng / bảng / matrix), tuân thủ các RULES.

Yêu cầu:
1. Phân nhóm thông tin theo các mục chính trong IA Pack (vd: Cây & giống / Đất & nước / Dinh dưỡng / ...).
2. Chỉ ra các chỗ đang thiếu dữ liệu (gap) ở level thông tin, không phán đoán thêm.

Chưa phân tích nguyên nhân, chỉ cấu trúc & rà thiếu.
```


### 5.5. `stacks/reason.md` — phase Reasoning

```markdown
# STACK: REASON

> Stack này:
> - Tuân thủ RULES (rules.md),
> - Được gọi sau khi FRAME & STRUCTURE hoàn tất,
> - Dựa trên Reasoning Pack (Buổi 6) để phân tích.

## Mục tiêu
- Phân tích bài toán theo:
  - Chain of Thought,
  - Tree of Thought,
  - Hypothesis-driven,
  - Causal,
  - Comparative (tùy bài toán).

## Pattern
- Nhận:
  - Framing Summary,
  - cấu trúc IA (bảng/outline).
- Trích áp dụng:
  - CoT nếu bài toán tuyến tính,
  - ToT nếu bài toán mở (3+ nhánh),
  - Hypothesis/Causal nếu cần giải thích “vì sao”.
- Tách lớp:
  - fact vs interpretation vs assumption vs hypothesis vs recommendation.
```

#### Prompt ví dụ

```text
Bạn đang hoạt động theo RULES và flow chính.

Dựa trên:
- Framing Summary: [DÁN],
- Cấu trúc thông tin: [DÁN],

Hãy phân tích vấn đề theo Reasoning Pack sau:
- Nếu đây là bài toán [giải thích/tư vấn/chọn lựa], hãy chọn kỹ thuật phù hợp (CoT/ToT/Hypothesis/Causal/Comparative).

Yêu cầu:
1. Liệt kê 2–5 giả thuyết hoặc hướng tiếp cận chính.
2. Với mỗi giả thuyết:
   - giải thích tại sao có thể đúng (CoT),
   - nêu điều gì có thể phản bác,
   - gợi ý dữ kiện kiểm chứng,
   - gắn nhãn confidence (cao/trung bình/thấp).
3. Phân biệt đâu là fact (từ user), đâu là inference, đâu là giả thuyết.

Chưa cần chốt khuyến nghị cuối cùng.
```


### 5.6. `stacks/validate.md` — phase Validation

```markdown
# STACK: VALIDATE

> Stack này:
> - Tuân thủ RULES (rules.md),
> - Dựa trên Validation Pack (Buổi 7),
> - Được gọi sau khi Reasoning có bản nháp kết luận.

## Mục tiêu
- Kiểm định bản nháp câu trả lời/khung phân tích:
  - Dán nhãn F/I/A/H/R,
  - Tìm assumption, gaps, contradictions,
  - Gắn confidence.

## Pattern

- Nhận:
  - Bản nháp kết luận/analysis.
- Thực hiện:
  - Epistemic labeling,
  - Self-critique,
  - Assumption check,
  - Gap detection.
```

#### Prompt ví dụ

```text
Dưới đây là bản nháp phân tích/kết luận:

[PASTE ANSWER DRAFT]

Hãy kiểm định nó theo các RULES và nguyên tắc validation:

1. Tách các mệnh đề chính và gắn nhãn:
   - F (fact), I (interpretation), A (assumption), H (hypothesis), R (recommendation).
2. Liệt kê tối thiểu 3 assumption quan trọng + rủi ro nếu chúng sai.
3. Chỉ ra ít nhất 2 gap (khía cạnh quan trọng bị thiếu).
4. Nếu có phần nào mâu thuẫn với chính nội dung trước đó, đánh dấu & mô tả.

Không cần viết lại câu trả lời; chỉ tập trung vào validation.
```


### 5.7. `stacks/synthesize.md` — phase Synthesize & Transfer

```markdown
# STACK: SYNTHESIZE

> Stack này:
> - Tuân thủ RULES (rules.md),
> - Dựa trên pattern & framework (Buổi 8),
> - Được gọi sau khi reasoning & validation cơ bản hoàn tất.

## Mục tiêu
- Đóng gói tri thức thành:
  - framework,
  - checklist,
  - workflow,
  - lesson/module,
  - decision model.

## Pattern
- Nhận:
  - các điểm/insight đã qua reasoning & validation.
- Sinh:
  - 1 framework rõ bước,
  - 1 plan/workflow,
  - 1 asset dạy/áp dụng.

```
#### Prompt ví dụ

```text
Dựa trên các insight đã qua reasoning & validation:

[INSIGHTS / KẾT LUẬN]

Hãy tổng hợp thành output có thể DÙNG ĐƯỢC NGAY cho [AUDIENCE] theo framework đã định:

Yêu cầu:
1. Tạo 1 framework 5–7 bước (tên + mục tiêu + input + output + lỗi phổ biến).
2. Tạo 1 workflow áp dụng framework này (bước → hành động → checkpoint).
3. (Nếu phù hợp) tạo 1 checklist/mini-lesson hoặc outline 1 buổi dạy.

Trả lời theo format rõ ràng (heading, bullet).
```


### 5.8. `checkpoint.md` — self-check & red-flag

```markdown
# CHECKPOINT

> Module này:
> - Được gọi sau khi assistant đã tạo bản nháp câu trả lời cuối (sau Synthesize),
> - Dùng để tự kiểm định theo RULES trước khi gửi cho user.

## Checklist trước khi trả lời

1. Gán nhãn confidence:
   - Xác định các kết luận chính,
   - Gắn nhãn high/medium/low confidence,
   - Có giải thích ngắn.

2. Assumption:
   - Liệt kê tối thiểu 3 assumption quan trọng,
   - Ghi rủi ro nếu mỗi assumption sai.

3. Gaps:
   - Nêu ít nhất 2 gap (khía cạnh/đối tượng chưa xét).

4. Red-flag:
   - Nếu nội dung chạm:
     - đầu tư lớn,
     - sức khoẻ,
     - tâm lý nặng, bạo lực, lạm dụng,
   - Kiểm tra:
     - có vượt out-of-scope theo RULES không?
     - có cần khuyến nghị gặp chuyên gia/hotline không?

5. Sửa:
   - Nếu thấy câu trả lời vi phạm RULES hoặc quá tự tin:
     - giảm độ mạnh khuyến nghị,
     - thêm caveat & hướng dẫn kiểm chứng.
```
#### Prompt ví dụ

```text
Hãy xem lại câu trả lời draft bạn vừa tạo theo RULES và CHECKPOINT:

1. Liệt kê các kết luận chính và gắn nhãn high/medium/low confidence.
2. Chỉ ra 3 assumption quan trọng và rủi ro nếu sai.
3. Nêu ít nhất 2 gap.
4. Nếu có chủ đề high-risk, hãy sửa câu trả lời để:
   - giảm độ mạnh khuyến nghị,
   - thêm gợi ý tìm chuyên gia hoặc nguồn uy tín,
   - không đưa hướng dẫn chi tiết gây hại.

Sau đó, viết lại phiên bản đã được hiệu chỉnh.
```


---

## 6. Nâng cao: Taxonomy, Facets, Knowledge

Khi assistant phức tạp hoặc liên quan tới sách/khóa học, bạn có thể thêm:

### 6.1. `taxonomy.md`

```markdown
# TAXONOMY

## Task Types
- Explain
- Compare
- Diagnose
- Design
- Critique
- Teach

## Content Types
- Concept/module
- Case study
- Workflow
- Checklist
- Lesson/chapter

## Mapping Task → Stack/Flow
- Explain → Frame + Structure + Reason (CoT)
- Diagnose → Frame + Structure + Reason (Hypothesis/Causal) + Validate
- Design → Frame + Explore + Synthesize
...
```

### 6.2. `facets.md`

```markdown
# FACETS

## Facets dùng để phân tích
- Technical
- User/Human
- Organizational/Operational
- Educational/Learning
- Ethical/Epistemic

## Hướng dẫn:
- Khi phân tích một chủ đề/phương án, cố gắng đề cập ít nhất 3 facet.
- Đối với chủ đề nhạy cảm, luôn có facet Ethical/Epistemic.
```

### 6.3. `knowledge/*.md`

- `domain-map.md`: bản đồ tri thức (Decomposition Tree + IA Pack).  
- `chapter-*.md`: outline, key ideas, pattern cho từng chương (trong book/tutor).  
- `topic-*.md`: note riêng cho topic quan trọng.

Các file này:

- **không trực tiếp là prompt**,  
- nhưng là nguồn bạn trích nội dung vào **system prompt**,  
- hoặc dùng để huấn luyện mental model khi design assistant.

---

## 7. Master Prompt & “gọi” các file ở mức khái niệm

Hiện tại GPT/Gemini không hỗ trợ `#include rules.md` trực tiếp, nhưng:

- Khi tạo assistant:
  - bạn copy nội dung rút gọn của `rules.md` + `flow-main.md` vào System Instructions.
- Khi chat/test:
  - bạn dùng các prompt trong `stacks/*.md`,
  - luôn nhắc assistant “tuân theo RULES”.

**Master prompt skeleton minh họa:**

```text
[Dưới đây là nội dung rút gọn từ RULES]
[...]

[Dưới đây là tóm tắt các FLOW chính bạn phải dùng]
[...]

Trong mọi câu trả lời:
- Bạn phải tuân theo RULES ở trên.
- Khi tôi yêu cầu "chạy phase X", bạn hãy làm theo hướng dẫn tương ứng trong stack X (FRAME/STRUCTURE/REASON/VALIDATE/SYNTHESIZE) đã được mô tả.
- Trước khi gửi câu trả lời cuối, bạn hãy tự kiểm theo CHECKPOINT (assumption, gaps, confidence, red-flag).

Xác nhận rằng bạn đã hiểu:
- vai trò & scope,
- các flow chính,
- các phase (stack) và checkpoint.
```

Về mặt dạy học, điều quan trọng là:

- Học viên hiểu **master prompt** không phải là “1 khối text khổng lồ viết đại”,  
- mà là **bản tổng hợp** của:
  - `rules.md`,
  - `flow-main.md`,
  - các stack quan trọng,
  - checkpoint & safety.

---

---

# Phần II – Tương tác tự động (Runtime Interaction)

Cho tới giờ, Prompt System Architecture tập trung vào **cách thiết kế bên trong**:

- `rules.md` – luật & biên,
- `flow-main.md` – các luồng kịch bản,
- `stacks/*.md` – prompt stack cho từng phase,
- `checkpoint.md` – quy tắc kiểm tra.

Trong thực tế, **người dùng cuối không đi từng phase**. Họ chỉ:

> gõ 1 câu yêu cầu  
> (ví dụ: “Tạo kịch bản thị trường tài chính sụp đổ”,  
> hoặc “Tạo kịch bản tiếp cận thiếu niên 14 tuổi bị áp lực học tập”)  

và mong nhận được **kết quả cuối cùng**, đã qua:

- framing,
- sắp xếp cấu trúc,
- suy luận,
- kiểm định an toàn.

Vì vậy, cần phân biệt rõ 2 chế độ:

- **Debug / Learning Mode** – cho người thiết kế, test từng phase,  
- **Runtime / Auto Mode** – cho người dùng cuối, assistant tự chạy full flow.

## 8. Debug Mode vs Runtime Mode

### 8.1. Debug / Learning Mode

- Dùng cho:
  - học viên học từng kỹ thuật (Frame, Reason, Validate…),
  - nhà thiết kế test behavior từng stack.

- Cách dùng:
  - mở chat,
  - copy prompt từ `stacks/frame.md` → chạy,
  - sau đó copy prompt từ `stacks/reason.md` → chạy,
  - v.v.

Trong mode này, bạn thấy rõ từng phase, dễ debug, nhưng **không phải** trải nghiệm của người dùng cuối.

### 8.2. Runtime / Auto Mode

- Dùng cho **người dùng cuối**:
  - Họ chỉ gõ:  
    “Tạo kịch bản X…”,  
    hoặc “Hãy giúp tôi xử lý tình huống Y…”.
- Assistant:
  - dựa trên **Master Instruction** (System Prompt),
  - tự động chạy toàn bộ flow nội bộ đã thiết kế trong `flow-main.md` và `stacks/*.md`,
  - áp dụng kiểm định theo `checkpoint.md`,
  - rồi **chỉ trả kết quả cuối cùng**, đúng format.

Người dùng:

- không thấy “Frame/Structure/Reason/Validate”,
- trừ khi họ **yêu cầu rõ**: “Hãy cho tôi xem các bước suy luận”.

## 9. Master Instruction trong chế độ tự động

Để Content Engine (hoặc bất kỳ assistant nào) hoạt động đúng trong Runtime Mode, **Master Instruction** phải:

- Nhắc rõ nó đang dùng:
  - `rules.md` (luật & biên),
  - `flow-main.md` (flow nội bộ),
  - `stacks/*.md` (logic cho từng phase),
  - `checkpoint.md` (self-check),
- Và mô tả cách nó **tự chạy** các phase nội bộ khi nhận input 1 câu.

Ví dụ skeleton (bạn chỉnh lại theo domain):

```markdown
You are [Tên assistant], an AI assistant designed according to a modular prompt system.

You operate with the following components:
- RULES (rules.md): your mission, audience, scope, safety and epistemic rules.
- FLOWS (flow-main.md): main interaction flows (sequences of phases).
- STACKS (stacks/*.md): prompt patterns for each phase (FRAME, STRUCTURE, REASON, VALIDATE, SYNTHESIZE).
- CHECKPOINT (checkpoint.md): how you validate and adjust your draft answers before responding.

Runtime behavior:

When the user gives you a request such as:
- "Tạo kịch bản video về ..." or "Hãy giúp tôi xử lý tình huống ...",

you must internally:

1. Follow the relevant FLOW defined in flow-main.md:
   - perform the FRAME phase (according to stacks/frame.md),
   - then STRUCTURE (stacks/structure.md),
   - then REASON (stacks/reason.md),
   - then VALIDATE (stacks/validate.md),
   - then SYNTHESIZE (stacks/synthesize.md).

2. Apply CHECKPOINT (checkpoint.md) to your draft answer before sending the final response:
   - list key assumptions,
   - mark confidence levels,
   - detect and patch missing aspects and red flags,
   - ensure full alignment with RULES (rules.md).

Unless the user explicitly asks to see your internal reasoning steps,
you should only show the final structured output (script, plan, framework, etc.),
not the phase-by-phase process.

Always respect the scope, safety and epistemic rules from rules.md.
```

## 10. Diagram kiến trúc (markdown)

Sơ đồ dưới tóm tắt kiến trúc module & runtime flow:

```markdown
               ┌────────────────────────┐
               │   SID Handbook (7 bước,│
               │   8 nhóm kỹ thuật)     │
               └──────────┬─────────────┘
                          │
                    ┌─────▼─────┐
                    │ rules.md  │  ← Mission, scope, safety, epistemic
                    └─────┬─────┘
                          │
                    ┌─────▼──────┐
                    │flow-main.md│ ← Định nghĩa các FLOW chính
                    └─────┬──────┘
          (Design-time)   │            (Runtime)
                          │
      ┌───────────────────┴───────────────────┐
      │                                       │
┌─────▼──────────┐                    ┌───────▼─────────┐
│ stacks/frame.md│                    │ stacks/structure│
└─────┬──────────┘                    └───────┬─────────┘
      │                                      │
┌─────▼──────────┐                    ┌──────▼───────────┐
│stacks/reason.md│                    │stacks/validate.md│
└─────┬──────────┘                    └──────┬───────────┘
      │                                      │
      └──────────────┬──────────────┬────────┘
                     │              │
               ┌─────▼─────┐  ┌─────▼───────┐
               │stacks/    │  │checkpoint.md│
               │synthesize │  └─────────────┘
               └─────┬─────┘
                     │
                     │
                     ▼
              Final answer to user
   (đã qua FRAME → STRUCTURE → REASON → VALIDATE → SYNTHESIZE
              + self-check theo CHECKPOINT)
```

Sơ đồ này:

- Cho thấy `rules.md` là gốc,
- `flow-main.md` định nghĩa trình tự phase,
- `stacks/*.md` là logic từng pha,
- `checkpoint.md` là chốt kiểm trước khi trả lời,
- Master Instruction đứng ngoài, mô tả:
  - assistant sẽ dùng toàn bộ hệ thống này **nội bộ**,  
  - khi xử lý 1 yêu cầu duy nhất từ người dùng cuối.

---

*SID Coach Pro v5.0 — Powered by Structured Intelligence Design Framework - Binh Truong*
