# Buổi 1 — Framing as Cognitive Control

Problem Framing & Goal Structuring for AI-mediated Knowledge Work  
> Tập trung cho người làm giáo dục, kinh doanh, marketing, dịch vụ, vận hành…

---

## 0. Bạn sẽ nhận được gì sau buổi này?

Sau khi hoàn thành Buổi 1, bạn sẽ:

- Phân biệt rõ:
  - Chủ đề (topic) vs bài toán (problem) vs đầu ra (output).
- Nhìn ra vì sao prompt mình đang dùng dài nhưng vẫn sai gốc.
- Viết được **Framing Brief** cho 1 chủ đề trong công việc thật của bạn:
  - có mục tiêu, audience, scope, output, task rõ ràng,
  - dùng được làm input cho mọi buổi sau (prompt stack, decomposition, IA,…).
- Tự chẩn đoán misframing trong 3–5 prompt cũ của bản thân.

Nếu bạn làm nghiêm túc, chỉ riêng buổi này đã làm chất lượng làm việc với AI tăng rõ rệt, ngay cả khi chưa học tiếp các buổi khác.

---

## 1. Tại sao “Framing” là buổi đầu tiên?

### 1.1. Lỗi điển hình của người dùng AI 1–3 năm

Bạn (chắc) đã từng:

Viết một prompt rất dài, kiểu:

> “Bạn hãy đóng vai chuyên gia hàng đầu về marketing, giải thích cho tôi một cách cực kỳ chi tiết và sâu sắc về cách xây dựng chiến dịch marketing cho sản phẩm mới, liệt kê các kênh nên dùng, các bước triển khai, các sai lầm thường gặp, đưa ví dụ thực tế và cho tôi lộ trình học marketing trong 3 tháng…”

Và nhận một câu trả lời:

- nghe rất hay,
- trông rất đầy đủ,

nhưng:

- khó dùng ngay,
- không ăn khớp với bối cảnh của bạn  
  (VD: bạn chỉ có ngân sách nhỏ, nhân sự hạn chế, cần tập trung 1–2 kênh chính),
- đọc xong vẫn… hơi “mù”.

Đó là triệu chứng của **framing sai**, không phải do model “ngu” hay bạn “viết chưa đủ dài”.

### 1.2. Bản chất của lỗi

Các prompt “dài mà sai gốc” thường có những lỗi:

- Chủ đề rõ (VD: “marketing”, “training nội bộ”, “dịch vụ khách hàng”), nhưng **bài toán mờ**:
  - bạn muốn hiểu, so sánh, thiết kế, dạy, hay ra quyết định?
- Không nói rõ **audience**:
  - ai là người sử dụng kiến thức này? khách hàng, nhân viên mới, quản lý, học viên?
- Không nêu **output** dưới dạng artifact:
  - bảng, framework, workflow, syllabus, rubric, kịch bản, checklist?
- **Scope trôi dạt**:
  - vừa muốn từ cơ bản đến nâng cao, vừa muốn cả chiến lược lẫn chi tiết kênh, lẫn đào tạo nhân sự… trong 1 prompt duy nhất.

**Framing** là bước bạn chỉnh lại gốc tư duy, trước khi nghĩ đến “prompt cho hay hơn”.

### 1.3. Framing là Extended Mind bằng NLP, và AI Mindset là cách kiểm soát hệ thống suy nghĩ

Nếu nhìn sâu hơn, bài học đầu tiên này không chỉ là kỹ thuật viết prompt. Nó là cách bạn dùng ngôn ngữ tự nhiên để mang “cấu trúc trong đầu” ra ngoài, biến suy nghĩ mơ hồ thành thông tin có tổ chức, có thể trao cho AI xử lý.

Đây là nơi mà ba khái niệm nối lại với nhau:

- **Extended Mind**: AI không chỉ là công cụ trả lời, mà là một phần của hệ thống nhận thức mở rộng của con người. Bạn đang dùng AI để mở rộng trí nhớ, cấu trúc và quy trình suy nghĩ của mình.
- **NLP Mindset**: ngôn ngữ tự nhiên không chỉ là “bài văn”, mà là cách mô tả đúng cấu trúc của vấn đề: mục tiêu, người dùng, bối cảnh, đầu ra, giới hạn và ràng buộc.
- **AI Mindset**: đánh giá AI như một hệ thống nhiều tầng, cần định hướng bằng tư duy chiến lược, hệ thống, cấu trúc, phân rã nhiệm vụ và phản biện.

#### Ví dụ thực tế
Thay vì viết một prompt mơ hồ như:

> “Hãy giúp tôi làm kế hoạch marketing cho cửa hàng cà phê.”

