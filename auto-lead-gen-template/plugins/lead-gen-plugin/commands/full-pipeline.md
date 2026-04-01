---
name: full-pipeline
description: รันระบบหาลูกค้าใหม่ครบวงจร ตั้งแต่ค้นหาจนถึงอัปเดต CRM
---

# Full Lead Generation Pipeline

รันขั้นตอนต่อไปนี้ตามลำดับ:

## Step 1: Prospect Research
ค้นหาบริษัทเป้าหมายใหม่ตามเกณฑ์ใน CLAUDE.md
- จำนวนที่ต้องการ: $1 (default: 10)
- ใช้ skill: prospect-research
- ผลลัพธ์: ไฟล์ CSV ใน prospects/1-new/

## Step 2: Lead Enrichment
เพิ่มข้อมูลรายละเอียดให้ lead ที่พบในขั้นตอนที่ 1
- ใช้ skill: lead-enrichment
- ผลลัพธ์: ไฟล์ enriched CSV ใน prospects/2-enriched/

## Step 3: Lead Scoring
ให้คะแนนและจัดลำดับความสำคัญ lead ทั้งหมด
- ใช้ skill: lead-scoring
- ผลลัพธ์: ไฟล์ scored CSV ใน prospects/3-scored/

## Step 4: Outreach Writing
ร่างอีเมลติดต่อสำหรับ lead ที่ได้ระดับ Hot และ Warm เท่านั้น
- ใช้ skill: outreach-writer
- ผลลัพธ์: ร่างอีเมลใน outreach/sent/drafts/

## Step 5: CRM Update
บันทึก lead ทั้งหมดเข้า CRM หรือ spreadsheet
- ใช้ skill: crm-update
- ผลลัพธ์: ข้อมูลใน CRM และสรุปใน reports/

## เมื่อเสร็จทุกขั้นตอน
แจ้งผู้ใช้ว่า pipeline เสร็จสมบูรณ์ พร้อมสรุป:
- จำนวน lead ใหม่ที่พบ
- จำนวน Hot / Warm / Cool / Low
- จำนวนร่างอีเมลที่สร้าง
- รายการที่ต้องตรวจสอบก่อนส่ง
