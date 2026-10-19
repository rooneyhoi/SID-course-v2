# Mô hình Agent / Skill / Tool / Knowledge Base

> Ví dụ nấu cơm và ứng dụng cho SID v2

## 1. Mục tiêu tài liệu

Tài liệu này dùng ví dụ “đầu bếp nấu cơm” để phân biệt các thành phần chính trong một hệ thống Agent:

- **Agent**: thành phần nhận mục tiêu, giữ ngữ cảnh và điều phối công việc.
- **Skill**: năng lực hoặc quy trình có thể tái sử dụng để hoàn thành một loại nhiệm vụ.
- **Tool**: phương tiện, API hoặc hệ thống mà Agent có thể sử dụng.
- **Knowledge Base (KB)**: nguồn tri thức phục vụ tra cứu và ra quyết định.
- **State / Memory**: trạng thái của cuộc hội thoại và tiến trình thực hiện nhiệm vụ.
- **Routing, Rules, Checkpoint, Validation và Recovery**: cơ chế điều khiển và kiểm soát chất lượng.

Mô hình khái quát:

```text
Agent
 ├── Instructions / Policy
 ├── Reasoning / Decision
 ├── Skills / Procedures
 ├── Tools
 ├── Knowledge / Retrieval
 └── State / Memory
```

---

## 2. Các khái niệm cốt lõi

### 2.1. Agent

Agent có thể được hình dung như một nhân viên nhận yêu cầu và chủ động điều phối cách xử lý trong phạm vi được cho phép.

Agent có thể:

- Thu thập và duy trì ngữ cảnh.
- Hỏi lại khi thiếu thông tin cần thiết.
- Chọn skill hoặc quy trình phù hợp.
- Áp dụng rules và policy.
- Gọi tool.
- Tra cứu knowledge.
- Kiểm tra kết quả và xử lý lỗi.

Agent không đồng nghĩa với LLM. LLM có thể là một thành phần hỗ trợ hiểu ngôn ngữ, reasoning hoặc sinh nội dung; phần điều phối còn có thể bao gồm logic xác định, workflow engine và code thông thường.

### 2.2. Skill

Skill là một **năng lực hoặc quy trình có thể tái sử dụng** để hoàn thành một loại nhiệm vụ.

Một skill nên có:

- Mục tiêu rõ ràng.
- Input và output rõ ràng.
- Điều kiện bắt đầu và kết thúc.
- Các bước thực hiện.
- Rules và validation liên quan.
- Tool và knowledge cần sử dụng.
- Cách xử lý khi thất bại.

> **Skill không phải là Tool.** Skill mô tả cách làm; Tool là phương tiện được sử dụng trong quá trình làm.

### 2.3. Tool

Tool là phương tiện mà Agent hoặc skill có thể gọi hoặc sử dụng, ví dụ:

- API gửi email.
- Cơ sở dữ liệu.
- Công cụ tìm kiếm.
- Nồi cơm điện, cân hoặc cốc đong trong ví dụ vật lý.

Tool nên có contract rõ ràng: input, output, quyền truy cập, lỗi có thể xảy ra và mức độ đảo ngược của hành động.

### 2.4. Knowledge Base và RAG

Knowledge Base là nguồn lưu trữ tri thức, ví dụ facts, hướng dẫn, chính sách, tài liệu kỹ thuật và kinh nghiệm chuyên môn.

**RAG (Retrieval-Augmented Generation)** không phải là Knowledge Base. RAG là một mẫu kiến trúc:

```text
Knowledge Base
      ↓
Retrieval
      ↓
Relevant Context
      ↓
LLM
      ↓
Generated Answer
```

Trong implementation cụ thể, chức năng retrieval có thể được expose cho Agent dưới dạng một tool, chẳng hạn `search_knowledge()`.

Không phải mọi KB đều cần RAG. Nếu tri thức nhỏ, ổn định và có cấu trúc rõ, rules hoặc dữ liệu có cấu trúc có thể phù hợp hơn.

### 2.5. State / Memory

State lưu thông tin cần thiết xuyên suốt cuộc hội thoại hoặc workflow.

Ví dụ:

```yaml
state:
  servings: 3
  texture: soft
  rice_type: jasmine
  allergy_notes: none
  current_step: measure_rice
```

Có thể phân biệt:

- **Conversation state**: thông tin đã trao đổi trong hội thoại hiện tại.
- **Task state**: bước hiện tại, kết quả trung gian và trạng thái hoàn thành.
- **User preferences**: lựa chọn được phép lưu để dùng lại.
- **Workflow state**: dữ liệu phục vụ retry, recovery hoặc audit.

Không nên lưu dữ liệu nhạy cảm nếu không cần thiết; việc lưu phải tuân theo policy và quyền truy cập.

