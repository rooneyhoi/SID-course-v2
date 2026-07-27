# Project Technique Mapping

Tài liệu này nối SID Core với các project mẫu bằng cách chỉ ra kỹ thuật nào đang được áp dụng rõ, kỹ thuật nào mới chạm tới, và kỹ thuật nào chưa được thể hiện mạnh.

---

## 1. Ma trận mapping theo 8 buổi SID

| Buổi | Kỹ thuật | Loại kỹ thuật | FruitTree Mentor | Content Engine | Book Design | AI Tutor |
|---|---|---|---|---|---|---|
| Buổi 1 — Framing | Problem framing, audience, scope | Cốt lõi | ✓ | ✓ | ✓ | ✓ |
| Buổi 2 — Prompt Stack | Master instruction, phase prompts | Cốt lõi | ✓ | ✓ | ✓ | ✓ |
| Buổi 3 — Decomposition | Top-down decomposition | Cốt lõi | ~ | ✓ | ✓ | ✓ |
| Buổi 4 — IA | Taxonomy, hierarchy, output schema | Cốt lõi | ✓ | ✓ | ✓ | ✓ |
| Buổi 5 — Expansion | Breadth/depth exploration | Phụ trợ / nâng cao | ~ | ~ | ✓ | ~ |
| Buổi 6 — Reasoning | CoT, ToT, causal, hypothesis | Cốt lõi | ✓ | ~ | ✓ | ✓ |
| Buổi 7 — Validation | Self-critique, gap check, confidence | Cốt lõi | ✓ | ✓ | ~ | ✓ |
| Buổi 8 — Synthesis | Framework, workflow, transfer | Cốt lõi | ✓ | ✓ | ✓ | ✓ |

### Phân loại kỹ thuật
- Cốt lõi: nên có trong hầu hết các project SID vì quyết định cấu trúc và độ rõ của hệ thống.
- Phụ trợ / nâng cao: có thể dùng khi project cần sâu hơn, phức tạp hơn hoặc cần nghiên cứu đa chiều.
- Chỉ phù hợp cho kiểu project nhất định: ví dụ Expansion mạnh hơn ở Book Design; Validation/Safety rất quan trọng ở AI Tutor; Reasoning branch logic rất phù hợp với FruitTree Mentor.

Ký hiệu:
- ✓ = áp dụng rõ và có cấu trúc
- ~ = có áp dụng nhưng chưa là trọng tâm

---

## 2. Kết luận ngắn

- FruitTree Mentor mạnh ở Framing, Reasoning, Validation và Synthesis.
- Content Engine mạnh ở Prompt Stack, IA và workflow sản xuất nội dung.
- Book Design là project thể hiện decomposition, IA và synthesis sâu nhất.
- AI Tutor mạnh ở Framing, safety, validation và reasoning theo nhiều lens.

---

## 3. Cách dùng tài liệu này

Dùng tài liệu này để trả lời ba câu hỏi:
1. Project này đang áp dụng SID ở đâu?
2. Kỹ thuật nào là cốt lõi, kỹ thuật nào là phụ trợ, và kỹ thuật nào chỉ phù hợp với kiểu project nhất định?
3. Kỹ thuật nào nên bổ sung thêm nếu muốn làm sâu hơn?

### Gợi ý triển khai thực tế
- Nếu project mới bắt đầu, ưu tiên dùng các kỹ thuật cốt lõi trước: Framing, Prompt Stack, IA, Validation, Synthesis.
- Nếu project cần nghiên cứu sâu hoặc kiến trúc tri thức phức tạp, mới thêm Expansion.
- Nếu project liên quan đến an toàn, chuyên môn nhạy cảm hoặc quyết định có rủi ro, nên ưu tiên Validation và Safety-bound reasoning.

