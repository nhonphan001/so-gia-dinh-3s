# Sổ Gia Đình 3s

Ứng dụng web kiểm soát thu chi gia đình theo triết lý **Ghi chép trong 3 giây – Minh bạch Quỹ Chung, Riêng tư Ví Cá Nhân**.

## Tính năng nổi bật
- **Số dư khả dụng thực tế & Hạn mức an toàn mỗi ngày (Safe-to-Spend):** Tự động trừ trước các khoản chi cố định để không tiêu lạm vào tiền hóa đơn.
- **Bàn phím mệnh giá VNĐ:** Nút cộng dồn `+10k`, `+20k`, `+50k`, `+100k`, `+200k`, `+500k` và gợi ý tự động thêm `000`.
- **Thao tác 1 chạm (Quick Presets):** Lưu nhanh các khoản chi quen thuộc kèm nút Hoàn tác (6 giây).
- **Lịch Thu - Chi cố định:** Theo dõi ngày nhận lương/hoa hồng và ngày đóng hóa đơn, chốt thực tế bằng 1 chạm.
- **2 Ví tách biệt:** Quỹ Gia Đình (đồng bộ vợ chồng) và Ví Cá Nhân (riêng tư).
- **Báo cáo & Xuất Excel (CSV UTF-8 BOM):** Biểu đồ tròn, thanh cảnh báo tiến độ ngân sách, sao kê không lỗi font tiếng Việt.

## Triển khai lên GitHub + Cloudflare Pages
1. Tải toàn bộ các file trong thư mục này lên kho lưu trữ GitHub (ví dụ: `nhonphan001/so-gia-dinh-3s`).
2. Vào **Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git**.
3. Chọn repo `so-gia-dinh-3s`, giữ trống *Build command* và đặt *Build output directory* là `/` → bấm **Save and Deploy**.
4. Vào tab **Custom domains** để gắn tên miền riêng của bạn.

## Kích hoạt đồng bộ gia đình thời gian thực (Firebase)
Ứng dụng chạy ngay lập tức bằng bộ nhớ cục bộ (`localStorage`). Để đồng bộ trực tuyến giữa điện thoại vợ và chồng:
1. Tạo dự án trên [Firebase Console](https://console.firebase.google.com/), bật **Authentication (Anonymous)** và **Firestore Database**.
2. Mở file `index.html`, tìm mục `FIREBASE_CONFIG` và dán cấu hình `firebaseConfig` của bạn vào.
3. Trong **Firebase Console → Authentication → Settings → Authorized domains**, thêm tên miền Cloudflare của bạn.
