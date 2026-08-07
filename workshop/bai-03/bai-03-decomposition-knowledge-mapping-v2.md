# Buổi 3 - Decomposition & Knowledge Mapping

> Bóc tách chủ đề lớn thành bản đồ tri thức để dễ dạy, dễ triển khai và dễ làm việc với AI.

---

## 0. Bạn sẽ làm được gì sau buổi này?

Sau buổi học, bạn có thể:

1. Tách một chủ đề lớn thành cây 3-4 tầng, không rối và không trùng lặp lớn.
2. Phân biệt 3 kiểu decomposition:
- Top-down
- Functional
- Stakeholder-based
3. Tạo 2 artifact có thể dùng ngay:
- Decomposition Tree
- Functional map hoặc Stakeholder map
4. Tự kiểm được chất lượng cây/map bằng checklist và rubric.

Nếu Buổi 1 giúp bạn "định đúng bài toán" và Buổi 2 giúp bạn "thiết kế chuỗi prompt", thì Buổi 3 giúp bạn nhìn được "toàn cảnh miền tri thức" để các buổi sau đi nhanh và chắc hơn.

---

## 1. Cần chuẩn bị gì trước khi vào Buổi 3?

Bạn nên có sẵn:

1. Framing Brief từ Buổi 1:
- Topic, Problem, Audience, Scope, Output.
2. Prompt Stack V1 từ Buổi 2:
- Ít nhất 1 prompt bóc khung nội dung,
- 1 prompt tinh chỉnh,
- 1 output tạm có thể xem là "bản nháp" của domain.

Nếu chưa có Framing Brief, nên quay lại Buổi 1 trước. Không có framing rõ, decomposition sẽ dễ bị lệch hướng.

---

## 2. Vì sao phải học decomposition?

Nếu chỉ hỏi AI theo kiểu "giải thích", "liệt kê", "tóm tắt", bạn thường nhận về:

- nhiều ý hay,
- nhiều đoạn văn đẹp,
- nhưng khó xếp thành chương trình học, framework hay quy trình hành động.

Decomposition giúp bạn:

- thấy bức tranh tổng thể,
- biết cấp nào là khung lớn, cấp nào là chi tiết,
- tránh dạy học theo kiểu "nhảy ý".

Nói dễ hiểu hơn: decomposition là bước "dọn bàn" trước khi làm việc lớn.

- Nếu chưa dọn bàn: cái gì cũng quan trọng, cuối cùng không biết làm gì trước.
- Khi đã dọn bàn: bạn biết phần nào làm trước, phần nào làm sau, phần nào chưa cần làm.

### 2.1 Decomposition để làm gì trong thực tế?

Bạn dùng decomposition để:

1. Biến một chủ đề mơ hồ thành cấu trúc có thể giao việc.
2. Chia rõ đầu việc cho người hoặc cho AI assistant.
3. Giảm rủi ro "làm rất nhiều nhưng lệch mục tiêu".
4. Tăng tốc từ học hiểu sang triển khai thật.

### 2.2 Decomposition áp dụng gì khi làm chatbot?

Đây là điểm quan trọng nhất với team làm sản phẩm AI.

Khi làm chatbot, decomposition giúp bạn tách rõ 4 lớp:

1. Lớp mục tiêu: chatbot dùng để làm gì?
- trả lời FAQ,
- tư vấn lựa chọn,
- hỗ trợ quy trình,
- hay thu lead.
2. Lớp tri thức: chatbot cần biết những cụm kiến thức nào?
- chính sách,
- sản phẩm,
- quy trình xử lý,
- tình huống ngoại lệ.
3. Lớp hội thoại: chatbot cần những luồng nào?
- mở đầu,
- làm rõ nhu cầu,
- đề xuất,
- xử lý phản đối,
- chốt bước tiếp theo.
4. Lớp vận hành: đo chất lượng bằng gì?
- tỉ lệ trả lời đúng,
- tỉ lệ chuyển đổi,
- thời gian phản hồi,
- tỉ lệ phải chuyển cho người thật.

Nếu không decomposition, chatbot thường gặp 3 lỗi:

1. Trả lời đúng từng câu lẻ, nhưng không đi được cả hành trình người dùng.
2. Biết nhiều thông tin, nhưng không biết thông tin nào ưu tiên theo ngữ cảnh.
3. Văn phong nghe ổn, nhưng không tạo được hành động tiếp theo.

### 2.3 Ví dụ thân thiện: chatbot tư vấn khóa học

Bài toán thô:

> Làm chatbot tư vấn khóa học cho học viên mới.

Khi decomposition, ta tách thành:

