# wallpaper-assets

Bộ hình nền của app `com.nnastudio.wallpaper` — **164 ảnh + 32 video live, 15 bộ sưu tập theo chủ đề**.

## Nguồn & bản quyền

Toàn bộ nội dung là **tác phẩm nguyên bản tạo mới** cho app này:

- Ảnh: tạo bằng mô hình sinh ảnh của OpenAI (gpt-image) từ mô tả viết riêng, không dùng nhân
  vật, thương hiệu hay tác phẩm có sẵn, không chèn chữ/logo. Theo điều khoản của OpenAI, quyền với
  nội dung đầu ra thuộc về người tạo.
- Video live: dựng bằng code từ chính các ảnh trên (zoom chậm + hiệu ứng hạt: sao, đom đóm,
  mưa, tuyết, bụi sáng, cánh hoa, tàn lửa), lặp liền mạch 8 giây.

Không có ảnh/video nào lấy từ trang stock hay app khác.

## Cấu trúc

```
index.json      danh sách bộ sưu tập + hình nền
photos/         ảnh JPEG q88 (~940×1670)
videos/         video live H.264, 720×1280, 24fps, 8s, không tiếng
thumbs/         ảnh xem trước JPEG q72, 450×800 (đủ nét cho ô lưới trên máy 1080p)
```

`index.json`:

```json
{
  "version": 3,
  "collections": [{ "id": "twilight_city", "title": "Twilight City", "subtitle": "Lo-fi anime skylines at dusk" }],
  "photos": [{ "id": 1, "name": "twilight_city_01", "type": "Photo", "file": "photos/twilight_city_01.jpg",
               "thumb": "thumbs/twilight_city_01.jpg", "size": 512345, "premium": false, "collection": "twilight_city" }],
  "videos": [{ "id": 1, "name": "twilight_city_01_live", "type": "Video", "file": "videos/twilight_city_01_live.mp4", "...": "..." }]
}
```

Đường dẫn trong `file` / `thumb` tương đối so với gốc repo; app ghép với
`https://raw.githubusercontent.com/anhngocnguyen1034/wallpaper-assets/main/`.

## Thêm hình nền mới

1. Tạo ảnh dọc 9:16, không chữ/logo, không nhân vật hay thương hiệu có sẵn.
2. Nén JPEG, thêm vào `photos/`, thumbnail 480px vào `thumbs/`.
3. Thêm mục vào `index.json` (id không trùng, gắn `collection`), tăng `version`.
