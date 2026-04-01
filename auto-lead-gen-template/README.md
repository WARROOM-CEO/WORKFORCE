# Auto Lead Gen Template

ระบบหาลูกค้าใหม่แบบอัตโนมัติด้วย Claude Cowork

> คู่มือนี้เป็น Template — แก้ไข CLAUDE.md ให้ตรงกับธุรกิจของคุณก่อนใช้งาน

## โครงสร้าง

```
auto-lead-gen/
├── CLAUDE.md                    # คู่มือโปรเจกต์สำหรับ Claude
├── README.md
├── prospects/                   # ข้อมูลลูกค้าเป้าหมาย (Pipeline 8 สถานะ)
│   ├── 1-new/
│   ├── 2-enriched/
│   ├── 3-scored/
│   ├── 4-contacted/
│   ├── 5-replied/
│   ├── 6-meeting-booked/
│   ├── 7-closed-won/
│   └── 8-closed-lost/
├── outreach/                    # ข้อความติดต่อลูกค้า
│   ├── templates/               # Template อีเมล
│   └── sent/drafts/            # ร่างอีเมลที่รอ approve
├── research/                    # ข้อมูลวิจัยบริษัทเป้าหมาย
│   ├── company-notes/
│   └── industry-reports/
├── reports/                     # รายงานสรุปผล
│   ├── weekly/
│   └── monthly/
├── skills/                      # Custom skills
│   └── lead-scoring/
└── plugins/                     # Claude Cowork plugin
    └── lead-gen-plugin/
```

## วิธีใช้

### 1. แก้ไข CLAUDE.md
เปิดไฟล์ `CLAUDE.md` และแก้ไขข้อมูลให้ตรงกับธุรกิจของคุณ:
- ชื่อบริษัทและบริการ
- กลุ่มเป้าหมาย (อุตสาหกรรม, ขนาด, พื้นที่)
- Pain points หลัก
- สไตล์การสื่อสาร

### 2. เชื่อมต่อ MCP Connectors
ใน Claude Desktop App → Settings → Connectors:
- **Gmail** - ส่งและอ่านอีเมล
- **Google Drive** - เก็บเอกสาร
- **Google Calendar** - จัดตารางนัดหมาย
- **HubSpot/Salesforce** (optional) - เชื่อม CRM

### 3. ติดตั้ง Plugin
1. ไปที่ Claude Desktop → Customize → Plugins
2. อัปโหลดโฟลเดอร์ `plugins/lead-gen-plugin`
3. พิมพ์ `/lead-gen-plugin:full-pipeline 10` เพื่อรันทั้งระบบ

### 4. ตั้ง Scheduled Tasks
ใน Claude Cowork พิมพ์ `/schedule` เพื่อตั้งเวลาทำงานอัตโนมัติ:
- **รายงานจันทร์** - ค้นหา lead ใหม่ พร้อม enrich และ score
- **เช้าทุกวันทำการ** - เตรียมข้อมูลก่อน call ลูกค้า
- **Follow-up ทุกวัน** - ตรวจสอบและติดตาม lead
- **สรุปผลวันศุกร์** - สร้างรายงานสัปดาห์

## Lead Scoring

| คะแนน | ระดับ | การดำเนินการ |
|-------|-------|-------------|
| 80-100 | 🔥 Hot | ติดต่อทันที |
| 60-79 | 🌡️ Warm | ติดต่อภายในสัปดาห์นี้ |
| 40-59 | ❄️ Cool | เก็บไว้ติดตาม |
| < 40 | 📉 Low | เก็บไว้ในฐานข้อมูล |

## กฎสำคัญ

⚠️ **อีเมลทุกฉบับต้องผ่านการตรวจสอบจากมนุษย์ก่อนส่ง**

- ข้อมูลที่ Claude หามาได้อาจไม่ถูกต้อง ต้องยืนยันก่อนใช้งาน
- ปฏิบัติตาม PDPA ในการเก็บและใช้ข้อมูลส่วนบุคคล
- คอมพิวเตอร์ต้องเปิดและ Claude Desktop App ต้องทำงานอยู่สำหรับ scheduled tasks

## ต้นทุน

- **Claude Pro**: ~700 บ./เดือน (เพียงพอสำหรับเริ่มต้น)
- **Claude Max**: ~3,500 บ./เดือน (สำหรับใช้งานหนัก)

---

_ต้นทาง: บทความ "สร้างระบบหาลูกค้าใหม่แบบ Auto ด้วย Claude Cowork"_
