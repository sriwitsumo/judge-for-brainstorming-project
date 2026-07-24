# Biogang Judging Committee

จำลองทีมระดมสมอง 2 มุม (เทค/ชีวะ) และคณะกรรมการอิสระ 5 ท่าน สำหรับคิดและกลั่นกรองไอเดียโครงงาน **Biogang Challenge 2026** (Youth Acting For Nature Positive) — ต่างจากการให้โมเดลเดียวสวมบททุกคนในบทสนทนาเดียว ตรงที่กรรมการ 5 ท่านในปลั๊กอินนี้รันเป็น **agent แยก context จริง** ทำให้ "ประเมินอิสระก่อนค่อยอ่านความเห็นคนอื่น" เป็นจริงตามกติกาการประกวดจริง (ISEF/YSC ใช้หลักการเดียวกัน) ไม่ใช่แค่จำลองด้วยการสลับบทบาทในข้อความเดียวกัน

## ส่วนประกอบ

### Skills
- **biogang-project-ideation** — orchestration skill หลัก คุมกระบวนการ 3 ขั้นตอน (ระดมสมอง → กรรมการ → วนลูปแก้ไข) ทีละหัวข้อ Nature Positive จนครบ 20 หัวข้อ พร้อม reference กติกาการแข่งขันและฐานความรู้กรรมการจริงแนบมาด้วย

### Agents (7 ตัว)

**ทีมระดมสมอง (STEP 1):**
- `biogang-tech-brainstormer` — มุมเทคโนโลยี (Electronics/IoT/AI/Fabrication)
- `biogang-bio-brainstormer` — มุมชีวะ/นิเวศ

**คณะกรรมการอิสระ (STEP 2):**
- `biogang-judge-tech-engineering` — เทคนิค/วิศวกรรม
- `biogang-judge-bio-environment` — ชีววิทยา/สิ่งแวดล้อม/ความยั่งยืน
- `biogang-judge-research-methodology` — ระเบียบวิธีวิจัย/สถิติ
- `biogang-judge-innovation-business` — นวัตกรรม/ผู้ใช้/ธุรกิจ (รวม novelty gate)
- `biogang-judge-feasibility-competition` — ความเป็นไปได้จริงสำหรับนักเรียนมัธยม (เกณฑ์แข็ง 4 ข้อ + งบ)

## Setup

ไม่ต้องตั้งค่า environment variable หรือเชื่อมต่อบริการภายนอกใด ๆ — ไม่มี MCP server ในปลั๊กอินนี้ ทุก agent ใช้ web search ที่มีอยู่ในสภาพแวดล้อม Cowork ได้ตามปกติเพื่อเช็ค prior art/feasibility/ต้นทุนจริง

## การใช้งาน

พิมพ์ข้อความทำนอง "คิดโครงงานประกวด Biogang" หรือ "ไปหัวข้อต่อไป" เพื่อ trigger `biogang-project-ideation` skill — skill นี้จะเป็นคนสั่ง dispatch agent ทั้ง 7 ตัวเองตามจังหวะของแต่ละ STEP ผู้ใช้ไม่ต้องเรียก agent เองโดยตรง

**สำคัญ:** ผู้ใช้จะเห็นเฉพาะไอเดียที่ผ่านกรรมการครบ 5 ท่านแล้วเท่านั้น (ระดับ Bronze ขึ้นไป, ไม่มีจุดอ่อนค้างจาก cross-examination) — งานร่างและไอเดียที่ตกกลางทางจะไม่ถูกโชว์ เว้นแต่ผู้ใช้ขอดู

## หมายเหตุ

- งบต้นแบบตั้งไว้ที่ < 10,000 บาท/โครงการ (ปรับลดจากเกณฑ์เดิม 50,000 บาทของ Biogang เอง ตามที่ผู้ใช้กำหนดเพิ่มเติม) — แก้ไขได้ที่ `skills/biogang-project-ideation/SKILL.md` และไฟล์ agent กรรมการท่านที่ 5 หากต้องการเปลี่ยนอีก
- กติกา/กำหนดการ/เงินรางวัลอย่างเป็นทางการอาจอัปเดตย่อยได้ทุกปี — เช็ค `references/competition-brief.md` และตรวจสอบกับประกาศทางการของ BEDO/Biogang หากไม่แน่ใจ
