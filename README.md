# prompt_workflow_gift — Landing nhận quà (email opt-in)

Trang nhập email để nhận **Bộ 20 Prompt + 5 Trợ Lý Claude cho công việc**.

🔗 Live: **https://baronguyen001.github.io/prompt_workflow_gift/**

## Nội dung repo
- `index.html` — trang opt-in (form nhập email).
- `leadmagnet.pdf` — bản PDF quà tặng (host kèm để có link tải trực tiếp).
- `cover.png` — ảnh bìa hiển thị trên trang.
- `apps-script/` — backend gửi email (Google Apps Script, **local-only**, đã gitignore).

## Cách hoạt động
Form → Google Apps Script → tự gửi email kèm PDF + BCC về Gmail + lưu email vào Google Sheet.
Hướng dẫn deploy: xem [`DEPLOY.md`](DEPLOY.md) và `apps-script/SETUP.md`.

---
Trang giới thiệu bản thân (tiếng Việt): **https://baronguyen001.github.io/home/**
