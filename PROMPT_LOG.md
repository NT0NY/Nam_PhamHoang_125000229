# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** Phạm Hoàng Nam
- **MSSV:** 125000229
- **Tên đề tài Website:** Website bán nước hoa NTONY
- **Công cụ AI đã sử dụng:** ChatGPT, Claude

## 1. Yêu cầu ban đầu (System/Initial Prompt)

> Tạo website bán nước hoa theo đề thi Thiết kế Web. Website tự chọn chủ đề nhưng phải đáp ứng Semantic HTML5 với header, nav, main, section/article và footer; dùng CSS Variables để quản lý màu sắc, font và spacing; dùng Flexbox hoặc CSS Grid cho layout responsive; tích hợp Animate.css và AOS; tự viết hiệu ứng hover và focus cho button và card. Website cần có giao diện bán nước hoa hiện đại, rõ ràng và hoàn chỉnh.

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)

### Lần 1: Dựng khung Semantic HTML & CSS Variable
- **Prompt đã dùng:** Tạo website bán nước hoa với cấu trúc semantic gồm header, nav, main, section, article và footer. Không dùng div thay cho các thành phần semantic khi không cần thiết. Dùng CSS Variables cho màu, font, spacing và radius.
- **Kết quả AI tạo ra:** Khung trang gồm Hero, sản phẩm, câu chuyện thương hiệu, nhóm nốt hương, dịch vụ, liên hệ và footer.
- **Nhận xét & Tinh chỉnh của SV:** Chỉnh lại nội dung để website có cảm giác như một cửa hàng nước hoa cao cấp, đồng thời giữ cấu trúc rõ ràng.

### Lần 2: CSS Flexbox/Grid & Responsive
- **Prompt đã dùng:** Chỉnh layout bằng CSS Grid/Flexbox, tối ưu desktop, tablet và mobile. Thêm menu mobile.
- **Kết quả AI tạo ra:** Các khu vực sản phẩm dùng Grid; navigation và các khu vực nội dung dùng Flexbox/Grid kết hợp.
- **Nhận xét & Tinh chỉnh của SV:** Giảm khoảng cách ở màn hình nhỏ, chuyển danh sách sản phẩm thành một cột trên điện thoại và giữ thao tác dễ sử dụng.

### Lần 3: Tích hợp Animate.css & AOS
- **Prompt đã dùng:** Tích hợp Animate.css cho Hero và AOS cho các section/card khi cuộn trang. Hiệu ứng nhẹ, không gây rối mắt.
- **Kết quả AI tạo ra:** Hero xuất hiện bằng Animate.css; các section, sản phẩm và nội dung được AOS animate khi scroll.
- **Thách thức gặp phải:** Nếu hiệu ứng quá nhiều có thể làm giao diện khó tập trung.
- **Cách sửa prompt (Debug prompt):** Chỉ dùng hiệu ứng ở các khu vực chính, đặt duration vừa phải và `once: true`.

### Lần 4: Hover, Focus và tương tác
- **Prompt đã dùng:** Thêm hover/focus bằng CSS cho navigation, button, product card và các nút thao tác. Thêm JavaScript cho menu mobile và nút thêm sản phẩm vào giỏ.
- **Kết quả AI tạo ra:** Card sản phẩm nâng nhẹ khi hover, button có hiệu ứng, menu mobile hoạt động và số lượng giỏ hàng thay đổi.
- **Nhận xét & Tinh chỉnh của SV:** Giữ hiệu ứng vừa phải để giao diện sang trọng và dễ sử dụng.