Bạn nên “đưa cấu trúc trong đầu” ra dạng rõ hơn bằng ngôn ngữ tự nhiên:

> “Tôi cần một campaign playbook 3 tháng cho quán cà phê nhỏ.  
> Audience: chủ quán + 2 nhân viên.  
> Mục tiêu: tăng lượt ghé lại 15%.  
> Bối cảnh: ngân sách 20 triệu/tháng, kênh chủ yếu là Facebook và TikTok.  
> Output: bảng ưu tiên kênh, timeline 12 tuần, checklist triển khai.  
> Scope: không cần phân tích công nghệ, chỉ tập trung vào nội dung và quảng cáo địa phương.”

Khi bạn mô tả đúng “cái trong đầu” bằng ngôn ngữ có cấu trúc, bạn đã dùng AI như một phần của Extended Mind theo cách đúng đắn.

#### AI Mindset cần có 5 loại thinking

- **Strategic Thinking**: nhìn mục tiêu lớn, trade-off, thứ tự ưu tiên. Tránh làm AI “biết nhiều nhưng vô dụng” bằng cách xác định business outcome rõ trước khi chạm vào prompt.
- **Systems Thinking**: nhìn AI như một pipeline nhiều tầng: input → retrieval → memory → tool → output → eval. Lỗi nằm ở tầng nào sẽ dẫn tới hậu quả gì?
- **Structural Thinking**: nhìn bài toán theo cấu trúc: mục tiêu, audience, output, scope, ràng buộc, KPI.
- **Task Decomposition**: chia một bài toán lớn thành sub-task nhỏ, độc lập, có thứ tự. AI làm tốt nhất khi từng bước được định nghĩa rõ.
- **Critical Thinking**: AI có thể nói trôi chảy nhưng không đồng nghĩa với đúng. Luôn kiểm tra giả định, nguồn gốc, độ tin cậy và tính phù hợp với bối cảnh thật.

Nói ngắn gọn:

> Framing không chỉ là “viết prompt tốt hơn”, mà là “tổ chức tư duy bằng ngôn ngữ, rồi dùng AI như một phần của hệ thống nhận thức mở rộng”.

---

## 2. Bức tranh tổng: Buổi 1 nằm ở đâu trong toàn khóa?

Khung 7 bước SID:

> Frame → Architect → Explore → Reason → Validate → Synthesize → Transfer

Buổi 1 chính là **Frame**.

Nếu Frame sai:

- Architect (bóc tách, dựng cấu trúc) sẽ lạc,
- Explore (quét rộng) sẽ quá rộng/hẹp,
- Reason (suy luận) sẽ “sâu nhầm chỗ”,
- Validate (kiểm định) sẽ chấm nhầm tiêu chí,
- Synthesize/Transfer sẽ đóng gói ra thứ không dùng được.

Từ Buổi 2 trở đi, bạn sẽ luôn xuất phát từ **Framing Brief** viết ở buổi này.

---

## 3. Bản đồ khái niệm của Buổi 1

### 3.1. Các khái niệm trụ cột

| Khái niệm         | Nghĩa / Vai trò chính                                                                 |
|-------------------|----------------------------------------------------------------------------------------|
| Topic             | Chủ đề, miền nội dung (“marketing online”, “đào tạo nội bộ”, “dịch vụ khách hàng”…) |
| Problem Framing   | Định rõ **nhiệm vụ nhận thức** cần làm với chủ đề: hiểu/so/thiết kế/dạy/đánh giá…   |
| Goal/Output Frame | Định rõ đầu ra là **artifact gì**: bảng, framework, checklist, syllabus, rubric…    |
| Audience Framing  | Ai sẽ dùng đầu ra: nền tảng, mục tiêu, bối cảnh                                   |
| Scope Design      | Phạm vi: nói tới đâu, không nói gì, sâu tới đâu, theo góc nào                       |
| Task Definition   | Loại nhiệm vụ AI được dùng: explain / compare / diagnose / design / critique / teach |
| Framing Brief     | Bản tóm tắt 150–250 từ, gom toàn bộ 5 thứ trên, làm “đầu não” cho mọi bước sau       |
| Misframing        | Định khung sai: chủ đề đúng nhưng bài toán/đầu ra/audience/scope/task sai hoặc mơ hồ |

### 3.2. Mô hình 5W-O (phiên bản đời thường)

Khung xương đơn giản nhưng cực mạnh:

> **What – Why – Who – Where – Width/Depth – Output**

