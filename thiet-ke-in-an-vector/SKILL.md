---
name: thiet-ke-in-an-vector
description: "Turn rough Word, PDF, or written source material into polished print-first designs for diagrams, menus, invitations, cards, posters, price lists, and similar items while preserving exact wording, order, and relationships. Use when a user asks to improve the visual design of existing content for printing, needs editable SVG or vector-first PDF output, or wants print preflight. Coordinate the documents, imagegen, and pdf skills; keep exact text and diagram geometry as vector and use generated raster art only as supporting decoration."
---

# Thiết kế đồ họa in

Biến nội dung thô thành bố cục đồ họa chuyên nghiệp để in, đồng thời giữ nguyên nội dung và cấu trúc mà người dùng yêu cầu. Ưu tiên thiết kế vector: chữ, khung, đường nối, biểu tượng đơn giản và sơ đồ là phần tử vector; ảnh chụp hoặc minh họa AI có thể là ảnh raster được đặt trong PDF/SVG.

## Quy trình

1. **Chọn skill nguồn phù hợp.** Với DOCX, đọc và trích nội dung bằng `$documents`; với PDF, dùng `$pdf` để đọc và kết xuất; với hình minh họa cần tạo mới, dùng `$imagegen`. Tuân thủ các yêu cầu tạo file, runtime và kiểm tra của từng skill được gọi.
2. **Khóa nội dung trước khi thiết kế.** Lập danh sách chính xác toàn bộ chữ, dấu tiếng Việt, số liệu, tên, ngày tháng, giá, liên kết và thứ tự. Với sơ đồ, ghi lại từng nút cùng quan hệ cha-con hoặc chiều mũi tên. Không tự sửa câu chữ, rút gọn, thêm thông tin hay đổi quan hệ khi người dùng chỉ yêu cầu làm đẹp.
3. **Xác định khổ và mục đích in.** Đọc khổ giấy từ nguồn nếu phù hợp. Hỏi gọn khi thiếu thông tin ảnh hưởng đáng kể đến thiết kế, như khổ cắt, hướng giấy, in một/hai mặt, lề xén hoặc yêu cầu từ nhà in. Nếu chưa có thông số nhà in, không tự tuyên bố đã chuẩn CMYK, PDF/X hay bleed theo chuẩn cụ thể.
4. **Lên bố cục rồi dựng bằng vector.** Chọn phân cấp chữ rõ, khoảng trắng đủ, tương phản dễ đọc và phong cách phù hợp nội dung. Dàn nội dung chính trong SVG hoặc PDF vector; dùng font có đủ ký tự tiếng Việt. Giữ chữ ở dạng văn bản/vector, không biến chữ thành một phần của ảnh AI. Dùng `$imagegen` cho nền, hoa văn, ảnh sản phẩm hoặc minh họa phụ; không dùng ảnh AI làm nguồn duy nhất cho sơ đồ hay đoạn chữ cần chính xác.
5. **Kiểm tra nội dung và bản in.** Đối chiếu văn bản trong bản xuất với danh sách đã khóa; kiểm tra nhánh sơ đồ, thứ tự, dấu tiếng Việt, số, tên và liên kết. Kết xuất mọi trang thành ảnh xem trước và soi lỗi tràn, cắt chữ, chồng lấn, lề, tương phản, cỡ chữ và hướng trang. Đọc thêm [print-production.md](references/print-production.md) khi cần chốt định dạng, độ phân giải, bleed hoặc preflight.
6. **Bàn giao rõ loại file.** Ưu tiên PDF vector để in; kèm SVG chỉnh sửa được khi phù hợp và PNG xem trước theo đúng khổ/tỉ lệ. Nêu rõ phần nào là vector, phần nào là ảnh raster, cùng giả định in còn thiếu. Không gọi ảnh “vector” chỉ vì đã phóng to lên 4K.

## Nguyên tắc theo loại thiết kế

- **Sơ đồ cây hoặc quy trình:** giữ nguyên mọi nút, nhánh, hướng và cấp bậc. Dàn lại khoảng cách để tránh giao cắt; không tự gộp hoặc diễn giải lại các nhánh. Chỉ dùng `figma-generate-diagram` khi người dùng muốn sơ đồ chỉnh sửa trong FigJam; với bản in, tạo bố cục vector phù hợp trang.
- **Thực đơn, bảng giá, tờ giới thiệu:** giữ nguyên tên món/sản phẩm, giá, đơn vị, ghi chú và thứ tự nhóm. Dùng căn lề và hệ phân cấp giúp quét nhanh; không thêm giá, mô tả hoặc cam kết chưa có trong nguồn.
- **Thiệp, poster, nhãn:** giữ nguyên chính tả, ngày, địa chỉ, tên và nội dung mặt trước/mặt sau. Chỉ thêm trang trí khi không che nội dung và không làm sai nhận diện thương hiệu.
- **Ảnh nguồn hoặc tài liệu mờ:** nếu không đọc chắc một từ, số hay nhánh, hỏi đúng phần đó thay vì đoán. Ghi nhận mọi chỗ chưa xác định trước khi hoàn thiện.

## Ranh giới chất lượng

“4K” chỉ nói về số pixel, không xác định khổ in hay độ phân giải in. Với chữ và sơ đồ, vector PDF/SVG thường sắc ở mọi kích thước; ảnh raster phải đủ pixel tại kích thước đặt in. Dùng thông số nhà in khi người dùng có. Nếu chỉ có thể cung cấp bản xem trước raster, nói rõ kích thước pixel và không quảng bá nó là file vector hoặc file đã preflight cho nhà in.