1. Domain map (chatbot cần biết gì)
- Khóa học nào dành cho ai
- Lộ trình học theo trình độ
- Hình thức học, lịch học, học phí
- Câu hỏi thường gặp trước khi đăng ký
2. Conversation map (chatbot nói theo luồng nào)
- Chào và xác định mục tiêu học
- Hỏi nền tảng hiện tại
- Đề xuất 1-2 lộ trình phù hợp
- Giải thích điểm khác nhau
- Mời để lại thông tin hoặc đặt lịch tư vấn
3. Escalation map (khi nào chuyển người thật)
- Câu hỏi ngoài phạm vi kiến thức
- Tình huống cần thương lượng học phí
- Vấn đề kỹ thuật hoặc khiếu nại

Nhìn vào 3 map này, team có thể phân công ngay:

- Người nội dung làm Domain map.
- Người conversation design làm Conversation map.
- Người vận hành làm Escalation + KPI.

Nói ngắn gọn:

> Decomposition không phải để "vẽ cho đẹp". Nó là cách biến ý tưởng chatbot thành hệ thống có thể build, test và cải tiến.

---

## 3. Bản đồ khái niệm của Buổi 3

| Khái niệm | Ý nghĩa dễ hiểu |
|---|---|
| Decomposition | Bóc một chủ đề lớn thành các phần nhỏ hơn |
| Top-down | Chia từ tổng quan đến chi tiết |
| Functional | Chia theo chức năng và dòng xử lý input-output |
| Stakeholder-based | Chia theo góc nhìn của từng bên liên quan |
| Node | Một điểm nội dung trong cây (nhánh, lá, cụm) |
| MECE-ish | Cố gắng không trùng lớn và không thiếu lớn |

Lưu ý: một domain không có duy nhất 1 cách chia đúng. Có cách chia phù hợp hơn với bài toán và audience của bạn.

---

## 4. Kỹ thuật 1 - Top-down Decomposition

### 4.1 Cốt lõi

- Bắt đầu từ 1 chủ đề tổng.
- Chia thành 3-7 miền chính (cấp 1).
- Mỗi miền chính chia tiếp thành cấp 2.
- Nếu cần, chia tiếp cấp 3-4 để đủ dễ dạy và dễ thực thi.

### 4.2 Sai lầm phổ biến

1. Cùng cấp nhưng khác loại:
- "khái niệm" đứng chung cấp với "quy trình" và "lỗi".
2. Trùng ý ở cấp 2-3:
- đổi tên khác nhau nhưng bản chất giống nhau.
3. Chia theo cảm tính:
- thấy gì hay thì thêm, không theo tiêu chí.

### 4.3 Cách làm nhanh 15-20 phút

1. Chọn tiêu chí cho cấp 1 (nhóm năng lực, workflow, hoặc nhóm nội dung).
2. Liệt kê 3-7 nhánh cấp 1 theo cùng 1 tiêu chí.
3. Gắn node cấp 2 cho từng nhánh, mỗi nhánh 3-6 node.
4. Kiểm tra trùng lặp và đổi tên cho đồng dạng.
5. Bổ sung cấp 3 nếu cần để dạy học/phân công rõ hơn.

### 4.4 Output mẫu

```markdown
[Chủ đề tổng]
  1. [Miền chính 1]
     1.1 [Node]
     1.2 [Node]
  2. [Miền chính 2]
     2.1 [Node]
     2.2 [Node]
```

### 4.5 Checkpoint

- Các nhánh cấp 1 có cùng loại không?
- Có node nào trùng ý rõ ràng không?
- Nhìn vào cây, bạn có dạy thành 3-5 buổi được không?

---

## 5. Kỹ thuật 2 - Functional Decomposition

### 5.1 Cốt lõi

Functional decomposition trả lời:

> Từ input đến output, hệ thống này cần các chức năng nào và theo thứ tự nào?

### 5.2 Cách làm

1. Xác định workflow trung tâm (ví dụ: dùng AI thiết kế module học).
2. Liệt kê các bước từ đầu vào đến đầu ra.
3. Với 1-2 bước quan trọng, bóc tiếp thành sub-function.

### 5.3 Output mẫu

```markdown
Workflow: [Tên workflow]

1. [Chức năng 1]
2. [Chức năng 2]
   2.1 [Sub-function]
   2.2 [Sub-function]
3. [Chức năng 3]
```

### 5.4 Checkpoint

- Đã có đủ các khâu từ input tới output chưa?
- Bước nào đang quá lớn, cần tách nhỏ?
- Có bước nào lặp ý với bước khác?

---