- **What**: đang bàn về cái gì? (topic, lĩnh vực, vấn đề)
- **Why**: hỏi để làm gì? (mục tiêu nhận thức, quyết định nào phụ thuộc?)
- **Who**: cho ai? (khách hàng, nhân viên, học viên, quản lý…)
- **Where**: trong bối cảnh nào? (doanh nghiệp nhỏ/vừa/lớn, ngành, ngân sách, ràng buộc)
- **Width/Depth**: rộng/sâu tới đâu? (không quá nông, không quá ôm đồm)
- **Output**: cần ra cái gì? (artifact nào, dùng để làm gì tiếp?)

Một **Framing Brief tốt** ít nhất phải chạm đủ 6 ô này.

---

## 4. Học từng kỹ thuật – với ví dụ gần với công việc đời thực

### 4.1. Kỹ thuật 1 — Problem Framing

#### 4.1.1. Cốt lõi

- **Topic** = “đang nói về cái gì”.
- **Problem** = “đang cần làm gì với cái đó”.

Ví dụ thực tế (sai):

> “Hãy giải thích thật chi tiết về marketing online, các kênh phổ biến, các chiến lược hiệu quả, các sai lầm thường gặp, đưa ví dụ trong doanh nghiệp và cho tôi lộ trình học marketing trong 6 tháng.”

Vấn đề:

- Topic = marketing online → rõ.
- Nhưng **Problem**:
  - Bạn muốn hiểu để làm gì?
  - Để tự chạy cho cửa hàng nhỏ?  
    Để thuê agency cho đúng?  
    Để đào tạo nhân viên?

AI sẽ trả lời “đúng chủ đề” nhưng **sai vấn đề**.

#### 4.1.2. Cách tư duy lại

Tự hỏi:

> “Tôi đang muốn:  
> - hiểu cho bản thân,  
> - so sánh các hướng/giải pháp,  
> - chẩn đoán vấn đề đang gặp,  
> - thiết kế thứ gì mới (khóa học, quy trình CSKH, chiến dịch),  
> - hay đánh giá/kiểm định 1 thứ hiện có?”

Đổi từ:

- “Giải thích marketing online”

sang:

- “Tôi muốn hiểu marketing online đủ để [mục đích]…”

Ví dụ tốt hơn:

- “Tôi muốn hiểu marketing online đủ để **tự thiết kế một chiến dịch 3 tháng cho cửa hàng đồ uống nhỏ, ngân sách quảng cáo 15 triệu/tháng**.”
- “Tôi muốn hiểu marketing online để **dạy lại cho đội sale hiện tại**, tập trung vào cách họ tận dụng nội dung và mạng xã hội, **không đi sâu kỹ thuật chạy ads**.”

#### 4.1.3. Prompt mẫu (để AI giúp bạn frame problem)

```text
Tôi đang quan tâm chủ đề: [TOPIC – ví dụ: đào tạo nội bộ bằng AI].

Hãy giúp tôi định khung bài toán thật sự tôi đang cần giải quyết.

Yêu cầu:
1. Liệt kê 4–6 bài toán nhận thức khác nhau có thể ẩn dưới chủ đề này, ví dụ:
   - hiểu khái niệm
   - so sánh giải pháp
   - chẩn đoán vấn đề
   - thiết kế giải pháp
   - thiết kế khóa học
   - thiết kế framework đánh giá
2. Với mỗi bài toán, mô tả:
   - mục tiêu thực sự
   - loại đầu ra (output) phù hợp
   - rủi ro nếu nhầm sang bài toán khác
3. Dựa trên mô tả của tôi: [MÔ TẢ NGẮN VỀ MỤC TIÊU/BỐI CẢNH – ví dụ: doanh nghiệp nhỏ, muốn đào tạo nhân viên sale], 
   hãy đề xuất 1 problem framing tối ưu và viết thành 1 câu rõ ràng.

Trả ra:
- 1 bảng các bài toán tiềm năng
- 1 câu problem statement bạn nghĩ phù hợp nhất với tôi.
```

---

### 4.2. Kỹ thuật 2 — Goal/Output Framing

#### 4.2.1. Cốt lõi

- Output không phải “câu trả lời dài hơn”.
- **Output = artifact tri thức / tài liệu cụ thể**.

Ví dụ các artifact:

- concept note (ghi chú khái niệm / bản ghi chú khái niệm)
- comparison table (bảng so sánh)
- 5–7-step framework (framework 5–7 bước / khung 5–7 bước)
- checklist (bảng kiểm / danh sách kiểm tra)
- decision tree (cây quyết định)
- workflow (quy trình làm việc / luồng công việc)
- syllabus (đề cương khóa học)
- rubric (bảng tiêu chí đánh giá / rubric đánh giá)
- playbook (cẩm nang triển khai / sổ tay hướng dẫn)
- script (kịch bản cuộc gọi / kịch bản buổi dạy / kịch bản hội thảo)

