# Buổi 2 — Prompt như Giao Diện Nhận Thức & Prompt Stack

> Từ một câu lệnh đơn lẻ đến chuỗi tương tác có cấu trúc với AI

---

## 0. Chuẩn bị trước Buổi 2

Trước khi bắt đầu, người học cần có một **Framing Brief** từ Buổi 1 cho một bài toán thật trong công việc hoặc đời sống. Framing Brief nên nêu rõ:

- Topic: đang làm việc với chủ đề gì?
- Problem: cần giải quyết bài toán nào?
- Audience: ai sẽ sử dụng kết quả?
- Scope: phần nào nằm trong và ngoài phạm vi?
- Output: cần tạo ra artifact gì?
- Task type: AI cần giải thích, phân tích, so sánh, thiết kế hay đánh giá?

Người học cũng nên chuẩn bị 2–3 prompt đã từng sử dụng nhưng cho kết quả chưa như mong đợi. Đây sẽ là nguyên liệu để phân tích và viết lại trong phần thực hành.

Nếu chưa có Framing Brief, nên hoàn thành assignment Buổi 1 trước. Prompt tốt không thể bù hoàn toàn cho một bài toán được định khung sai.

---

## 1. Mục tiêu của Buổi 2

Kết thúc Buổi 2, người học có thể:

1. Hiểu prompt là một **giao diện nhận thức** để hướng dẫn AI thực hiện nhiệm vụ, không chỉ là một câu hỏi.
2. Phân biệt được prompt viết theo cảm tính với prompt được thiết kế có chủ đích.
3. Hiểu Prompt Engineering ở mức nền tảng và biết các nguyên tắc cần thiết để cải thiện một prompt.
4. Dùng khung **RTC-COE** để thiết kế và kiểm tra một prompt:
   - Role
   - Task
   - Context
   - Constraints
   - Output
   - Evaluation
5. Bóc một bài toán phức tạp thành 3–6 task hoặc step có thứ tự.
6. Chuyển các task đã bóc tách thành một **Prompt Stack** có đầu vào, đầu ra và checkpoint.
7. Viết được Prompt Stack V1 cho một domain thật, bám sát Framing Brief từ Buổi 1.

Luồng học chính của buổi này là:

```text
Prompt
→ Prompt Engineering
→ RTC-COE
→ Task Decomposition
→ Prompt Stack
```

---

## 2. Prompt là gì?

### 2.1. Prompt không chỉ là một câu hỏi

Trong cách dùng phổ biến, prompt thường được hiểu là câu người dùng nhập vào ô chat. Cách hiểu này đúng nhưng chưa đủ.

**Prompt** là phần hướng dẫn, thông tin hoặc dữ liệu mà người dùng cung cấp để AI thực hiện một nhiệm vụ.

Một prompt có thể chỉ gồm một câu hỏi ngắn:

```text
KPI là gì?
```

Nhưng prompt cũng có thể chứa:

- nhiệm vụ cần thực hiện;
- bối cảnh;
- dữ liệu đầu vào;
- giới hạn cần tuân thủ;
- dạng đầu ra;
- tiêu chí để tự kiểm tra chất lượng.

Ví dụ:

```text
Hãy viết một email thông báo thay đổi lịch họp cho đội sales.

Bối cảnh:
- Cuộc họp chuyển từ 9:00 sáng thứ Hai sang 2:00 chiều thứ Ba.
- Lý do: trưởng bộ phận phải tham gia cuộc họp với khách hàng.
- Người nhận: 12 nhân viên sales.

Yêu cầu:
- Giọng lịch sự, trực tiếp.
- Không dài quá 150 từ.
- Nêu rõ thời gian mới và yêu cầu mọi người xác nhận đã nhận thông báo.
```

Đây không còn là một câu hỏi đơn thuần. Nó là một giao diện bằng ngôn ngữ để điều khiển AI tạo ra một đầu ra cụ thể.

### 2.2. Vì sao gọi prompt là “giao diện nhận thức”?

Khi sử dụng một phần mềm thông thường, người dùng điều khiển hệ thống qua nút bấm, menu và biểu mẫu. Khi sử dụng AI tạo sinh, người dùng chủ yếu điều khiển hệ thống bằng ngôn ngữ.

Ngôn ngữ trở thành giao diện để chỉ định:

- AI cần chú ý đến điều gì;
- cần thực hiện loại nhiệm vụ nào;
- cần bỏ qua điều gì;
- cần tổ chức kết quả ra sao;
- cần dùng tiêu chí nào để kiểm tra.

Vì vậy, chất lượng prompt không chỉ liên quan đến cách viết câu. Nó phản ánh cách người dùng hiểu và tổ chức bài toán.

Một prompt mơ hồ thường là dấu hiệu của một bài toán nhận thức chưa được làm rõ.

---

## 3. Từ prompt cảm tính đến Prompt Engineering

### 3.1. Prompt cảm tính

Người dùng mới thường viết prompt theo cách nghĩ đến đâu viết đến đó:

```text
Hãy phân tích thật chi tiết về chăm sóc khách hàng và đưa ra mọi thứ tôi cần biết.
```

Prompt này không hẳn sai, nhưng AI phải tự đoán quá nhiều:

- “phân tích” để làm gì?
- dành cho nhân viên mới hay quản lý?
- chăm sóc khách hàng qua điện thoại, cửa hàng hay mạng xã hội?
- đầu ra cần là tài liệu đào tạo, checklist hay quy trình?
- “mọi thứ” rộng đến đâu?

Kết quả có thể dài và nghe hợp lý, nhưng khó dùng trong một tình huống cụ thể.

### 3.2. Prompt Engineering là gì?

**Prompt Engineering** là quá trình thiết kế, kiểm tra và cải tiến prompt để AI hiểu đúng nhiệm vụ và tạo ra đầu ra phù hợp hơn.

Ở mức nền tảng, Prompt Engineering không phải là việc tìm “câu thần chú” hoặc sử dụng từ ngữ bí mật. Nó là một vòng lặp có chủ đích:

```text
Xác định nhiệm vụ
→ Viết prompt
→ Xem kết quả
→ Phát hiện điểm thiếu hoặc sai
→ Điều chỉnh prompt
→ Thử lại
```

Prompt Engineering tốt không được đo bằng độ dài của prompt. Nó được đo bằng mức độ prompt giúp AI:

