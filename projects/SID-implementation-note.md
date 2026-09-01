# Implementation Note — Từ SID Spec sang Prompt System Thực Tế

Mục tiêu của note này là giúp bạn chuyển từ tài liệu SID dạng spec sang một hệ prompt thực tế, có thể dùng ngay cho Gem, Custom GPT, Assistant API hoặc project học tập.

> Phiên bản này gộp lại phần implementation và phần architecture, để giảm sự lặp lại giữa 3 tài liệu cũ.

---

## 1. Hai lớp cần phân biệt

### Spec
Là tài liệu thiết kế và kiến trúc:
- framing brief,
- IA pack,
- reasoning pack,
- validation rules,
- project spec.

### Prompt
Là phần thực thi ngắn gọn hơn:
- master instruction,
- phase prompts,
- test prompts,
- output format chuẩn.

SID giúp bạn viết spec tốt; prompt giúp bạn làm assistant chạy được.

---

## 2. Khi nào dùng single-file, khi nào dùng multi-file

### Mức 1 — MVP / single-file
Dùng khi project nhỏ, vòng đời ngắn, hoặc mục tiêu là thử nghiệm nhanh:
- 1 file master instruction,
- 3–5 test scenarios,
- 1 output format chuẩn.

### Mức 2 — Full SID / multi-file
Dùng khi project cần mở rộng, có nhiều phase, nhiều guardrail, nhiều knowledge module:
- rules.md,
- flow-main.md,
- stacks/frame.md,
- stacks/structure.md,
- stacks/reason.md,
- stacks/validate.md,
- stacks/synthesize.md,
- checkpoint.md.

### Nguyên tắc chọn mức
- Project nhỏ: dùng MVP.
- Project có nhiều domain rules hoặc nhạy cảm: dùng full SID.
- Không bắt buộc mọi project đều phải dùng kiến trúc phức tạp.

---

## 3. 3 tầng prompt trong thực tế

### Tầng 1 — Master Instruction / System Prompt
Dùng cho Gem, Custom GPT, hoặc API system message.

Nội dung nên gồm:
- mission và audience,
- scope và out-of-scope,
- core behaviors,
- safety và epistemic rules,
- default output format.

Độ dài thường: 300–1500 từ.

### Tầng 2 — Prompt Stack
Dùng để test từng phase:
- Frame,
- Structure,
- Reason,
- Validate,
- Synthesize.

Ví dụ:
- Frame: hỏi lại context và tóm tắt bối cảnh.
- Reason: liệt kê hypothesis và mức độ tin cậy.
- Validate: tự check gap, assumption, contradiction.

### Tầng 3 — Test Prompts
Mỗi project nên có 5–10 scenario thực tế để test:
- user prompt gần với người dùng thật,
- expected behavior rõ ràng,
- đầu ra không được vượt scope.

---

## 4. Evaluation rubric nên có

Mỗi project nên có một bảng chấm đơn giản sau:

| Tiêu chí | Câu hỏi | Mức mong muốn |
|---|---|---|
| Độ đúng | Assistant có trả lời đúng trọng tâm không? | Có đúng ý chính và đúng scope |
| Độ rõ | Output có dễ đọc, có cấu trúc không? | Có heading, bullet, bảng, flow |
| Độ an toàn | Có vượt scope, đưa khuyến nghị nguy hiểm không? | Có guardrail và giới hạn rõ |
| Độ hữu ích | Người dùng có thể dùng ngay không? | Có hành động cụ thể và rõ ràng |
| Độ dạy được | Có giúp người dùng hiểu, không chỉ trả lời tắt? | Có giải thích, ví dụ, hoặc workflow |

Nếu chưa có metric, hệ thống dễ trở nên “đẹp trên giấy” nhưng kém hiệu quả thực tế.

---

## 5. Chỉ số đánh giá để biết prompt có “tốt” thật không

Không nên đánh giá prompt chỉ bằng cảm giác. Một prompt tốt nên được đo bằng những chỉ số cụ thể sau:

### 5.1. Chỉ số về độ tuân thủ instruction
- Tỷ lệ assistant thực hiện đúng scope, đúng format và đúng bước workflow.
- Mức đánh giá: 1–5 điểm cho từng test case.

### 5.2. Chỉ số về hallucination
- Tỷ lệ câu trả lời có đưa ra thông tin không có căn cứ, không được xác nhận, hoặc vượt quá dữ liệu đầu vào.
- Có thể đo bằng:
  - số claim không được hỗ trợ,
  - số lỗi factual,
  - số lần đưa ra kết luận quá mạnh khi chưa đủ dữ liệu.

### 5.3. Chỉ số về cải thiện độ hiểu
- So sánh trước và sau khi dùng prompt mới:
  - điểm kiểm tra ngắn trước/ sau,
  - tỷ lệ người dùng hiểu đúng vấn đề,
  - tỷ lệ người dùng có thể tự tổng hợp lại nội dung bằng câu của họ.
- Đây là chỉ số quan trọng nếu prompt dùng cho coaching, teaching hoặc advisory system.

### 5.4. Chỉ số về khả năng giúp người dùng hoàn thành task
- Người dùng có hoàn thành mục tiêu cuối cùng không?
- Ví dụ: có xây được outline, có hiểu được vấn đề, có biết bước hành động tiếp theo không?

### 5.5. Chỉ số về calibration / độ tin cậy của mức độ chắc chắn
- Khi assistant nói “cao”, “trung bình”, “thấp”, liệu mức độ đó có đúng với thực tế không?
- Nếu prompt dùng cho chuyên môn nhạy cảm, calibration là chỉ số rất quan trọng.

### 5.6. Mẫu cách đo đơn giản
Một cách đơn giản là chạy cùng 1 bộ test trên 2 phiên bản prompt:
- prompt cũ vs prompt mới,
- cùng 20–30 cases,
- ghi lại:
  - instruction adherence,
  - hallucination rate,
  - task completion,
  - understanding gain,
  - user satisfaction.

Nếu prompt mới có:
- tỷ lệ tuân thủ cao hơn,
- hallucination thấp hơn,
- understanding gain tốt hơn,
- task completion cao hơn,
thì có thể xem là prompt cải tiến thành công.

---

## 6. User state assessment

Một điểm thường bị bỏ qua là không phân biệt người dùng đang ở đâu:
- beginner: cần hỏi lại nhiều, giải thích chậm hơn,
- intermediate: cần ngắn gọn hơn, cho workflow thực tế,
- advanced: cần sâu, logic, trade-off và framework.

Do đó, master instruction nên có một bước “user state assessment” trước khi quyết định mức độ chi tiết.

---

## 6. Socratic / Feynman loop

Một hệ prompt tốt không chỉ “trả lời”, mà còn giúp người dùng hiểu sâu hơn.

Nên thêm vòng lặp như:
1. Trả lời ngắn gọn.
2. Hỏi người dùng hiểu đến đâu.
3. Nếu chưa rõ, dùng cách giải thích đơn giản hơn.
4. Nếu cần, yêu cầu người dùng tự tổng hợp lại bằng câu của họ.

Điều này làm cho assistant không chỉ là “chatbot”, mà trở thành coach / mentor.

---

## 7. Starter template cho project mới

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

Output format:
- Summary
- Analysis
- Action plan
- Safety boundary
```

---

## 8. Chuẩn tối thiểu cho mỗi project

Mỗi project nên có ít nhất:
1. 1 master instruction draft,
2. 1 prompt stack cho 3–5 phase,
3. 5–10 test prompts,
4. 1 evaluation rubric ngắn.

Nếu thiếu các phần này, project thường chỉ là “thiết kế đẹp” chứ chưa phải “hệ thống dùng được”.

---

*SID Coach Pro v5.0 — Powered by Structured Intelligence Design Framework - Binh Truong*