## 6. Kỹ thuật 3 - Stakeholder Decomposition

### 6.1 Cốt lõi

Trả lời:

> Chủ đề này nhìn từ từng bên liên quan thì kỳ vọng, nỗi sợ và nhu cầu năng lực khác nhau ra sao?

### 6.2 4 câu hỏi cho mỗi stakeholder

1. Họ kỳ vọng gì?
2. Họ sợ điều gì nếu làm sai?
3. Họ cần năng lực/tri thức gì?
4. Họ sẽ dùng AI vào việc gì?

### 6.3 Output mẫu

```markdown
Stakeholder - [Tên]
- Kỳ vọng:
- Sợ:
- Cần:
- Dùng AI để:
```

### 6.4 Checkpoint

- Đã có 3-5 stakeholder chính chưa?
- Mỗi stakeholder có khác biệt thật sự hay đang copy ý?
- Map này có giúp ưu tiên nội dung dạy học/huấn luyện không?

---

## 7. So sánh output giữa 3 kỹ thuật

Đây là chỗ người mới hay nhầm nhất: cùng một chủ đề, nhưng mỗi kỹ thuật decomposition tạo ra một loại output khác nhau.

Để dễ hình dung, ta dùng một ví dụ gần gũi với người non-IT:

> Thiết kế chương trình đào tạo nội bộ cho nhân viên chăm sóc khách hàng mới.

### 7.1 Nếu dùng Top-down Decomposition

Mục tiêu là nhìn chủ đề như một cây nội dung nhiều tầng.

Output thường ra dạng:

```markdown
Chương trình đào tạo CSKH cho nhân viên mới
  1. Nền tảng dịch vụ khách hàng
     1.1 Vai trò của CSKH
     1.2 Các tiêu chuẩn phục vụ cơ bản
  2. Kỹ năng giao tiếp
     2.1 Chào hỏi và tạo thiện cảm
     2.2 Đặt câu hỏi để hiểu nhu cầu
     2.3 Giữ bình tĩnh khi khách khó chịu
  3. Xử lý tình huống
     3.1 Khiếu nại phổ biến
     3.2 Chuyển ca hoặc escalation
  4. Vận hành nội bộ
     4.1 Ghi nhận thông tin
     4.2 Phối hợp với bộ phận liên quan
```

Bạn dùng output này khi cần:

- dựng syllabus,
- chia module học,
- nhìn toàn cảnh nội dung cần dạy.

### 7.2 Nếu dùng Functional Decomposition

Mục tiêu là nhìn chương trình như một quy trình vận hành hoặc quy trình học.

Output thường ra dạng:

```markdown
Workflow: Đào tạo nhân viên CSKH mới

1. Xác định chuẩn đầu ra sau đào tạo
2. Chọn các nhóm kỹ năng bắt buộc
3. Thiết kế nội dung theo thứ tự học
4. Tạo hoạt động thực hành cho từng kỹ năng
5. Kiểm tra mức độ đạt chuẩn
6. Theo dõi áp dụng sau đào tạo
```

Bạn dùng output này khi cần:

- thiết kế flow triển khai,
- phân công bước làm,
- xây checklist vận hành hoặc timeline.

### 7.3 Nếu dùng Stakeholder Decomposition

Mục tiêu là nhìn chủ đề từ góc nhìn của những người liên quan.

Output thường ra dạng:

```markdown
Nhân viên CSKH mới
- Kỳ vọng: hiểu việc nhanh, tự tin khi nói chuyện với khách
- Sợ: trả lời sai, bị khách phản ứng, không nhớ quy trình
- Cần: kỹ năng giao tiếp, xử lý tình huống, biết khi nào cần hỏi hỗ trợ

Trưởng nhóm CSKH
- Kỳ vọng: nhân viên lên việc nhanh, giảm lỗi lặp lại
- Sợ: đào tạo xong nhưng không áp dụng được
- Cần: tiêu chí quan sát, checklist kèm cặp, cách phản hồi

Bộ phận vận hành
- Kỳ vọng: thông tin khách được ghi nhận đúng, phối hợp trơn tru
- Sợ: nhân viên bỏ sót thông tin hoặc chuyển sai việc
- Cần: quy trình bàn giao, chuẩn ghi chú, mốc escalation
```

Bạn dùng output này khi cần:

- thiết kế nội dung sát từng vai trò,
- ưu tiên pain point thật,
- tránh dạy một kiểu cho tất cả mọi người.

### 7.4 Nhìn nhanh sự khác nhau