- hiểu đúng nhiệm vụ;
- sử dụng đúng bối cảnh;
- tạo đúng loại đầu ra;
- tuân thủ giới hạn;
- cho kết quả có thể kiểm tra và sử dụng.

### 3.3. Sáu nguyên tắc nền tảng

#### Nguyên tắc 1 — Nêu rõ nhiệm vụ chính

Một prompt nên có một nhiệm vụ chính hoặc một nhóm nhiệm vụ có quan hệ trực tiếp.

Không tốt:

```text
Hãy giải thích, phân tích, so sánh, viết quy trình, làm checklist và thiết kế khóa học về onboarding.
```

Tốt hơn:

```text
Hãy thiết kế một khung nội dung onboarding cho nhân viên mới.
```

Các nhiệm vụ như viết quy trình, tạo checklist và xây lịch đào tạo có thể được thực hiện ở những bước sau.

#### Nguyên tắc 2 — Cung cấp đủ bối cảnh

AI cần biết ai sẽ dùng kết quả, trong tình huống nào và với mục tiêu gì.

```text
Đối tượng là nhân viên sales mới, chưa có kinh nghiệm trong ngành. Công ty có 20 nhân viên và chỉ có 5 ngày để onboarding.
```

Context không cần dài. Nó chỉ cần đủ để thay đổi cách AI xử lý nhiệm vụ.

#### Nguyên tắc 3 — Đặt constraints có ý nghĩa

Constraints là các giới hạn giúp AI tránh tạo ra kết quả quá rộng hoặc không phù hợp.

Ví dụ:

- không đi sâu vào phần mềm chuyên dụng;
- chỉ đề xuất hoạt động có thể thực hiện trong 5 ngày;
- không vượt quá 6 nhóm nội dung;
- dùng ngôn ngữ dễ hiểu cho người mới;
- không đưa ra khuyến nghị pháp lý.

“Thật chuyên sâu”, “cực kỳ chi tiết” hoặc “hay nhất có thể” không phải constraints tốt vì khó kiểm tra.

#### Nguyên tắc 4 — Chỉ định dạng đầu ra

Đầu ra càng rõ, khả năng sử dụng càng cao.

Thay vì:

```text
Hãy cho tôi kế hoạch onboarding.
```

Có thể viết:

```text
Hãy trình bày thành bảng gồm: ngày, mục tiêu, nội dung, người phụ trách và đầu ra cần hoàn thành.
```

#### Nguyên tắc 5 — Cung cấp reference hoặc example khi cần

Khi đầu ra khó mô tả chỉ bằng yêu cầu, có thể đưa một ví dụ, mẫu tham khảo hoặc tiêu chuẩn.

Ví dụ:

```text
Mỗi hoạt động nên được mô tả theo mẫu:
Tên hoạt động → mục tiêu → thời lượng → cách thực hiện → dấu hiệu hoàn thành.
```

#### Nguyên tắc 6 — Đánh giá và cải tiến

Không nên coi output đầu tiên là kết quả cuối cùng. Sau mỗi lần chạy, cần hỏi:

- AI đã hiểu đúng nhiệm vụ chưa?
- Có thiếu bối cảnh quan trọng không?
- Đầu ra có đúng format không?
- Có phần nào chung chung hoặc không dùng được?
- Prompt cần sửa, hay bài toán cần tách thành bước nhỏ hơn?

Nguyên tắc cuối cùng dẫn đến một vấn đề quan trọng: một prompt được viết tốt vẫn có thể không phù hợp nếu bài toán chứa quá nhiều nhiệm vụ. Khi đó, ta cần Task Decomposition và Prompt Stack.

---

## 4. RTC-COE — Khung thiết kế một prompt

### 4.1. Vì sao cần RTC-COE?

Nếu chỉ ghi nhớ các nguyên tắc chung, người học vẫn có thể bỏ sót thành phần quan trọng. RTC-COE cung cấp một khung đơn giản để thiết kế hoặc kiểm tra một prompt.

| Thành phần | Câu hỏi cần trả lời |
|---|---|
| **Role** | AI nên tiếp cận nhiệm vụ từ góc nhìn hoặc năng lực nào? |
| **Task** | AI cần thực hiện nhiệm vụ chính gì? |
| **Context** | Bối cảnh, đối tượng và dữ liệu cần thiết là gì? |
| **Constraints** | Những giới hạn hoặc điều cần tránh là gì? |
| **Output** | Kết quả cần được trình bày thành artifact nào? |
| **Evaluation** | Dựa vào tiêu chí nào để biết output đạt yêu cầu? |

RTC-COE không phải công thức bắt buộc phải viết đủ sáu nhãn trong mọi prompt. Đây là checklist tư duy. Một prompt đơn giản có thể không cần Role hoặc Evaluation. Tuy nhiên, với nhiệm vụ quan trọng hoặc phức tạp, việc kiểm tra đủ sáu thành phần giúp giảm sự mơ hồ.

### 4.2. Role

Role giúp xác định góc nhìn hoặc loại chuyên môn phù hợp.

Ví dụ:

```text
Đóng vai người phụ trách đào tạo nội bộ có kinh nghiệm onboarding nhân viên mới.
```

Role chỉ hữu ích khi nó thay đổi cách AI xử lý nhiệm vụ. Các cụm như “chuyên gia hàng đầu thế giới” thường không cung cấp thêm thông tin thực chất.

### 4.3. Task

Task là phần quan trọng nhất. Nó mô tả hành động nhận thức chính mà AI cần thực hiện.

Một số loại task phổ biến:

- Explain: giải thích.
- Extract: trích xuất.
- Classify: phân loại.
- Compare: so sánh.
- Analyze: phân tích.
- Design: thiết kế.
- Evaluate: đánh giá.
- Rewrite: viết lại.

Task nên dùng động từ rõ và có đối tượng cụ thể.

### 4.4. Context

Context trả lời các câu hỏi:

- ai sẽ dùng đầu ra?
- bài toán xảy ra trong hoàn cảnh nào?
- dữ liệu hoặc thông tin nền nào ảnh hưởng đến kết quả?
- người dùng đã có gì và còn thiếu gì?

Context tốt giúp AI tránh trả lời theo tình huống chung chung.

### 4.5. Constraints

Constraints định nghĩa giới hạn của nhiệm vụ. Có thể bao gồm:

