# Bản đồ banner đầy đủ — mỗi banner 1 link riêng

Gói này được viết để anh upload nhanh lên GitHub repo `banner-library`.

## 1. File quan trọng nhất

Plugin WordPress đọc file:

```text
sites/default.json
```

Trong file này, mỗi banner có 2 link:

```json
"image": "link ảnh banner trên GitHub Pages",
"target_url": "link khi khách bấm vào ảnh"
```

Anh muốn gắn link riêng cho từng banner thì sửa dòng:

```json
"target_url": "..."
```

## 2. Số lượng banner đã viết sẵn

```text
Tổng banner trong sites/default.json: 41
- Banner ngang / CAT FISH: 18
- Banner vuông / VUÔNG: 5
- Banner dọc / DỌC: 18
```

## 3. Vì sao không bật hết tất cả?

Nếu bật hết, website sẽ hiện quá nhiều banner cùng lúc.

Bản `sites/default.json` đã bật mẫu 4 banner an toàn:
- 1 banner dọc trái
- 1 banner dọc phải
- 1 banner ngang dưới cùng
- 1 banner vuông mobile

Các banner còn lại đã có sẵn trong JSON nhưng để:

```json
"enabled": false
```

Muốn bật banner nào thì đổi thành:

```json
"enabled": true
```

## 4. File để anh sửa link nhanh

```text
data/target-url-map-edit-me.csv
```

File này là bảng phụ giúp anh nhìn toàn bộ banner và link cần sửa.

Nhưng plugin không đọc CSV. Plugin chỉ đọc:

```text
sites/default.json
```

## 5. Quy tắc upload ảnh từ Google Drive lên GitHub

| Nhóm Drive | Upload vào GitHub | Dùng cho |
|---|---|---|
| `1. CAT FISH` | `assets/library/{brand}/horizontal/` | banner ngang, bottom_fixed, top_header |
| `2. VUÔNG` | `assets/library/{brand}/square/` | mobile_grid, content_grid |
| `3. DỌC` | `assets/library/{brand}/vertical/` | left_floating, right_floating |

## 6. Ví dụ sửa link riêng cho từng banner

### TOP dọc trái

```json
{
  "id": "top_vertical_01_left",
  "image": "https://baner-meo-beo-cpu.github.io/banner-library/assets/library/top/vertical/TOP_CPD-WC2026_150x500.gif",
  "target_url": "https://link-rieng-cua-top-doc-trai.com"
}
```

### BIG dọc phải

```json
{
  "id": "big_vertical_09_right",
  "image": "https://baner-meo-beo-cpu.github.io/banner-library/assets/library/big/vertical/BIG_CPD-WC2026_150x500.gif",
  "target_url": "https://link-rieng-cua-big-doc-phai.com"
}
```

### LK88 vuông mobile

```json
{
  "id": "lk88_square_05_mobile",
  "image": "https://baner-meo-beo-cpu.github.io/banner-library/assets/library/lk88/square/LK88_CPD_WC26_600x500.gif",
  "target_url": "https://link-rieng-cua-lk88-mobile.com"
}
```

## 7. Cách upload gói này lên GitHub

1. Giải nén file ZIP.
2. Vào GitHub repo `banner-library`.
3. Bấm `Add file → Upload files`.
4. Kéo toàn bộ file/thư mục sau khi giải nén vào.
5. Bấm `Commit changes`.

## 8. Cách upload ảnh thật

Gói này chỉ chứa cấu trúc + JSON + bảng link, **không chứa ảnh thật từ Google Drive**.

Anh tải ảnh từ Drive xuống rồi upload vào đúng path trong cột:

```text
github_upload_path
```

Ví dụ:

```text
assets/library/top/vertical/TOP_CPD-WC2026_150x500.gif
assets/library/top/horizontal/TOP_CPD-WC2026_728x90.gif
assets/library/lk88/square/LK88_CPD_WC26_600x500.gif
```

## 9. Test sau khi upload

Mở:

```text
https://baner-meo-beo-cpu.github.io/banner-library/sites/default.json
```

Nếu thấy JSON hiện ra là đúng.

Sau đó mở thử ảnh, ví dụ:

```text
https://baner-meo-beo-cpu.github.io/banner-library/assets/library/top/vertical/TOP_CPD-WC2026_150x500.gif
```

Nếu ảnh hiện ra là đúng.

## 10. Lưu ý về JSON

- Mỗi banner phải có `id` khác nhau.
- `target_url` là link khách bấm vào.
- `image` là link ảnh.
- Muốn bật banner: `"enabled": true`
- Muốn tắt banner: `"enabled": false`
- Không thêm dấu phẩy ở block cuối cùng.
