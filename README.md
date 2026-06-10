# prompt_workflow_gift — Landing nhận quà (email opt-in)

Trang nhập email để nhận **Bộ 20 Prompt + 5 Trợ Lý Claude cho công việc**.

🔗 Live: **https://baronguyen001.github.io/prompt_workflow_gift/**

## Nội dung repo
- `index.html` — trang opt-in (form nhập email). Đã tối ưu SEO/social (OG + Twitter card + canonical + favicon), a11y (skip-link, focus-visible, `aria-live` cho trạng thái form) và perf (cover.png có `width/height` + `loading="lazy"`).
- `leadmagnet.pdf` — bản PDF quà tặng (host kèm để có link tải trực tiếp + làm fallback nếu email lỗi).
- `cover.png` — ảnh bìa hiển thị trên trang (cũng là `og:image` khi share).
- `apps-script/` — backend gửi email (Google Apps Script, **local-only**, đã gitignore).

## Cách hoạt động
Form → Google Apps Script → tự gửi email kèm PDF + BCC về Gmail + lưu email vào Google Sheet.
Nếu submit lỗi (hoặc người dùng không muốn để lại email), trang vẫn có link **tải PDF trực tiếp** làm phương án dự phòng.
Hướng dẫn deploy: xem [`DEPLOY.md`](DEPLOY.md) và `apps-script/SETUP.md`.

---
Trang giới thiệu bản thân (tiếng Việt): **https://baronguyen001.github.io/home/**
