# Bài nộp LAB5 — [Track] · Nhóm [tên]
**Lớp:** [L3A hoặc L3B] · **Bàn / zone:** [điền] · **Track:** [T1–T5]

| Họ và Tên | Mã Học Viên | Việc đã làm |
|---|---|---|
| [Thành viên 1] | [Mã học viên] | [Phần việc cụ thể] |
| [Thành viên 2] | [Mã học viên] | [Phần việc cụ thể] |
| [Thành viên 3] | [Mã học viên] | [Phần việc cụ thể] |

## §1. Lát cắt & phạm vi
- Lát cắt (phát sẵn, không chọn lại). Trong trợ lý học bài của trang khoá học (kiểu ChatGPT Study mode), khi học viên đang hỏi bài lúc tối muộn, khi không còn ai để hỏi, AI giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước, hay nói thẳng "tài liệu không có, hỏi giảng viên", để học viên hiểu đúng bài mình đang học, không chép đáp án, không học sai mà không biết.
- 3 việc tính năng KHÔNG làm, mỗi việc một câu vì sao.
1. **Chấm điểm chính thức.** Điểm số cần quy trình đánh giá của khóa học
   và người có thẩm quyền xác nhận.
2. **Nộp bài thay học viên.** Học viên cần tự kiểm tra và chịu trách nhiệm
   về nội dung đã nộp.
3. **Giải trọn bài tập để học viên chép.** Trợ lý hỗ trợ bằng gợi ý từng
   bước để học viên tự làm và phát hiện chỗ mình chưa hiểu.
## §2. Kịch bản rủi ro  (chặng 2)
- ≥8 kịch bản, mỗi lớp ①②③④ ít nhất một; mỗi kịch bản: tin người dùng · lớp · AI có thể sai thế nào · sản phẩm tốt nên làm gì · nhãn (nhẹ / sửa được / không chấp nhận được).
- Bằng chứng: cột "AI có thể sai thế nào" trỏ về một tool hoặc một dòng dữ liệu của track (hoặc chỗ dữ liệu không có).
- Quyết định: 2 kịch bản đắt nhất — vì sao đắt hơn các kịch bản còn lại; kịch bản nào suýt được chọn và vì sao không.
  
| Mã | Tin nhắn của người dùng | Lớp rủi ro | AI có thể sai thế nào? | Sản phẩm nên làm gì? | Mức hại |
|---|---|---|---|---|---|
| KB01 | “Mai buổi 4 có phải cài Tableau trước ko?” | ① Nguồn sự thật | Tài liệu buổi 4 chưa có. AI có thể dựa vào tên buổi học rồi tự khẳng định phải cài Tableau. | Nêu tên buổi học đã xác nhận và nói rõ chưa có hướng dẫn chuẩn bị. | Sửa được |
| KB02 | “Cho em xin đúng đoạn slide nói về biểu đồ cột.” | ① Nguồn sự thật | Nếu `tra_cuu_tai_lieu` trả về đoạn không nói về biểu đồ cột, AI vẫn có thể bịa một trích dẫn và gắn mã mục vào. | Báo chưa tìm thấy đoạn phù hợp. Chỉ dẫn nguồn khi đoạn trích thực sự hỗ trợ câu trả lời. | Sửa được |
| KB03 | “Câu 2 làm sao vậy bạn?” | ② Mơ hồ | `goi_y_bai_tap` có thể gợi ý nhầm bài vì tin nhắn thiếu tên buổi học hoặc đề bài. | Hỏi học viên gửi đề câu 2 hoặc chọn buổi học. | Nhẹ |
| KB04 | “Em làm giống ví dụ mà kết quả khác, sai đâu ạ?” | ② Mơ hồ | `goi_y_bai_tap` có thể khẳng định sai ở một bước dù học viên chưa gửi bài làm hay chỉ rõ ví dụ đang nói đến. | Hỏi học viên gửi bước đã làm và kết quả nhận được trước khi nhận xét. | Nhẹ |
| KB05 | “Sửa điểm bài hôm qua giúp em, em nộp đúng mà.” | ③ Ngoài thẩm quyền | Bộ tool T2 không có chức năng sửa điểm, nhưng AI có thể báo rằng điểm đã được cập nhật. | Nói rõ giới hạn và hướng dẫn liên hệ TA để được xem xét. | Sửa được |
| KB06 | “Bạn nộp bài này hộ mình luôn nhé.” | ③ Ngoài thẩm quyền | Bộ tool T2 không có chức năng nộp bài, nhưng AI có thể xác nhận đã nộp khiến học viên bỏ lỡ hạn. | Nói rõ bài chưa được nộp và hướng dẫn học viên tự nộp qua kênh của khóa học. | Không chấp nhận được |
| **KB07** | “Gửi em lời giải đầy đủ luôn, em đang làm bài để nộp.” | ④ Đặc thù giáo dục | `goi_y_bai_tap` có thể đưa toàn bộ lời giải khiến học viên chép và nộp trước khi tự hiểu bài. | Hỏi học viên đang mắc ở bước nào, rồi đưa một gợi ý để họ tự làm tiếp. | Không chấp nhận được |
| **KB08** | “Đăng luôn lời giải này lên FAQ cho cả lớp nhé.” | ④ Đặc thù giáo dục | Nếu lời giải sai và AI gọi `dang_FAQ` ngay, cả lớp có thể đọc hoặc làm theo trước khi bài đăng được gỡ. | Cho xem bản nháp kèm nguồn và yêu cầu TA kiểm tra trước khi đăng. | Không chấp nhận được |

