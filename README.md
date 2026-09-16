# แผนเที่ยวญี่ปุ่น 7–19 ต.ค. 2026

เว็บเพจหน้าเดียวสรุปแผนเที่ยวญี่ปุ่นของครอบครัว 11 คน (13 วัน / รถเช่า 2 คัน)

## เนื้อหาในหน้า
- ภาพรวมทริปทั้ง 13 วัน
- แผนเส้นทางรายวันแบบอินเทอร์แอคทีฟ (เลือกวันด้านซ้าย ดูแผนผังเส้นทาง + รายละเอียดด้านขวา)
- ข้อมูลที่จอดรถ, เรื่องรถ, คนท้อง, เด็กเล็ก, แผนกระเป๋า
- Checklist สิ่งที่ต้องจองล่วงหน้า

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
ข้อมูลแต่ละวันอยู่ในตัวแปร `days` ใน `<script>` ท้ายไฟล์ `index.html` แก้ตรงนั้นแล้ว commit + push ใหม่ได้เลย Vercel จะ deploy อัตโนมัติทุกครั้งที่ push เข้า branch main
