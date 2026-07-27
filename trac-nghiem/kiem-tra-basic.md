# SID — Bộ câu hỏi kiểm tra cơ bản

Tài liệu này tổng hợp các câu hỏi kiểm tra từ các bài 01–05 của khóa SID để người học có thể ôn tập và tự đánh giá nhanh.

---

## 1. Buổi 1 — Framing & Cognitive Control

### Câu hỏi

1. Sự khác biệt cốt lõi giữa Topic và Problem Framing là gì?
2. Tại sao Framing được gọi là Cognitive Control đối với AI?
3. Một câu lệnh chỉ chứa Topic thường dẫn tới kết quả gì?
4. Thành phần Where và Task trong ví dụ về campaign playbook là gì?
5. Ý nghĩa của Width/Depth (Scope) là gì?
6. Tại sao Output Framing lại quan trọng?
7. Dấu hiệu rõ ràng nhất cho thấy Goal/Output Framing chưa hoàn thành là gì?
8. Artifact nào tối ưu nhất cho nhân viên tổng đài xử lý khiếu nại?
9. Artifact nào phù hợp cho quản lý cần đào tạo nội bộ 2 tiếng?
10. Artifact nào hữu ích nhất cho lãnh đạo muốn quyết định có nên thay nhân sự viết bài bằng AI?
11. Vì sao prompt “phân tích chi tiết về chăm sóc khách hàng” bị xem là tồi?
12. Yếu tố nào ngăn AI đề xuất giải pháp quá tầm?

### Đáp án

1. B — Topic trả lời “đang nói về cái gì”, còn Problem Framing trả lời “cần thực hiện nhiệm vụ nhận thức gì với cái đó”.
2. C — Framing điều hướng tư duy AI vào phạm vi nhất định, tránh câu trả lời đúng nhưng không dùng được.
3. C — AI sẽ cung cấp lý thuyết chung chung thay vì giải quyết bài toán thực thi.
4. B — Where là bối cảnh như ngân sách và quy mô, Task là Design.
5. B — Scope giúp phân biệt In-scope và Out-of-scope.
6. B — Output Framing biến yêu cầu mơ hồ thành artifact cụ thể.
7. C — Chưa gọi tên được artifact cụ thể cần nhận.
8. B — Checklist + script thoại mẫu.
9. B — Training outline hoặc syllabus.
10. C — Comparison table so sánh AI và freelancer.
11. B — Prompt thiếu Audience, Scope và Artifact.
12. B — Xác định Audience rõ và Out-of-scope.

---

## 2. Buổi 2 — Prompt as Cognitive Interface & Prompt Stack

### Câu hỏi

1. Mục tiêu chính của khung RTC-COE là gì?
2. Thành phần nào không thuộc RTC-COE?
3. Constraints trong RTC-COE nên được hiểu như thế nào?
4. Điểm khác biệt quan trọng nhất của Prompt Stack so với master prompt là gì?
5. Ví dụ nào là dấu hiệu của master prompt dài-sai?
6. Trong Prompt Stack chuẩn, các prompt nên như thế nào?
7. Khi viết Output trong RTC-COE, cần chỉ rõ điều gì?
8. Khi nào nên thêm Evaluation vào prompt?
9. Sự khác biệt giữa RTC-COE và Prompt Stack là gì?
10. Bước nào nên làm trước khi thiết kế Prompt Stack?

### Đáp án

1. B — Giúp cấu trúc prompt thành các phần rõ ràng: Role, Task, Context, Constraints, Output, Evaluation.
2. D — Memory không thuộc RTC-COE.
3. B — Ràng buộc về độ dài, phong cách, điều phải tránh/điều phải có.
4. C — Mỗi prompt xử lý một phase khác nhau, dùng output trước làm input cho bước sau.
5. B — Master prompt dài-sai khi đổ quá nhiều nhiệm vụ vào cùng một prompt.
6. B — Các bước khác nhau: clarify → structure → refine → critique.
7. C — Cần chỉ rõ dạng artifact: bảng, checklist, kế hoạch, khung.
8. A — Khi muốn mô hình tự kiểm tra chất lượng output theo tiêu chí cụ thể.
9. C — RTC-COE là stack vi mô trong một prompt; Prompt Stack là stack vĩ mô giữa nhiều prompt.
10. C — Viết Framing Brief trước, sau đó dùng Clarify Prompt.

