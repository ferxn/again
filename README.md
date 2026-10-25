# KLOZNN

หน้าเว็บ static ใช้ GitHub Pages ไม่มี build step

## ขึ้นเว็บ
1. สร้าง repo บน GitHub (public) แล้ว push ทุกไฟล์ในโฟลเดอร์นี้
2. Settings > Pages > Source: Deploy from a branch > main / root
3. เว็บอยู่ที่ https://USER.github.io/REPO/

## แก้เนื้อหา มี 2 วิธี
**A. หน้า studio (แนะนำ)** เปิด https://USER.github.io/REPO/studio-llgz9h/
- ครั้งแรกใส่ username, ชื่อ repo, และ token (fine-grained, เลือกเฉพาะ repo นี้, Contents = Read and write)
- แก้ tagline, ลิงก์, สถานะ collab, theme, โพสต์เพลงใหม่ (ขึ้น 3 วันแล้วหายเอง), อัปเพลง/วิดีโอ แล้วกด Save
- กด Save แล้วเว็บอัปเดตใน 1-2 นาที
- จะเปลี่ยนชื่อโฟลเดอร์ studio-llgz9h เป็นอะไรก็ได้ที่เดายาก

**B. แก้ไฟล์เอง** แก้ config.json (tag, open, theme, links, tracks, video) แล้ว git push
- เพลง: ไฟล์ใน audio/ แล้วเพิ่ม {"t": "ชื่อเพลง", "u": "audio/song.mp3"} ใน tracks
- วิดีโอ: ไฟล์ใน video/ แล้วตั้ง "video": "video/bg.mp4"
- การ์ดเพลงใหม่: แก้ releases.json เป็น {"t": "ชื่อ", "u": "ลิงก์", "at": 1760000000000} (at = เวลาเป็น ms)

ทดสอบในเครื่องต้องรันเซิร์ฟเวอร์ (เปิดไฟล์ตรงๆ โหลด config ไม่ได้): python3 -m http.server

## หมายเหตุ
- token ของ studio เก็บในเบราว์เซอร์เครื่องที่ใช้เท่านั้น อย่าแชร์ และตั้งวันหมดอายุไว้
- ไฟล์เพลง/วิดีโอแนะนำไม่เกิน 25 MB ต่อไฟล์ (GitHub รับสูงสุด 100 MB)
