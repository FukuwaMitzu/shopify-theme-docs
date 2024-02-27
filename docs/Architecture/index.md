---
sidebar_position: 1
title: Architecture
description: Tổng quan về kiến trúc Shopify theme
---

# Kiến trúc của Shopify theme

## Nội dung

Theme files được chia làm 3 mục:

+ [**Markup and features**](https://shopify.dev/docs/themes/architecture#markup-and-features) - Các file này kiểm soát layout và chức năng của một theme. Bằng cách sử dụng Liquid để tạo ra nội dung HTML cho các page của store.

+ [**Tài nguyên bổ sung**](https://shopify.dev/docs/themes/architecture#supporting-assets) - Bao gồm các css file, JavaScript, locales,...bất cứ những file hỗ trợ cho giao diện và chức năng của theme.

+ [**Config files**](https://shopify.dev/docs/themes/architecture#allowing-for-customization-of-theme-components) - Bao gồm các JSON file để lưu thông tin cấu hình có thể sử dụng để tùy biến bởi merchant thông qua [theme editor](https://shopify.dev/docs/themes/tools/online-editor).

## Cấu trúc thư mục và các thành phần

```bash title="Shopify theme directory structure"
.
├── assets
├── config
├── layout
├── locales
├── sections
├── snippets
└── templates
    └── customers
```

Các thư mục con không nằm trong các thư mục kể trên sẽ không được Shopify hỗ trợ.

### `assets`

Thư mục `assets` chứa tất cả các tài nguyên sử dụng trong theme, bao gồm ảnh, css, file JavaScript.

Sử dụng filter asset_url của Liquid để lấy thông tin đường dẫn tài nguyên theme của bạn.