---

## 3. Buổi 3 — Decomposition & Knowledge Mapping

### Câu hỏi

1. Mục tiêu chính của decomposition là gì?
2. Nếu chỉ hỏi AI kiểu “giải thích” mà không decomposition, vấn đề lớn nhất là gì?
3. Khẳng định nào đúng về decomposition của một domain?
4. “MECE-ish Thinking” được hiểu như thế nào?
5. “Node” trong cây tri thức là gì?
6. Top-down decomposition có đặc trưng gì?
7. Functional decomposition tập trung vào gì?
8. Stakeholder decomposition trả lời câu hỏi chính nào?
9. Ví dụ “AI literacy cho giảng viên” có thể decomposition theo stakeholder như thế nào?
10. Conceptual decomposition thường bao gồm gì?
11. Trong top-down decomposition, cấp 1 lý tưởng nên gồm bao nhiêu miền chính?
12. Sai lầm phổ biến khi làm cây top-down là gì?
13. Khi kiểm tra chất lượng cây, “Cấp 1 có đang đồng đẳng không?” nghĩa là gì?
14. Dấu hiệu “node trùng ý” là gì?
15. Tiêu chí thực dụng để đánh giá cây decomposition là gì?
16. Functional decomposition giúp làm gì?
17. Bước khởi đầu của functional decomposition là gì?
18. Trong ví dụ “quy trình dùng AI thiết kế bài giảng”, việc bóc bước 4 thành 4.1, 4.2, 4.3 minh họa điều gì?
19. Functional view quan trọng vì sao?
20. Đầu ra điển hình của functional decomposition thường được biểu diễn thế nào?
21. Với mỗi stakeholder, bộ 4 câu hỏi gợi ý là gì?
22. Stakeholder map không phải là gì?
23. Trong ví dụ “AI literacy trong trường đại học”, phòng đảm bảo chất lượng là ví dụ của gì?
24. Lợi ích chính của stakeholder map là gì?
25. Yêu cầu tối thiểu cho decomposition tree là gì?
26. Một yêu cầu về chất lượng cho decomposition tree là gì?
27. Trong bài tập 2, functional map yêu cầu gì?
28. Ngoài decomposition tree và functional/stakeholder map, bạn cần thêm gì?
29. Tiêu chí “Functional/Stakeholder map” trong rubric tự chấm đánh giá điều gì?
30. Sau khi hoàn thành Buổi 1–3, người học có gì?

### Đáp án

