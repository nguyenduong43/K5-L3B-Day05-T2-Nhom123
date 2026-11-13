# Bài nộp LAB5 — Track 2: Giáo dục · Nhóm Nhom123

| Họ và Tên | Mã Học Viên | Vai trò & Việc đã làm |
|---|---|---|
| [Nguyễn Tùng Dương] | [2A202603850] | **Product & Autonomy Lead:** Phụ trách §1 (Lát cắt & 3 việc không làm), §4 (Mức tự chủ 4 tool, lập luận cost-of-error, thử nghiệm kịch bản). |
| [Tên Người 2] | [Mã HV 2] | **Risk & Scenario Lead:** Phụ trách §2 (8 kịch bản rủi ro 4 lớp, lập luận 2 ca đắt nhất), §6 (3 tiêu chí Pass/Fail). |
| [Tên Người 3] | [Mã HV 3] | **UX & HAX/PAIR Lead:** Phụ trách §3 (Chi tiết trải nghiệm khi AI sai, câu thoại nguyên văn, phân loại lỗi, ánh xạ HAX/PAIR). |
| [Tên Người 4] | [Mã HV 4] | **Prototype Engineer:** Phụ trách §5 (Dựng giao diện prototype 1–2 màn hình, chụp ảnh đánh số các trạng thái tự chủ và HAX/PAIR). |

---

## §1. Lát cắt & phạm vi

### 1.1 Lát cắt sản phẩm (Chuẩn từ đề bài)
> Trong **trợ lý học bài của trang khoá học (kiểu ChatGPT Study mode)**, khi **học viên** đang hỏi bài lúc tối muộn (ngoài khung giờ trực 08:00–22:00 của TA, khi không còn ai để hỏi), **AI giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước, hay nói thẳng "tài liệu không có, hỏi giảng viên"**, để học viên hiểu đúng bài mình đang học, không chép đáp án, không học sai mà không biết.

### 1.2 Ba việc tính năng KHÔNG LÀM (Kèm lý do cụ thể)
1. **Không giải hộ, không đưa đáp số cuối cùng, không xác nhận đúng/sai cho bài tập đang mở (§3.5 Bài tập 3):**
   * *Lý do:* Hạn nộp Bài tập 3 là 13/11/2026 23:59 (đang mở). Nếu AI cung cấp hoặc xác nhận đáp số ("em tính ra 11.5 đúng không" → "đúng rồi"), học viên sẽ đối phó nộp bài lấy điểm mà không tự tư duy, dẫn đến việc rỗng kiến thức một cách âm thầm (cost-of-error đặc thù của giáo dục).
2. **Không giảng sâu hoặc bịa đặt nội dung tài liệu của các buổi chưa học (Buổi 4 đến Buổi 10):**
   * *Lý do:* Trang khoá học mới chỉ mở Buổi 1, 2, 3; các buổi sau mới chỉ có tên đề cương (ví dụ Buổi 7: "Kiểm định giả thuyết và p-value"). AI cố tình giải thích các kiến thức chưa học sẽ vượt khỏi phạm vi nhập môn của Buổi 3 hoặc bịa kiến thức không có trong giáo trình chính thức.
3. **Không tự ý thay đổi hạn nộp bài, không hứa hẹn việc nằm ngoài thẩm quyền hệ thống:**
   * *Lý do:* AI không có quyền can thiệp vào quy chế khóa học hoặc cơ sở dữ liệu chấm điểm. AI nói *"tôi đã báo giảng viên gia hạn cho bạn"* sẽ làm học viên an tâm ảo và trễ hạn nộp bài thật.

---

## §2. Kịch bản rủi ro (chặng 2 — Do Người 2 phụ trách)
*(Đang cập nhật bởi Người 2)*

---

## §3. Khi AI sai (chặng 3 — Do Người 3 phụ trách)
*(Đang cập nhật bởi Người 3)*

---

## §4. Mức tự chủ (chặng 4)

### 4.1 Quyết định mức tự chủ cho từng công cụ (Tools)

#### Bảng tổng hợp mức tự chủ:

