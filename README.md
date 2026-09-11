# From Keywords to Meaning — Search Demo

Interactive demo สำหรับ workshop *"From Keywords to Meaning: Build a Smarter Search for AI"*
เทียบ **Keyword Search** (จับคู่ตัวอักษร) กับ **Semantic Search** (เข้าใจความหมาย) แบบ side-by-side

> Demo dataset เพื่อการสาธิตเท่านั้น ไม่ใช่ข้อมูล/แบรนด์จริง

## ไฟล์ในโปรเจกต์

| ไฟล์ | หน้าที่ |
|------|--------|
| `index.html` | ตัว demo หลัก (vanilla HTML/CSS/JS, offline 100%, ไม่มี dependency) |
| `qr.html` | หน้าแสดง QR code ให้ผู้ฟังสแกนเข้าเล่นบนมือถือ (สร้าง QR ในเบราว์เซอร์) |
| `qrcode.js` | ไลบรารีสร้าง QR แบบ vendored (qrcode-generator, MIT license) — ไม่เรียก API ภายนอก |

## URL หลัง Deploy

```
https://pookhincui.github.io/mongodb-search-workshop/
```

- Demo: `https://pookhincui.github.io/mongodb-search-workshop/`
- หน้า QR: `https://pookhincui.github.io/mongodb-search-workshop/qr.html`

## เล่นแบบ Local (ออฟไลน์)

เปิด `index.html` ด้วยเบราว์เซอร์ได้เลย (ดับเบิลคลิก) — ทำงานเต็มรูปแบบโดยไม่ต้องต่อเน็ต

## Deploy ขึ้น GitHub Pages

1. Commit ไฟล์ทั้งหมดไว้ที่ root ของ branch หลัก (`main`)
   ```bash
   git add .
   git commit -m "Add search demo (index.html, qr.html, qrcode.js)"
   git push origin main
   ```
2. ไปที่ repo บน GitHub → **Settings → Pages**
3. **Source:** เลือก `Deploy from a branch`
4. **Branch:** เลือก `main` และโฟลเดอร์ `/ (root)` → กด **Save**
5. รอสักครู่ Pages จะ deploy ให้ที่ URL ด้านบน

> ทางเลือกอื่นที่ลากวางได้เร็ว: [Netlify Drop](https://app.netlify.com/drop) หรือ Cloudflare Pages
> (ลากทั้งโฟลเดอร์ไปวาง แล้วได้ URL สาธารณะทันที)

## QR code สำหรับขึ้นสไลด์

- เปิด `qr.html` (local หรือบน Pages) จะเห็น QR ของ URL demo พร้อมสแกน
- แก้ช่อง URL แล้วกด **สร้าง QR** เพื่อสร้าง QR ของลิงก์อื่นได้
- QR สร้างด้วย JS ในเครื่อง ไม่พึ่ง external API — ใช้ได้แม้เน็ตหลุด

## โมเดลการเล่นบนเวที

- ผู้ฟังสแกน QR → โหลดไฟล์เดียวกันไปรันบนมือถือตัวเอง (**self-play แยกเครื่อง**)
- คำค้นของแต่ละคนเป็นของใครของมัน ไม่มี backend/รวม state ขึ้นจอกลาง
- ใช้เน็ตแค่ตอนโหลดครั้งแรก โหลดเสร็จเล่นต่อได้แม้สัญญาณหลุด

## Acceptance highlights

| คำค้น | Keyword | Semantic (อันดับ 1) |
|-------|---------|---------------------|
| เล่นเฟสไม่ได้ | 0 ผลลัพธ์ | แก้ปัญหาเข้าแอปโซเชียลฯ |
| จะบินไปญี่ปุ่นอาทิตย์หน้า | 0 ผลลัพธ์ | เปิดโรมมิ่งฯ |
| โดนหักเงินทั้งที่ไม่ได้สมัคร | 0 ผลลัพธ์ | ยกเลิกบริการเสริมฯ |
| เน็ตหมดกลางเดือน | เจอปนๆ | ซื้อแพ็กเกจเน็ตเสริมฯ |
| อยากรู้ว่าเดือนนี้จ่ายเท่าไหร่ | เจอน้อย/ปนๆ | เช็กยอดค่าบริการฯ + เติมเงินและจ่ายบิลฯ |

## Credits

QR generation: [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) by Kazuhiko Arase (MIT License)