- độ dài;
- phạm vi;
- thời gian;
- ngân sách;
- mức độ chuyên môn;
- điều bắt buộc phải có;
- điều không được làm.

Constraints nên có khả năng quan sát hoặc kiểm tra.

### 4.6. Output

Output chỉ định artifact cần tạo ra, ví dụ:

- bảng;
- checklist;
- outline;
- workflow;
- email;
- SOP;
- rubric;
- kế hoạch theo tuần;
- danh sách câu hỏi phỏng vấn.

Output rõ giúp chuyển kết quả AI từ “nội dung để đọc” thành “tài sản để sử dụng”.

### 4.7. Evaluation

Evaluation xác định dấu hiệu của một output tốt.

Ví dụ:

```text
Output đạt yêu cầu khi:
- bao phủ đủ ba nhóm: kiến thức công ty, kỹ năng công việc và quy trình phối hợp;
- mỗi hoạt động có người phụ trách;
- toàn bộ chương trình có thể hoàn thành trong 5 ngày;
- nhân viên mới tạo ra ít nhất một đầu ra quan sát được mỗi ngày.
```

Evaluation đặc biệt hữu ích khi yêu cầu AI tự kiểm tra, tự phản biện hoặc khi người dùng cần so sánh nhiều phương án.

---

## 5. Ví dụ RTC-COE cho người dùng non-IT

### 5.1. Ví dụ A — Thiết kế onboarding cho nhân viên mới

#### Prompt viết theo cảm tính

```text
Hãy giúp tôi thiết kế chương trình onboarding thật đầy đủ cho nhân viên mới, gồm nội dung đào tạo, lịch trình, checklist, tài liệu và cách đánh giá.
```

Prompt này chứa nhiều đầu ra khác nhau nhưng chưa xác định ưu tiên. AI không biết ngành nghề, loại nhân viên, thời lượng hoặc nguồn lực triển khai.

#### Prompt theo RTC-COE

```text
[Role]
Đóng vai người phụ trách đào tạo nội bộ có kinh nghiệm xây chương trình onboarding cho doanh nghiệp nhỏ.

[Task]
Thiết kế khung nội dung onboarding 5 ngày cho nhân viên sales mới.

[Context]
- Công ty kinh doanh dịch vụ B2B, có 20 nhân viên.
- Nhân viên mới chưa có kinh nghiệm trong ngành.
- Mục tiêu sau 5 ngày: hiểu sản phẩm, biết quy trình sales cơ bản và có thể thực hiện một cuộc gọi thử.
- Người hướng dẫn gồm sales manager và một nhân viên sales senior.

[Constraints]
- Không sử dụng phần mềm đào tạo chuyên dụng.
- Mỗi ngày chỉ dành tối đa 3 giờ cho onboarding.
- Không vượt quá 6 nhóm nội dung chính.
- Mỗi nội dung phải gắn với một hoạt động thực hành.

[Output]
Tạo bảng gồm:
1. Nhóm nội dung
2. Mục tiêu học
3. Hoạt động thực hành
4. Người phụ trách
5. Bằng chứng hoàn thành

[Evaluation]
Khung đạt yêu cầu khi:
- có đủ kiến thức sản phẩm, quy trình sales và kỹ năng giao tiếp;
- mỗi nhóm nội dung tạo ra một hành vi hoặc đầu ra có thể quan sát;
- phù hợp với giới hạn 5 ngày và nguồn lực hiện có.
```

Prompt này chưa tạo toàn bộ chương trình onboarding. Nó chỉ giải quyết một nhiệm vụ rõ: thiết kế khung nội dung. Lịch chi tiết, checklist và tài liệu có thể được tạo ở các bước sau.

### 5.2. Ví dụ B — Quản lý thời gian cho nhân viên văn phòng

#### Prompt viết theo cảm tính

```text
Hãy hướng dẫn thật chi tiết cách quản lý thời gian hiệu quả, gồm nguyên tắc, mô hình, công cụ, sai lầm và kế hoạch 30 ngày.
```

#### Prompt theo RTC-COE

```text
[Role]
Đóng vai người hướng dẫn kỹ năng làm việc cho nhân viên văn phòng.

[Task]
Thiết kế một khung kỹ năng quản lý thời gian cốt lõi để làm nền cho kế hoạch luyện tập 30 ngày.

[Context]
- Đối tượng: nhân viên văn phòng làm việc toàn thời gian.
- Vấn đề thường gặp: nhiều việc xen ngang, khó ưu tiên và thường trễ deadline.
- Mỗi ngày người học có thể dành 20 phút để luyện tập.

[Constraints]
- Không vượt quá 7 kỹ năng chính.
- Không tập trung vào ứng dụng hoặc công cụ phức tạp.
- Mỗi kỹ năng phải có một hành động nhỏ có thể thực hiện trong ngày.

[Output]
Tạo bảng gồm:
1. Kỹ năng
2. Vấn đề kỹ năng đó giải quyết
3. Ví dụ trong công việc
4. Bài tập nhỏ hằng ngày

[Evaluation]
Output đạt yêu cầu khi:
- các kỹ năng không trùng lặp lớn;
- mỗi kỹ năng có thể luyện tập;
- phù hợp với người bận rộn và không cần công cụ đặc biệt.
```

Hai ví dụ cho thấy RTC-COE có thể áp dụng cho các bài toán quen thuộc trong đào tạo, quản lý và công việc văn phòng mà không yêu cầu nền tảng kỹ thuật.

---

## 6. Giới hạn của một prompt tốt

Một prompt có RTC-COE vẫn có thể thất bại nếu Task chứa quá nhiều nhiệm vụ.

Ví dụ:

```text
Hãy phân tích nhu cầu onboarding, xây khung năng lực, thiết kế lịch 5 ngày, viết checklist, tạo tài liệu, xây rubric và tự đánh giá toàn bộ chương trình.
```

Prompt này có thể được viết rất chi tiết nhưng vẫn gặp ba vấn đề:

1. AI phải xử lý nhiều loại task trong cùng một lần.
2. Người dùng không có checkpoint để kiểm tra từng phần.
3. Nếu bước đầu sai, tất cả các phần sau tiếp tục dựa trên nền sai.

Do đó, trước khi tạo Prompt Stack, cần bóc bài toán thành các task hoặc phase nhỏ.

---

## 7. Khi một prompt RTC-COE vẫn chưa đủ

### 7.1. Một prompt tốt vẫn có thể quá tải

