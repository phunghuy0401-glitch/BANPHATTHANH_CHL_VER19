# Version 13 — THE CINEMATIC EXPERIENCE

## Hotfix V13.1.1 — 18/11/2026

- Gỡ nút `BẮT ĐẦU XEM` do website tự phủ lên video; chỉ giữ bộ điều khiển gốc của MP4 hoặc YouTube để tránh hai nút phát cùng xuất hiện.
- Giữ đầy đủ thao tác phát, tạm dừng, tua và phát lại bằng trình điều khiển gốc. Không bật tự phát.
- Chỉ hiện liên kết `Mở video trên YouTube` khi trình phát nhúng gặp lỗi; không để liên kết che nút điều khiển của video đang chạy bình thường.
- Thay biểu tượng tam giác phát tĩnh ở trạng thái chưa có video bằng dấu trang trí, tránh tạo cảm giác có nút phát giả. Đồng bộ nhãn phản hồi thành “Dễ thương xiuruuu” và “Cảm ơn các bạn nữ nhiều nhaaa”; lời xác nhận sau khi chọn được viết lại ngắn, tự nhiên hơn.
- Khi đổi nguồn trong công cụ quản trị, xóa bản xem thử cũ và thu hồi URL tạm trước khi chọn nguồn mới.

## Hướng nâng cấp

- Khu vực video dùng bộ điều khiển phát gốc của trình duyệt/YouTube làm điểm điều khiển duy nhất; không chồng thêm nút phát phủ. Video không tự phát khi khách vừa mở trang.
- Khi video kết thúc, lời mời khám phá vườn thư đổi trạng thái và chuyển sắc nhẹ; không tự động cuộn trang hoặc ép người xem rời video. Có thể phát lại bằng điều khiển gốc của trình phát.
- Đọc tỷ lệ khung hình từ metadata của tệp để hỗ trợ MP4 ngang, dọc hoặc vuông, không khóa theo thông số clip demo.
- Mỗi trái tim có nhịp nổi, vị trí ánh lấp lánh và một trong sáu biến thể chuyển động; 36 lớp vẫn giữ nguyên màu nhận diện theo khối.
- Bổ sung điều hướng thư trước/sau ngay trong hộp thư. Bộ đếm theo danh sách đang lọc; nút đầu/cuối tự vô hiệu hóa, không chuyển vòng ngoài danh sách.
- Căn hộp thư nổi chính giữa trên điện thoại, có lề hai bên bằng nhau; giữ thao tác đóng, cuộn nội dung và hỗ trợ vùng an toàn của thiết bị.
- Giữ đủ 36 lớp và dùng `data.js` hiện tại làm nguồn dữ liệu chuẩn. Nội dung hiện tại đã bao gồm các cập nhật V13.1 cho 9 lớp; không khôi phục nhầm dữ liệu của bản V13 cũ.

## Thay video demo sau này

Video hiện tại trong `media/` vẫn là bản demo và được giữ nguyên trong gói. Khi có MP4 chính thức, chỉ cần thay đường dẫn `src`, `title`, `caption` và `poster` (nếu cần) trong `media/video-config.js`; hướng dẫn chi tiết ở `media/README.md`. Không cần sửa giao diện hay JavaScript. Thời lượng, kích thước và tỷ lệ clip mới không bị kế thừa từ bản demo.

## Kiểm tra sau nâng cấp

- `node --check` cho `app.js`, `data.js` và `media/video-config.js`.
- CSS được phân tích không phát hiện lỗi cú pháp; HTML không có ID trùng.
- Kiểm thử giao diện tương tác: render đủ 36 lớp, mở thư, chuyển đến thư tiếp theo, đến thư cuối, quay lại thư trước và đóng thư; không ghi nhận lỗi JavaScript trong lượt kiểm thử.
- Kiểm tra hộp thư ở viewport 320, 360, 390, 430, 699, 768 và 1280 px; tâm hộp thư trùng tâm màn hình trong các kích thước được kiểm tra.
- Kiểm tra logic tự nhận diện hướng video bằng sự kiện metadata mô phỏng. Phát video thực tế vẫn cần được xác nhận trên hosting/trình duyệt mục tiêu với clip MP4 chính thức.

---

19.11 — CHUYÊN HẠ LONG
BẢN HOÀN THIỆN GIAO DIỆN VƯỜN TRÁI TIM & LÁ THƯ