| Tool | Làm gì | Khả năng đảo ngược | Mức tự chủ chốt |
|---|---|---|---|
| `tra_cuu_tai_lieu` | Tìm trong tài liệu Buổi 3 (§3.1–§3.5), trả đoạn trích kèm mã mục | Chỉ đọc | **Tự làm (Auto)** |
| `goi_y_bai_tap` | Gửi gợi ý từng bước giải bài cho học viên | Gợi ý quá tay thì học viên đã chép | **Tự làm có điều kiện (Guardrails)** |
| `chuyen_TA` | Đẩy câu hỏi thắc mắc vào hàng đợi của TA, hẹn giờ trả lời | Đảo lại được | **Cần học viên duyệt (Confirmation)** |
| `dang_FAQ` | Đăng câu hỏi và giải đáp vào mục FAQ chung của cả lớp | Gỡ được nhưng nhiều người đã đọc | **CẤM AI tự làm (Bắt buộc TA duyệt)** |

#### Chi tiết lập luận và Cost-of-Error cho từng tool:

1. **Tool `tra_cuu_tai_lieu`:**
   * **Mức tự chủ:** Tự làm (Auto).
   * **Lý do theo Cost-of-Error:**
     * *Sai thì ai chịu gì:* Không ai mất gì vì đây là tác vụ chỉ đọc (read-only), không làm thay đổi dữ liệu hay điểm số. Nếu trích nhầm mục, học viên tự nhận biết được ngay trên ngữ cảnh chat.
     * *Đảo lại được không:* Không cần đảo lại.
     * *Chờ người thì mất gì:* Nếu tra cứu tài liệu lúc 23:00 đêm mà phải chờ người duyệt thì học viên bị gián đoạn luồng học hoàn toàn, triệt tiêu giá trị của trợ lý tự học ban đêm.
   * **Phương án đã cân nhắc:** Mức *Cần người duyệt* đã bị loại vì chi phí chờ đợi (độ trễ và quá tải cho TA) quá lớn trong khi rủi ro của việc đọc tài liệu là cực thấp.

2. **Tool `goi_y_bai_tap`:**
   * **Mức tự chủ:** Tự làm có điều kiện (Conditional Auto / Guardrails).
   * **Lý do theo Cost-of-Error:**
     * *Sai thì ai chịu gì:* Nếu gợi ý quá tay làm lộ đáp số Bài tập 3 (đang mở), học viên nhìn thấy và chép luôn → không đảo ngược được vì đáp án đã lộ. Học viên mất cơ hội rèn luyện tư duy, chịu hậu quả rỗng kiến thức âm thầm.
     * *Chờ người thì mất gì:* Chờ TA duyệt gợi ý vào lúc 23:00 đêm là bất khả thi vì TA chỉ làm việc 08:00–22:00.
     * *Quy chế Guardrail:* AI được tự động gửi gợi ý nhưng bị cấm tuyệt đối đưa ra con số kết quả hoặc xác nhận đáp án bài đang mở; chỉ được đặt câu hỏi gợi mở (phương pháp Socratic) và trỏ vào công thức lý thuyết (§3.1, §3.2).
   * **Phương án đã cân nhắc:** Mức *Tự làm hoàn toàn* bị loại vì AI dễ bị học viên "jailbreak" hoặc nài nỉ xin đáp án. Mức *Cấm* bị loại vì học viên sẽ hoàn toàn bế tắc khi làm bài đêm muộn.

3. **Tool `chuyen_TA`:**
   * **Mức tự chủ:** Cần học viên bấm xác nhận (Student Confirmation).
   * **Lý do theo Cost-of-Error:**
     * *Sai thì ai chịu gì:* Nếu AI tự động chuyển câu hỏi bừa bãi mỗi khi học viên than khó, hàng đợi của TA sẽ bị quá tải bởi các câu hỏi rác hoặc câu hỏi học viên chưa thực sự cần hỏi.
     * *Đảo lại được không:* Đảo lại được (học viên hoặc TA có thể huỷ/đóng ticket).
     * *Quy trình duyệt:* Khi AI không giải quyết được, AI soạn sẵn nội dung tóm tắt và hiển thị nút `[Gửi câu hỏi cho TA (Phản hồi sau 08:00 sáng mai)]`. Học viên chủ động bấm thì tool mới kích hoạt. Quá hạn thì ticket không được tạo, cuộc trò chuyện tiếp tục bình thường.
   * **Phương án đã cân nhắc:** Mức *AI tự động chuyển* bị loại vì TA sáng hôm sau sẽ ngập trong hàng trăm ticket không phân loại được mức độ ưu tiên.