1. B — Bóc chủ đề lớn thành bản đồ tri thức nhiều tầng, rõ khối lớn/khối nhỏ.
2. B — Không thấy bức tranh toàn bộ và ranh giới khối lớn/chi tiết.
3. C — Không có cách chia duy nhất đúng; quan trọng là phù hợp với bài toán và audience.
4. B — Cố gắng “không trùng lớn, không thủng lớn”.
5. C — Một “khối” trong cây tri thức: nhánh, lá hoặc cụm nội dung.
6. C — Từ tổng quan → miền chính → nhóm con → node cụ thể.
7. B — Chia theo chức năng/khâu trong hệ.
8. B — Chủ đề này trông thế nào từ góc nhìn mỗi bên liên quan.
9. A — Giảng viên, sinh viên, khoa/bộ môn, ban giám hiệu.
10. B — Khái niệm nền, khái niệm trung gian, ứng dụng.
11. C — Thường 3–7 miền chính, có cùng tiêu chí chia.
12. B — Chia theo cảm tính, lẫn các loại node trên cùng một cấp.
13. B — Các node cấp 1 phải cùng loại.
14. A — Hai node khác tên nhưng đề cập cùng một nội dung.
15. B — Nhìn vào cây, bạn có thể dạy 4–5 buổi logic theo thứ tự được không.
16. B — Để thiết kế workflow và assistant/agent.
17. C — Xác định quy trình trung tâm cần phân tích từ input → output.
18. C — Bổ sung sub-function bên trong một chức năng lớn.
19. B — Gắn decomposition với workflow thực tế.
20. B — Dòng bước/bullet từ 1 → n, có thể kèm sub-function.
21. B — Kỳ vọng, sợ điều gì, cần năng lực/tri thức gì, dùng AI vào việc gì.
22. A — Stakeholder map không phải cây tri thức.
23. B — Phòng đảm bảo chất lượng là stakeholder.
24. B — Giúp thiết kế module, nội dung và ưu tiên khác nhau cho từng vai trò.
25. B — Ít nhất 3 miền chính cấp 1, tổng số node ≥ 20.
26. B — Cây 3–4 tầng, tránh lẫn khái niệm/quy trình/lỗi trên cùng một cấp.
27. B — Chọn 1 workflow thực, liệt kê chức năng từ input → output, có thể bóc sub-function.
28. B — Thêm đoạn 150–250 từ giải thích tiêu chí cấp 1 và cách dùng cây cho syllabus/assistant/khóa học.
29. B — Map có phản ánh thực tế và giúp hiểu system/people hơn không.
30. B — Có bản đồ tri thức đầu tiên cho domain, cả phía nội dung lẫn vận hành/con người.

---

## 4. Buổi 4 — Information Architecture & Representation

### Câu hỏi

1. Mục tiêu chính của việc chọn dạng biểu diễn không phải là gì?
2. Điểm khác biệt giữa taxonomy và hierarchy là gì?
3. Vì sao taxonomy cần dựa trên một tiêu chí phân loại rõ?
4. Lỗi thường gặp khi thiết kế bảng so sánh là gì?
5. Vì sao nên thiết kế schema bảng trước khi yêu cầu AI điền nội dung?
6. Khi chuyển từ Decomposition Tree sang Hierarchy dạy học, yêu cầu quan trọng nhất là gì?
7. Vì sao các mục lớn trong hierarchy được sắp xếp theo logic nhất định?
8. Khi nào nên ưu tiên dùng matrix thay vì table 1 chiều?
9. Lợi ích nhận thức của ma trận nhóm năng lực × giai đoạn là gì?
10. Giá trị của việc liệt kê thực thể – thuộc tính – quan hệ – phụ thuộc là gì?
11. Điểm kiểm tra để đánh giá taxonomy là “tốt” là gì?
12. Vì sao IA Pack cần có taxonomy, hierarchy và table/matrix cùng lúc?
13. Tiêu chí “Alignment với Frame” đánh giá điều gì?
14. Khi thiết kế bảng so sánh các năng lực AI literacy để giúp hiệu trưởng quyết định ưu tiên đào tạo, cột nào ít phù hợp nhất?
15. Thế nào là representation fit trong bối cảnh IA?

### Đáp án

