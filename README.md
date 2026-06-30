# HMH Banner Library

Repo này chứa ảnh banner và file JSON để plugin WordPress đọc từ GitHub Pages.

URL JSON sau khi bật GitHub Pages:

```text
https://baner-meo-beo-cpu.github.io/banner-library/sites/default.json
```

## Cấu trúc

```text
sites/default.json
assets/default/left-1.webp
assets/default/right-1.webp
assets/default/mobile-1.webp
assets/default/bottom-1.webp
assets/common/fallback.webp
```

## Cách dùng

1. Upload toàn bộ file/folder trong gói này lên repo `banner-library`.
2. Vào Settings → Pages.
3. Chọn Deploy from a branch → main → /root.
4. Mở link GitHub Pages và test `sites/default.json`.

## Đổi link quảng cáo

Sửa trường `target_url` trong `sites/default.json`.
