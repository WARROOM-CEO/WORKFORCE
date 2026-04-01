# Scheduled Tasks Setup

ใช้คำสั่ง `/schedule` ใน Claude Cowork เพื่อตั้งเวลาทำงานอัตโนมัติ

---

## Task 1: รายงานเช้าวันจันทร์

**ความถี่:** ทุกสัปดาห์ วันจันทร์ เช้า

**Prompt:**
```
ค้นหา publishers ที่รับเกม roguelite หรือ co-op multiplayer บน Steam จำนวน 10 รายตามเกณฑ์ใน CLAUDE.md
enrich ข้อมูลเบื้องต้น (ชื่อ publisher, เว็บไซต์, เกมที่เคย publish, genre ที่รับ)
ให้คะแนนตาม lead-scoring skill
สร้างไฟล์ CSV วางใน prospects/1-new/ สำหรับ lead ใหม่
ย้าย lead ที่ผ่านเกณฑ์ไป prospects/3-scored/
สร้างรายงานสรุปสั้นๆ วางใน reports/weekly/ ระบุ:
- จำนวน lead ใหม่ที่เพิ่มเข้ามา
- จำนวน lead ในแต่ละสถานะของ pipeline
```

---

## Task 2: เตรียมข้อมูลก่อนติดต่อ (ทุกวันทำการ เช้า)

**ความถี่:** ทุกวันทำการ 08:00

**Prompt:**
```
ดูจาก Google Calendar ว่าวันนี้มีนัด call กับ publisher รายไหนบ้าง
ค้นหาข่าวล่าสุดของบริษัทนั้นจากเว็บไซต์หรือ LinkedIn
ดึงประวัติการติดต่อจาก Gmail
เตรียม talking points สำหรับแต่ละราย
สร้างไฟล์สรุปวางไว้ใน research/company-notes/ ตามชื่อ publisher
```

---

## Task 3: ติดตาม Follow-up (ทุกวันทำการ)

**ความถี่:** ทุกวันทำการ 14:00

**Prompt:**
```
ตรวจสอบ lead ใน prospects/4-contacted/ ดูว่ารายไหนส่งอีเมลไปแล้วเกิน 3 วัน
ค้นหาใน Gmail ว่ามีการตอบกลับหรือยัง
ถ้าลูกค้าตอบกลับแล้ว → ย้าย lead รายนั้นไป prospects/5-replied/
ถ้ายังไม่ตอบและยังติดตามไม่ครบ 3 รอบ → ร่างอีเมล follow-up โดยใช้ template จาก outreach/templates/follow-up-1-publisher.md แล้ว personalize ตามข้อมูลของแต่ละราย เก็บร่างไว้ใน outreach/sent/drafts/
ถ้าติดตามครบ 3 รอบแล้วยังไม่ตอบ → ย้าย lead รายนั้นไป prospects/8-closed-lost/
```

---

## Task 4: สรุปผลประจำสัปดาห์ (ทุกวันศุกร์)

**ความถี่:** ทุกวันศุกร์ 17:00

**Prompt:**
```
สร้างรายงานสรุปผลการหา publisher ทั้งสัปดาห์ ประกอบด้วย:
- จำนวน lead ใหม่ที่พบ
- จำนวนอีเมลที่ส่ง
- อัตราการตอบกลับ
- จำนวนนัด call ที่ได้
- สถานะ pipeline ทั้งหมด
- Lead ที่มีแนวโน้มดีที่สุด 3 ราย
สร้างเป็นไฟล์ markdown วางไว้ใน reports/weekly/
```

---

## วิธีตั้ง Scheduled Task

1. เปิด Claude Cowork
2. พิมพ์ `/schedule`
3. ตอบคำถามตามขั้นตอน:
   - ทำอะไร → paste prompt ด้านบน
   - ทำบ่อยแค่ไหน → เลือกความถี่
   - ใช้ connectors อะไร → Gmail, Google Calendar, Google Drive

## หมายเหตุ

- Claude Desktop ต้องเปิดอยู่และเชื่อมต่อ internet สำหรับ scheduled tasks
- ถ้าปิดไป task ที่พลาดจะไม่ทำงานย้อนหลัง