1. C — Không phải để trang trí.
2. B — Taxonomy phân loại theo một tiêu chí rõ; hierarchy là cấu trúc cha–con để dạy/học.
3. B — Tránh trộn nhiều tiêu chí trên cùng một chiều.
4. B — Cột đặt ngẫu hứng, không có tiêu chí, khiến người đọc không rút ra quyết định.
5. C — Schema mã hóa tiêu chí so sánh/quyết định.
6. C — Ưu tiên mạch học hợp lý hơn là trung thành tuyệt đối với cây ban đầu.
7. C — Tuân theo logic: khái niệm nền → ứng dụng → đánh giá → đạo đức & policy → dạy lại.
8. B — Khi có giao cắt 2 chiều có ý nghĩa.
9. B — Giúp nhìn đa chiều và hỗ trợ ưu tiên thiết kế training/assistant.
10. C — Giúp thấy các phụ thuộc giữa năng lực/khái niệm.
11. C — Mỗi nhóm tuân theo một tiêu chí phân loại rõ.
12. B — Mỗi dạng biểu diễn phục vụ một mục tiêu nhận thức khác nhau.
13. B — IA Pack có trung thành với Framing Brief và scope hay không.
14. D — Tên viết tắt ưa thích của tác giả không liên quan tới quyết định.
15. C — Dùng đúng dạng biểu diễn phù hợp với mục tiêu nhận thức cụ thể.

---

## 5. Buổi 5 — Expansion & Research Depth

### Câu hỏi

1. Breadth-first exploration khác decomposition ở điểm nào?
2. Trong Exploration Map, miền nào nên xếp vào nhóm Core?
3. Khi tự sanity check Exploration Map, câu hỏi nào không nằm trong 3 câu hỏi gợi ý?
4. Từ khóa nào thuộc lớp Technical/Scholarly trong ví dụ HR?
5. Keyword shortlist khuyến nghị tối đa bao nhiêu term cho 1–2 tuần?
6. Mục đích chính của bước kiểm chứng thuật ngữ technical/scholarly là gì?
7. Faceted exploration giải quyết vấn đề gì?
8. Trong Facet Matrix cho node “Quy trình đánh giá cuối năm”, facet nào là domain-specific?
9. Khi nào nên dùng full 4–6 facet, khi nào chỉ cần 2–3 facet?
10. “Change management” được phân loại là loại domain lân cận nào?
11. Tiêu chí nào cho thấy việc đọc adjacent domain “đã giúp được”?
12. Trong 4 tiêu chí chấm điểm Node, “Confusion risk” đo lường điều gì?
13. Feedback loop trong Node Prioritization có mục đích gì?
14. Checkpoint B trong Research Path được thực hiện vào thời điểm nào?
15. Trong Research Path v1 của ví dụ HR, node “Thiết kế framework đánh giá” đóng góp vào phần nào của deliverable?

### Đáp án

1. B — Breadth-first quét toàn bộ vùng tri thức xung quanh chủ đề; decomposition bẻ nhỏ vấn đề thành cấu phần.
2. B — Core là miền trực tiếp phục vụ bài toán cần giải.
3. D — Loại bỏ keyword không phải là sanity check của Exploration Map.
4. C — Rater bias / halo effect.
5. B — 10–15 term.
6. B — Phát hiện term hiếm, mơ hồ hoặc dùng khác nghĩa trong thực tế.
7. B — Ép người dùng nhìn cùng một chủ đề qua nhiều góc nhìn cố định.
8. D — Manager capability.
9. B — Full 4–6 facet cho node cấp 1–2; 2–3 facet cho node cấp 3–4.
10. B — Applied.
11. B — Có thể trả lời ít nhất 1 trong 3 câu: hiểu thêm tại sao, thêm ý tưởng thiết kế, hoặc biết thêm rủi ro cần tránh.
12. B — Node này có dễ hiểu sai hoặc dễ làm sai không.
13. B — Là công cụ học kinh nghiệm, không chỉ bài tập một lần.
14. B — Cuối Pha 2, để quyết định có nên pivot sang node khác không.
15. C — Framework tổng quan — trang 1 của deliverable.

---

## 6. Gợi ý cách dùng

- Dùng như bộ ôn tập trước khi làm bài tự đánh giá.
- Có thể dùng làm nền cho chấm bài, audit project hoặc xây prompt stack SID.
- Nếu cần, có thể tiếp tục tách thành phiên bản ngắn hơn cho học viên hoặc phiên bản có đáp án riêng.