---

## 3. Ví dụ Knowledge Base: nấu cơm

KB nấu cơm có thể chứa:

- Các loại gạo và đặc tính của từng loại.
- Tỷ lệ gạo và nước.
- Các loại cơm: mềm, khô, dẻo, cháo hoặc cơm trộn.
- Khẩu vị và thói quen ăn uống theo bối cảnh văn hóa.
- Dấu hiệu nhận biết cơm chín, sống, nhão, khê hoặc cháy.
- Hướng dẫn an toàn thực phẩm.
- Thông tin dinh dưỡng đã được kiểm chứng.

Nếu yêu cầu liên quan đến bệnh nền, dị ứng hoặc chế độ ăn đặc biệt, Agent không nên tự đưa ra chẩn đoán. Hệ thống cần áp dụng policy phù hợp, sử dụng nguồn đáng tin cậy và chuyển sang chuyên gia khi cần.

---

## 4. Ví dụ Skill

### 4.1. Skill: vo gạo

**Input**

- Loại gạo.
- Lượng gạo.
- Yêu cầu giữ hoặc giảm tinh bột bề mặt.

**Procedure**

1. Đong lượng gạo cần dùng.
2. Kiểm tra sạn hoặc dị vật.
3. Cho nước sạch vào.
4. Vo nhẹ theo hướng dẫn phù hợp với loại gạo.
5. Chắt nước và kết thúc khi đạt tiêu chí.

**Knowledge tham chiếu**

- Đặc tính của loại gạo.
- Số lần vo phù hợp.
- Hướng dẫn an toàn và chất lượng.

**Output**

- Gạo đã được làm sạch và sẵn sàng cho bước nấu.

### 4.2. Skill: nấu cơm

**Input**

- Số khẩu phần.
- Loại gạo.
- Độ mềm hoặc khô mong muốn.
- Thiết bị nấu.
- Hạn chế liên quan đến dị ứng hoặc chế độ ăn, nếu có.

**Procedure**

1. Tính lượng gạo.
2. Gọi skill `vo-gao`.
3. Tính lượng nước.
4. Cho gạo và nước vào nồi.
5. Chọn chế độ và bắt đầu nấu.
6. Kiểm tra sau chu kỳ nấu.
7. Xử lý theo kết quả validation.

**Tools**

- Nồi cơm điện.
- Cốc đong hoặc cân.
- Dụng cụ vo và xới cơm.

**Knowledge tham chiếu**

- Tỷ lệ nước theo loại gạo.
- Tiêu chí nhận biết cơm chín.
- Cách xử lý các trạng thái chưa đạt.

---

## 5. Ví dụ Agent: đầu bếp nấu cơm

### 5.1. Định nghĩa

```text
Agent: Đầu bếp
Goal: Chuẩn bị cơm phù hợp và an toàn trong phạm vi được định nghĩa
```

### 5.2. Context collection và Routing

Không phải mọi câu hỏi đều là routing. Cần phân biệt:

- **Context / parameter collection**: thu thập dữ liệu còn thiếu, ví dụ “Bạn muốn cơm mềm hay khô?”.
- **Routing**: dựa trên dữ liệu đã có để chọn skill, flow, từ chối hoặc escalation.

```text
Input
  ↓
Context collection
  ↓
Routing
  ├── Skill nấu cơm
  ├── Skill hâm cơm
  ├── Clarify
  ├── Refuse vì ngoài phạm vi
  └── Escalate vì cần chuyên gia/người giám hộ
```

Chỉ nên hỏi thông tin thật sự ảnh hưởng đến cách xử lý. Không hỏi dữ liệu cá nhân không cần thiết.

### 5.3. Rules và deterministic logic

Nên tách quyết định xác định khỏi phần sinh ngôn ngữ linh hoạt:

```text
Deterministic Logic / Rules
          +
         LLM
```

Ví dụ:

```text
if request is out_of_scope:
    route → refuse_or_redirect
elif required_parameter is missing:
    route → clarify
else:
    route → selected_skill
```

- **Rules / code** phù hợp với quyền hạn, điều kiện bắt buộc, giới hạn an toàn và quyết định cần tính nhất quán.
- **LLM** phù hợp với việc hiểu yêu cầu không cấu trúc, giải thích và tạo hội thoại tự nhiên.

Nếu `Jev` là một thành phần riêng của SID v2, phải định nghĩa rõ tên đầy đủ, trách nhiệm, input/output và vị trí của nó trong kiến trúc. Nếu không, nên dùng thuật ngữ dễ kiểm chứng hơn như **deterministic logic**, **rule engine** hoặc **workflow engine**.

### 5.4. Out of Scope

Ví dụ Agent chỉ phụ trách nấu cơm:

- Không hướng dẫn chế biến món không thuộc phạm vi.
- Không tự đưa ra chẩn đoán y khoa.
- Không thực hiện hành động vượt quyền.
- Có thể chuyển hướng sang Agent hoặc nguồn phù hợp nếu hệ thống hỗ trợ.

---

## 6. Checkpoint, Validation và Recovery

Ba khái niệm này cần được tách riêng:

- **Checkpoint**: thời điểm hệ thống dừng để kiểm tra.
- **Validation**: tiêu chí xác định kết quả đạt hay không đạt.
- **Recovery**: hành động xử lý sau khi validation thất bại.

```text
Step
 ↓
Checkpoint
 ↓
Validation
 ↓
Pass ─────→ Next step
 │
Fail
 ↓
Recovery
```

Ví dụ:

```yaml
step: cook_rice
checkpoint: after_cooking_cycle
validation:
  expected_status: cooked
recovery:
  undercooked: retry_with_additional_heat
  too_dry: apply_defined_recovery
  unsafe_or_unknown: stop_and_escalate
```

### 6.1. Các chiến lược xử lý lỗi

```text
Failure handling
 ├── Retry
 ├── Loop
 ├── Rollback
 ├── Compensating action
 └── Escalation
```

Không phải hành động nào cũng rollback được. Các hành động như gửi email, chuyển tiền, xóa dữ liệu hoặc đặt vé có thể cần **compensating action**, phê duyệt hoặc escalation thay vì đơn giản quay lại bước trước.

Với hành động có ảnh hưởng lớn hoặc khó đảo ngược, nên có:

- Xác nhận trước khi thực hiện.
- Idempotency hoặc chống thực hiện trùng.
- Log và audit trail.
- Phân quyền.
- Cơ chế bồi hoàn hoặc xử lý ngoại lệ.

---

## 7. Output, Few-shot và Test case

### 7.1. Output contract

Mỗi skill hoặc workflow nên định nghĩa:

- Thành công được biểu diễn như thế nào.
- Lỗi được biểu diễn như thế nào.
- Trường dữ liệu bắt buộc.
- Thông tin nào được phép hiển thị cho user.

### 7.2. Few-shot examples

Few-shot examples minh họa hành vi mong muốn ở các nhánh quan trọng, nhưng không thay thế rules hoặc test case.

Ví dụ nên bao phủ:

- Đủ dữ liệu và xử lý thành công.
- Thiếu dữ liệu và cần clarify.
- Yêu cầu ngoài phạm vi.
- Tool lỗi.
- Validation thất bại.
- Hành động cần xác nhận hoặc escalation.

### 7.3. Test case

Mỗi test case nên có:

```yaml
name: cook_rice_happy_path
input: {}
initial_state: {}
expected_route: cook_rice
expected_tool_calls: []
expected_output: {}
expected_state: {}
```

Cần kiểm thử:

- Routing.
- Rules và policy.
- State transition.
- Checkpoint và validation.
- Retry, recovery, rollback hoặc compensating action.
- Quyền truy cập tool.
- OOS và refusal.
- Multi-agent handoff nếu có.

---

## 8. Multi-Agent và Tools

Multi-Agent là hệ thống có nhiều Agent phối hợp theo vai trò hoặc chuyên môn. Không nên mặc định rằng mọi bài toán đều cần Multi-Agent; một Agent với workflow rõ ràng thường đơn giản và dễ kiểm soát hơn.

Một số pattern phổ biến:

### 8.1. Supervisor

```text
Supervisor
 ├── Agent A
 ├── Agent B
 └── Agent C
```

### 8.2. Sequential

```text
Agent A → Agent B → Agent C
```

### 8.3. Maker–Reviewer

```text
Agent A tạo kết quả
      ↓
Agent B review
      ↓
Đạt → hoàn tất
Chưa đạt → trả về A để sửa
```

### 8.4. Specialist routing

```text
        Router
       /      \
Agent chuyên môn A   Agent chuyên môn B
```

Khi thiết kế Multi-Agent cần định nghĩa rõ:

- Agent nào sở hữu mục tiêu cuối.
- Dữ liệu nào được truyền giữa các Agent.
- Handoff contract.
- Điều kiện kết thúc loop.
- Quyền gọi tool của từng Agent.
- Cách tránh loop vô hạn và xung đột kết quả.

---

## 9. Quy trình review dự án bằng SID v2

### 9.1. Cấu trúc thư mục gợi ý

```text
SID-v2/
├── framing-brief.md
├── architecture.md
├── rules.md
├── skills/
├── knowledge/
├── tests/
└── projects/
    └── <project-name>/
```

### 9.2. Prompt review gợi ý