Sai lầm rất phổ biến:

> “Hãy giải thích thật chi tiết…”

→ không nói cần “chi tiết” dưới dạng gì.

#### 4.2.2. Ví dụ prompt sai → sửa

Prompt sai (rất giống người dùng 1–3 năm):

> “Hãy phân tích thật chi tiết về chăm sóc khách hàng cho doanh nghiệp dịch vụ, đưa ra các bước triển khai, các kịch bản cho nhân viên, các sai lầm thường gặp và cho tôi lộ trình đào tạo nhân viên CSKH trong 1 tháng.”

Lỗi:

- quá nhiều task (explain + design quy trình + design kịch bản + design khóa học),
- không nói output muốn ở dạng gì.

Sửa theo Goal/Output Framing:

> “Mục tiêu của tôi: trong 2 tuần tới, tôi phải tổ chức 1 buổi **đào tạo nội bộ 2 tiếng cho đội CSKH** của công ty dịch vụ nhỏ (call center 10 người).
> 
> Hãy:
> 1) đề xuất 3 dạng output có thể phù hợp nhất (ví dụ: outline buổi training, checklist xử lý cuộc gọi khó, bộ kịch bản thoại theo tình huống),
> 2) phân tích ưu/nhược của mỗi dạng,
> 3) sau đó chọn 1 dạng tối ưu và tạo **outline buổi training 2 tiếng** với: mục tiêu học, các phần chính, thời lượng dự kiến.”

Thấy khác biệt?

- Bài toán rõ (đào tạo nội bộ 2 tiếng),
- Audience rõ (đội CSKH),
- Output = outline buổi đào tạo,
- Scope: tập trung vào kỹ năng CSKH, không đòi hỏi xây hệ thống công nghệ.

#### 4.2.3. Template ngắn để tự check

Trước khi hỏi AI, tự hỏi:

> “Output mình cần là:
- table (bảng / bảng so sánh / bảng tổng hợp)
- framework (framework / khung 5–7 bước / mô hình khung)
- checklist (checklist / bảng kiểm / danh sách kiểm tra)
- syllabus (syllabus / đề cương khóa học / đề cương nội dung)
- rubric (rubric / bảng tiêu chí đánh giá / thang đánh giá)
- playbook (playbook / cẩm nang triển khai / sổ tay hướng dẫn)
- script (kịch bản buổi dạy / kịch bản cuộc gọi / kịch bản hội thảo)

Nếu chưa trả lời được → **chưa xong Goal Framing**.

---

### 4.3. Kỹ thuật 3 — Audience Framing

#### 4.3.1. Cốt lõi

Nội dung đúng không đủ; nó phải **đúng với người này**.

Bạn cần nêu rõ cho AI:

- nền tảng (kinh doanh, giáo dục, dịch vụ, marketing…),
- trải nghiệm với chủ đề/AI (chưa dùng / dùng 1–3 năm / rất quen),
- mục tiêu (hiểu, dạy, triển khai, quản lý),
- ràng buộc (thời gian, ngôn ngữ, tài nguyên).

Ví dụ:

> “Người học là nhân viên bán hàng đã dùng AI để viết content 1 năm, nhưng chưa được đào tạo bài bản về marketing.”

#### 4.3.2. Case thực tế

Prompt thực tế (sai):

> “Hãy giải thích về cách xây dựng chương trình đào tạo nội bộ một cách chi tiết, có ví dụ minh họa.”

AI sẽ đưa 1 bài giảng… **chung chung**.

Sửa với Audience Framing:

> “Hãy giải thích về cách xây dựng chương trình đào tạo nội bộ cho **doanh nghiệp dịch vụ nhỏ**, người học là **trưởng nhóm vận hành**, đã từng tổ chức vài buổi training nhưng **chưa có nền tảng về thiết kế khóa học**.
> 
> Bối cảnh:
> - họ ít thời gian,
> - cần công cụ đơn giản,
> - ưu tiên ví dụ gần với việc training nhân viên tuyến đầu (CSKH, bán hàng).
> 
> Hãy:
> - tránh thuật ngữ chuyên môn quá sâu,
> - tập trung vào 3–5 bước rõ ràng,
> - chỉ ra 3 lỗi phổ biến khi trưởng nhóm tự thiết kế khóa học.”

---

### 4.4. Kỹ thuật 4 — Scope Design

#### 4.4.1. Cốt lõi

**Scope tốt = chọn cái không làm rõ ràng.**

Ví dụ prompt sai (rất phổ biến):

