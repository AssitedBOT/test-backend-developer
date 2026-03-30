# 📌 Backend Developer Test

## 🎯 Objective
ทดสอบความสามารถในการออกแบบและพัฒนา Backend System แบบ Production-ready  
ครอบคลุม:

- RESTful API Design
- Authentication (JWT)
- WebSocket (Realtime)
- External API Integration (Binance)
- Caching (Redis)
- Database Design
- System Architecture (Monolith vs Microservices)

---

# 🧱 Scope งาน

## 1. User Management API (Core System)

### Requirement
พัฒนา RESTful API สำหรับจัดการผู้ใช้งาน (CRUD):

- Create User
- Get User (list + detail)
- Update User
- Delete User

### Constraints
- ต้องมี Authentication (JWT)
- Endpoint ต้องมี:
  - Validation input
  - Error handling ที่เหมาะสม

### Expected Behavior
- API ใช้งานได้จริง (ไม่ mock)
- Structure ต้อง scalable

---

## 2. WebSocket (Realtime System)

### Requirement
เพิ่ม WebSocket support โดย:

- เมื่อมีการ:
  - Create User
  - Update User
- ต้อง broadcast event ไปยัง client แบบ realtime

### Expected Events
- `user.created`
- `user.updated`

### Expected Behavior
- Client connect แล้ว receive event ได้ทันที
- ไม่มี delay หรือ duplicate event
- รองรับหลาย client พร้อมกัน

---

## 3. Tech Stack Selection

### Requirement
เลือกใช้ 1 อย่าง:

- FastAPI (Python)
- Node.js (Express / Fastify)

### Deliverable
ใน README ต้องอธิบาย:

- เหตุผลที่เลือก stack นี้
- เปรียบเทียบกับอีกตัวเลือก (ข้อดี / ข้อเสีย)

---

## 4. Binance Integration (External API + Realtime)

### Requirement

#### REST API
- ดึงราคาปัจจุบัน เช่น:
  - BTC/USDT

API:
- https://api.binance.com


#### WebSocket
- Subscribe realtime ticker:
  - wss://stream.binance.com:9443


### Data Handling
- ต้องเก็บข้อมูลลง database
- ต้องมี process สำหรับ update ข้อมูลทุก ๆ 1 นาที (minimum)
- ต้อง handle reconnect เมื่อ WebSocket หลุด

### Expected Behavior
- ระบบต้องไม่ crash หาก Binance ล่ม
- ต้องมี retry / fallback logic
- แยก logic การดึงข้อมูลออกจาก controller

---

## 5. Aggregated API (สำหรับ Frontend)

### Requirement

สร้าง endpoint:
  GET /dashboard


### Response ต้องประกอบด้วย:
- ข้อมูลผู้ใช้งาน
- ราคาล่าสุดของ crypto (จาก Binance)

### Expected Behavior
- Response ต้องเร็ว (ใช้ cache)
- Data ต้อง sync และ consistent

---

## 6. Redis Caching

### Requirement
ใช้ Redis สำหรับ cache:

- ราคาจาก Binance
- ข้อมูลที่เรียกบ่อย

### Constraints
- ต้องกำหนด TTL (เช่น 30–60 วินาที)
- ต้องลดจำนวน request ไปยัง Binance

### Expected Behavior
- Cache hit → ไม่เรียก external API
- Cache miss → fetch + set cache

---

## 7. Database Design & Architecture

### Requirement

#### Database Design
ออกแบบ schema สำหรับ:
- Users
- Crypto Prices / Market Data

#### Architecture Comparison
อธิบาย:

- Monolithic Architecture
- Microservices Architecture

### Deliverable
- อธิบาย:
  - ข้อดี / ข้อเสีย
  - Use case ที่เหมาะสม
- เลือกแบบที่เหมาะกับระบบนี้ พร้อมเหตุผล

---

## 8. Internal API Layer

### Requirement
สร้าง internal service สำหรับ:

- ดึงข้อมูลจาก Binance
- ให้ service อื่นเรียกใช้งาน

### Constraints
- ต้องมี authentication (เช่น API key / JWT)
- ห้ามให้ controller เรียก Binance โดยตรง

### Expected Behavior
- ลด coupling กับ external API
- สามารถ scale แยก service ได้ในอนาคต

---

# 🧪 Non-Functional Requirements

### Performance
- API response time ต้องเหมาะสม (< 300ms เมื่อ cache hit)
- รองรับ concurrent requests ได้

### Reliability
- Handle error จาก external API ได้
- มี retry / timeout mechanism

### Code Quality
- Clean code
- Separation of concerns
- โครงสร้าง project ชัดเจน

---

# 📦 Deliverables

ผู้สมัครต้องส่ง:

## 1. Source Code
- Git Repository

## 2. Deployment
- Deploy บน Cloud (เช่น AWS / Render / Railway)
- แนบ URL สำหรับทดสอบ

## 3. API Documentation
- Swagger / OpenAPI หรือ README
- อธิบายทุก endpoint

## 4. Postman Collection
- พร้อมตัวอย่าง request / response

## 5. Unit Tests
- ครอบคลุม business logic สำคัญ

## 6. README ต้องมี:
- วิธี run project
- Tech stack ที่ใช้ + เหตุผล
- Architecture decision
- ปัญหาที่เจอ + วิธีแก้

---

# ⚖️ Evaluation Criteria

### 🔥 Core System
- CRUD + Auth ใช้งานได้จริง
- WebSocket ทำงานถูกต้อง

### 🧠 Code Quality
- โครงสร้างดี
- Maintainable

### ⚡ Performance
- ใช้ cache ถูกต้อง
- ลด external API call

### 🔐 Security
- JWT implementation ถูกต้อง

### 🧪 Testing
- มี test ที่ meaningful

### 📄 Documentation
- ชัดเจน อ่านแล้วเข้าใจ

### 🎯 Architecture Thinking
- อธิบาย trade-off ได้
- เลือก solution มีเหตุผล

---

# 🚫 ข้อห้าม

- ห้าม hardcode data แทน logic
- ห้ามไม่มี authentication
- ห้ามเรียก Binance API ทุก request (ต้องมี cache)
- ห้ามเขียนทุกอย่างในไฟล์เดียว

---

# 🧪 Expected Level

นี่คือ **Mid → Senior Level Test**

เราต้องการดูว่า:

- คุณออกแบบ system ได้จริงไหม
- คุณเข้าใจ real-world constraint ไหม
- คุณ optimize performance เป็นไหม
- คุณเขียน code ที่ scale ได้หรือไม่

---

# 📩 Submission

- ส่งผลงานมาที่: **nanobotsup@gmail.com**
- แนบ:
  - Git repo
  - Deployment URL
  - Postman collection

---

💡 Bonus: หากมีการออกแบบระบบให้รองรับ scaling (เช่น queue, pub/sub, horizontal scaling) จะได้รับการพิจารณาเป็นพิเศษ

🚀 ขอให้โชคดี!
