# Kích thước ảnh và chất lượng in

Dùng tài liệu này khi tạo ảnh 4K, gắn 600/1200 PPI hoặc chuẩn bị ảnh để in.

## 4K theo tỷ lệ ảnh

- Khung UHD ngang tiêu chuẩn: 3840 × 2160 px.
- Khung dọc UHD: 2160 × 3840 px. Đây là tỷ lệ dọc 4K hợp lệ; không đổi thành ngang nếu người dùng cần bố cục dọc.
- Với tỷ lệ trang hoặc khung riêng, giữ tỷ lệ nguồn và đặt cạnh dài ở 3840 px, trừ khi người dùng chỉ định chính xác kích thước khác.
- Kết xuất chữ, shape, đường nối và các chi tiết hình học ngay ở kích thước đích. Không làm ảnh nhỏ rồi phóng lớn toàn trang để giả độ nét.

## 600/1200 PPI và kích thước in

PPI là số pixel trên mỗi inch khi in. Metadata 600 hoặc 1200 PPI ghi kích thước in dự kiến của ảnh, nhưng tự nó không thêm pixel hoặc chi tiết. Muốn có độ phân giải hiệu dụng thật tại khổ in, phải có đủ pixel.

Công thức:

`pixel = inch × PPI`

Ví dụ:

- 3840 × 2160 px ở 600 PPI tương ứng khoảng 6.4 × 3.6 inch; ở 1200 PPI, khoảng 3.2 × 1.8 inch.
- 2160 × 3840 px ở 600 PPI tương ứng khoảng 3.6 × 6.4 inch; ở 1200 PPI, khoảng 1.8 × 3.2 inch.
- A4 ở 600 PPI cần khoảng 4961 × 7016 px (ngang: 7016 × 4961 px).
- A4 ở 1200 PPI cần khoảng 9921 × 14031 px (ngang: 14031 × 9921 px), tức gần 139 megapixel.

Mặc định dùng khung 4K phù hợp tỷ lệ và metadata 600 PPI. Nếu người dùng yêu cầu 1200 PPI nhưng không nêu khổ in, có thể gắn metadata 1200 PPI; nêu rõ đó chỉ là metadata, không phải chi tiết tăng thêm. Nếu họ yêu cầu 1200 PPI hiệu dụng tại khổ in, tính pixel cần có từ khổ đó và kết xuất chữ/hình học ở kích thước đích. Nếu công cụ không thể xử lý kích thước đó hoặc ảnh minh họa AI có độ phân giải thấp hơn, nói rõ giới hạn; không tuyên bố đã đạt độ phân giải hiệu dụng bằng cách chỉ gắn metadata hay phóng lớn ảnh.

Nếu người dùng đồng thời yêu cầu đúng 4K và 1200 PPI hiệu dụng trên khổ lớn hơn kích thước in của khung 4K, giải thích hai điều kiện đang xung đột. Chỉ hỏi họ ưu tiên điều kiện nào khi không thể đáp ứng cả hai.

## Xuất và kiểm tra

- Mặc định dùng PNG cho chữ, sơ đồ, nét mảnh và mảng màu phẳng. Dùng JPG chỉ khi người dùng hoặc nhà in yêu cầu; dùng TIFF khi quy trình in cần.
- Gắn metadata PPI theo yêu cầu bằng công cụ xuất ảnh. Đọc lại metadata sau khi lưu; không suy ra PPI từ tên tệp hoặc lời nhắc.
- Xác minh chiều rộng và chiều cao pixel thực tế, tỷ lệ trang và độ sắc nét ở 100%.
- Tính PPI hiệu dụng theo khổ in thực tế: pixel cạnh tương ứng ÷ kích thước cạnh tính bằng inch. Nếu máy in phóng ảnh 4K lên A4, độ phân giải hiệu dụng sẽ thấp hơn 600 PPI dù metadata ghi 600; ở 1200 PPI hiệu dụng cần gấp đôi pixel mỗi chiều so với 600 PPI.
- Không tuyên bố ảnh đã có profile CMYK hoặc chuẩn nhà in cụ thể nếu chưa xuất và kiểm tra với thông số đó.
- Soát chính tả, dấu tiếng Việt, số liệu, lề an toàn, tương phản, chi tiết bị cắt và khả năng đọc ở kích thước in. Đối chiếu toàn bộ nội dung với danh sách đã khóa.
