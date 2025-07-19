# n8n Docker Tutorial

ตัวอย่างการติดตั้งและรัน **n8n** ด้วย **Docker Compose** แบบง่าย ๆ บน macOS/Windows/Linux

---
1. **Docker Desktop**  
   - macOS: https://www.docker.com/products/docker-desktop  
   - Windows: https://www.docker.com/products/docker-desktop  
   - Linux: ติดตั้ง Docker Engine ตามคู่มือของดิสโทร (Ubuntu, CentOS ฯลฯ)

2. (ถ้ายังไม่มี) **Git**  
   - macOS: `brew install git`  
   - Windows: https://git-scm.com/download/win  
   - Linux: `sudo apt-get install git` (Ubuntu/Debian) หรือ `sudo yum install git` (RHEL/CentOS)

---

3. Clone Repository

```bash
cd <your-folder>
git clone https://github.com/benzondataen/n8n-docker-tutorial.git
cd n8n-docker-tutorial
```

4. เริ่มต้น (Start) (เปิด Docker Desktop ก่อนนะ)
```bash
# ใช้ Docker Compose V2
docker compose up -d

# หรือถ้าใช้ Compose V1
docker-compose up -d
```

– คำสั่งนี้จะดาวน์โหลด image, สร้าง container ชื่อ `n8n-benz` และรันแบบ detached  
– ข้อมูล Workflow จะเก็บ persist ไว้ที่ volume `n8n_data`  

5. ตรวจสอบสถานะ
```bash
# ดู container ที่รันอยู่
docker ps

# ดู logs ของ n8n container
docker logs -f n8n-benz
```

6. เข้าถึง n8n
เปิดเบราเซอร์ไปที่:

```
http://localhost:5678
```

หากรันสำเร็จ คุณจะเห็นหน้า UI ของ n8n พร้อมใช้งานทันที

7. หยุดและลบ Container
```bash
# หยุด container
docker compose down

# (ถ้าใช้ V1)
docker-compose down
```

– ถ้าต้องการลบ volume ด้วย ให้เพิ่ม flag `-v`:
  ```bash
  docker compose down -v
  ```

---

8. เอกสารอ้างอิง
- n8n Docs: https://docs.n8n.io/  
- Docker Docs: https://docs.docker.com/  

---