4. **Tool `dang_FAQ`:**
   * **Mức tự chủ:** CẤM AI tự làm — Bắt buộc Giảng viên/TA duyệt.
   * **Lý do theo Cost-of-Error:**
     * *Sai thì ai chịu gì:* Nếu AI đăng bài giải có chứa đáp án Bài tập 3 hoặc đưa thông tin sai (như khẳng định lỗi sai toán học ở §3.3) lên FAQ lớp → toàn bộ học viên trong lớp cùng đọc và cùng hiểu sai, gây hậu quả lan rộng toàn khóa.
     * *Đảo lại được không:* Dù có gỡ bài được thì nhiều học viên đã kịp đọc và ghi nhớ sai lệch.
     * *Chờ người mất gì:* Đăng FAQ không phải là việc khẩn cấp trong đêm, chờ TA duyệt vào sáng hôm sau là hoàn toàn hợp lý.
   * **Phương án đã cân nhắc:** Mức *Tự làm* bị loại thẳng tay vì bán kính ảnh hưởng (blast radius) quá rộng, cái giá khi sai là mất uy tín của cả khóa học.

### 4.2 Tool khó xếp nhất & Sáng kiến tách tool
* **Tool khó xếp nhất:** `dang_FAQ` và `goi_y_bai_tap`. Trong đó nhóm tranh luận gay gắt nhất về `dang_FAQ`:
  * *Ý kiến A:* Cho AI tự đăng nếu độ chắc chắn cao để làm giàu ngân hàng câu hỏi tự động.
  * *Ý kiến B:* Cấm hoàn toàn AI đụng vào FAQ vì sợ lộ đề và lan truyền sai sót.
  * *Cách nhóm chốt — Sáng kiến tách tool (Tool Splitting):* Nhóm quyết định tách quy trình đăng FAQ thành 2 tool riêng biệt:
    1. `soan_du_thao_FAQ` (AI **Tự làm**): Khi có câu hỏi hay về khái niệm chung, AI tự động tổng hợp thành một bản nháp (draft FAQ) đẩy vào hàng đợi kiểm duyệt của TA.
    2. `xuat_ban_FAQ` (Quyền **Cấm đối với AI / Chỉ dành cho TA**): Chỉ có TA hoặc Giảng viên sau khi rà soát độ chính xác vào sáng hôm sau mới bấm nút xuất bản lên bảng tin FAQ của lớp. Nhờ việc tách tool này, rủi ro lan truyền sai lệch được chặn đứng 100%.

### 4.3 Thử nghiệm mức tự chủ trên 3 kịch bản kiểm thử

#### 1. Kịch bản đắt nhất 1 (Học viên đòi xác nhận đáp số bài tập đang mở):
* **Tình huống:** 23:15 đêm 13/11, học viên nhắn: *"Cô ơi em tính ra trung vị của bài 3 là 11.5 triệu đúng không cô? Sắp hết hạn nộp rồi trả lời nhanh giúp em với!"*
* **AI xử lý:** 
  * AI nhận diện Bài tập 3 đang mở (hạn 23:59 hôm nay). 
  * Cơ chế Guardrail của `goi_y_bai_tap` kích hoạt: Cấm xác nhận đúng/sai.
  * AI từ chối khéo: *"Bài tập 3 đang trong thời gian nộp bài nên mình không thể xác nhận đáp số cụ thể. Bạn hãy đối chiếu lại §3.2: Dãy 8 số lương sau khi xếp tăng dần có 2 số ở giữa là bao nhiêu? Trung vị chính là trung bình cộng của 2 số đó."*
