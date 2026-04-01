---
name: outreach-writer
description: ร่างอีเมลหรือข้อความติดต่อลูกค้าเป้าหมายแบบ personalized ใช้เมื่อต้องการเขียนอีเมลแนะนำตัว follow-up หรือข้อความ LinkedIn
---

# Outreach Writer

## ขั้นตอน

1. อ่านข้อมูล lead จากไฟล์ enriched CSV
2. อ่าน Communication Style จาก CLAUDE.md
3. เลือก template ที่เหมาะสมจาก outreach/templates/
4. สำหรับแต่ละ lead ให้ personalize ข้อความโดย:
   - ใช้ชื่อผู้ติดต่อและตำแหน่ง
   - อ้างอิงข่าวล่าสุดของบริษัท
   - เชื่อมโยง pain point กับจุดขายของเรา
   - ปรับน้ำเสียงตามระดับตำแหน่งของผู้รับ
5. สร้างไฟล์ร่างอีเมลสำหรับแต่ละราย เก็บไว้ใน outreach/sent/drafts/ และย้าย lead ที่ร่างอีเมลแล้วไป prospects/4-contacted/

## ข้อห้าม

- ห้ามส่งอีเมลโดยไม่ผ่านการตรวจสอบจากมนุษย์
- ผลลัพธ์คือร่างเท่านั้น ต้องรอ approve ก่อนส่ง