CÁC NÂNG CẤP
- Tổ chức 36 lớp thành ba cụm Khối 10, Khối 11 và Khối 12.
- Làm nổi bật trái tim bằng ánh sáng, sắc màu theo khối và chuyển động nhẹ.
- Thiết kế lại phần hiển thị bên trong thư như một tờ thư lưu niệm riêng.
- Chia nhịp hiển thị theo câu/đoạn để dễ đọc hơn; nội dung văn bản được giữ nguyên.
- Nâng cấp mở thư ngẫu nhiên để không lặp lớp cho đến khi hết lượt trong danh sách đang lọc.
- Cải thiện trình bày trên màn hình điện thoại và máy tính.

BẢO TOÀN (mô tả trạng thái của bản V13 trước V13.1)
- Giữ nguyên data.js (36 nội dung thư và dữ liệu lớp) của mốc V13 đó; V13.1 đã cập nhật 9 lớp theo yêu cầu người dùng, xem phần Hotfix và ghi chú V13.1 ở trên.
- Giữ nguyên video MP4, ảnh poster và cấu hình video.
- Giữ nguyên các chức năng tìm kiếm, lọc khối, mở thư, phản hồi, video và công cụ cấu hình media.

CÁCH SỬ DỤNG
1. Giải nén toàn bộ thư mục `Version-13-Cinematic-Experience`.
2. Mở `index.html` để xem thử, hoặc tải toàn bộ thư mục lên hosting.
3. Giữ nguyên cấu trúc thư mục `media/` và các tệp JavaScript/CSS đi kèm.
4. Không chỉ tải riêng `index.html`; website cần `style.css`, `app.js`, `data.js` và thư mục `media/`.


## Chỉnh sửa tinh gọn giao diện — Polish Pass 03

- Bỏ dòng “12 tập thể · một sắc màu riêng” dưới tiêu đề của cả ba khối; giữ tên khối ngắn gọn.
- Bỏ các nhãn lặp trong lá thư: “Lời nhắn dành riêng cho cậu.” và “MỘT LỜI NHẮN DÀNH RIÊNG”.
- Bỏ ghi chú kỹ thuật về lựa chọn phản hồi trên thiết bị; đổi câu hỏi phản hồi thành “Cậu cảm thấy lá thư này thế nào?” để không tạo cảm giác phản hồi đã được gửi đi.
- Làm nổi bật chữ ký tác giả “DESIGNED & DEVELOPED BY — PHÙNG GIA HUY” bằng một khu vực credit riêng, đồng bộ với bảng màu website.
- Tinh chỉnh độ thoáng, đường nhấn và kiểu chữ bên trong tờ thư; không sửa nội dung các lá thư.
- Đã giữ nguyên `data.js`, video MP4, poster và cấu hình video so với bản Experience-Enhanced.

## Version 12 — Cân lại bố cục và dấu bản quyền

- Gỡ nhãn `DESIGNED & DEVELOPED BY` khỏi phần đầu trang để tiêu đề và nội dung mở đầu có thứ bậc rõ hơn.
- Thay bằng một dòng bản quyền nhỏ `© 2026 PHÙNG GIA HUY`, căn giữa và kẹp bằng hai nét mảnh; không dùng nền thẻ, viền khung hay bóng đổ.
- Giữ nguyên khối chữ ký lớn `PHÙNG GIA HUY` ở cuối website làm điểm nhận diện chính.
- Thu gọn khoảng đệm cuối khu vườn và chân trang trên điện thoại; bỏ khoảng trống 68px từng được cộng vào chân trang dù khối chữ ký vẫn còn nằm phía sau.
- Cân lại khoảng cách của phần mở đầu, tiêu đề khu vườn và khối chữ ký cuối trang trên màn hình nhỏ.
- Giữ nguyên 36 lá thư, nội dung dữ liệu, video, poster, công cụ cấu hình media và các tương tác hiện có.

### Kiểm tra sau chỉnh sửa

- JavaScript: `node --check` cho `app.js`, `data.js` và `media/video-config.js`.
- Kiểm thử trình duyệt ở viewport điện thoại: dựng đủ 36 thẻ lớp, mở được lá thư đầu tiên và không ghi nhận lỗi JavaScript trong lượt kiểm tra.
- Ảnh kiểm thử dùng nội dung nhúng để chạy giao diện cục bộ; đường dẫn video/poster vẫn cần được kiểm tra trên bản website đã giải nén hoặc host thật.

## Hotfix — căn giữa lá thư trên điện thoại

- Căn hộp thư trượt lên vào chính giữa theo chiều ngang, tạo khoảng cách hai bên bằng nhau.
- Giữ nguyên kiểu mở thư từ cạnh dưới, bo góc, hiệu ứng xuất hiện và khả năng cuộn nội dung.
- Không thay đổi `app.js`, `data.js`, nội dung 36 lá thư, video hoặc poster.