```text
Dùng các tiêu chí SID v2 trong thư mục hiện tại để review dự án
[project-name].

Kiểm tra tối thiểu:
- framing brief;
- Agent, Skill, Tool, Knowledge và State;
- routing và context collection;
- rules, policy và quyền hạn;
- checkpoint, validation và recovery;
- OOS;
- output contract;
- test case;
- multi-agent handoff nếu có.

Ghi kết quả vào file SID-v2-review-report.md.
Với mỗi vấn đề, nêu: bằng chứng, mức ảnh hưởng, đề xuất sửa và test case liên quan.
```

### 9.3. Review thủ công

Sau khi tạo report, cần phản biện lại:

- Nhận xét có dẫn đúng vị trí trong dự án không?
- Có nhầm giữa Skill và Tool không?
- Có nhầm KB với RAG không?
- Routing có hay chỉ đang thu thập parameter?
- Checkpoint, validation và recovery đã tách rõ chưa?
- Có action khó đảo ngược nhưng thiếu xác nhận không?
- Test case có thật sự kiểm tra hành vi không?

---

## 10. Framing Brief: hợp đồng phạm vi

Nên tách riêng file `framing-brief.md` và xem đây là hợp đồng định nghĩa bài toán.

Nội dung tối thiểu:

1. **Problem**: Bài toán cần giải quyết là gì?
2. **Users / Actors**: Hệ thống phục vụ ai?
3. **Goals**: Kết quả mong muốn là gì?
4. **Input / Output**: Dữ liệu vào và kết quả ra.
5. **In Scope**: Hệ thống làm gì?
6. **Out of Scope**: Hệ thống không làm gì?
7. **Constraints**: Giới hạn kỹ thuật, pháp lý, bảo mật hoặc vận hành.
8. **Permissions**: Ai được phép làm gì?
9. **Risk & Reversibility**: Hành động nào có rủi ro hoặc khó đảo ngược?
10. **Success Criteria**: Tiêu chí chấp nhận.
11. **Failure Handling**: Retry, recovery, compensating action và escalation.
12. **Test Strategy**: Những nhóm test bắt buộc.

---

## 11. Sơ đồ tổng thể

```text
                    ┌──────────────┐
                    │     USER     │
                    └──────┬───────┘
                           │
                           ▼
                    ┌──────────────┐
                    │    AGENT     │
                    └──────┬───────┘
                           │
              ┌────────────┼────────────┐
              │            │            │
              ▼            ▼            ▼
           CONTEXT       ROUTING       RULES
              │            │
              │            ▼
              │          SKILL
              │            │
              │        PROCEDURE
              │            │
        ┌─────┴─────┬──────┼────────┐
        ▼           ▼      ▼        ▼
      STATE        TOOL   KNOWLEDGE  EXTERNAL SYSTEM
                            │
                        RETRIEVAL
                            │
                           LLM
                            │
                       CHECKPOINT
                            │
                       VALIDATION
                       /        \
                    PASS        FAIL
                     │            │
                     ▼            ▼
                  NEXT        RECOVERY
                                  │
                   ┌──────────────┼──────────────┐
                   ▼              ▼              ▼
                 RETRY      COMPENSATE       ESCALATE
                                  │
                              ROLLBACK
                         (nếu thực sự khả thi)
```

---

## 12. Checklist hoàn tất thiết kế

- [ ] Framing brief đã rõ problem, user, scope và OOS.
- [ ] Agent, Skill, Tool và Knowledge không bị trộn khái niệm.
- [ ] Đã xác định State / Memory cần giữ.
- [ ] Context collection và Routing được tách rõ.
- [ ] Rules xác định không bị giao hoàn toàn cho LLM.
- [ ] RAG chỉ được dùng khi retrieval thực sự cần thiết.
- [ ] Mỗi checkpoint có validation cụ thể.
- [ ] Mỗi failure mode có recovery phù hợp.
- [ ] Hành động khó đảo ngược có xác nhận và cơ chế bảo vệ.
- [ ] Output có contract rõ ràng.
- [ ] Test case bao phủ happy path, edge case và failure path.
- [ ] Multi-Agent chỉ được dùng khi có lý do và handoff contract rõ ràng.

## Kết luận

Chuỗi thiết kế đề xuất cho SID v2:

```text
Framing Brief
  → Context & State
  → Routing
  → Skills & Procedures
  → Rules & Permissions
  → Tools & Knowledge
  → Checkpoint & Validation
  → Recovery
  → Output Contract
  → Test Cases
```

Cấu trúc này giúp biến việc thiết kế prompt hoặc Agent thành một quy trình engineering có phạm vi, trạng thái, quyền hạn, tiêu chí kiểm tra và cách xử lý lỗi rõ ràng.

*Review thực hiện theo SID-course-v2 (SID Coach Pro v5.0 — Structured Intelligence Design). by Binh Truong*
