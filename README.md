# Aranea-templates

ร้านเทมเพลตของแอป Aranea (แจกฟรี) แอปอ่านรายการจาก [`index.json`](index.json) แก้ไฟล์นี้แล้วร้านในแอปเปลี่ยนตาม ไม่ต้องลงแอปใหม่

- แอปดึงรายการตอนเปิดร้าน (เก็บไว้ใช้ตอนออฟไลน์)
- หลังแก้อาจใช้เวลาถึงประมาณ 5 นาทีกว่าจะเห็นในแอป (GitHub เก็บแคชไฟล์ไว้)

## อยากส่งเทมเพลต

เปิด [Issue ใหม่ แบบ "ส่งเทมเพลต"](../../issues/new?template=submit-template.yml) กรอกชื่อ แนบไฟล์ แล้วรอผู้ดูแลรับเข้าร้าน

## ผู้ดูแล: เพิ่มเทมเพลตเข้าร้าน

1. สร้างโฟลเดอร์ใหม่ใน `templates/` ชื่อเป็นภาษาอังกฤษไม่มีเว้นวรรค เช่น `templates/cornell-pastel/`
2. ใส่ไฟล์ 2 ไฟล์:
   - `template.jpg` หรือ `template.png` หรือ `template.pdf` (PDF หลายหน้าได้ แต่ละหน้าจะกลายเป็นเทมเพลตหนึ่งอันในแอป)
   - `preview.jpg` รูปตัวอย่างเล็ก กว้างประมาณ 450 px
3. เพิ่มรายการใน `index.json` ในหมวด `templates`:

```json
{ "id": "cornell-pastel", "name": "Cornell สีพาสเทล", "author": "ชื่อผู้ทำ", "category": "study",
  "description": "คำอธิบายสั้นๆ",
  "preview": "https://raw.githubusercontent.com/k-zencool/Aranea-templates/main/templates/cornell-pastel/preview.jpg",
  "file": "https://raw.githubusercontent.com/k-zencool/Aranea-templates/main/templates/cornell-pastel/template.jpg",
  "price": 0, "added": "2026-11-20" }
```

4. กด **Commit changes** (ถ้าไฟล์ JSON เขียนผิดรูปแบบ แอปจะใช้รายการเดิมต่อ เช็คก่อนได้ที่ [jsonlint.com](https://jsonlint.com))

| ช่อง | ความหมาย |
|---|---|
| `id` | ชื่อเฉพาะ **ห้ามซ้ำ** แอปใช้จำว่าโหลดอันไหนไปแล้ว |
| `name` | ชื่อที่ขึ้นในร้าน |
| `author` | ผู้ทำ |
| `category` | `id` ของหมวดใน `categories` (เพิ่มหมวดใหม่ได้ ใส่ `icon` เป็นชื่อ [SF Symbol](https://developer.apple.com/sf-symbols/)) |
| `description` | คำอธิบาย |
| `preview` | ที่อยู่รูปตัวอย่าง |
| `file` | ที่อยู่ไฟล์เทมเพลต (`.jpg` `.png` หรือ `.pdf`) |
| `price` | ใส่ `0` (ฟรี) ช่องนี้เผื่อไว้สำหรับอนาคต ตอนนี้แอปยังขายไม่ได้ ของที่ราคามากกว่า 0 จะขึ้นว่า "เร็วๆ นี้" |
| `added` | วันที่ลงร้าน (ปี ค.ศ.-เดือน-วัน) ใหม่สุดขึ้นก่อน |

ห้ามลงงานที่ไม่มีสิทธิ์แจก (เช่นเทมเพลตเสียเงินของคนอื่น)
