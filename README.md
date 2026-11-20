# Sổ Bán Hàng

Trang quản lý bán hàng: đơn hàng, tồn kho, nhập hàng, chi phí, công nợ khách hàng / nhà cung cấp, chỉ tiêu và hoa hồng nhân viên, báo cáo năm.

## Lưu ý quan trọng về dữ liệu

Bản này lưu dữ liệu qua `window.claude.use("db")` và `window.claude.use("user")`, tức là kho dữ liệu và tài khoản của trang Artifact trên claude.ai.
Nếu mở file `index.html` trực tiếp hoặc qua GitHub Pages, trang chỉ hiện thông báo "cần mở trên claude.ai" vì không có kho dữ liệu đó.

Muốn chạy độc lập (GitHub Pages, tên miền riêng) cần thay phần dữ liệu bằng một dịch vụ như Firebase hoặc Supabase:
- Các hàm cần thay: `mutateDoc`, `sub`, `subscribeStatic`, `subscribeYear`, `boot` và các lệnh `db.doc(...).set/update/delete`.
- Cấu trúc dữ liệu giữ nguyên: `products/{mã}`, `customers/{mã}`, `suppliers/{mã}`, `sales/{ngày}_{uid}`, `imports/{ngày}`, `expenses/{YYYY-MM}`, `payments/{ngày}_{uid}`, `staff/{uid}`, `joinreq/{uid}`, `settings/shop`.
- Quyền: chỉ chủ ghi `products`, `suppliers`, `imports`, `staff`, `settings`; chỉ chủ đọc/ghi `expenses`; nhân viên ghi `sales`, `customers`, `payments`.

## Thư viện

- Chart.js 4.4.1 (cdnjs)
- Font Be Vietnam Pro (Google Fonts)