> “Hãy dạy tôi về marketing từ A đến Z, từ kiến thức cơ bản đến triển khai chiến dịch lớn cho doanh nghiệp, từ góc nhìn chiến lược lẫn chi tiết từng kênh, giúp tôi có thể tự làm marketing cho doanh nghiệp của mình.”

Lỗi:

- A–Z,
- cơ bản → chiến dịch lớn,
- chiến lược lẫn chi tiết từng kênh,
- trong 1 shot.

Sửa với Scope:

> “Tôi **không** muốn học toàn bộ marketing từ A đến Z.
> 
> Mục tiêu hiện tại:
> - hiểu đủ về marketing online để:
>   - chọn 1–2 kênh phù hợp (ví dụ: Facebook, TikTok),
>   - thiết kế 1 chiến dịch 3 tháng cho **cửa hàng thời trang nhỏ**,
>   - và dạy lại cơ bản cho 2 nhân viên bán hàng.
> 
> Do đó:
> - **in-scope**: khái niệm cơ bản về funnel, cách chọn kênh, cách lên kế hoạch 3 tháng, cách đo lường đơn giản.
> - **out-of-scope**: tối ưu quảng cáo nâng cao, chiến lược thương hiệu dài hạn, nghiên cứu thị trường chuyên sâu.
> 
> Hãy thiết kế 1 outline nội dung 3 buổi (mỗi buổi 90 phút) phù hợp với scope trên.”

Scope rõ → AI không bị kéo đi quá xa.

---

### 4.5. Kỹ thuật 5 — Task Definition

#### 4.5.1. Cốt lõi

Bạn đang yêu cầu AI làm **nhiệm vụ gì**?

Các task điển hình:

- **Explain** – giải thích, định nghĩa, mô tả.
- **Compare** – so sánh A/B/C theo tiêu chí.
- **Diagnose** – tìm nguyên nhân, lỗi, nguyên nhân gốc.
- **Design** – tạo framework, quy trình, chiến dịch, khóa học.
- **Critique** – phản biện, tìm điểm yếu, rủi ro.
- **Teach** – soạn giáo án, bài tập, ví dụ để dạy người khác.

Sai lầm: nhét 4–5 task vào 1 prompt mà **không tách phase**.

Ví dụ xấu rất quen:

> “Hãy giải thích, so sánh, thiết kế, phản biện và dạy tôi về chăm sóc khách hàng trong một câu trả lời duy nhất, càng chi tiết càng tốt.”

Thay vào đó, **tách phase**; ví dụ:

- Explain → hiểu khái niệm CSKH tốt là gì.
- Compare → so sánh 2–3 mô hình CSKH khác nhau.
- Design → thiết kế quy trình CSKH cho doanh nghiệp của bạn.
- Critique → phản biện và tối ưu quy trình đó.
- Teach → biến quy trình thành tài liệu đào tạo nhân viên mới.

Ví dụ tốt (đã tách phase, mỗi prompt 1 task chính) có thể viết lại như sau:

```text
[Phase 1 – Explain]
Tôi đang xây chương trình chăm sóc khách hàng cho một công ty dịch vụ nhỏ (10 nhân viên CSKH tuyến đầu).

Hãy GIẢI THÍCH giúp tôi, ở mức dễ hiểu:
1) “Chăm sóc khách hàng tốt” thường được hiểu là gì trong bối cảnh doanh nghiệp dịch vụ?
2) 5–7 tiêu chí quan trọng nhất để đánh giá một trải nghiệm CSKH là tốt.

Trả lời ngắn gọn, có ví dụ đơn giản.
```

```text
[Phase 2 – Compare]
Dựa trên các tiêu chí chăm sóc khách hàng tốt ở trên, hãy SO SÁNH 3 mô hình CSKH sau:
1) Chăm sóc chủ động (chủ động gọi/lên lịch chăm sóc)
2) Chăm sóc phản ứng (chỉ xử lý khi khách yêu cầu hoặc phàn nàn)
3) Chăm sóc theo “vòng đời khách hàng” (từng giai đoạn có kịch bản riêng)

Yêu cầu:
- Trình bày dưới dạng bảng so sánh, các dòng: ưu điểm, nhược điểm, phù hợp với loại doanh nghiệp nào.
```

```text
[Phase 3 – Design]
Hãy DESIGN một QUY TRÌNH CSKH 5–7 bước cho công ty dịch vụ nhỏ của tôi, dựa trên:
- 10 nhân viên CSKH,
- chủ yếu hỗ trợ qua điện thoại và Zalo,
- khách hàng là cá nhân, không phải doanh nghiệp.

Yêu cầu:
- Mỗi bước nêu rõ: mục tiêu, ai phụ trách, đầu vào, đầu ra.
```

