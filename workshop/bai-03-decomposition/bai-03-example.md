# Bài 3 — Decomposition & Knowledge Mapping với Ví dụ "Báo Cáo Tài Chính Tháng"

## Tóm tắt nhanh

**Bài 3 (L3)** dạy cách **bóc tách một domain lớn thành bản đồ tri thức có cấu trúc**. Nếu domain của bạn là "**tạo báo cáo tài chính tháng**", bài này giúp bạn:

1. **Conceptual**: Hiểu domain này gồm những khái niệm, module, nhóm nội dung nào
2. **Functional**: Hiểu quy trình từ khi nhận dữ liệu cho đến khi output báo cáo hoàn chỉnh
3. **Stakeholder**: Hiểu nhu cầu của từng bên (kế toán, quản lý, ban giám đốc)

Bài 3 là **nền tảng không thể thiếu** để sau này xây dựng **agent tạo báo cáo tài chính tự động**.

---

## 3 Loại Decomposition — Ứng dụng vào Báo Cáo Tài Chính

### Loại 1️⃣: **Conceptual Decomposition** — Cây khái niệm

**Mục tiêu**: Bóc domain thành **cây khái niệm 3–4 tầng**, từ tổng quan đến chi tiết.

**Ví dụ: Báo cáo tài chính tháng**
<img width="1472" height="1160" alt="image" src="https://github.com/user-attachments/assets/c385e15f-ebcc-485d-a80f-a2badbe87f6a" />


**Lý giải:**
- **Cấp 1** (5 nhóm chính): Dữ liệu đầu vào → Xử lý → Báo cáo → Phân tích
- Mỗi nhóm là **một giai đoạn hoàn chỉnh** trong quy trình
- **Cấp 2** (3–4 node con) bóc tách chi tiết từng giai đoạn
- **Cấp 3** (tùy chọn) bóc tách thêm nếu một node cấp 2 quá phức tạp

Cấu trúc này giúp bạn:
- 🎓 **Dạy** nhân viên kế toán từng bước trong quy trình
- 📚 **Tổ chức Knowledge Base** cho agent (mỗi node = 1 file)
- 📊 **Thiết kế output schema** (cấu trúc dữ liệu của báo cáo)

---

### Loại 2️⃣: **Functional Decomposition** — Quy trình từ input → output

**Mục tiêu**: Bóc domain theo **workflow thực tế**, từ khi nhận dữ liệu đến output báo cáo hoàn chỉnh.
<img width="1472" height="768" alt="image" src="https://github.com/user-attachments/assets/5a5a24d5-7438-473b-a569-c7179b4a35a5" />


**Lý giải quy trình:**

```
INPUT: Dữ liệu thô từ hệ thống bán hàng, kế toán, kho hàng
  ↓
Bước 1: Xác thực & làm sạch
  • Check số liệu (có thiếu/lỗi không?)
  • Điều chỉnh ghi sai (nếu có)
  • Output: Dữ liệu sạch, đầy đủ
  ↓
Bước 2: Tính toán & hợp nhất
  • Tính lãi suất, khấu hao, thuế
  • Loại trừ giao dịch nội bộ
  • Output: Số liệu tính toán hoàn chỉnh
  ↓
Bước 3: Generate báo cáo tài chính cơ bản
  • Bảng kế toán (BKD, BQVĐ, DCT)
  • Cash flow statement
  • Output: 3–4 bảng báo cáo
  ↓
Bước 4: Phân tích & kiểm định
  • Tính ratio tài chính
  • So sánh kỳ trước
  • Phát hiện lỗi/điểm lạ
  ↓
Bước 5: Tạo visualizations & insights
  • Vẽ biểu đồ xu hướng
  • Viết nhận xét (insights)
  ↓
Bước 6: Format & export
  • Dàn trang, format đẹp
  • Export PDF/Excel
  ↓
OUTPUT: Báo cáo hoàn chỉnh sẵn sàng trình ban giám đốc
```

Cấu trúc này **cực kỳ quan trọng** để thiết kế **agent tạo báo cáo tự động**:
- Mỗi bước = **1 prompt hoặc 1 quy trình con**
- Giữa các bước có **state machine** (output bước n = input bước n+1)
- Có thể **parallelize** hoặc **branch** một số bước (vd: tính toán + kiểm định có thể chạy song song)

---

### Loại 3️⃣: **Stakeholder Decomposition** — Góc nhìn từng bên

**Mục tiêu**: Nhìn domain từ góc nhìn của **người thực tế** dùng báo cáo này.

