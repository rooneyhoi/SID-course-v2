# SID Projects — Learning by Building

> Từ lý thuyết SID sang xây dựng sản phẩm AI thực tế

Folder này chứa **7 projects** được sắp xếp theo 3 cấp độ: **Basic**, **Pro**, **Advance**. Mỗi project là 1 bài tập thực hành để áp dụng SID vào domain thực tế.

---

## 🚀 Quick Start

**Bạn đang ở mức nào? Chọn cấp độ phù hợp:**

| Bạn Vừa Hoàn Thành | Cấp Độ | Projects | Đọc Chi Tiết |
|---|---|---|---|
| Bài 01–04 (SID Basic) | **Basic** | P1–P2 | [👇 Basic Projects](#tier-1-basic) |
| Bài 01–07 (SID Pro) | **Pro** | P3–P5 | [👇 Pro Projects](#tier-2-pro) |
| Bài 01–08 (SID Advance) | **Advance** | P6–P7 | [👇 Advance Projects](#tier-3-advance) |

---

## 📊 Project Overview

| # | Project Name | Tier | Hard | Time | Key Skills | Output |
|---|---|---|---|---|---|---|
| **P1** | Kích bản video | Basic | 4/10 | 2–3w | Framing, Prompt Stack | Video script + outline |
| **P2** | IELTS Preparation Coach | Basic | 6/10 | 3–4w | IA, Output Format | Chatbot spec + test cases |
| **P3** | Travel Search Onboarding | Pro | 5/10 | 2–3w | Framing + IA | Onboarding workflow + samples |
| **P4** | Knowledge Extraction System | Pro | 7.5/10 | 4–6w | Decomposition, Reasoning | Knowledge base architecture |
| **P5** | Fruity Tree Expert (Cây Ăn Quả) | Pro | 7.5/10 | 4–6w | Domain expertise, IA | Expert chatbot spec + dialogues |
| **P6** | Book Architect Design | Advance | 9/10 | 8–12w | Deep research, Validation, Synthesis | Book architecture + sample chapters |
| **P7** | Kid Lens (Tâm Lý Trẻ Em) | Advance | 9/10 | 6–8w | Safety, Validation, Epistemic control | Tutor spec + safety protocols |

---

## Tier 1: Basic

> **Prerequisite**: Bài 01–04  
> **Focus**: Framing + Prompt Stack + basic IA  
> **Time per project**: 2–4 tuần  
> **Difficulty**: 4–6/10 (Dễ đến trung bình)

Cấp độ này học viên học cách **define vấn đề rõ** và **thiết kế prompt stack đầu tiên**. Output là các chatbot/workflow đơn giản nhưng có cấu trúc.

### P1 — Kích bản video (Video Script)

**Mô tả**: Xây dựng 1 hệ thống tạo **kịch bản video** từ chủ đề (nông nghiệp, khởi nghiệp, self-development,…).

**Mục tiêu học tập**:
- Định khung bài toán rõ (topic vs problem, audience, scope)
- Thiết kế prompt stack để đi từ **ý tưởng → outline → script**
- Output format chuẩn cho video script

**Output bắt buộc**:
- Framing Brief (150–200 từ) — mục tiêu, audience, scope
- Prompt Stack v1 (3 phase) — brainstorm → outline → script skeleton
- 1 video script hoàn chỉnh (~500 từ)
- Test cases (3–5 scenarios thực tế)

**Difficulty**: Hard 4/10  
**Time**: 2–3 tuần

**Tài liệu tham khảo**: Bài 01 (Framing), Bài 02 (Prompt Stack)

---

### P2 — IELTS Preparation Coach

**Mô tả**: Xây dựng 1 **chatbot hỗ trợ ôn IELTS**, có khả năng:
- Giải thích nội dung thi
- Luyện tập từ vựng, ngữ pháp
- Feedback writing/speaking

**Mục tiêu học tập**:
- Định rõ scope (in/out — IELTS only, không general English)
- IA (taxonomy ngành IELTS: Listening, Reading, Writing, Speaking)
- Output format cho từng task

**Output bắt buộc**:
- Framing Brief
- Chatbot Spec (mission, audience, scope, core behaviors)
- IA Pack (taxonomy, rubric chấm writing/speaking)
- Prompt Stack v1
- 5–10 test dialogues (sample Q&A)

**Difficulty**: Hard 6/10  
**Time**: 3–4 tuần

**Tài liệu tham khảo**: Bài 01–04

---

## Tier 2: Pro

> **Prerequisite**: Bài 01–07  
> **Focus**: Decomposition + IA + Reasoning  
> **Time per project**: 2–6 tuần  
> **Difficulty**: 5–7.5/10 (Trung bình đến khó)

Cấp độ này học viên bắt đầu **bóc tách vấn đề phức tạp** thành các thành phần, thiết kế **architecture thông tin**, và dùng **reasoning patterns** để xử lý logic.

### P3 — Travel Search Onboarding Assistant

**Mô tả**: Xây hệ thống **onboarding** cho platform tìm kiếm du lịch, giúp user định rõ:
- Budget, thời gian, loại hình du lịch
- Preferences (playa vs mountain, culture, adventure,…)

Sau đó đề xuất **travel itinerary** phù hợp.

**Mục tiêu học tập**:
- Phân tách quá trình onboarding thành các bước logic
- Thiết kế workflow hỏi-đáp có cấu trúc
- Dùng output từ onboarding làm input cho recommendation

**Output bắt buộc**:
- Framing Brief + Problem Statement
- Decomposition Tree (onboarding flow)
- IA Pack (data structure, user persona taxonomy)
- Prompt Stack cho onboarding → recommendation
- Sample dialogues (3–5)

**Difficulty**: Hard 5/10  
**Time**: 2–3 tuần

**Tài liệu tham khảo**: Bài 03–04

---

### P4 — Knowledge Extraction System

**Mô tả**: Xây hệ thống **trích xuất tri thức** từ:
- Bài báo khoa học
- Sách/document dài
- Video transcript

Tổ chức thành:
- Concept hierarchy
- Relationship graph
- Key findings

**Mục tiêu học tập**:
- Thiết kế taxonomy cho domain cụ thể
- Decompose document dài thành units nhỏ
- Design prompt để AI trích xuất structure knowledge

**Output bắt buộc**:
- Domain specification (chọn 1 domain: medicine, psychology, agriculture,…)
- IA Pack (concept taxonomy, relationships, attributes)
- Extraction schema (output format chuẩn)
- Prompt stack cho extraction
- Validation criteria (cách kiểm tra kết quả)

**Difficulty**: Hard 7.5/10  
**Time**: 4–6 tuần

**Tài liệu tham khảo**: Bài 03–07

---

### P5 — Fruity Tree Expert (Cây Ăn Quả Chuyên Gia)

**Mô tả**: Xây **Gem/chatbot chuyên gia nông nghiệp** tư vấn về cây ăn quả:
- Chọn giống (cam, bưởi, xoài, sầu riêng,…)
- Chăm sóc (đất, nước, phân, tỉa cành,…)
- Sâu bệnh, vụ mùa, thu hoạch

**Mục tiêu học tập**:
- Xây expert system với domain knowledge sâu
- Reasoning pattern: hỏi lại context, đề xuất có basis
- Validation: không bịa, cảnh báo giới hạn

**Output bắt buộc**:
- Framing Brief (expert profile, scope, audience)
- IA Pack (taxonomy cây, bệnh, quy trình chăm sóc,…)
- Expert Spec:
  - Mission & boundaries
  - Core behaviors (hỏi lại, suggest có basis, disclaimer risk)
  - Prompt stack
  - Failure modes & guardrails
- 5 sample dialogues (hỏi → tư vấn → warning)
- Validation report (cách kiểm tra lời tư vấn)

**Difficulty**: Hard 7.5/10  
**Time**: 4–6 tuần

**Tài liệu tham khảo**: Bài 01–07

---

## Tier 3: Advance

> **Prerequisite**: Bài 01–08  
> **Focus**: Validation + Synthesis + Deep reasoning  
> **Time per project**: 6–12 tuần  
> **Difficulty**: 9/10 (Rất khó)

Cấp độ này học viên **validate tri thức sâu**, **thiết kế framework** toàn diện, và **synthesis** thành sản phẩm/hệ thống có thể dạy lại, transfer cho người khác.

### P6 — Book Architect Design (Thiết Kế Cấu Trúc Sách)

**Mô tả**: Thiết kế **architecture cho 1 cuốn sách** (5–8 chương, 150–200 trang), sử dụng SID pipeline hoàn chỉnh:
- Deep research → Knowledge mapping
- Decompose thành chương, section
- Reasoning: mạch lập luận, hypothesis, causal
- Validation: fact-check, triangulation, epistemic control
- Synthesis: framework sách, workflow viết, asset dạy lại

**Mục tiêu học tập**:
- Áp dụng toàn bộ 8 bước SID vào 1 project dài hạn
- Thiết kế book architecture (không chỉ viết lách lách)
- Dùng AI co-pilot trong research, outline, validation
- Biết khi nào cần con người (trải nghiệm, ví dụ, critical thinking)

**Output bắt buộc**:
1. **Book Architecture Document**:
   - Framing (reader persona, objective, scope)
   - Chapter structure (5–8 chương, tên + 1–2 mô tả)
   - Chapter decomposition (sections, sub-sections)
   - IA (concept map toàn sách, taxonomy)
   - Mạch lập luận (từ intro → main → advanced → future)

2. **Sample Content**:
   - 1 chương hoàn chỉnh (hoặc part of chapter, ~3–5k từ):
     - Thiết kế bằng SID
     - Draft với AI support
     - Validate + revise
   - Reasoning examples (CoT, hypothesis, causal in chương)
   - Validation notes (fact-check, sources, limitations)

3. **Writing Workflow**:
   - Mô tả cách tác giả dùng AI:
     - Research phase: keyword research, source gathering
     - Outline phase: AI brainstorm, structure suggest
     - Draft phase: AI content generation, human revise
     - Validation phase: AI fact-check, peer review
   - Timeline (3–6 tháng, milestone per chương)

**Difficulty**: Hard 9/10  
**Time**: 8–12 tuần

**Tài liệu tham khảo**: Tất cả 8 bài, đặc biệt: Bài 05 (Research), Bài 06 (Reasoning), Bài 07 (Validation), Bài 08 (Synthesis)

---

### P7 — Kid Lens: AI Tutor cho Tâm Lý Trẻ Em

**Mô tả**: Thiết kế **AI tutor** hỗ trợ phụ huynh/giáo viên hiểu và giao tiếp với trẻ, về:
- Cảm xúc, hành vi, phát triển tâm lý
- Kỹ năng giao tiếp phù hợp
- Khi nào cần tìm chuyên gia

**Constraints**:
- **KHÔNG** đóng vai trò nhà trị liệu hoặc chẩn đoán lâm sàng
- **CÓ** cảnh báo rõ boundary
- **PHẢI** detect "red flags" (bạo lực, tự hại, lạm dụng) → escalate

**Mục tiêu học tập**:
- Thiết kế safety-critical system (high epistemic humility)
- Validate mỗi recommendation (có basis, không guessing)
- Synthesis: decision tree, flowchart, safety protocol
- Handling edge cases, ethical dilemmas

**Output bắt buộc**:
1. **Tutor Specification**:
   - Mission & Audience (phụ huynh, giáo viên, trình độ)
   - Scope (in: giao tiếp tips, out: diagnosis, therapy)
   - Core behaviors:
     - Hỏi lại context, không gắn nhãn
     - Tư vấn dựa trên developmental psychology
     - Escalation flow (red flag → not handle → refer)

2. **Safety Architecture**:
   - Red flag detection (list of indicators)
   - Escalation protocol (khi nào stop → refer tới ai)
   - Epistemic rules (khi không chắc → admit + recommend expert)
   - Tone & language (empathetic, non-judgmental)

3. **Reasoning & Validation**:
   - Reasoning examples (CoT: situation → analysis → suggestion)
   - Validation checklist (assumptions, biases, limitations)
   - Triangulation (multiple sources, expert review)

4. **Dialogue Samples**:
   - 3–5 hội thoại mẫu:
     - 1–2 case bình thường (normal parenting concern)
     - 1 case red flag (tutor stops, escalates)
     - 1 case edge (uncertainty, multiple valid paths)

**Difficulty**: Hard 9/10  
**Time**: 6–8 tuần

**Tài liệu tham khảo**: Tất cả 8 bài, đặc biệt: Bài 07 (Validation, Safety), Bài 08 (Synthesis)

---

## 📋 Yêu Cầu Chung (Tất Cả Projects)

### Artifacts Bắt Buộc

**Tier Basic** (P1–P2):
- Framing Brief
- Prompt Stack (v1)
- Output format specification
- 3–5 test cases

**Tier Pro** (P3–P5):
- Framing Brief + Problem Statement
- Decomposition Tree / Knowledge Map
- IA Pack (taxonomy, hierarchy, schema)
- Prompt Stack (v1+)
- Validation notes
- 5+ test cases / sample dialogues

**Tier Advance** (P6–P7):
- Framing Brief
- Deep IA Pack
- Reasoning pack (multiple patterns)
- Validation report (fact-check, epistemic labeling)
- Sample output / content
- Framework & workflow
- Asset dạy lại (nếu applicable)

### Quality Criteria

Mỗi project phải satisfy:
- ✅ **Scope rõ** — in-scope / out-of-scope định nghĩa tường minh
- ✅ **Logic cohere** — không có mâu thuẫn, giả định rõ
- ✅ **Output usable** — không chỉ "concept", mà có thể dùng ngay
- ✅ **Testable** — có cách verify/validate kết quả
- ✅ **Transferable** — có thể learn, teach, scale được

---

## 🎯 Cách Làm Project

### Step 1: Chọn project phù hợp tier
- Bạn hoàn thành bài nào? → Chọn project tier tương ứng
- Sẵn có domain thực tế? → Chọn project phù hợp domain

### Step 2: Đọc kỹ mô tả project
- Hiểu vấn đề, audience, output yêu cầu
- Xác định prerequisite (nên hoàn thành buổi nào trước)

### Step 3: Thực hiện theo SID pipeline
Dù project nào, cũng nên qua các bước:
1. **Frame** — Define vấn đề, audience, scope, goal
2. **Architect** — Bóc tách, thiết kế structure
3. **Explore** — Research, expand knowledge
4. **Reason** — Thiết kế reasoning pattern
5. **Validate** — Check, validate, fact-check
6. **Synthesize** — Tổng hợp thành artifact cuối
7. **Transfer** — Làm sao dùng lại, teach, scale?

### Step 4: Document & Submit
- Ghi lại từng artifact (không chỉ "làm", mà phải document)
- Chuẩn bị presentation + sample output
- Nhận feedback từ mentor/instructor

### Step 5: Revise & Finalize
- Dựa trên feedback, cải tiến
- Finalize artifacts cho portfolio / triển khai thực tế

---

## 📚 Tài Liệu Hỗ Trợ

Mỗi project link tới relevant lessons:
- **SID-01-handbook.md** — SID core concepts
- **SID-02-syllabus.md** — Lộ trình, artifacts per buổi
- **bai-01 ~ bai-08.md** — Chi tiết từng bài học
- **SID-implementation-note.md** — Từ spec sang prompt thực tế
- **SID-project-audit.md** — Cách audit project
- **SID-prompt-system-architecture.md** — Prompt system design

---

## ✋ Important Notes

1. **Projects không bắt buộc hoàn thành toàn bộ 8 bước SID**. Tùy tier:
   - Basic: Focus framing + prompt stack
   - Pro: Add decomposition + reasoning
   - Advance: Full pipeline 01–08

2. **Có thể làm project trong team** (1–2 người), nhưng phải clear division of labor.

3. **Projects là long-term commitment**:
   - Basic: 2–4 tuần
   - Pro: 2–6 tuần
   - Advance: 6–12 tuần
   
   Nên plan thời gian kỹ, không "bao giờ lúc rảnh".

4. **Quality over speed**. Tốt hơn làm 1 project tốt, còn hơn 3 project tồi.

5. **Output phải có thể dùng/deploy thực tế** (nếu có thể), hoặc ít nhất là "production-ready spec".

---

## 📞 Support & Feedback

- **Stuck on a project?** → Hỏi mentor/instructor (không nên ngồi chỉ tự làm mà không feedback)
- **Want to suggest a new project?** → Liên hệ product lead
- **Found a bug/typo in project spec?** → Issue/PR welcome

---

**Last updated**: January 2025  
**Version**: 2.0 (Reorganized per SID Syllabus)  
**Status**: Active — All 7 projects ready to launch