```text
[Phase 4 – Critique]
Hãy CRITIQUE quy trình CSKH 5–7 bước dưới đây của tôi: 
[ DÁN QUY TRÌNH HIỆN TẠI / QUY TRÌNH AI VỪA ĐỀ XUẤT ]

Yêu cầu:
1) Chỉ ra ít nhất 5 điểm yếu hoặc rủi ro (ví dụ: bước bị thiếu, chồng chéo, không thực tế với 10 nhân viên).
2) Đề xuất chỉnh sửa cụ thể cho từng điểm yếu đó.
```

```text
[Phase 5 – Teach]
Hãy biến quy trình CSKH 5–7 bước đã chỉnh sửa thành TÀI LIỆU ĐÀO TẠO cho nhân viên mới.

Yêu cầu:
1) Viết một bản tóm tắt dễ hiểu cho nhân viên tuyến đầu (không dùng jargon).
2) Đề xuất cấu trúc 1 buổi training 2 giờ:
   - mục tiêu,
   - các phần chính,
   - 1–2 hoạt động thực hành,
   - cách kiểm tra nhanh cuối buổi.
```

---

## 5. Framing Brief – sản phẩm cuối của Buổi 1

### 5.1. Framing Brief là gì?

Một đoạn **150–250 từ**, mô tả:

- topic (chủ đề)
- problem (bài toán / vấn đề cần giải quyết)
- audience (đối tượng / người nhận / người dùng đầu ra)
- context (bối cảnh / hoàn cảnh / môi trường áp dụng)
- scope (phạm vi in-scope / out-of-scope)
- draft output (output sơ bộ / dạng đầu ra dự kiến)
- main task type (task type chính / loại nhiệm vụ chính: explain/compare/design/teach/critique…)

Framing Brief **không phải prompt**; nó là mô tả bài toán để dùng:

- cho chính bạn,
- cho AI (như context),
- cho các buổi sau (bóc tách, IA, reasoning…),
- cho mentor/đồng đội hiểu bạn đang làm gì.

### 5.2. Template Framing Brief

```text
[1] Chủ đề (topic)
Tôi đang làm việc với chủ đề: [TOPIC – ví dụ: dùng AI để thiết kế chương trình đào tạo nội bộ về chăm sóc khách hàng].

[2] Bài toán (problem)
Bài toán thực sự tôi cần giải quyết là: [PROBLEM STATEMENT 1–2 câu]. 
(Mục đích cuối cùng: [MỤC ĐÍCH], ví dụ: dạy lại, thiết kế quy trình, ra quyết định…)

[3] Audience
Đầu ra của tôi sẽ dùng cho: [AI CHO TÔI? CHO TEAM? CHO NHÂN VIÊN? CHO HỌC VIÊN?]
- Nền tảng: [VD: nhân viên tuyến đầu, đã làm việc 1–3 năm, ít dùng AI]
- Mục tiêu học/dùng: [vd: hiểu để áp dụng vào công việc mỗi ngày…]

[4] Scope (in-scope / out-of-scope)
Trong phạm vi này, tôi:
- In-scope: [NHỮNG GÌ SẼ BÀN – ví dụ: kỹ năng giao tiếp, xử lý phàn nàn, quy trình 5 bước]
- Out-of-scope: [NHỮNG GÌ KHÔNG BÀN – ví dụ: hệ thống CRM, tích hợp công nghệ phức tạp] (vì [LÝ DO])

[5] Output & Task Type
Tôi đang cần AI hỗ trợ chủ yếu cho nhiệm vụ: [EXPLAIN/COMPARE/DESIGN/CRITIQUE/TEACH…]
Đầu ra ưu tiên: [VD: outline khóa 3 buổi + checklist xử lý phàn nàn + rubric đánh giá kỹ năng].

[6] Rủi ro nếu framing sai
Nếu định khung sai, rủi ro là: [VD: khóa học không bám vào vấn đề thật của nhân viên, nội dung quá lý thuyết, team không áp dụng được].
```

---

## 6. Thực hành từng bước – với prompt sai thật của bạn

### 6.1. Bài tập 1 — Misframing Diagnosis Lab (dùng prompt thật của bạn)

**Mục tiêu**  
Nhìn ra lỗi ở gốc trong cách mình hỏi AI.

**Bước 1: Lấy dữ liệu thật**

- Mở lịch sử chat AI (ChatGPT, Claude, Gemini,…),
- Chọn 3–5 prompt mà bạn:
  - đã từng rất kỳ vọng,
  - nhưng output nhận về dù “hay” vẫn không dùng được hoặc không đúng cái bạn cần.

Ví dụ (giả lập):

