---
name: thiet-ke-in-an-vector
description: "Turn rough Word, PDF, diagram, or written source material into polished, art-directed raster artwork for print, including tree diagrams, menus, invitations, cards, posters, and price lists. Preserve every required word and relationship while redesigning the visual hierarchy and composition. Use when a user wants a professional, artistic image from rough source material; deliver a 4K PNG with 600-PPI metadata by default, and calculate larger pixel dimensions when a specified physical print size requires them."
---

# Thiết kế ảnh in có mỹ thuật

Biến tài liệu thô thành một ảnh đồ họa hoàn chỉnh, có chủ ý mỹ thuật và đủ rõ để in. Đầu ra mặc định là PNG raster độ phân giải cao. Hãy thiết kế lại bố cục để đẹp, dễ đọc, có điểm nhấn; giữ chính xác nội dung và quan hệ mà người dùng yêu cầu. Không mặc định bàn giao PDF, SVG hay tệp vector.

## Quy trình

1. **Đọc nguồn và xác định yêu cầu.** Với DOCX, trích nội dung và khổ trang bằng `$documents`; với PDF, dùng `$pdf` để đọc và xem các trang; với hình minh họa mới, dùng `$imagegen`. Xem hình trang nguồn khi cần để hiểu cấp bậc, nhóm nội dung và bố cục.
2. **Khóa nội dung.** Lập bản kiểm kê nguyên văn gồm tiêu đề, nhãn, đoạn chữ, dấu tiếng Việt, con số, giá, ngày tháng, tên, đường dẫn và thứ tự. Với sơ đồ, ghi từng nút, cấp bậc và quan hệ nối. Không tự viết lại, lược bỏ, bổ sung hoặc suy đoán nội dung. Nếu nguồn có đoạn không đọc chắc, hỏi đúng phần chưa rõ.
3. **Chọn hướng mỹ thuật trước khi dàn trang.** Xác định người xem, cảm xúc, điểm nhìn chính và cách mắt di chuyển qua thiết kế. Chọn một ý tưởng thị giác riêng cho nội dung, bảng màu gọn, tối đa hai họ chữ có đủ dấu tiếng Việt, cách xử lý hình minh họa và một hệ lưới nhất quán. Tham khảo [art-direction.md](references/art-direction.md). Tránh chỉ thay màu cho tài liệu Word, dùng mẫu chung chung hoặc rải trang trí không có lý do.
4. **Dựng bố cục chính xác, rồi tạo ảnh.** Dàn chữ, sơ đồ, giá, khung và đường nối bằng văn bản/shape trong HTML-CSS, SVG, canvas hoặc công cụ đồ họa phù hợp; kết xuất chúng ở kích thước đầu ra cuối. Dùng `$imagegen` cho tranh minh họa, ảnh sản phẩm, họa tiết hoặc nền phụ. Không yêu cầu ảnh AI tự viết nội dung chính xác; đặt chữ lên trên bằng lớp văn bản riêng để giữ nguyên chính tả, dấu và quan hệ. Giữ tương phản, khoảng thở, căn chỉnh, phân cấp chữ và độ đọc ở kích thước thực.
5. **Xuất ảnh 4K và gắn 600 PPI.** Ưu tiên PNG. Với khung UHD chuẩn, dùng 3840 × 2160 ngang hoặc 2160 × 3840 dọc. Với tỷ lệ riêng, giữ tỷ lệ nguồn và đặt cạnh dài 3840 px, trừ khi người dùng chỉ định kích thước khác. Gắn metadata 600 PPI và kiểm tra metadata thật của tệp. Nếu người dùng nêu khổ in vật lý và cần 600 PPI hiệu dụng, tính pixel theo khổ đó; khổ A4 ở 600 PPI cần xấp xỉ 4961 × 7016 px. Không phóng to ảnh nhỏ rồi tuyên bố rằng chi tiết đã tăng. Xem [print-production.md](references/print-production.md) để xử lý xung đột giữa 4K, tỷ lệ trang và khổ in.
6. **Kiểm tra và hoàn thiện.** So ảnh cuối với bản kiểm kê nội dung; xem toàn bố cục ở dạng thu nhỏ và soi ở 100%. Sửa chữ bị sai/cắt, nhánh nối sai, bố cục chật, tương phản yếu, chi tiết thừa hoặc điểm nhấn chưa rõ. Xác minh kích thước pixel và metadata PPI bằng công cụ đọc ảnh nếu có. Nếu hình minh họa sinh ra có độ phân giải thấp hơn ảnh đích, dùng nó như chi tiết phụ và giữ chữ, đường nét cùng hình học chính ở kích thước xuất cuối.

## Yêu cầu theo loại thiết kế

- **Sơ đồ cây hoặc quy trình:** giữ nguyên nút, nhánh, hướng và cấp bậc. Thiết kế lại nhịp điệu, khoảng cách, hình dạng nút và điểm nhấn để người xem hiểu luồng nhanh; không biến sơ đồ thành danh sách phẳng.
- **Thực đơn và bảng giá:** làm nổi tên nhóm, món/sản phẩm và giá bằng một hệ căn lề có trật tự. Giữ nguyên đơn vị, ghi chú và thứ tự; chỉ thêm hình món ăn hoặc họa tiết khi hợp phong cách và không làm giảm độ đọc.
- **Thiệp, poster, nhãn:** tạo điểm nhìn và không khí phù hợp dịp hoặc thương hiệu. Giữ nguyên tên, ngày, địa chỉ, thông tin liên hệ và nội dung từng mặt; không tự bịa lời chúc, ưu đãi hay thông tin.
- **Nguồn mờ hoặc thiếu:** không đoán chữ hoặc quan hệ. Hỏi ngắn về phần chưa đọc được rồi tiếp tục với phần còn lại.

## Bàn giao

Bàn giao ảnh PNG hoàn thiện. Nêu kích thước pixel và xác nhận metadata 600 PPI đã được kiểm tra. Nếu biết khổ in, nêu độ phân giải hiệu dụng tại khổ đó; không gọi ảnh “600 PPI khi in” chỉ dựa vào metadata. Chỉ tạo thêm JPG/TIFF khi người dùng yêu cầu hoặc nơi in cần định dạng đó.