| **Stakeholder** | **Kỳ vọng gì** | **Sợ điều gì** | **Cần năng lực** | **Dùng báo cáo để** |
|---|---|---|---|---|
| **Kế toán** | Quy trình nhanh, chính xác, tuân thủ luật | Lỗi tính toán, thiếu liệu, bị kiểm toán chỉ trích | Nắm quy trình, tính toán, điều chỉnh hạch toán | Xác thực dữ liệu, tính toán, kiểm định nội bộ |
| **Quản lý tài chính** | Nhìn rõ tình hình tiền, lợi nhuận, xu hướng | Bị bất ngờ (thiếu tiền, lỗ bất ngờ), báo cáo sai | Đọc hiểu báo cáo, phân tích ratio, nhận diện trend | Theo dõi tình hình, phát hiện vấn đề sớm |
| **Ban giám đốc / CEO** | Tóm tắt nhanh, so sánh với plan, dự báo tương lai | Không biết tình hình thực tế, bị đánh lừa | Phân tích chiến lược, nhận thức kinh doanh | Ra quyết định chiến lược, báo cáo cho cổ đông |
| **Kiểm toán viên** | Báo cáo rõ ràng, có thuyết minh, trace back được | Thiếu bằng cứ, không chứng minh được | Kiểm tra độ trung thực, compliance | Độc lập xác nhận tính chính xác, tuân thủ |
| **Nhân viên bán hàng** | (Gián tiếp) Biết được kết quả từ bán hàng của họ | Không biết đóng góp của mình, kết quả sai | Hiểu được commission/bonus từ báo cáo | Tính lương, bonus, đánh giá hiệu suất |

**Ý nghĩa:**
- Mỗi **stakeholder khác nhau** → Báo cáo cần có **phần khác nhau**
- **Kế toán** cần chi tiết, **CEO** cần tóm tắt
- **Kiểm toán** cần thuyết minh đầy đủ, **quản lý** cần insights nhanh
- Khi thiết kế **agent tạo báo cáo**, phải có **branching logic**: "Bạn là ai? → Tạo báo cáo phù hợp"

---

## Tại sao Decomposition quan trọng cho việc tạo Agent?

Khi bạn muốn **tạo 1 agent tự động hóa báo cáo tài chính**, decomposition là **nền tảng**:

### 1️⃣ **Conceptual Decomposition** → Tổ chức Knowledge Base

```
KB cho agent:
├─ 1. Dữ liệu đầu vào
│  ├─ 1.1 Cách đọc dữ liệu từ hệ ERP
│  ├─ 1.2 Làm sạch outliers
│  └─ 1.3 Điều chỉnh hạch toán
├─ 2. Tính toán & xử lý
│  ├─ 2.1 Công thức tính lãi suất
│  ├─ 2.2 Công thức khấu hao
│  └─ 2.3 Qui tắc loại trừ nội bộ
├─ 3. Báo cáo chính
│  ├─ 3.1 Template BCTC
│  ├─ 3.2 Template Cash flow
│  └─ 3.3 Notes template
...
```

**→ Agent có thể:**
- Retrieve dúng **node** từ KB theo context
- Không bị confuse (không lẫn "dữ liệu đầu vào" với "báo cáo")
- Expand hoặc contract chi tiết theo **confidence label**

### 2️⃣ **Functional Decomposition** → Thiết kế Prompt Stack

```
Agent workflow:
Phase 1 (Validate): Prompt để xác thực dữ liệu
  → Output: ✓ Dữ liệu OK / ✗ Lỗi cần fix

Phase 2 (Calculate): Prompt để tính toán
  → Output: Số liệu tính toán

Phase 3 (Report): Prompt để tạo báo cáo
  → Output: BCTC thô

Phase 4 (Analyze): Prompt để phân tích & kiểm định
  → Output: Insights, cảnh báo

Phase 5 (Format): Prompt để format đẹp
  → Output: Báo cáo PDF/Excel hoàn chỉnh
```

**→ Agent có:**
- **Clear workflow**: từng phase có role rõ ràng
- **State machine**: output phase N = input phase N+1
- **Testability**: dễ test từng phase riêng lẻ

### 3️⃣ **Stakeholder Decomposition** → Thiết kế Persona-based Output

```
Agent với branching logic:

User input: "Tôi cần báo cáo" + "Tôi là [role]?"

IF role = "Kế toán":
  → Generate chi tiết: tất cả bảng, thuyết minh đầy đủ
  → Format: Excel với tab riêng

ELSE IF role = "Quản lý tài chính":
  → Generate tóm tắt: trang 1 summary + key ratios
  → Format: PDF 3 trang

ELSE IF role = "CEO":
  → Generate executive summary: 1 trang, chỉ insights
  → Format: PDF 1 trang

ELSE IF role = "Kiểm toán":
  → Generate full audit trail: tất cả + footnotes
  → Format: Excel với trace link
```

