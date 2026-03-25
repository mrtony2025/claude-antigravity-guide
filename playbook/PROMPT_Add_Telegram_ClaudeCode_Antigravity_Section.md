# PROMPT: Thêm Section Hướng dẫn Telegram + Claude Code + Antigravity vào index.html

**Asset name:** `PROMPT_Add_Telegram_ClaudeCode_Antigravity_Section.md`  
**Save path:** `/playbook/PROMPT_Add_Telegram_ClaudeCode_Antigravity_Section.md`

---

## Mục tiêu

Thêm 1 section mới vào `index.html` hướng dẫn đầy đủ quy trình kết nối **Antigravity + Claude Code + Telegram Chat**.

---

## Yêu cầu trình bày

- Đọc toàn bộ `index.html` trước khi sửa
- Tái sử dụng CSS/UI pattern hiện có (accordion, callout, code-block, fix-step, tips-grid)
- Section mới ID: `#telegram`, chèn trước `#cta`
- Cập nhật cả desktop navbar và mobile overlay để có link `#telegram`

---

## Cấu trúc section mới

### Tiêu đề
`Kết nối Telegram + Claude Code`

### Nội dung chính (theo thứ tự)

1. **Overview callout** — giải thích 2 vùng nhập lệnh trong Antigravity: Terminal vs Khung chat Claude Code
2. **Accordion 10 bước:**
   - Bước 1: Cài Bun
   - Bước 2: Tạo bot Telegram qua BotFather
   - Bước 3: Mở đúng project trong Antigravity
   - Bước 4: Khởi động Claude Code session (trong Terminal)
   - Bước 5: `/plugin install telegram@claude-plugins-official` (trong khung chat)
   - Bước 6: `/telegram:configure YOUR_BOT_TOKEN` (trong khung chat)
   - Bước 7: `/reload-plugins` (trong khung chat)
   - Bước 8: `claude --channels plugin:telegram@claude-plugins-official` (trong Terminal)
   - Bước 9: Pair bot bằng `hi` → `/telegram:access pair <code>` → `/telegram:access policy allowlist`
   - Bước 10: Test thực tế
3. **Troubleshooting blocks** (5 lỗi thường gặp)
4. **Security block** (bordered với màu accent-anthropic)
5. **Post-install checklist** (7 checkbox items)

---

## Key lỗi thường gặp cần cover

| Lỗi | Nguyên nhân |
|-----|------------|
| `zsh: no such file or directory: /plugin` | Gõ slash command trong Terminal |
| `Unknown skill: telegram:configure` | Plugin chưa load, chưa reload |
| Bot không trả pairing code | Session chưa có `--channels`, chưa reload sau đổi token |
| Listening nhưng Telegram im | Lỗi runtime/plugin |
| Không nhận channel messages | Admin block ở cấp tổ chức |

---

## Security checklist items

- Không để lộ bot token trong screenshot
- Không commit token / `.env` lên Git
- Pair xong → `allowlist` ngay
- Token lộ → revoke qua `/revoke` ở BotFather
- Không dùng chung 1 bot cho nhiều session

---

## Lưu ý kỹ thuật

- Accordion trong section này là accordion riêng biệt (không ảnh hưởng accordion khác trong trang)
- `acc-item` đầu tiên set `active` và `max-height: 400px` để mở mặc định
- `copyCode()` function đã có sẵn trong file, chỉ cần gọi với chuỗi đơn giản
- Không dùng string có dấu nháy đơn trong `onclick` để tránh lỗi JS lint

---

*Cập nhật lần cuối: Tháng 3/2026*