Hãy xem lại bài toán onboarding cho nhân viên sales mới. Giả sử ta viết một prompt khá đầy đủ theo RTC-COE như sau:

```text
[Role]
Đóng vai chuyên gia đào tạo bán hàng có kinh nghiệm xây chương trình onboarding cho doanh nghiệp B2B.

[Task]
Thiết kế chương trình onboarding 5 ngày cho nhân viên sales mới.

[Context]
- Công ty bán phần mềm cho doanh nghiệp.
- Nhân viên mới chưa có kinh nghiệm sales B2B.
- Sau 5 ngày, họ cần hiểu sản phẩm, nắm quy trình sales cơ bản và thực hiện được một cuộc gọi thử.
- Người phụ trách gồm sales manager và một nhân viên sales senior.

[Constraints]
- Mỗi ngày tối đa 3 giờ.
- Phải có hoạt động thực hành.
- Không sử dụng phần mềm đào tạo trả phí.
- Chương trình phải triển khai được với nguồn lực hiện có.

[Output]
Tạo:
1. Khung nội dung cần học
2. Lịch onboarding 5 ngày
3. Hoạt động thực hành
4. Checklist triển khai
5. Tiêu chí đánh giá cuối chương trình

[Evaluation]
Chương trình đạt yêu cầu khi:
- bao phủ đủ kiến thức sản phẩm, quy trình sales và kỹ năng giao tiếp;
- có thứ tự hợp lý;
- có bằng chứng hoàn thành rõ;
- triển khai được trong 5 ngày.
```

Prompt này không thiếu RTC-COE. Role, Task, Context, Constraints, Output và Evaluation đều đã có.

Vấn đề nằm ở chỗ khác: phần Task và Output đang chứa quá nhiều nhiệm vụ nhận thức khác nhau. AI phải đồng thời:

- xác định nhân viên mới cần đạt gì;
- quyết định nội dung cần học;
- sắp xếp thứ tự học;
- lập lịch 5 ngày;
- thiết kế hoạt động thực hành;
- tạo checklist triển khai;
- xây tiêu chí đánh giá;
- tự kiểm tra tính khả thi.

Một prompt có thể tạo ra tất cả các phần trên, nhưng kết quả thường chỉ chạm nhẹ mỗi phần. Khi một đầu ra ban đầu chưa đúng, các phần phía sau vẫn tiếp tục được xây trên nền sai đó.

Vì vậy, vấn đề không còn là “prompt chưa đủ thành phần”. Vấn đề là:

> Một prompt đang phải giải quyết quá nhiều task phụ thuộc lẫn nhau trong một lần.

Đây là thời điểm cần **Task Decomposition**.

### 7.2. Task Decomposition là gì?

**Task Decomposition** là quá trình bóc một bài toán phức tạp thành các task nhỏ hơn, có thứ tự và có quan hệ đầu vào–đầu ra rõ ràng.

Mục tiêu không phải là chia nhỏ cho thật nhiều. Mục tiêu là xác định:

- bài toán thực sự gồm những việc nào;
- việc nào phải làm trước;
- mỗi việc cần input gì;
- mỗi việc tạo ra output gì;
- output nào sẽ trở thành input cho bước tiếp theo.

Task Decomposition trong Buổi 2 chỉ tập trung vào **quy trình giải quyết nhiệm vụ**. Nó chưa đi sâu vào decomposition một domain thành cây tri thức nhiều tầng; nội dung đó thuộc Buổi 3.

### 7.3. Bóc bài toán onboarding thành các task

Từ prompt RTC-COE ở trên, ta có thể decomposition như sau:

| Step | Task cần thực hiện | Câu hỏi chính | Input | Output |
|---|---|---|---|---|
| 1 | Xác định yêu cầu onboarding | Sau 5 ngày, nhân viên mới cần biết và làm được gì? | Framing Brief | Onboarding Requirements |
| 2 | Xác định khung nội dung | Cần dạy những nhóm nội dung nào để đạt yêu cầu? | Onboarding Requirements | Content Framework |
| 3 | Thiết kế tiến trình học | Nội dung nên được học theo thứ tự nào? | Content Framework | Learning Sequence |
| 4 | Lập kế hoạch 5 ngày | Mỗi ngày học gì, thực hành gì và tạo đầu ra nào? | Learning Sequence | 5-Day Onboarding Plan |
| 5 | Chuẩn bị triển khai | Ai phụ trách, cần chuẩn bị gì và theo dõi bằng cách nào? | 5-Day Onboarding Plan | Implementation Checklist |
| 6 | Đánh giá và hoàn thiện | Kế hoạch có đủ, hợp lý và khả thi không? | Toàn bộ output trước | Reviewed Onboarding Pack |

Điểm quan trọng là các task không được tạo ra tùy ý. Chúng được suy ra từ chính những việc đang bị trộn trong prompt ban đầu.

### 7.4. Dependency giữa các task

Các task trên có quan hệ phụ thuộc:

```text
Onboarding Requirements
→ Content Framework
→ Learning Sequence
→ 5-Day Onboarding Plan
→ Implementation Checklist
→ Reviewed Onboarding Pack
```

Ví dụ, chưa nên lập lịch 5 ngày nếu chưa biết nội dung nào là bắt buộc. Chưa nên thiết kế checklist triển khai nếu kế hoạch 5 ngày vẫn chưa ổn định.

Task Decomposition tốt giúp người học nhìn thấy logic này trước khi viết nhiều prompt.

### 7.5. Output của Task Decomposition

Kết quả của Task Decomposition không phải là các prompt. Nó là một **Task Map** hoặc bảng quy trình cho biết:

- có những task nào;
- thứ tự của chúng;
- input và output của từng task;
- dependency giữa các task.

Chỉ sau khi Task Map đã rõ, ta mới chuyển từng task thành một prompt trong Prompt Stack.

---

## 8. Prompt Stack — Từ Task Map thành chuỗi prompt

### 8.1. Prompt Stack là gì?

**Prompt Stack** là chuỗi nhiều prompt được sắp theo logic phụ thuộc, trong đó mỗi prompt thực hiện một task tương đối rõ và output của bước trước thường trở thành input hoặc context cho bước sau.

```text
Task Decomposition
├── Task 1
├── Task 2
├── Task 3
└── Task 4

Chuyển thành Prompt Stack
├── Prompt 1 thực hiện Task 1
├── Prompt 2 thực hiện Task 2
├── Prompt 3 thực hiện Task 3
└── Prompt 4 thực hiện Task 4
```