> “Hãy đóng vai chuyên gia hàng đầu về đào tạo, giải thích cho tôi tất cả những gì cần biết về việc xây dựng chương trình đào tạo nội bộ từ cơ bản đến nâng cao, bao gồm cấu trúc chương trình, phương pháp giảng dạy, đánh giá kết quả, ví dụ trong doanh nghiệp và lộ trình học cho tôi trở thành chuyên gia đào tạo.”

**Bước 2: Tự chấm prompt**

Cho mỗi prompt, tạo 1 bảng (viết tay, Google Doc, hoặc markdown):

| Yếu tố   | Trạng thái hiện tại                                    | Ghi chú lỗi                                      |
|----------|--------------------------------------------------------|--------------------------------------------------|
| Topic    | [Có / Không]                                          |                                                  |
| Problem  | [Rõ / Mơ hồ / Trộn nhiều bài toán]                    |                                                  |
| Audience | [Có / Mơ hồ / Không]                                  |                                                  |
| Scope    | [Có / Quá rộng / Quá hẹp / Không]                     |                                                  |
| Output   | [Rõ dạng artifact / “trả lời chi tiết”]               |                                                  |
| Task     | [1 nhiệm vụ / 3–4 nhiệm vụ trộn]                      |                                                  |

Đánh dấu lỗi, ví dụ:

- Problem: “muốn biết tất cả mọi thứ” → không phải bài toán.
- Audience: không nêu.
- Scope: từ cơ bản đến nâng cao, cho mọi kiểu doanh nghiệp.
- Task: explain + design lộ trình học → ít nhất 2 task trộn.

**Bước 3: Viết lại prompt theo tư duy Framing (chưa cần hoàn hảo)**

Đừng nhảy ngay sang “prompt đẹp”; trước hết, viết 1–3 câu tóm lại **Framing Brief rút gọn** cho prompt đó.

Ví dụ:

> “Tôi là quản lý nhân sự của một doanh nghiệp dịch vụ 50 người. Trong 1 tháng tới, tôi cần thiết kế 1 khóa đào tạo nội bộ 3 buổi (mỗi buổi 2 tiếng) cho nhân viên chăm sóc khách hàng về kỹ năng giao tiếp và xử lý phàn nàn. Tôi cần 1 outline khóa học 3 buổi + 1 checklist kỹ năng cơ bản, không đi sâu vào công cụ phần mềm.”

---

### 6.2. Bài tập 2 — One Topic, Many Problems

**Mục tiêu**  
Hiểu sâu rằng **chủ đề =/= bài toán**.

**Bước 1: Chọn 1 chủ đề trong domain của bạn**

Ví dụ:

- “Đào tạo nhân viên bán hàng bằng AI”
- “AI hỗ trợ content marketing cho doanh nghiệp nhỏ”
- “AI trợ lý cho giáo viên trung học”
- “AI hỗ trợ chăm sóc khách hàng sau bán”

**Bước 2: Liệt kê ít nhất 5 bài toán khác nhau**

Ví dụ với “AI hỗ trợ content marketing cho doanh nghiệp nhỏ”:

1. Hiểu/định nghĩa AI có thể hỗ trợ những khâu nào trong content marketing.
2. So sánh việc dùng AI vs thuê freelancer ngoài.
3. Thiết kế quy trình dùng AI để lên lịch và viết bài cho fanpage trong 3 tháng.
4. Thiết kế khóa học 2 buổi dạy nhân viên content cách dùng AI hiệu quả.
5. Thiết kế rubric đánh giá chất lượng nội dung khi có AI hỗ trợ.

**Bước 3: Với mỗi bài toán, gán 1 output chính & 1 task type**

Ví dụ:

- Bài toán 3:
  - Output: **workflow 5–7 bước** + template brief cho mỗi bài.
  - Task type: **design**.
- Bài toán 5:
  - Output: **rubric 4–5 tiêu chí, 4–5 mức mỗi tiêu chí**.
  - Task type: **design + critique**.

---

### 6.3. Bài tập 3 — Audience Shift Exercise

**Mục tiêu**  
Nhận ra audience thay đổi thì cách đặt bài toán & output cũng đổi hẳn.

**Bước 1: Chọn 1 chủ đề**

Ví dụ: **“Sử dụng AI trong marketing nội dung”**.

**Bước 2: Viết 3 phiên bản framing cho 3 audience**

- **Audience A**: Chủ doanh nghiệp nhỏ, ít dùng công nghệ.
- **Audience B**: Nhân viên content đã dùng AI 1–2 năm để viết bài.
- **Audience C**: Giám đốc marketing muốn hiểu để ra quyết định chiến lược.

Với mỗi audience, viết 3–4 câu:

- mục tiêu,
- phạm vi,
- output.