| Kỹ thuật | Câu hỏi chính | Output điển hình | Dùng khi nào? |
|---|---|---|---|
| Top-down | Chủ đề này gồm những phần nào? | Cây nội dung nhiều tầng | Dựng syllabus, khung kiến thức |
| Functional | Việc này diễn ra theo dòng bước nào? | Workflow / process map | Thiết kế quy trình, triển khai |
| Stakeholder | Mỗi bên liên quan cần gì và lo gì? | Stakeholder map | Cá nhân hóa nội dung, ưu tiên pain point |

Nói ngắn gọn:

> Top-down cho bạn bản đồ nội dung. Functional cho bạn bản đồ hành động. Stakeholder cho bạn bản đồ con người.

---

## 8. Mẹo nhỏ để giữ bài dễ hiểu

Khi viết bài decomposition, giữ nhịp sau để người mới dễ theo:

1. Nói rõ "làm để làm gì" trước khi vào lý thuyết.
2. Mỗi kỹ thuật đều giữ 1 khung giống nhau:
- Cốt lõi
- Sai lầm
- Cách làm
- Output mẫu
- Checkpoint
3. Dùng 1 case xuyên suốt, không đổi case liên tục.
4. Mỗi 1-2 phần có 1 dòng "Nói ngắn gọn" để đóng lại ý chính.

---

## 9. Bài tập trên lớp

### Bài tập 1 - Vẽ Decomposition Tree 3-4 tầng

Yêu cầu tối thiểu:

- Ít nhất 3 nhánh cấp 1.
- Tổng ít nhất 20 node.
- Cùng cấp không trộn quá nhiều loại node.

### Bài tập 2 - Chọn 1 map bổ sung

Chọn 1 trong 2:

1. Functional map, hoặc
2. Stakeholder map.

### Bài tập 3 - Giải thích lựa chọn

Viết đoạn 150-250 từ:

- Vì sao bạn chọn tiêu chí chia cấp 1 như vậy?
- Cây/map này giúp gì cho buổi 4 và project của bạn?

---

## 10. Assignment cuối buổi

```markdown
# Buổi 3 Assignment - [Tên domain]

## 1. Framing tóm tắt (3-5 dòng)
## 2. Decomposition Tree (3-4 tầng)
## 3. Functional map hoặc Stakeholder map
## 4. Lý giải lựa chọn (150-250 từ)
## 5. Tự chấm theo rubric
```

---

## 11. Rubric tự chấm

| Tiêu chí | Câu hỏi kiểm tra | Điểm |
|---|---|---:|
| Logic cấp 1 | Các nhánh cấp 1 có đồng dạng không? | /5 |
| Breadth | Có bao quát đủ phần quan trọng của domain không? | /5 |
| Rõ cấp 2-3 | Node cùng cấp có ít trùng lặp và dễ phân biệt không? | /5 |
| Map bổ sung | Functional/Stakeholder map có dùng được trong thực tế không? | /5 |
| Tính dạy được | Nhìn vào cây/map có dạy ngay thành buổi học được không? | /5 |
| Clarity | Tài liệu có mạch lạc, người mới đọc có theo được không? | /5 |

Thang điểm gợi ý:

- 0-14: Cần xem lại tiêu chí chia cấp 1.
- 15-22: Đã có khung, cần sửa trùng lặp và clarity.
- 23-30: Tốt, có thể mang sang Buổi 4.

---

## 12. Kết nối sang Buổi 4

Buổi 4 sẽ dùng chính các artifact này để làm Information Architecture:

1. Từ Decomposition Tree -> chuẩn hóa taxonomy và hierarchy.
2. Từ Functional/Stakeholder map -> thiết kế matrix và luồng điều hướng nội dung.

Nói ngắn gọn:

> Buổi 3 tạo bản đồ. Buổi 4 dùng bản đồ để xây kiến trúc thông tin.

---

## 13. Tự kiểm cuối buổi

Trước khi chuyển sang Buổi 4, tự trả lời 5 câu:

1. Tôi đã có cây 3-4 tầng cho domain thật của mình chưa?
2. Tôi đã có ít nhất 1 map bổ sung (functional hoặc stakeholder) chưa?
3. Tôi có biết node nào trùng lặp và cách sửa không?
4. Tôi có thể dùng cây/map này để dạy người khác không?
5. Tôi có biết cách biến cây/map thành taxonomy ở Buổi 4 không?

Nếu còn "chưa" ở câu nào, sửa ngay artifact trước khi học tiếp.

---

*Nội dung được xây dựng theo hướng dẫn Structured Intelligence Design (SID) và được tinh chỉnh theo phong cách thân thiện, dễ hiểu của Buổi 1-2.*
