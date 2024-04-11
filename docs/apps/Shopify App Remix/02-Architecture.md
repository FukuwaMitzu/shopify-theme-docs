---
id: architecture
title: Architecture
---

# Cấu trúc thư mục của Shopify app

## app

Đây là thư mục làm việc chính của project, bao gồm các file và thư mục sau:

```bash title="your-app/"
app/
├─ routes/
├─ db.server.ts
├─ entry.server.tsx
├─ globals.d.ts
├─ root.tsx
├─ shopify.server.ts
```

### routes

Thư mục routing của Remix. Tham khảo [Route Configuration](https://remix.run/docs/en/main/discussion/routes) và [Route File Naming](https://remix.run/docs/en/main/file-conventions/routes) để tìm hiểu cách hoạt động của Remix router.