### Lần 5: Nâng cấp giao diện và thêm hình ảnh thật
- **Prompt đã dùng:** "Chỉnh sửa giao diện nhìn như chuyên gia và lấy thêm hình ảnh trên mạng."
- **Kết quả AI tạo ra:** Chữ to và dễ đọc hơn, nút bo tròn, thêm dải cam kết (chính hãng, giao hàng, đổi trả, gói quà), dùng ảnh nước hoa miễn phí từ Unsplash cho hero, 3 sản phẩm và phần câu chuyện, có ghi nguồn ảnh ở footer. Thay `div` bằng `figure`, `ol`, `section`. Sửa lỗi nút giỏ hàng bị đè chữ "Đăng Nhập" khi thêm sản phẩm.
- **Nhận xét & Tinh chỉnh của SV:** Rà soát kết quả AI theo ba hướng. (1) Nội dung: ảnh phải miễn phí và có ghi nguồn, nên footer liệt kê tên tác giả ảnh Unsplash. (2) Ngữ nghĩa: nhắc AI hạn chế `div`, nên ảnh được bọc bằng `figure`/`figcaption` và các danh sách dùng `ul`/`ol`. (3) Chất lượng ảnh và lỗi: ảnh dưới màn hình đầu dùng `loading="lazy"`, mọi ảnh có `alt` và `width`/`height` để bố cục không bị nhảy, có `onerror` để trang không vỡ nếu ảnh lỗi. Lỗi phát hiện: nút giỏ hàng bị đè chữ "Đăng Nhập" khi thêm sản phẩm, đã yêu cầu AI sửa và giữ nguyên phần còn lại.

### Lần 6: Tìm kiếm, xem giỏ hàng và đặt hàng
- **Prompt đã dùng:** "Thêm chức năng xem giỏ hàng, tìm kiếm và đặt hàng."
- **Kết quả AI tạo ra:** Thanh tìm kiếm lọc sản phẩm theo tên hoặc nhóm hương (không phân biệt dấu), nút "Khám phá" ở mục nhóm hương cũng lọc sản phẩm. Giỏ hàng dạng ngăn kéo (thẻ `<aside>`) cho tăng giảm số lượng, xóa, tính tổng và nhắc miễn phí giao hàng. Form đặt hàng có kiểm tra dữ liệu, tạo mã đơn và lưu giỏ hàng, đơn hàng vào `localStorage`.
- **Nhận xét & Tinh chỉnh của SV:** Đối chiếu từng chức năng với hành vi mong muốn. Tìm kiếm: gõ "rose" ra Velvet Rose vì từ khóa nằm trong `data-search`; gõ không dấu như "tuoi mat" vẫn ra nhóm Fresh nhờ hàm bỏ dấu; có nút "Xóa bộ lọc" và thông báo khi không có kết quả. Giỏ hàng: tăng, giảm, xóa đều cập nhật tổng tiền và số trên nút giỏ, giảm về 0 thì món bị xóa, nhắc miễn phí giao hàng từ 1.000.000₫. Đặt hàng: số điện thoại phải đúng định dạng Việt Nam, giỏ rỗng thì không đặt được, giỏ và đơn hàng lưu bằng `localStorage` nên tải lại trang không mất. Chỉ đạo AI về khả năng sử dụng: ngăn kéo giỏ hàng có `role="dialog"`, đóng được bằng phím Esc hoặc bấm nền, và trả focus về nút đã mở để dùng được bằng bàn phím.

### Lần 7: Thêm sản phẩm
- **Prompt đã dùng:** "thêm sản phẩm"
- **Kết quả AI tạo ra:** Thêm 2 sản phẩm mới là Amber Sunset (nhóm Oriental) và Green Garden (nhóm Fresh) kèm ảnh Unsplash, giá, nút thêm vào giỏ, từ khóa tìm kiếm. Ô thứ 6 trong lưới là thẻ mời nhận tư vấn để hàng không bị lệch.
- **Nhận xét & Tinh chỉnh của SV:** Kiểm tra dữ liệu hai sản phẩm mới: tên, giá hiển thị (Amber Sunset 1.690.000₫, Green Garden 1.390.000₫), `data-price` và từ khóa tìm kiếm khớp nhau, mỗi sản phẩm có `data-id` riêng nên giỏ hàng không gộp nhầm. Với 5 sản phẩm, lưới 3 cột sẽ bị lẻ một ô nên AI thêm thẻ mời tư vấn làm ô thứ 6; thẻ này tự ẩn khi đang lọc để không lẫn vào kết quả tìm kiếm. Đã cập nhật câu mô tả đầu mục sản phẩm thành "Năm lựa chọn" cho khớp số lượng thực tế.

