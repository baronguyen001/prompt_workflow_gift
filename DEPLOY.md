# Hướng dẫn deploy & setup (nội bộ) — trang nhận quà

Trang opt-in tĩnh trên GitHub Pages, 100% free. (Phần giới thiệu công khai ở `README.md`.)

---

## A. Tạo repo + deploy lên GitHub Pages

> Repo: `baronguyen001/prompt_workflow_gift` → live tại https://baronguyen001.github.io/prompt_workflow_gift/

Thư mục đã `git init` sẵn + remote `git@baronguyen001:baronguyen001/prompt_workflow_gift.git` + identity baronguyen001.

1. Tạo repo rỗng **`prompt_workflow_gift`** trên GitHub (account `baronguyen001`, Public).
2. Push:
   ```bash
   git add . && git commit -m "prompt_workflow_gift landing" && git push -u origin main
   ```
3. Repo **Settings → Pages → Source: `main` / (root) → Save**. ~60s sau là live.

---

## B. Bật gửi email tự động (Google Apps Script) — FREE

Form trong `index.html` POST tới Google Apps Script → gửi email kèm PDF + BCC + lưu Google Sheet.
Toàn bộ hướng dẫn deploy script + dán `SCRIPT_URL`: xem **`apps-script/SETUP.md`**.

> ⚠️ `apps-script/` đã nằm trong `.gitignore` (chứa email cá nhân + ID Drive) → KHÔNG push lên GitHub public.

---

## C. PDF quà tặng
- **Nguồn PDF**: build từ `e:/Indie Hacker/_leadmagnet/leadmagnet.html` (render bằng Playwright). Sửa nội dung ở đó rồi gen lại, copy `leadmagnet.pdf` sang đây.
- Đã copy `leadmagnet.pdf` vào repo → tải trực tiếp tại `https://baronguyen001.github.io/prompt_workflow_gift/leadmagnet.pdf`.
- Apps Script hiện đính kèm PDF từ Google Drive (xem `PDF_FILE_ID` trong `apps-script/Code.gs`); có thể đổi sang link Pages ở trên nếu muốn.

---

## D. Cần thay trong `index.html`
- [ ] `SCRIPT_URL` = URL web app Apps Script (xem `apps-script/SETUP.md`). Đây là endpoint POST công khai của Apps Script (`script.google.com/macros/s/.../exec`) — **không phải secret**, có thể để công khai. KHÔNG dán API key/token vào trang.
- [x] `cover.png` đã có sẵn (ảnh bìa PDF) — cũng dùng làm `og:image` (URL tuyệt đối tới GitHub Pages). Nếu repo/đường dẫn Pages đổi, sửa các URL tuyệt đối trong khối `<meta property="og:*">` + `<link rel="canonical">`.

## E. SEO / social / a11y (đã tích hợp sẵn — không cần chỉnh khi deploy thường)
- `<title>` + meta description + `canonical` + `lang="vi"` + favicon (inline SVG, không cần file ngoài).
- Open Graph (`og:image` = `cover.png`, kèm `og:image:width/height/alt`) + Twitter `summary_large_image` → share đẹp trên FB / Zalo / X.
- `cover.png` có `width`/`height`/`loading="lazy"`/`decoding="async"` + `alt` (giảm layout shift, đạt WCAG AA).
- Form có trạng thái success/error qua `aria-live`, skip-link, focus ring; có link **tải PDF trực tiếp** làm fallback.

## Git identity (quan trọng)
- Repo này MUST dùng **baronguyen001**, KHÔNG dùng bao-mk1.
- Đã set: local `user.name=baronguyen001`, `user.email=265752715+baronguyen001@users.noreply.github.com`, remote `git@baronguyen001:baronguyen001/prompt_workflow_gift.git`.
