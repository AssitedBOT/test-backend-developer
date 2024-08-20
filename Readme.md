# การทดสอบทักษะผู้พัฒนา Backend

## แนะนำ
ยินดีต้อนรับสู่การทดสอบทักษะผู้พัฒนา Backend! การทดสอบนี้ถูกออกแบบมาเพื่อประเมินทักษะของคุณในการพัฒนา RESTful API, การเชื่อมต่อ WebSocket, การใช้ FastAPI, Node.js, การจัดการแคชข้อมูล, การออกแบบฐานข้อมูล, และการทำงานร่วมกับ API ภายนอก โปรดทำตามคำแนะนำด้านล่างและส่งงานที่คุณทำเสร็จแล้วตามคำแนะนำ

## ภาพรวมของงาน

### 1. การพัฒนา RESTful API
**งานที่ต้องทำ:**  
สร้าง RESTful API สำหรับจัดการข้อมูลผู้ใช้งาน (User Management) ที่รองรับการทำงานแบบ CRUD (Create, Read, Update, Delete) โดย API ต้องมีการตรวจสอบสิทธิ์ (Authentication) ด้วย JWT เพื่อความปลอดภัย

### 2. การเชื่อมต่อ WebSocket
**งานที่ต้องทำ:**  
เพิ่มการรองรับ WebSocket ใน API ที่คุณพัฒนาจากงานที่ 1 โดยให้มีการแจ้งเตือนแบบเรียลไทม์ เมื่อมีการสร้างหรือแก้ไขข้อมูลผู้ใช้งาน

### 3. การใช้ FastAPI และ Node.js
**งานที่ต้องทำ:**  
เลือกใช้ FastAPI (Python) หรือ Node.js (Express.js) ในการพัฒนา API จากงานที่ 1 พร้อมอธิบายเหตุผลในการเลือกใช้ และเปรียบเทียบกับอีกทางเลือกหนึ่ง

### 4. การดึงข้อมูลจาก API ภายนอก
**งานที่ต้องทำ:**  
ดึงข้อมูลราคาสกุลเงินดิจิทัลปัจจุบัน (เช่น BTC/USDT) จาก Binance API และจัดเก็บลงในฐานข้อมูลที่คุณเลือก (SQL หรือ NoSQL) โดยข้อมูลควรถูกอัพเดททุก ๆ นาที

### 5. การทำงานร่วมกับ Frontend
**งานที่ต้องทำ:**  
สร้าง endpoint ที่ให้ Frontend สามารถเรียกใช้เพื่อดึงข้อมูลผู้ใช้งานพร้อมกับราคาสกุลเงินดิจิทัลล่าสุดที่ดึงจาก Binance

### 6. การจัดการ Data Caching ด้วย Redis
**งานที่ต้องทำ:**  
ใช้ Redis ในการแคชข้อมูลราคาสกุลเงินดิจิทัลที่ดึงจาก Binance API โดยตั้งค่า TTL (Time-to-Live) สำหรับข้อมูลที่แคชเพื่อลดการดึงข้อมูลจาก API หลัก

### 7. การออกแบบฐานข้อมูลและ Microservices
**งานที่ต้องทำ:**  
ออกแบบโครงสร้างฐานข้อมูลสำหรับจัดเก็บข้อมูลผู้ใช้งานและข้อมูลการเทรด โดยแสดงการออกแบบทั้งแบบ Microservices และ Monolithic อธิบายข้อดีและข้อเสียของแต่ละแบบ และเลือกแบบที่คุณคิดว่าเหมาะสมที่สุด

### 8. การทำงานร่วมกับ API ภายนอก
**งานที่ต้องทำ:**  
สร้าง API ภายในที่เชื่อมต่อกับ Binance API เพื่อดึงข้อมูลราคาสกุลเงินและให้บริการข้อมูลนี้กับ API ภายในอื่น ๆ พร้อมทั้งเพิ่มระบบ Authentication เพื่อรักษาความปลอดภัยของ API ภายในนี้

## เกณฑ์การประเมิน
- **คุณภาพของโค้ด:** ความชัดเจน การจัดระเบียบ และการปฏิบัติตามหลักการที่ดีที่สุดในการเขียนโค้ด
- **ความถูกต้อง:** ความถูกต้องและความสมบูรณ์ของการทำงาน
- **ประสิทธิภาพ:** การพิจารณาด้านประสิทธิภาพ โดยเฉพาะในการดึงข้อมูลและการจัดการแคชข้อมูล
- **การเขียนเอกสาร:** ความชัดเจนและความครบถ้วนของเอกสารประกอบ
- **การทดสอบ:** ความครอบคลุมและคุณภาพของการทดสอบที่ให้มา
- **ความคิดสร้างสรรค์:** แนวทางใหม่ ๆ หรือฟีเจอร์เพิ่มเติมที่ช่วยเพิ่มคุณค่าให้กับโซลูชัน

## วิธีการส่งงาน
- **Deployment:** ผู้สมัครต้อง deploy API ที่พัฒนาแล้วไปยังผู้ให้บริการ Cloud (เช่น Heroku, AWS, Vercel) และแนบลิงก์ URL สำหรับการทดสอบการใช้งานจริง
- **Postman Collection:** สร้างและส่ง Postman collection สำหรับการทดสอบ API พร้อมด้วยตัวอย่าง request และ response เพื่อให้ทีมงานสามารถทดสอบ API ได้ง่ายขึ้น
- **API Documentation:** อธิบายแต่ละ endpoint ของ API ใน `README.md` หรือใช้ Swagger ในการสร้างเอกสาร API ที่ชัดเจน พร้อมแนบลิงก์ URL ของเอกสาร
- **การทดสอบ:** ผู้สมัครต้องเขียน unit tests และรวมโค้ดการทดสอบใน repository

เรารอคอยที่จะเห็นผลงานของคุณ!
email: nanobotsup@gmail.com
ขอให้โชคดี!