Prompt Stack không phải là một danh sách prompt rời rạc. Nó cần có:

- thứ tự;
- dependency;
- input và output rõ;
- checkpoint để quyết định có nên đi tiếp.

### 8.2. Stack, step, task và phase khác nhau thế nào?

| Thuật ngữ | Nghĩa |
|---|---|
| **Task** | Một nhiệm vụ cần hoàn thành |
| **Step** | Vị trí của một task trong quy trình |
| **Prompt** | Câu lệnh dùng để AI thực hiện task |
| **Prompt Stack** | Toàn bộ chuỗi prompt có quan hệ phụ thuộc |
| **Phase** | Một nhóm nhiều step có cùng mục tiêu lớn; chỉ cần dùng khi quy trình đủ phức tạp |

Trong Buổi 2, nên ưu tiên dùng từ **step** thay vì phase. Một step thường tương ứng với một task chính và một prompt chính.

### 8.3. Clarify, Structure, Design, Critique và Refine có bắt buộc không?

Không.

Các tên như:

```text
Clarify → Structure → Design → Critique → Refine
```

chỉ là một pattern thường gặp trong một số bài toán thiết kế. Chúng không phải Prompt Stack cứng và không phải mọi bài toán đều phải dùng đủ các bước đó.

Ví dụ, một stack viết báo cáo có thể là:

```text
Collect Evidence
→ Organize Findings
→ Analyze
→ Draft
→ Review
```

Một stack so sánh nhà cung cấp có thể là:

```text
Define Criteria
→ Collect Options
→ Compare
→ Assess Risks
→ Recommend
```

Một stack xử lý khiếu nại có thể là:

```text
Understand Situation
→ Classify Issue
→ Generate Resolution Options
→ Select Response
→ Draft Message
```

Nguyên tắc là:

> Các step trong Prompt Stack phải được suy ra từ Task Decomposition của bài toán cụ thể, không phải lấy từ một template cố định.

### 8.4. Mỗi prompt trong stack vẫn dùng RTC-COE

RTC-COE không biến mất khi chuyển sang Prompt Stack.

- **Task Decomposition** quyết định stack cần những step nào.
- **RTC-COE** quyết định mỗi prompt trong từng step được thiết kế như thế nào.

Một step trong stack có thể được mô tả theo cấu trúc:

```text
Tên step

Purpose:
Tại sao step này cần tồn tại trong toàn bộ stack?

Input:
Step này nhận dữ liệu nào từ người dùng hoặc từ output trước?

Prompt theo RTC-COE:
- Role
- Task
- Context
- Constraints
- Output
- Evaluation

Expected output:
Artifact mà prompt phải tạo.

Checkpoint:
Điều kiện cần đạt trước khi chuyển sang step tiếp theo.
```

Purpose, Input, Expected output và Checkpoint không phải là thành phần thay thế RTC-COE. Chúng là metadata để mô tả vai trò của một step trong toàn bộ stack.

### 8.5. Checkpoint dùng để làm gì?

Checkpoint là điểm kiểm tra giữa các step.

Checkpoint trả lời:

- output đã đúng artifact chưa;
- có thiếu dữ liệu quan trọng không;
- có giả định nào cần xác nhận không;
- có đủ điều kiện để chuyển sang step tiếp theo không;
- cần quay lại sửa prompt hay bổ sung input không.

Ví dụ sau Step 2 — Content Framework:

```text
Checkpoint:
- Khung nội dung có bao phủ mục tiêu onboarding không?
- Có nhóm nội dung nào trùng lặp lớn không?
- Mỗi nhóm có gắn với năng lực hoặc hành vi quan sát được không?
- Có đủ dữ liệu để thiết kế Learning Sequence không?
```

Checkpoint giúp stack trở thành một quy trình có kiểm soát, không chỉ là chuỗi prompt chạy liên tục.

---

## 9. Ví dụ hoàn chỉnh — Prompt Stack onboarding nhân viên sales

### 9.1. Entry point

Sử dụng stack này khi:

- đã có Framing Brief tương đối rõ;
- mục tiêu là xây chương trình onboarding 5 ngày cho nhân viên sales mới;
- người dùng chưa có một onboarding pack hoàn chỉnh.

Nếu audience, mục tiêu sau 5 ngày hoặc constraints chính vẫn chưa rõ, cần làm rõ Framing Brief trước khi chạy stack.

### 9.2. Task Map

| Step | Task | Expected output |
|---|---|---|
| 1 | Xác định yêu cầu onboarding | Onboarding Requirements |
| 2 | Xác định khung nội dung | Content Framework |
| 3 | Thiết kế tiến trình học | Learning Sequence |
| 4 | Lập kế hoạch 5 ngày | 5-Day Onboarding Plan |
| 5 | Chuẩn bị triển khai | Implementation Checklist |
| 6 | Đánh giá và hoàn thiện | Reviewed Onboarding Pack |

### 9.3. Step 1 — Xác định yêu cầu onboarding

**Purpose:** Chuyển Framing Brief thành danh sách yêu cầu đầu ra rõ ràng cho chương trình onboarding.

**Input:** Framing Brief từ Buổi 1.

#### Prompt theo RTC-COE

```text
[Role]
Đóng vai người phụ trách đào tạo nội bộ có kinh nghiệm onboarding nhân viên sales B2B.

[Task]
Phân tích Framing Brief và xác định các yêu cầu cốt lõi của chương trình onboarding 5 ngày.

[Context]
Chương trình dành cho nhân viên sales mới tại một công ty bán phần mềm cho doanh nghiệp.
Kết quả của bước này sẽ được dùng để thiết kế khung nội dung ở bước tiếp theo.

[Constraints]
- Chỉ tập trung vào kết quả cần đạt sau 5 ngày.
- Không thiết kế lịch học ở bước này.
- Phân biệt rõ kiến thức, kỹ năng và hành vi.
- Không tự bổ sung yêu cầu không có căn cứ; đánh dấu rõ thông tin còn thiếu.

[Output]
Tạo bảng gồm:
1. Nhóm yêu cầu
2. Kết quả cần đạt
3. Bằng chứng quan sát được
4. Mức ưu tiên
5. Thông tin còn thiếu

[Evaluation]
Tự kiểm tra:
- các yêu cầu có bám Framing Brief không;
- mỗi kết quả có thể quan sát hoặc đánh giá không;
- có giả định nào chưa được xác nhận không.

Framing Brief:
[DÁN FRAMING BRIEF]
```

