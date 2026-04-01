---
name: crm-update
description: อัปเดตข้อมูล lead และกิจกรรมการขายเข้า CRM ใช้เมื่อมี lead ใหม่ที่ต้องบันทึก หรือเมื่อมีการเปลี่ยนแปลงสถานะ lead
---

# CRM Update

## ขั้นตอน

1. อ่านข้อมูล lead จาก prospects/3-scored/
2. สำหรับ lead ที่ได้ระดับ Hot หรือ Warm:
   - สร้าง lead record ใหม่ใน CRM (ถ้ามี CRM connector)
   - บันทึกคะแนน ระดับ และ recommended action
   - ตั้ง follow-up task ใน CRM
3. ถ้าไม่มี CRM connector:
   - สร้างไฟล์ Excel สรุปใน reports/ แทน
   - สร้างนัดหมาย follow-up ใน Google Calendar
4. ส่งสรุปเข้า Slack ช่อง sales (ถ้ามี Slack connector)

## ข้อห้าม

- ห้ามลบหรือเขียนทับข้อมูลเดิมใน CRM
- ข้อมูลที่ยังไม่ได้ยืนยันให้ระบุ status เป็น "unverified"