**So sánh 3 bản**: bạn sẽ thấy framing thay đổi rất mạnh, dù topic vẫn là “AI trong marketing nội dung”.

---

## 7. Assignment Buổi 1 – Framing Brief cho domain của bạn

### 7.1. Đề bài

Chọn một chủ đề thuộc domain thật của bạn (càng thực tế càng tốt).

Ví dụ:

- AI trong thiết kế chương trình đào tạo nhân viên.
- AI hỗ trợ content marketing cho doanh nghiệp nhỏ.
- AI hỗ trợ chăm sóc khách hàng.
- AI trợ lý soạn giáo án cho giáo viên.
- AI hỗ trợ xây dựng quy trình bán hàng.

Viết **1 Framing Brief hoàn chỉnh** theo template dưới.

### 7.2. Yêu cầu cấu trúc

Bài nộp nên có dạng markdown:

```markdown
Framing Brief — [Tên chủ đề]

1. Chủ đề (Topic)

...

2. Bài toán (Problem)

...

3. Audience

...

4. Scope (In-scope / Out-of-scope)

...

5. Output & Task Type

...

6. Rủi ro nếu framing sai

...
```

Gợi ý độ dài: **150–250 từ**.

### 7.3. Gợi ý rubric tự chấm

| Tiêu chí           | Mô tả                                                                                         | Điểm (0–5) |
|--------------------|-----------------------------------------------------------------------------------------------|-----------:|
| Problem clarity    | Phân biệt rõ topic và problem? Problem statement sắc, không chung chung?                     |        /5  |
| Goal/Output frame  | Artifact đầu ra được nêu rõ? (bảng, framework, syllabus, checklist…)? Dùng được ngay?        |        /5  |
| Audience fit       | Audience mô tả cụ thể (nền tảng, mục tiêu, bối cảnh), không chỉ “người mới/người dùng AI”?    |        /5  |
| Scope quality      | In-scope / out-of-scope rõ? Phù hợp với mục tiêu, không A–Z một lượt?                         |        /5  |
| Task definition    | Có chỉ ra nhiệm vụ chính (explain/compare/design/teach/critique…)? Không trộn quá nhiều?     |        /5  |
| Clarity & usability| Bản brief rõ ràng, đọc xong có thể dùng ngay làm input cho prompt stack buổi 2?              |        /5  |

Nếu tổng < 20/30, hãy quay lại chỉnh cho đến khi đạt.  
Bạn sẽ “nợ” chính mình ở các buổi sau nếu Framing Brief chưa đạt.

---

## 8. Cách dùng Buổi 1 cho các buổi sau

- **Buổi 2 (Prompt Stack)**:
  - dùng Framing Brief này làm context để:
    - thiết kế role,
    - gán rõ task per prompt,
    - tránh nhồi quá nhiều task trong 1 prompt.

- **Buổi 3–4 (Decomposition & IA)**:
  - dùng topic + scope trong brief để bóc tách và dựng cấu trúc.

- **Buổi 5 (Expansion)**:
  - dùng problem + audience để chọn trọng tâm khi quét rộng và đào sâu.

- **Buổi 6–7 (Reasoning & Validation)**:
  - dùng goal/output + task type để:
    - chọn kỹ thuật reasoning,
    - đặt tiêu chí validation.

- **Buổi 8 (Synthesis & Transfer)**:
  - dùng toàn bộ brief để:
    - chọn framework phù hợp,
    - thiết kế asset dạy/áp dụng sát với bối cảnh thực tế.

---

## 9. Tự kiểm cuối buổi – 5 câu hỏi bạn nên trả lời “Có”

- Tôi có thể nhìn vào 1 prompt dài (của chính mình) và chỉ ra:
  - nó đang thiếu gì trong: Problem, Audience, Scope, Output, Task?
- Tôi có thể viết 3–5 bài toán nhận thức khác nhau cho cùng 1 chủ đề.
- Tôi có thể nêu rõ output ưu tiên cho một nhiệm vụ  
  (VD: “tôi cần 1 framework 5–7 bước + checklist”, không chỉ “trả lời chi tiết”).
- Tôi đã viết xong Framing Brief cho 1 chủ đề thật của mình.
- Tôi cảm thấy, nếu chỉ cần thay đổi framing, chất lượng làm việc với AI của tôi đã khác đi rõ ràng, mà chưa cần kỹ thuật nâng cao.

Nếu bạn chưa thoải mái với bất kỳ câu nào ở trên, hãy:

- quay lại assignment,
- hoặc gửi lại 1 prompt cũ của bạn (trong thực tế), rồi áp dụng lại mọi thứ trong buổi này để “phẫu thuật” đến khi thấy rõ mình đã đổi.

---