**Expected output:** Onboarding Requirements.

**Checkpoint:**

- Mục tiêu sau 5 ngày đã rõ.
- Các yêu cầu có bằng chứng quan sát được.
- Thông tin thiếu quan trọng đã được đánh dấu.
- Có đủ dữ liệu để xác định nội dung cần học.

### 9.4. Step 2 — Xác định khung nội dung

**Purpose:** Xác định nhân viên sales cần học gì trước khi lập lịch chi tiết.

**Input:** Onboarding Requirements từ Step 1.

#### Prompt theo RTC-COE

```text
[Role]
Đóng vai chuyên gia thiết kế chương trình đào tạo sales B2B.

[Task]
Xây dựng khung nội dung onboarding dựa trên Onboarding Requirements.

[Context]
Khung nội dung này sẽ được dùng làm đầu vào để thiết kế tiến trình học và kế hoạch 5 ngày.

[Constraints]
- Chỉ đề xuất 4–6 nhóm nội dung chính.
- Không lập lịch theo ngày ở bước này.
- Phân biệt nội dung bắt buộc và nội dung có thể học sau.
- Mỗi nhóm phải gắn với một năng lực hoặc hành vi quan sát được.

[Output]
Tạo bảng gồm:
1. Nhóm nội dung
2. Mục tiêu học
3. Nội dung chính
4. Bằng chứng hoàn thành
5. Mức ưu tiên
6. Lý do

[Evaluation]
Tự kiểm tra:
- các nhóm có bao phủ Onboarding Requirements không;
- có trùng lặp lớn không;
- có nội dung nào không phục vụ mục tiêu không;
- mỗi nhóm có bằng chứng hoàn thành rõ không.

Onboarding Requirements:
[DÁN OUTPUT STEP 1]
```

**Expected output:** Content Framework.

**Checkpoint:**

- Nội dung bao phủ mục tiêu onboarding.
- Không có nhóm trùng lặp lớn.
- Mỗi nhóm có đầu ra quan sát được.
- Có đủ dữ liệu để sắp xếp tiến trình học.

### 9.5. Step 3 — Thiết kế tiến trình học

**Purpose:** Sắp xếp các nhóm nội dung theo logic học trước–sau.

**Input:** Content Framework từ Step 2.

#### Prompt theo RTC-COE

```text
[Role]
Đóng vai learning designer cho chương trình đào tạo ngắn hạn.

[Task]
Sắp xếp các nhóm nội dung onboarding thành một Learning Sequence hợp lý.

[Context]
Người học là nhân viên sales mới, chưa có kinh nghiệm B2B.
Learning Sequence sẽ được dùng để lập kế hoạch 5 ngày ở bước sau.

[Constraints]
- Không chia lịch theo ngày ở bước này.
- Chỉ rõ nội dung nào là prerequisite.
- Đi từ hiểu công ty và sản phẩm đến thực hành quy trình sales.
- Không thêm nhóm nội dung mới nếu không có lý do rõ.

[Output]
Tạo bảng gồm:
1. Thứ tự
2. Nhóm nội dung
3. Lý do đặt ở vị trí này
4. Kiến thức hoặc kỹ năng prerequisite
5. Dấu hiệu sẵn sàng chuyển tiếp

[Evaluation]
Tự kiểm tra:
- thứ tự có logic không;
- có prerequisite nào bị đặt sai vị trí không;
- sequence có dẫn đến mục tiêu cuối là thực hiện cuộc gọi thử không.

Content Framework:
[DÁN OUTPUT STEP 2]
```

**Expected output:** Learning Sequence.

**Checkpoint:**

- Quan hệ trước–sau rõ.
- Không có prerequisite bị bỏ qua.
- Sequence dẫn được đến hành vi cuối chương trình.
- Có thể chuyển sang lập lịch 5 ngày.

### 9.6. Step 4 — Lập kế hoạch onboarding 5 ngày

**Purpose:** Chuyển Learning Sequence thành lịch triển khai cụ thể.

**Input:** Learning Sequence từ Step 3.

#### Prompt theo RTC-COE

```text
[Role]
Đóng vai người phụ trách đào tạo nội bộ và vận hành sales.

[Task]
Thiết kế kế hoạch onboarding 5 ngày dựa trên Learning Sequence.

[Context]
- Mỗi ngày tối đa 3 giờ.
- Người phụ trách gồm sales manager và sales senior.
- Nhân viên mới cần thực hiện được một cuộc gọi thử vào cuối chương trình.

[Constraints]
- Mỗi ngày phải có mục tiêu rõ.
- Mỗi ngày phải có ít nhất một hoạt động thực hành.
- Không vượt quá 3 giờ mỗi ngày.
- Không đưa nội dung chưa có trong Learning Sequence.
- Phải có đầu ra quan sát được sau mỗi ngày.

[Output]
Tạo bảng gồm:
1. Ngày
2. Mục tiêu
3. Nội dung
4. Hoạt động thực hành
5. Người phụ trách
6. Thời lượng
7. Đầu ra cuối ngày

[Evaluation]
Tự kiểm tra:
- tổng thời lượng mỗi ngày có vượt giới hạn không;
- hoạt động có dẫn đến đầu ra quan sát được không;
- lịch có tuân theo Learning Sequence không;
- ngày thứ 5 có đủ điều kiện cho cuộc gọi thử không.

Learning Sequence:
[DÁN OUTPUT STEP 3]
```

**Expected output:** 5-Day Onboarding Plan.

**Checkpoint:**

- Mỗi ngày không vượt quá 3 giờ.
- Có thực hành và đầu ra cuối ngày.
- Người phụ trách được phân công rõ.
- Kế hoạch dẫn tới mục tiêu cuối chương trình.

### 9.7. Step 5 — Chuẩn bị checklist triển khai

**Purpose:** Biến kế hoạch thành danh sách công việc có thể giao và theo dõi.

**Input:** 5-Day Onboarding Plan từ Step 4.

#### Prompt theo RTC-COE

