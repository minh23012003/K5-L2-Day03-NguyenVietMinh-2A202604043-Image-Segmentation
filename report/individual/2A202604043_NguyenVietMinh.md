# Báo cáo thực hành Day 3 — điền trực tiếp trong fork của bạn

**Cách dùng:** Thay mọi dấu `…` bằng bài làm thật của bạn trước khi nộp link fork trên [LMS](https://aithucchien.vinuni.edu.vn). Giữ nguyên bốn mục và bảng để coach đọc nhanh. Viết ngắn, cụ thể theo ảnh/vùng; không cần thuật ngữ chuyên sâu. Ví dụ trong [hướng dẫn mẫu](../../reports/REPORT_TEMPLATE.md) chỉ giúp hiểu cách điền, không phải câu trả lời để chép lại.

- Mã học viên theo lớp: 2A202604043
- Ngày / CVAT local:  
- Công cụ đã dùng: CVAT

Mã học viên là mã lớp cấp; không cần ghi họ tên trong report nếu kênh [LMS](https://aithucchien.vinuni.edu.vn) đã nhận diện bạn. Chỉ ghi công cụ thật sự đã dùng; không có SAM vẫn làm bài bình thường.

## 1. Bài đã nộp

Ghi tên ZIP đúng như file trong `submissions/` và số ảnh đã vẽ, Save. Chưa làm hoặc export lỗi thì ghi `chưa có`, không tạo ZIP rỗng. Cột điểm là điểm tối đa của task, **không phải điểm tự chấm**.

| Task | File ZIP đúng tên | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
| --- | --- | ---: | ---: |
| easy_semantic |easy_semantic.zip | 3 / 3 | 20 |
| medium_instance | medium_instance.zip |3 / 3 | 32 |
| hard_panoptic | hard_panoptic.zip |2 / 2 | 30 |
| cp1_holes | … |0 / 1 | 3 |
| cp2_slice | … |0/ 1 | 3 |
| cp5_occlusion | … |0 / 1 | 3 |
| cp3_thin | … |0 / 1 | 3 |
| cp4_curb | … |0 / 1 | 3 |
| cp6_coverage | … |0 / 1 | 3 |
| **Tổng tối đa** | | | **100** |

Nếu export lỗi, ghi task, dữ liệu đã Save đến đâu và lỗi đã báo coach.

## 2. Một quyết định trước khi dùng gợi ý

Chọn object đầu tiên bạn tự vẽ ở `medium_instance`, trước khi xem bất kỳ đề xuất tự động nào cho object đó. Ghi ảnh/vị trí đủ để tìm lại; “quy tắc biên” là lý do bạn chọn hoặc dừng mask ở ranh đó.

- Ảnh, vị trí và object Medium đầu tiên tự vẽ: Ảnh đường phố có cửa hàng Chanel phía sau, vạch kẻ qua đường. Object là người phụ nữ mặc áo dài đang đi bộ qua vạch kẻ ở giữa ảnh, nhãn PERSON 26, ID 26 trong danh sách
- Class và quy tắc tôi dùng để chọn biên: Class là person. Mask bám theo viền ngoài của áo dài và thân người, gồm cả tay và bàn chân, dừng ở chỗ tiếp giáp với nền đường và phần nền phía sau
- Nếu dùng gợi ý sau đó: vùng gợi ý sai/đúng, hành động sửa/giữ và lý do: Không dùng, object được gán person vì đây là một người đứng riêng, tách rõ khỏi xe máy và người phía sau. Khi vẽ, mình tách phần áo dài khỏi nền xám của đường, và không gộp người đi xe máy phía sau vào mask này
- Nếu không dùng gợi ý: ghi “không dùng”; vẫn giải thích một quyết định gán nhãn của mình.

## 3. Một lỗi tôi tìm thấy và sửa

Chọn một lỗi **có thật** trong bài. Nếu công cụ lỗi khiến bạn chưa sửa được, ghi rõ đã thử gì và cần coach hỗ trợ gì; không ghi “đã sửa” khi chưa sửa.

- Task/ảnh/vùng:Task Easy_semantic, ảnh 817bca71-00000000.jpg, giữa building 16 và building 22
- Lỗi thuộc loại: sai lớp / thiếu-thừa vật / gộp-tách / biên / phủ vùng / khác: gộp-tách
- Bằng chứng tôi nhìn thấy: hiện tại không gộp được 2 obj 
- Quy tắc và hành động sửa: giữ nguyên (đã hỏi labcoach)
- Sau sửa đã Save và export lại chưa? đã save và export

Nếu bạn **đã xem Summary tự đánh giá trên GitHub Actions hoặc tự chạy script**, ghi ngắn một kết quả liên quan lỗi vừa sửa (ví dụ task, metric trước/sau nếu có): … / chưa có điểm. Scorecard ba tier tối đa **82**, không phải điểm cuối trên 100. Không tự ghi PASS/top 3/bonus; người phụ trách xác nhận theo tiêu chí lớp. Không đưa file ground truth vào fork.

## 4. Ba ca chưa chắc hoặc đã cân nhắc

Mỗi ca là một **vùng cụ thể** khiến bạn phải cân nhắc hai cách hiểu. Ghi dấu hiệu nhìn thấy hoặc quy tắc đã dùng, rồi nêu quyết định hoặc câu hỏi cho coach. Không cần ba lỗi; ca đã quyết định được cũng hợp lệ.

| Ảnh/vị trí | Hai cách hiểu có thể | Quy tắc/chứng cứ | Quyết định hoặc câu hỏi cho coach |
| --- | --- | --- | --- |
| 1 | 000000350023.jpg/hàng rào ở 2 bên đường | bỏ qua hoặc cho vào class building  | quyết định bỏ qua  |
| 2 | 000000460147.jpg/cây khô 2 bên đường | bỏ qua hoặc cho vào class building | quyết định bỏ qua |
| 3 | … | … | … |