**→ Agent có:**
- **Flexible output**: cùng 1 agent, output khác nhau
- **User-centric**: báo cáo match nhu cầu thực tế
- **Reusability**: 1 KB, 1 workflow, N output formats

---

## Ví dụ cụ thể: Từ Decomposition đến Agent thực tế

### **Bài toán**: Tạo agent tự động hóa báo cáo tài chính tháng

**Bước 1: Làm Conceptual Decomposition** (từ diagram ở trên)
- Hiểu domain gồm 5 nhóm: Dữ liệu → Tính toán → Báo cáo → Phân tích
- Mỗi nhóm gồm 3–4 node chi tiết

**Bước 2: Làm Functional Decomposition** (từ flow diagram ở trên)
- Xác định 6 bước chính từ input đến output
- Mỗi bước có input/output rõ ràng

**Bước 3: Làm Stakeholder Decomposition** (từ bảng ở trên)
- Nhận ra có 5 stakeholder khác nhau
- Mỗi stakeholder cần output khác nhau

**Bước 4: Thiết kế Prompt Stack** (từ Bài 2)
```
Master Instruction (RTC-COE):
  Role: Chuyên gia báo cáo tài chính
  Task: Tạo báo cáo tài chính hoàn chỉnh từ dữ liệu thô
  Context: [Chi tiết từ Conceptual decomposition]
  Constraints: [Qui tắc từ Functional decomposition]
  Output: [Theo stakeholder]
  Evaluation: [Criteria]

Prompt Phase 1 (Validate):
  → Input: Raw data
  → Output: Cleaned data + validation report

Prompt Phase 2 (Calculate):
  → Input: Cleaned data
  → Output: Computed numbers

...
```

**Bước 5: Thiết kế Knowledge Base** (từ Conceptual tree)
- File 1: `1_dung_lieu_dau_vao.md` - Cách đọc dữ liệu từ ERP
- File 2: `1_1_lam_sach_data.md` - Làm sạch outliers
- File 3: `2_tinh_toan_lai_suat.md` - Công thức lãi suất
- ... (mỗi node = 1 file)

**Bước 6: Thiết kế Test Suite** (từ Stakeholder map)
```
Test case 1 (Kế toán path):
  Input: Raw data từ tháng 1
  Expected output: Báo cáo chi tiết + thuyết minh
  ✓ Test pass nếu: có 4 bảng + đầy đủ footnotes

Test case 2 (CEO path):
  Input: Cùng raw data
  Expected output: Executive summary 1 trang
  ✓ Test pass nếu: summary ≤ 5 KPIs, 3 insights

Test case 3 (Kiểm toán path):
  Input: Cùng raw data
  Expected output: Full audit trail + link traceability
  ✓ Test pass nếu: mỗi số liệu có trace link
```

---

## Tóm tắt: 3 Loại Decomposition cho Báo Cáo Tài Chính

| Loại | Dùng để | Output | Kỹ thuật | Áp dụng vào Agent |
|---|---|---|---|---|
| **Conceptual** | Hiểu domain gồm những gì | Cây 3–4 tầng, MECE | Top-down, không trùng ý | Tổ chức KB, chunking strategy |
| **Functional** | Hiểu quy trình như thế nào | Workflow 6–8 bước | Input → output, sequence | Thiết kế Prompt Stack phases, state machine |
| **Stakeholder** | Hiểu ai cần gì | Bảng 5–7 stakeholder | Expectation, fear, need, use-case | Branching logic, persona-based output |

---

## Bài tập tự làm (cho domain của bạn)

Nếu bạn muốn practice với domain báo cáo tài chính:

**Bài tập 1**: Làm lại **Conceptual Decomposition**
- Lấy 5 nhóm ở diagram trên, bóc tách thêm 1 cấp
- Ví dụ: Node "1.1 Dữ liệu bán hàng" → Bóc thành 3 node: "bán hàng theo kênh", "bán hàng theo sản phẩm", "giảm giá & hoàn lại"

**Bài tập 2**: Làm lại **Functional Decomposition**
- Lấy flow 6 bước ở diagram trên, mở rộng bước 4 "Phân tích & kiểm định" thành 3 sub-step

**Bài tập 3**: Làm **Stakeholder Decomposition**
- Thêm 2 stakeholder mới: "Cổ đông", "Ngân hàng cho vay"
- Trả lời 4 câu hỏi cho từng stakeholder

---

Có muốn tôi:
1. **Tạo Master Instruction** cho agent báo cáo tài chính dựa trên decomposition này?
2. **Thiết kế Prompt Stack** cụ thể (6 phase)?
3. **Viết test case** hoàn chỉnh cho từng stakeholder?

---

*SID Coach Pro v5.0 — Powered by Structured Intelligence Design Framework - Binh Truong*
