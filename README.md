# ☣️ Đại Dịch (Pandemic)

Game hợp tác **Pandemic** (Matt Leacock) bản Việt hoá cho 2–4 nhân vật, chơi ngay trên trình duyệt, tối ưu cho điện thoại: bản đồ thế giới 48 thành phố vẽ từ đường bờ biển thật (Natural Earth), kéo/chụm để phóng to.

Chơi online: https://tranviethoang99.github.io/pandemic/

## Chế độ chơi
- **Chơi một mình**: nhập tên, chọn số nhân vật (2–4) và độ khó, bấm *Bắt đầu*. Bạn điều khiển cả đội. Ván được **tự lưu** — lần sau bấm *Tiếp tục ván đang chơi*.
- **Online 2–4 người**: bấm *Tạo phòng*, gửi mã hoặc link; bạn bè nhập mã và bấm *Vào phòng*.
  Chủ phòng có thể thêm *nhân vật do tôi điều khiển* vào ghế trống. Người tạo phòng phải **giữ tab mở**.
  Khách rớt mạng thì chủ phòng tạm điều khiển thay; khách vào lại (cùng tab) là lấy lại quyền.
- Độ khó: Nhập môn (4 thẻ Bùng dịch) · Tiêu chuẩn (5) · Anh hùng (6). Vai trò chia ngẫu nhiên.

## Luật (bản cơ bản, đầy đủ)
- Thắng khi bào chế đủ thuốc giải 4 bệnh. Thua khi: 8 lần bùng phát, hết khối dịch một màu, hoặc chồng thẻ người chơi không đủ 2 lá.
- Mỗi lượt: 4 hành động → rút 2 thẻ (Bùng dịch xử lý ngay, tối đa 7 thẻ trên tay) → lây nhiễm theo tốc độ 2·2·2·3·3·4·4.
- 8 hành động: đi bộ, bay thẳng, thuê chuyên cơ, bay con thoi, xây trạm, chữa bệnh, trao đổi kiến thức, bào chế thuốc.
- 7 vai trò: Bác sĩ, Nhà khoa học, Nhà nghiên cứu, Chuyên gia vận hành, Điều phối viên, Chuyên gia cách ly, Nhà hoạch định.
- 5 thẻ Sự kiện: Không vận, Dự báo, Tài trợ chính phủ, Một đêm yên bình, Cộng đồng kiên cường (dùng được giữa bước Lây nhiễm và Tăng cường của Bùng dịch).

## Cách bấm
- Chạm thành phố → hiện mọi cách đi tới đó (đi nhiều chặng tự tính đường ngắn nhất, kể cả bay con thoi).
- Vòng xanh đứt nét = nơi đi bộ tới được · vòng đỏ nhấp nháy = thành phố có 3 khối (sắp bùng phát).
- Chạm thẻ trên tay để bay thẳng / thuê chuyên cơ / dùng Sự kiện. Chạm tên đồng đội để xem bài của họ.
- Nút ↩ hoàn tác hành động trong lượt (trước khi rút thẻ). ☰ mở nhật ký, chồng bỏ Lây nhiễm, luật chơi, âm thanh.

## Kỹ thuật
Một file `index.html` duy nhất, không cần build. Kết nối P2P bằng [PeerJS](https://peerjs.com/), chủ phòng giữ trạng thái ván (`applyAction` / `viewFor`), khách không thấy thứ tự các chồng bài.
Bản đồ: đường bờ biển Natural Earth 1:50m (world-atlas), chiếu phẳng và phóng to cục bộ châu Âu / Đông Á để các thành phố không chồng nhau, rút gọn còn ~19 KB.
Chạy thử: `npx http-server pandemic -p 5196`.
