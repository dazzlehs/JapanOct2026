# Chimelong Trip 5–8 ธ.ค. 2026

เว็บเพจหน้าเดียวสรุปแผนเที่ยว Chimelong (เหิงฉิน จูไห่ ผ่านมาเก๊า) ของครอบครัว ผู้ใหญ่ 2 + เด็ก 2 (4 วัน 3 คืน)

## เนื้อหาในหน้า
- ข้อมูลการจอง: เที่ยวบิน Air Macau, ที่พัก Chimelong Spaceship Hotel + แพ็กเกจ, นโยบายเด็ก, ทิปเรื่องเงิน/เน็ต/ข้ามด่าน
- Checklist เตรียมก่อนไป (ติ๊กได้ จำไว้ในเครื่องที่เปิด)
- แผนรายวันทั้ง 4 วัน: ตารางเวลา + หมายเหตุ + ทิป มีแถบวันที่ด้านบนไว้กระโดดไปวันที่ต้องการ
- ชื่อสถานที่คลิกเปิด Google Maps ได้ทันที
- Animation: ยานอวกาศ+วาฬที่หัวเว็บ, นับถอยหลังวันเดินทาง (ระหว่างทริปจะไฮไลต์ "วันนี้"), การ์ดแต่ละวันค่อยๆ โผล่ตอนเลื่อน, แถบ progress ด้านบน, ปุ่มกลับขึ้นบน, ฟองอากาศลอย (กดปุ่ม 🫧 เพื่อปิด/เปิด) — ถ้าเครื่องตั้งค่า "ลดการเคลื่อนไหว" ไว้ animation จะปิดเองอัตโนมัติ

## รันดูในเครื่อง
เปิดไฟล์ `index.html` ด้วยเบราว์เซอร์ได้เลย ไม่ต้อง build ไม่มี dependency

## Deploy ขึ้น Vercel
1. Push โค้ดนี้ขึ้น GitHub (ดูขั้นตอนด้านล่าง)
2. เข้า https://vercel.com/new แล้วเลือก "Import Git Repository"
3. เลือก repo นี้ แล้วกด Deploy (ไม่ต้องตั้งค่า build command ใดๆ เพราะเป็น static HTML ล้วน)
4. เสร็จแล้วจะได้ลิงก์ `https://ชื่อโปรเจกต์.vercel.app` ใช้แชร์ให้ทุกคนในทริปได้เลย

## Push ขึ้น GitHub ครั้งแรก
```bash
# 1. สร้าง repo ใหม่บน https://github.com/new (ตั้งชื่อ เช่น japan-trip-2026) อย่าติ๊กสร้าง README
# 2. ในโฟลเดอร์นี้ รันคำสั่ง (แทน YOUR-USERNAME และ REPO-NAME ด้วยของจริง)
git remote add origin https://github.com/YOUR-USERNAME/REPO-NAME.git
git branch -M main
git push -u origin main
```
เมื่อรัน `git push` ครั้งแรก เบราว์เซอร์หรือเทอร์มินัลจะถาม login GitHub — ใส่บัญชีของคุณเอง (แนะนำใช้ Personal Access Token แทนรหัสผ่านถ้า GitHub ขอ เพราะ GitHub เลิกรับรหัสผ่านตรงๆ ผ่าน HTTPS แล้ว สร้าง token ได้ที่ Settings → Developer settings → Personal access tokens)

## แก้ไขแผนภายหลัง
ข้อมูลแต่ละวันอยู่ในตัวแปร `days` ใน `<script>` ท้ายไฟล์ `index.html` แต่ละวันมี `table` (แถวละ `[เวลา, กิจกรรม, หมายเหตุ]`) และ `tips` (`type` เป็น `tip` หรือ `warn`) ส่วนรายการเตรียมของอยู่ใน `CHECKLIST` แก้ตรงนั้นแล้ว commit + push ใหม่ได้เลย Vercel จะ deploy อัตโนมัติทุกครั้งที่ push เข้า branch main

ลิงก์ไป Google Maps ใช้ฟังก์ชัน `P('ชื่อสถานที่', 'lat,lng')` หรือ `P('ชื่อสถานที่', 'คำค้นหา')` ถ้าไม่มีพิกัด — ใส่ในข้อความช่องกิจกรรมของ `table`

ฉากอนิเมชั่นเล็กๆ ที่หัวการ์ดแต่ละวันอยู่ในตัวแปร `SCENES` (เรียงตามลำดับวันเดียวกับ `DAYS`) แต่ละตัวคือ `[อีโมจิ, ท่าขยับ, ตำแหน่งซ้าย %, ความสูงจากพื้น px, ขนาด px, ดีเลย์ วินาที, ความยาว วินาที]` ท่าที่มี: bob, sway, hop, wave, pulse, twinkle, rise, fall, drop, jump, swim, drive, fly, takeoff, roll, stomp, wand, broom, swing