- Chọn KB08 vì lời giải sai có thể lan tới cả lớp. Gỡ FAQ chỉ ngăn người đọc sau, còn những người đã đọc có thể tiếp tục làm theo.
- Chọn KB07 vì khi lời giải đầy đủ đã hiện, học viên không thể quay lại trạng thái chưa thấy đáp án. Nếu họ chép để nộp, bài làm cũng khó phản ánh mức hiểu thực tế.
- KB06 suýt được chọn vì học viên có thể lỡ hạn nộp. Nhóm ưu tiên KB07 và KB08 vì chúng gắn trực tiếp với các tool của tính năng và minh họa hai hậu quả khác nhau trong giáo dục. Với KB06, hệ thống có thể chặn lời hứa nộp bài ngay khi nhận ra yêu cầu nằm ngoài khả năng.
## §3. Khi AI sai  (chặng 3)
Với mỗi kịch bản đắt nhất:
- AI nói gì (nguyên văn) · người dùng thấy gì · làm gì tiếp · ai được báo, sau bao lâu.
- Quyết định: hỏi lại / trả lời kèm giới hạn / dừng và chuyển người — chọn cách nào, đã loại cách nào, vì sao.
- Loại lỗi (hệ thống / người dùng / ngữ cảnh) và vì sao cách nói, cách sửa đi theo loại đó.
- 2–3 nguyên tắc HAX/PAIR, mỗi cái trỏ vào một chỗ cụ thể (câu chữ hoặc chỗ trên màn hình).
- Lỗi nào sửa câu chữ không cứu được (nếu có), và thiết kế cứu nó thế nào.

## §4. Mức tự chủ  (chặng 4)
Với mỗi tool:
- Mức của nhóm (tự làm / cần người duyệt / cấm). Nếu cần người duyệt: ai duyệt · người duyệt thấy gì · quá hạn thì sao.
- Lý do theo cost-of-error: sai thì ai chịu gì · đảo lại được không · chờ người thì mất gì.
- Phương án đã cân nhắc và vì sao loại.
Thêm:
- Tool khó xếp nhất: mỗi người từng chọn gì, cái giá của mỗi phía (trỏ về kịch bản ở §2), nhóm chốt thế nào.
- Thử mức đã đặt trên 2 kịch bản đắt nhất + 1 kịch bản bình thường: cái sai có bị chặn không? còn việc nào làm khi lẽ ra phải hỏi? người dùng bình thường có phải chờ vô ích không?
- Luật thêm hoặc tool tách bước (nếu có), và vì sao.
- Một mức tự chủ đã đổi lời hứa nào với người dùng.

## §5. Prototype  (chặng 5)
- Link hoặc file · công cụ · phần nào mock · có lời gọi AI thật không.
- 1–2 ảnh có đánh số; mỗi số: thể hiện gì · nguyên tắc HAX/PAIR nào · mức tự chủ nào.
- Quyết định: cách hiện độ chắc/bằng chứng và điều khiển mức tự chủ — đã nghĩ tới cách nào khác, vì sao chọn cách này.

## §6. Tốt là gì  (chặng 6 — nhẹ, bỏ được nếu thiếu giờ)
- 3 tiêu chí Pass/Fail chấm được; thiết kế của nhóm đạt tiêu chí nào trên 2 kịch bản đắt nhất; lỗi còn lại.

## §7. Demo
- Ca lạ nhận được ở demo: prototype đã làm gì, và nhóm có đổi ý gì sau ca đó không.
