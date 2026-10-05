# LAN2 Order Analyzer – GitHub Pages

Mô hình: web tĩnh + nhiều file JSON. **Mỗi file JSON = 1 Mail**. Tên file (bỏ `.json`) chính là Mail hiển thị trong bảng Order.

```text
index.html
index.json
data/
  abc@gmail.com.json
  xyz@gmail.com.json
  shop@gmail.com.json
```

`index.json` chỉ là danh sách tên file trong `data/`. Mỗi file Mail có thể chứa nhiều Response:

```json
{
  "responses": [
    { "orders": [] },
    { "orders": [] }
  ]
}
```

## Cách chạy
1. Tạo **public GitHub repo**.
2. Upload `index.html`, `index.json` và thư mục `data/`.
3. GitHub → **Settings → Pages** → Deploy from branch → `main` / `/root`.
4. Tạo Fine-grained Personal Access Token, giới hạn đúng repo và cấp **Contents: Read and write**.
5. Mở web → nhập Owner / Repository / Branch / Token.
6. Chọn `abc@gmail.com.json` → **Upload & cập nhật**.
7. Web sẽ upload file vào `data/abc@gmail.com.json` và tự thêm tên file vào `index.json`.

### Lưu ý
Token không được lưu vào file, nhưng vì upload trực tiếp từ trình duyệt nên vẫn có rủi ro khi dùng trên web công khai. Nên dùng Fine-grained token chỉ có quyền Contents trên đúng repo và không commit token vào GitHub.