```text
[Role]
Đóng vai điều phối viên đào tạo nội bộ.

[Task]
Tạo checklist triển khai cho kế hoạch onboarding 5 ngày.

[Context]
Checklist sẽ được sales manager và sales senior sử dụng để chuẩn bị và theo dõi chương trình.

[Constraints]
- Chia theo ba giai đoạn: trước onboarding, trong onboarding và sau onboarding.
- Mỗi việc phải có owner, deadline và bằng chứng hoàn thành.
- Không thêm công cụ trả phí.
- Chỉ tạo các đầu việc thực sự cần để triển khai kế hoạch.

[Output]
Tạo bảng gồm:
1. Giai đoạn
2. Đầu việc
3. Người phụ trách
4. Deadline
5. Bằng chứng hoàn thành
6. Trạng thái

[Evaluation]
Tự kiểm tra:
- mọi hoạt động trong kế hoạch đã có đầu việc chuẩn bị tương ứng chưa;
- có đầu việc nào không có owner không;
- bằng chứng hoàn thành có đủ rõ không.

5-Day Onboarding Plan:
[DÁN OUTPUT STEP 4]
```

**Expected output:** Implementation Checklist.

**Checkpoint:**

- Mọi đầu việc có owner.
- Mọi đầu việc có deadline.
- Hoạt động quan trọng đã có phần chuẩn bị tương ứng.
- Checklist có thể dùng trực tiếp để triển khai.

### 9.8. Step 6 — Đánh giá và hoàn thiện toàn bộ onboarding pack

**Purpose:** Kiểm tra sự nhất quán và tính khả thi trước khi sử dụng.

**Input:** Toàn bộ output từ Step 1 đến Step 5.

#### Prompt theo RTC-COE

```text
[Role]
Đóng vai reviewer độc lập có kinh nghiệm về đào tạo sales và vận hành doanh nghiệp nhỏ.

[Task]
Đánh giá toàn bộ onboarding pack, chỉ ra điểm thiếu, mâu thuẫn và rủi ro triển khai; sau đó đề xuất bản chỉnh sửa ưu tiên.

[Context]
Onboarding pack gồm:
- Onboarding Requirements
- Content Framework
- Learning Sequence
- 5-Day Onboarding Plan
- Implementation Checklist

[Constraints]
- Không viết lại toàn bộ ngay từ đầu.
- Phân biệt lỗi nghiêm trọng, lỗi trung bình và điểm có thể cải thiện.
- Mỗi nhận xét phải chỉ rõ vị trí hoặc artifact liên quan.
- Chỉ đề xuất thay đổi phục vụ mục tiêu 5 ngày.

[Output]
Tạo:
1. Bảng audit gồm vấn đề, mức độ, bằng chứng và cách sửa
2. Danh sách 3–5 chỉnh sửa ưu tiên
3. Kết luận: sẵn sàng triển khai / cần sửa trước khi triển khai

[Evaluation]
Tự kiểm tra:
- mọi nhận xét có căn cứ từ onboarding pack không;
- có phát hiện mâu thuẫn giữa các artifact không;
- các đề xuất có thực hiện được với nguồn lực hiện có không.

Onboarding Pack:
[DÁN OUTPUT STEP 1–5]
```

**Expected output:** Reviewed Onboarding Pack.

**Checkpoint cuối:**

- Không còn mâu thuẫn nghiêm trọng giữa mục tiêu, nội dung và lịch.
- Kế hoạch đáp ứng constraints 5 ngày và 3 giờ mỗi ngày.
- Các chỉnh sửa ưu tiên đã được xác định.
- Có thể quyết định triển khai hoặc quay lại step cần sửa.

### 9.9. Logic của toàn bộ ví dụ

Ví dụ trên cho thấy ba lớp khác nhau:

```text
Task Decomposition
→ quyết định có những step nào

RTC-COE
→ thiết kế prompt bên trong từng step

Prompt Stack
→ nối các prompt bằng input, output, dependency và checkpoint
```

Câu chốt:

> Task Decomposition quyết định Prompt Stack gồm những bước nào; RTC-COE quyết định mỗi prompt trong stack được viết như thế nào.


## 10. Bài tập thực hành trên lớp

### 10.1. Bài tập 1 — Từ prompt cảm tính đến RTC-COE

Chọn hai prompt cũ của bạn. Với mỗi prompt:

1. Gạch chân các động từ nhiệm vụ.
2. Xác định thành phần RTC-COE đã có.
3. Chỉ ra thành phần còn thiếu hoặc mơ hồ.
4. Viết lại prompt để giải quyết một task chính.
5. So sánh output cũ và output mới.

Mẫu làm bài:

| Thành phần | Prompt hiện tại | Vấn đề | Cách sửa |
|---|---|---|---|
| Role |  |  |  |
| Task |  |  |  |
| Context |  |  |  |
| Constraints |  |  |  |
| Output |  |  |  |
| Evaluation |  |  |  |

### 10.2. Bài tập 2 — Phát hiện khi nào cần Task Decomposition

Đọc prompt sau:

```text
Hãy thiết kế chương trình đào tạo kỹ năng chăm sóc khách hàng, gồm phân tích nhu cầu, khung năng lực, lịch học, tài liệu, bài tập, checklist và rubric đánh giá.
```

Thực hiện:

1. Liệt kê tất cả task đang bị trộn.
2. Chia chúng thành 3–6 task hoặc step.
3. Xác định output của từng step.
4. Chỉ ra step nào phụ thuộc vào step nào.
5. Viết checkpoint cho ít nhất hai step.

Mẫu:

| Step | Task | Input | Output | Checkpoint |
|---|---|---|---|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |
| 3 |  |  |  |  |

### 10.3. Bài tập 3 — Chuyển Task Decomposition thành Prompt Stack

Dùng kết quả Bài tập 2 để viết Prompt Stack V1.

Yêu cầu:

- 3–6 prompt;
- mỗi prompt chỉ xử lý một task chính;
- mỗi prompt được thiết kế và audit bằng RTC-COE;
- mỗi prompt có output rõ;
- output trước được dùng làm input cho bước sau;
- có ít nhất hai checkpoint;
- chỉ thêm critique hoặc refine khi Task Map cho thấy cần thiết.

### 10.4. Bài tập 4 — Test và sửa stack

Chạy Prompt Stack với một tình huống thật. Sau mỗi step, ghi lại:

- output có đúng artifact không;
- có phần nào AI tự giả định;
- checkpoint đạt hay chưa;
- prompt cần sửa ở đâu;
- có step nào nên gộp hoặc tách.