* **Đánh giá 3 câu hỏi:**
  * *Cái sai có bị chặn không?* Có! Tránh việc lộ đáp số và gian lận nộp bài.
  * *Còn việc nào làm khi lẽ ra phải hỏi?* Không.
  * *Người dùng bình thường có phải chờ vô ích không?* Không, học viên nhận được phản hồi định hướng ngay lập tức.

#### 2. Kịch bản đắt nhất 2 (Tài liệu có lỗi sai logic toán học ở §3.3):
* **Tình huống:** Học viên hỏi: *"Tại sao trong §3.3 ghi 'Vì là căn bậc hai, độ lệch chuẩn luôn nhỏ hơn phương sai'? Em thấy nếu phương sai là 0.25 thì căn bậc hai là 0.5 lớn hơn mà cô?"*
* **AI xử lý:**
  * AI gọi `tra_cuu_tai_lieu` trích §3.3, nhận thấy mâu thuẫn toán học logic.
  * AI không được khẳng định tài liệu đúng, cũng không tự ý gọi `dang_FAQ` để đính chính cho cả lớp.
  * AI phản hồi: *"Phát hiện của bạn rất chính xác! Về mặt toán học, khi giá trị nằm trong khoảng (0, 1), căn bậc hai sẽ lớn hơn số ban đầu. Câu trong tài liệu §3.3 có thể chưa bao quát trường hợp này. Mình đã chuẩn bị sẵn câu hỏi để chuyển cho TA/Giảng viên xác nhận lại giáo trình."*
  * AI kích hoạt `chuyen_TA` dưới dạng nút bấm: `[Xác nhận gửi phản ánh tài liệu cho TA (Phản hồi sau 08:00 sáng)]`.
* **Đánh giá 3 câu hỏi:**
  * *Cái sai có bị chặn không?* Có! Không lan truyền kiến thức sai, không bao che lỗi tài liệu.
  * *Còn việc nào làm khi lẽ ra phải hỏi?* Không, AI đã hỏi xác nhận trước khi đẩy ticket cho TA.
  * *Người dùng bình thường có phải chờ vô ích không?* Không.

#### 3. Kịch bản bình thường (Hỏi khái niệm lý thuyết thông thường):
* **Tình huống:** *"Trung vị khác trung bình cộng chỗ nào ạ? Khi nào dùng cái nào?"*
* **AI xử lý:**
  * AI tự động gọi `tra_cuu_tai_lieu` trích xuất §3.1 và §3.2.
  * Trả lời so sánh rõ ràng: Trung bình bị kéo bởi ngoại lai (§3.1), Trung vị ít bị ảnh hưởng bởi ngoại lai nên dùng cho dữ liệu lệch như thu nhập, giá nhà (§3.2). Kèm thẻ trích dẫn nguồn.
* **Đánh giá 3 câu hỏi:**
  * *Cái sai có bị chặn không?* Không có nguy cơ sai.
  * *Còn việc nào làm khi lẽ ra phải hỏi?* Không.
  * *Người dùng bình thường có phải chờ vô ích không?* Hoàn toàn không, tốc độ phản hồi tức thì.

### 4.4 Sự thay đổi trong lời hứa với người dùng (Change of Promise)
* **Nếu thả lỏng mức tự chủ (AI tự do):** Lời hứa ngầm là *"AI là người giải bài hộ bạn trong đêm, bạn hỏi gì có nấy"*. → Lời hứa này tạo ra sự ỷ lại độc hại, học viên đối phó và dễ tin vào những câu trả lời bịa đặt.
* **Khi siết chặt mức tự chủ theo thiết kế này:** Lời hứa chuyển thành *"AI là một trợ giảng định hướng (Socratic Tutor) bám sát tài liệu khóa học; hướng dẫn phương pháp để bạn tự làm chủ kiến thức; và là cầu nối minh bạch đến đội ngũ TA khi gặp vấn đề vượt quá thẩm quyền"*.

---

## §5. Prototype (chặng 5 — Do Người 4 phụ trách)
*(Đang cập nhật bởi Người 4)*

---

## §6. Tốt là gì (chặng 6 — Do Người 2 phụ trách)
*(Đang cập nhật bởi Người 2)*

---

## §7. Demo (Do cả nhóm phối hợp)
*(Sẽ ghi nhận ca lạ sau buổi demo)*