### Lần 8: Chức năng tư vấn khách hàng
- **Prompt đã dùng:** "thêm chức năng tư vấn khách hàng"
- **Kết quả AI tạo ra:** Thêm mục "Tư vấn mùi hương" (`section#consult`) gồm trắc nghiệm 3 câu hỏi (dịp dùng, nhóm hương, ngân sách) và form "Gửi yêu cầu tư vấn" (họ tên, số điện thoại, nhu cầu). Trang chấm điểm theo nhóm hương và dịp dùng, loại sản phẩm vượt ngân sách rồi gợi ý 2 sản phẩm, có nút thêm vào giỏ. Thêm liên kết "Tư vấn" trên menu.
- **Nhận xét & Tinh chỉnh của SV:** Yêu cầu AI giữ nguyên các phần đã có và chỉ thêm chức năng mới, nên giao diện, giỏ hàng và đặt hàng không bị thay đổi. Chỉ đạo AI tái sử dụng giỏ hàng sẵn có: nút "Thêm vào giỏ" trong kết quả gọi lại nút của thẻ sản phẩm nên số lượng, tổng tiền và `localStorage` vẫn thống nhất. Các nút "Nhận tư vấn" ở Hero và thẻ mời trong lưới sản phẩm được trỏ về mục mới. Form yêu cầu tư vấn kiểm tra số điện thoại Việt Nam và lưu vào `localStorage`; nếu ngân sách quá thấp thì trang báo chưa có sản phẩm phù hợp thay vì để trống.

### Lần 9: Rà soát theo đề thi và tinh chỉnh
- **Prompt đã dùng:** "kiểm tra file coi đúng hết yêu cầu chưa" (kèm file đề thi), sau đó "sửa luôn".
- **Kết quả AI tạo ra:** Đối chiếu website với thang điểm của đề, phát hiện 3 chỗ chưa đạt: còn nhiều thẻ `div`, nhiều mã màu ghi trực tiếp trong CSS, README chưa đúng tên repository. AI thay các `div` bằng thẻ ngữ nghĩa (`header`, `hgroup`, `article`, `section`, `footer`), chỉ giữ `div` cho khung bố cục. AI đưa các màu và giá trị lặp lại vào CSS Variables, đổi tiêu đề README thành `Nam_PhamHoang_125000229`, thêm mục Live Preview, bổ sung công cụ AI và nhật ký Lần 8, 9.
- **Nhận xét & Tinh chỉnh của SV:** Yêu cầu AI giữ nguyên giao diện và chức năng, chỉ đổi cấu trúc thẻ và cách khai báo màu. Đối chiếu với đề: tên repository phải theo mẫu `Ten_Ho_MSSV`, nên dùng `Nam_PhamHoang_125000229`. Sau khi sửa cần kiểm tra lại trên trình duyệt rằng hiệu ứng AOS, Animate.css, giỏ hàng và trắc nghiệm tư vấn vẫn chạy bình thường.

## 3. Đánh giá cá nhân về quá trình Vibe Coding
- AI giúp tiết kiệm thời gian nhất ở phần dựng khung HTML/CSS, responsive và hiệu ứng.
- Bài học rút ra là prompt cần nói rõ cấu trúc HTML, cách tổ chức CSS, responsive và hành vi tương tác.
- Khi AI tạo phần chưa đúng, cần mô tả chính xác phần cần sửa và yêu cầu giữ lại các phần đã đúng.
- Sau khi AI tạo code, sinh viên vẫn cần kiểm tra giao diện, semantic HTML, responsive và các tương tác trước khi nộp.
