# ข้อความเขียนบนราว

เว็บใส่ข้อความลายมือเอียงตามมุมบนรูป ใช้ได้หลายรูป ปรับขนาด/ความคมชัดก่อนบันทึก และให้ Claude คิดข้อความให้

## ขึ้น GitHub Pages
1. สร้าง repo ใหม่ แล้วอัปโหลด `index.html`
2. Settings → Pages → Source: Deploy from a branch → `main` / `(root)` → Save
3. รอสักครู่ แล้วเปิด `https://<ชื่อผู้ใช้>.github.io/<ชื่อ repo>/`

## ใช้ AI คิดข้อความ
- วาง Anthropic API key ในช่อง "Anthropic API key" บนหน้าเว็บ (สร้างได้ที่ console.anthropic.com)
- key เก็บใน localStorage ของเบราว์เซอร์คนใช้เท่านั้น ไม่ถูกส่งไปที่อื่นนอกจาก api.anthropic.com
- **อย่าใส่ key ลงในไฟล์แล้ว commit** เพราะ repo สาธารณะมองเห็นได้ทุกคน
- เปลี่ยนโมเดลได้ที่ค่า `MODEL` ต้นไฟล์ส่วน JS

## ถ้าอยากให้คนอื่นใช้ AI โดยไม่ต้องมี key ของตัวเอง
ทำ proxy เล็กๆ (เช่น Cloudflare Worker) เก็บ key ไว้ฝั่งเซิร์ฟเวอร์ แล้วใส่ URL ที่ค่า `ENDPOINT` ในไฟล์ หน้าเว็บจะไม่ขอ key อีก
ควรจำกัดโดเมนที่เรียกได้และตั้ง rate limit เพื่อกันคนอื่นใช้ key ของคุณจนหมด