Không đánh giá stack chỉ bằng văn phong của AI. Hãy đánh giá khả năng stack dẫn đến một đầu ra có thể sử dụng.

---

## 11. Assignment Buổi 2 — Prompt Stack V1 cho domain riêng

### 11.1. Đề bài

Dựa trên Framing Brief từ Buổi 1, tạo một file Markdown gồm các phần sau.

#### Phần A — Prompt ban đầu

Ghi lại một prompt bạn từng sử dụng hoặc có thể đã sử dụng để giải quyết toàn bộ bài toán trong một lần.

#### Phần B — RTC-COE Audit

Phân tích prompt ban đầu theo RTC-COE:

- thành phần nào đã có;
- thành phần nào còn thiếu;
- task nào đang bị trộn;
- vì sao một prompt duy nhất chưa phù hợp.

#### Phần C — Task Decomposition

Chia bài toán thành 3–6 step. Với mỗi step, xác định:

- task cần thực hiện;
- câu hỏi chính;
- input;
- expected output;
- dependency với step khác.

#### Phần D — Prompt Stack V1

Viết prompt cho từng step. Mỗi step cần có:

- Purpose: vai trò của step trong toàn bộ stack;
- Input: dữ liệu hoặc output bước trước;
- Prompt được thiết kế theo RTC-COE;
- Expected output: artifact cần tạo;
- Checkpoint: điều kiện để đi tiếp hoặc quay lại.

Mỗi prompt phải bám Framing Brief, chỉ xử lý task của step hiện tại và không làm thay nhiệm vụ của step sau.

#### Phần E — Test Log

Chạy stack ít nhất một lần và ghi:

- phần nào hoạt động tốt;
- phần nào AI hiểu sai;
- prompt nào cần sửa;
- step nào cần đổi thứ tự;
- phiên bản thay đổi sau test.

### 11.2. Rubric tự chấm

| Tiêu chí | 1 — Yếu | 3 — Đạt | 5 — Tốt |
|---|---|---|---|
| Framing alignment | Stack lệch Framing Brief | Phần lớn bám framing | Mọi step đều phục vụ đúng mục tiêu |
| RTC-COE quality | Prompt mơ hồ | Có task, context và output | Thành phần được dùng có chủ đích |
| Task decomposition | Các step tùy ý | Có thứ tự tương đối rõ | Mỗi step có vai trò và dependency rõ |
| Output chaining | Output rời rạc | Một số bước có nối | Output trước trở thành input có ý nghĩa |
| Checkpoint | Không có | Có kiểm tra cơ bản | Checkpoint quyết định rõ đi tiếp hay quay lại |
| Evaluation | Chỉ dựa vào cảm giác | Có một bước critique | Có tiêu chí và sửa dựa trên bằng chứng |
| Practicality | Khó dùng trong thực tế | Có thể thử nghiệm | Tạo được artifact gần với công việc thật |

Điểm gợi ý:

- 7–14: cần làm rõ framing và task.
- 15–24: đã có stack cơ bản nhưng cần cải thiện dependency và checkpoint.
- 25–31: stack tốt, có thể sử dụng và tiếp tục test.
- 32–35: stack chặt chẽ, có khả năng tái sử dụng và chuyển sang project thực tế.

---

## 12. Những lỗi phổ biến

### Lỗi 1 — Biến RTC-COE thành mẫu điền máy móc

Không phải prompt nào cũng cần viết đủ sáu nhãn. Hãy dùng RTC-COE để kiểm tra tư duy, không phải để làm prompt dài hơn.

### Lỗi 2 — Dùng Role phóng đại

“Chuyên gia số một thế giới” không thay thế cho task rõ và context đủ.

### Lỗi 3 — Gọi danh sách nhiều prompt là Prompt Stack

Nhiều prompt chỉ trở thành stack khi chúng có logic nối tiếp, đầu vào–đầu ra và dependency.

### Lỗi 4 — Decomposition theo cảm tính

Không nên tách thành “Prompt 1 hỏi tổng quan, Prompt 2 hỏi chi tiết, Prompt 3 hỏi sâu hơn”. Mỗi step phải có nhiệm vụ và artifact khác nhau.

### Lỗi 5 — Để một step làm thay toàn bộ stack

Prompt Structure không nên tự viết luôn kế hoạch, checklist và rubric nếu các phần đó thuộc step sau.

### Lỗi 6 — Không có checkpoint

Nếu không kiểm tra output trước khi chuyển bước, lỗi ở step đầu sẽ lan sang toàn bộ stack.

### Lỗi 7 — Tạo quá nhiều step

Task Decomposition không có nghĩa chia nhỏ mọi thao tác. Nếu hai step có cùng mục tiêu và output gần giống nhau, nên gộp.

### Lỗi 8 — Không test với dữ liệu thật

Một stack nhìn hợp lý trên giấy vẫn có thể thất bại khi AI thiếu context, tự suy diễn hoặc tạo output không phù hợp.

---

## 13. Kết quả sau Buổi 2

Sau Buổi 2, người học cần có:

1. Hai prompt cũ đã được audit bằng RTC-COE.
2. Một bảng Task Decomposition cho domain thật.
3. Một Prompt Stack V1 gồm 3–6 step.
4. Ít nhất hai checkpoint.
5. Một Test Log ghi lại lần chạy đầu tiên.
6. Một phiên bản stack đã được sửa sau test.

Artifact này sẽ được dùng làm đầu vào cho Buổi 3. Trong Buổi 3, người học sẽ chuyển từ việc decomposition **quy trình nhiệm vụ** sang decomposition **miền tri thức**, xây cây 3–4 tầng và các dạng knowledge map.

---

## 14. Câu chốt của Buổi 2

> Prompt Engineering giúp chúng ta thiết kế một prompt có chủ đích. RTC-COE giúp kiểm tra cấu trúc của prompt đó. Task Decomposition giúp bóc một bài toán phức tạp thành các task có thứ tự. Prompt Stack biến các task đó thành một chuỗi prompt có đầu vào, đầu ra và checkpoint.

Nói ngắn gọn:

```text
Đừng bắt một prompt làm tất cả.
Hãy làm rõ bài toán, bóc task, rồi thiết kế từng prompt cho đúng step.
```

---

*Nội dung được xây dựng theo phương pháp Structured Intelligence Design (SID) do Trương Đắc Bình phát triển.*
