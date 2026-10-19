# Mô hình Agent / Skill / KB – Ví dụ nấu cơm & Ứng dụng cho SID v2

## 1. Khái niệm

### Agent
- Như nhân viên: tự làm việc theo **yêu cầu** + **quy định (rules)** + **công cụ (tools)** + **tri thức (KB)**.
- Có thể:
  - Hỏi lại (routing, clarification).
  - Quyết định theo rules + Jev + LLM.
  - Kích hoạt skill, gọi tool, tra cứu KB.

### Skill
- Là **1 kỹ năng**, dùng đi dùng lại.
- Có thể được dùng bởi:
  - Agent (nhân viên).
  - User (chính mình, thông qua UI / lệnh).
- Có input / output rõ ràng.
- Thường tham chiếu tới 1 hoặc nhiều KB.

### KB (Knowledge Base)
- Kho tri thức.
- Lưu trữ thông tin, facts, guidelines.
- Được RAG (Retrieve-Augment-Generate) khi tri thức nhiều / phức tạp.

---

## 2. Ví dụ KB – Nấu cơm

**KB: nấu cơm** có thể gồm:

- Các loại gạo.
- Các loại cơm.
- Các món ăn đi kèm.
- Cơm phù hợp với sức khỏe nào.
- Nghệ thuật ăn cơm (Ý, Hàn, Việt, Trung Quốc).
- Đặc tính tinh bột, đường (liên quan tới bệnh nền, dị ứng).

> Nếu tri thức nhiều, phức tạp → dùng RAG để truy vấn.

---

## 3. Ví dụ Skill

### Skill: vo gạo
- Bước:
  - Đong gạo.
  - Vo gạo.
- Tham chiếu:
  - KB về các loại gạo (để biết vo mấy lần, giữ hay bỏ nước đầu, v.v.).

### Skill: nấu cơm
- Input:
  - Người nước nào?
  - Món cơm cho ai (tuổi, sức khỏe, dị ứng?).
- Bước:
  - Cho gạo và nước vào nồi.
  - Chọn chế độ, bấm nút.
  - Kiểm tra cơm chín.
- Tham chiếu:
  - KB về món cơm phù hợp (theo văn hóa, khẩu vị).
  - KB về loại cơm (mềm, khô, dẻo…).

---

## 4. Ví dụ Agent – Đầu bếp nấu cơm

### Định nghĩa Agent
- **Agent = Đầu bếp**.

#### Tools
- Nồi cơm điện.
- Ổ cắm điện.
- Thìa xúc cơm.
- Rá/giá vo gạo.
- Bơ đong gạo.

#### Skills
- `skill-vo-gao`
- `skill-nau-com`
- `skill-kiem-tra-com`

---

### Routing

Agent sẽ hỏi để routing:

- "Bạn là ai?"
- "Người nước nào?"
- "Mấy tuổi?" (5 tuổi thì gọi bố mẹ ra đây).
- "Muốn ăn món gì?"
- "Có dị ứng / bệnh nền gì không?"

**Logic routing:**
- Người rất nhỏ tuổi:
  - Gọi bố mẹ, từ chối hướng dẫn trực tiếp.
- Người già:
  - Gọi con cái / người chăm sóc.
- Có dị ứng / bệnh nền:
  - Lưu ý loại gạo (nhiều/ít tinh bột, carbohydrate, v.v.).
  - Tham chiếu KB sức khỏe – chế độ ăn.

---

### Rules

- **OOS (Out of Scope):**
  - Không hướng dẫn:
    - Rang cơm.
    - Luộc rau.
    - Chế biến các món khác ngoài cơm.
- **Quy trình bắt buộc:**
  1. Đong gạo.
  2. Vo gạo  
     - Checkpoint: nhặt sạn, dị vật.
  3. Nấu cơm.
  4. Kiểm tra.
  5. Xác thực cơm chín:
     - Chín vừa.
     - Chín và để lâu 1h.
     - Các trạng thái khác…

- **Jev + LLM:**
  - Jev: Make decision nhanh (ra quyết định nhanh).
  - LLM: Sinh nội dung, giải thích, hội thoại.

---

### Checkpoint & Rollback

Theo từng bước, có **checkpoint** để:
- Nếu fail → rollback (quay lại bước trước) hoặc
- Yêu cầu loop lại ngay.

Ví dụ checkpoint:
- Thế nào là đủ gạo cho 3 người ăn?
  - Tính bằng bơ gạo hay gram?
- Thế nào là:
  - Cơm chín.
  - Cơm cháy.
  - Cơm khê.
  - Cơm nhão.
  - v.v.

---

### Output

- **Few-shot examples:**
  - Ví dụ hội thoại và hành vi của Agent ở từng nhánh (đủ tuổi / không đủ tuổi, khỏe mạnh / có bệnh nền, v.v.).
- **Test case:**
  - Kịch bản vào / ra để test routing, rules, checkpoint, rollback.

---

## 5. Multi-Agent & Tools

- Nhiều Agent cùng hệ thống:
  - Agent ↔ Tools:
    - RAG.
    - Dịch vụ bên ngoài (mail, bank, v.v.).
    - Harness (Hermes, Antigravity…).
- Workflow:
  - Agent A làm việc → Agent B kiểm tra.
  - Nếu chưa đạt → từ chối → A phải làm lại → Loop.

---

## 6. Prompt review dự án bằng SID v2

Quy trình gợi ý:

1. **Cấu trúc thư mục**
   - Đặt chung:
     - Folder `SID v2`
     - Folder dự án  
   → Cùng một thư mục gốc.

2. **Prompt**
   - “Dùng tri thức trong SID v2 để review dự án [tên dự án] rồi ghi ra file output `SID-v2-review-report.md`.”

3. **Review thủ công**
   - Xem lại report và phản biện:
     - Kiểm tra routing, rules, checkpoint, OOS, test case, v.v.

---

## 7. Lưu ý thiết kế hệ thống

- **Tập trung vào:**
  - Routing.
  - Rules.
  - Checkpoint.

- **Routing dùng cho 2 việc:**
  1. Định vị hội thoại (user là ai, bối cảnh gì).
  2. Định nghĩa tính năng rẽ nhánh:
     - Theo yêu cầu.
     - Theo đối tượng sử dụng (tuổi, vai trò, quyền hạn…).

- **Framing brief – bắt buộc kỹ & tách riêng file: `framing-brief.md`**
  - Mô tả rõ:
    - Bài toán là gì?
    - Giải quyết cho ai?
    - OOS là gì (Out of Scope)?
  - File này là “hợp đồng” định nghĩa phạm vi:  
    - Input / Output.
    - Đối tượng.
    - Use case chính.
    - Không làm gì.

- **Sau cùng:**
  - Xây dựng **test case**:
    - Bao phủ:
      - Routing.
      - Rules.
      - Checkpoint.
      - Rollback / loop.
      - Multi-agent (nếu có).
