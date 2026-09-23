# Menu quán — bản web quét QR

Trang thực đơn ba ngôn ngữ (Nga / Việt / Trung) cho khách quét mã QR.
Menu giấy vẫn là chính; trang này là bản phụ.

- `index.html` — trang menu, không cần sửa
- `menu.json` — **toàn bộ tên món và giá nằm ở đây**, sửa giá là sửa file này

Sửa xong, trang tự cập nhật sau 1–2 phút.

---

## Sửa giá một món

1. Bấm vào file **`menu.json`** ở trên.
2. Bấm biểu tượng **cây bút chì** (Edit this file) góc phải.
3. Bấm `Ctrl + F`, gõ số hiệu món, ví dụ `"n": "47"`.
4. Ngay dưới đó là dòng giá — chỉ sửa **con số sau `"a":`**:

   ```json
   "p": [ { "a": 1280, "s": null } ]
   ```

5. Kéo xuống cuối, ô **Commit changes**: gõ một dòng lý do (`tăng giá món 47`), bấm **Commit changes**.
6. Chờ 1–2 phút, mở lại trang menu kiểm tra.

**Món có hai mức giá** (canh tô lớn / tô nhỏ, vịt nguyên con / nửa con):

```json
"p": [ { "a": 980, "s": "L" }, { "a": 480, "s": "S" } ]
```

Sửa từng số `"a"`, không đụng vào `"s"`.

---

## Ba điều cấm

1. **Không xoá** dấu `{ }` `[ ]` `,` `"`. Mất một dấu là cả trang menu trắng.
2. **Không sửa** `"n"` — số hiệu món phải khớp với menu giấy và với bếp.
3. **Không đổi giá riêng trên web.** Đổi ở đây thì in lại menu giấy cùng lúc. Giấy một giá, web một giá là quán thua khi khách thắc mắc.

## Lỡ làm hỏng

Tab **Commits** → bấm vào lần sửa gây lỗi → **Revert**. Mọi lần sửa đều lưu ai sửa, sửa gì, lúc nào.

---

## Còn dở

- Tên tiếng Nga đang là bản rút gọn, chưa lấy nguyên văn từ thực đơn gốc.
- Nhãn cảnh báo (cay / nội tạng / lạc / sữa) là suy ra từ thực đơn, **bếp chưa xác nhận** — chưa được coi là thông tin dị ứng chính thức.
- Chưa có ảnh món.
