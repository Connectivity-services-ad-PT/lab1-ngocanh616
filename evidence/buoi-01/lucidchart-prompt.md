# Prompt vẽ Service Boundary Diagram trên Lucidchart

> Copy toàn bộ nội dung trong khối bên dưới và dán vào ô "Describe your diagram" của Lucidchart AI.

---

## Prompt (Tiếng Anh — Lucidchart AI hoạt động tốt nhất với tiếng Anh)

```
Create a professional Service Boundary Diagram for an "IoT Ingestion Service" with 4 clearly labeled sections arranged left to right. Use a clean, modern style with rounded rectangles, soft colors, and clear labels.

=== SECTION 1: ACTOR (leftmost, light blue background) ===
Title: "1. Actor — Who interacts with the system?"
Show these actors as icons with labels:
- IoT Devices / Sensors (use a device/sensor icon)
- IoT Gateway (use a router/gateway icon)
- Admin / Monitoring System (use a person/monitor icon)
Add a note below: "Devices and gateways send telemetry data into the system. Admin monitors health."

=== SECTION 2: BOUNDARY (center-left, light green background with dashed border) ===
Title: "2. Boundary — What does the team build vs integrate?"
Draw a large dashed-border rectangle labeled "System Boundary".
Inside the boundary (labeled "Team Controls & Builds"):
- IoT Ingestion Service (central gear/service icon)
- REST API Endpoint (POST /api/v1/telemetry)
- MQTT Listener (subscribe to telemetry/# topics)
- Authentication & Validation module
- Queue Publisher module

Outside the boundary on the LEFT (labeled "External — Send Data"):
- IoT Devices (arrow pointing INTO the boundary)

Outside the boundary on the RIGHT (labeled "External — Receive Data"):
- Message Broker (Kafka / RabbitMQ) — the team only integrates, does not manage
- Device Management Service — the team only calls its API to verify devices

Add a legend:
- Solid border = Team controls & builds
- Dashed border = Team only integrates (external)

=== SECTION 3: SERVICE (center-right, light purple background) ===
Title: "3. Service — Internal functional blocks"
Show a box labeled "IoT Ingestion System" containing these sub-services as rounded boxes:
- API Gateway / MQTT Broker (entry point)
- Authentication Service (validates device token/API key)
- Data Validation & Normalization (checks schema, cleans data)
- Queue Publisher (publishes validated data to message queue)
- Health Check API (GET /health)

Draw arrows showing the internal flow:
API Gateway → Authentication → Data Validation → Queue Publisher

=== SECTION 4: PLATFORM (rightmost, light gray background) ===
Title: "4. Platform — Infrastructure & tools"
Show these platform components as icons in a grid layout:
- Docker / Container
- Cloud Hosting (AWS / Azure / On-premise)
- Message Queue (Kafka / RabbitMQ)
- Database (optional, for logging/audit)
- Monitoring (Prometheus / Grafana)
- Authentication (JWT / API Key management)

=== DATA FLOW ARROWS (across all sections) ===
1. IoT Device → (HTTP POST / MQTT) → API Gateway
2. API Gateway → Authentication Service
3. Authentication Service → (verify device) → Device Management Service [external]
4. Data Validation → Queue Publisher
5. Queue Publisher → (publish) → Message Queue [external]
6. All services run on → Platform

=== STYLE NOTES ===
- Use soft pastel colors: light blue for actors, light green for boundary, light purple for services, light gray for platform
- Use rounded rectangles for all boxes
- Use dashed lines for external/integration boundaries
- Use solid lines for internal team boundaries
- Add numbered section headers (1, 2, 3, 4) with colored circle badges
- Keep the layout horizontal (left to right) to show the flow
- Make it look professional and presentation-ready
```

---

## Prompt (Tiếng Việt — dùng nếu công cụ hỗ trợ tiếng Việt)

```
Vẽ sơ đồ Service Boundary Diagram cho dịch vụ "IoT Ingestion Service" với 4 phần chính sắp xếp từ trái sang phải, phong cách chuyên nghiệp, màu pastel nhẹ.

=== PHẦN 1: ACTOR (bên trái, nền xanh dương nhạt) ===
Tiêu đề: "1. Actor — Ai tương tác với hệ thống?"
Các actor:
- Thiết bị IoT / Cảm biến (icon thiết bị)
- IoT Gateway (icon router)
- Quản trị viên / Hệ thống giám sát (icon người dùng)
Ghi chú: "Thiết bị gửi dữ liệu telemetry. Admin giám sát health."

=== PHẦN 2: BOUNDARY (giữa trái, nền xanh lá nhạt, viền nét đứt) ===
Tiêu đề: "2. Boundary — Nhóm xây phần nào?"
Vẽ hình chữ nhật viền nét đứt lớn ghi "Ranh giới hệ thống".

Bên trong ranh giới (Nhóm kiểm soát & xây dựng):
- IoT Ingestion Service (icon bánh răng)
- REST API Endpoint (POST /api/v1/telemetry)
- MQTT Listener
- Module Xác thực & Kiểm tra dữ liệu
- Module Đẩy dữ liệu vào Queue

Bên ngoài ranh giới (bên trái - Gửi dữ liệu):
- Thiết bị IoT (mũi tên chỉ VÀO ranh giới)

Bên ngoài ranh giới (bên phải - Nhận dữ liệu):
- Message Broker (Kafka / RabbitMQ) — chỉ tích hợp
- Device Management Service — chỉ gọi API xác minh thiết bị

Chú giải:
- Viền liền = Nhóm kiểm soát, xây dựng
- Viền nét đứt = Chỉ tích hợp từ bên ngoài

=== PHẦN 3: SERVICE (giữa phải, nền tím nhạt) ===
Tiêu đề: "3. Service — Các khối chức năng bên trong"
Hộp lớn "Hệ thống IoT Ingestion" chứa:
- API Gateway / MQTT Broker (điểm vào)
- Xác thực thiết bị (kiểm tra Token/API Key)
- Chuẩn hóa & Kiểm tra dữ liệu (validate schema)
- Đẩy dữ liệu (Queue Publisher)
- Health Check API (GET /health)

Luồng: API Gateway → Xác thực → Chuẩn hóa → Queue Publisher

=== PHẦN 4: PLATFORM (bên phải, nền xám nhạt) ===
Tiêu đề: "4. Platform — Nền tảng hạ tầng"
Hiển thị dạng lưới icon:
- Docker / Container
- Cloud (AWS / Azure)
- Message Queue (Kafka / RabbitMQ)
- Database (log/audit)
- Monitoring (Prometheus / Grafana)
- Authentication (JWT / API Key)

=== MŨI TÊN LUỒNG DỮ LIỆU ===
1. Thiết bị IoT → (HTTP/MQTT) → API Gateway
2. API Gateway → Xác thực
3. Xác thực → (verify) → Device Management [bên ngoài]
4. Chuẩn hóa → Queue Publisher
5. Queue Publisher → (publish) → Message Queue [bên ngoài]
6. Tất cả service chạy trên → Platform
```

---

## Hướng dẫn sử dụng trên Lucidchart

1. Mở **Lucidchart** → Tạo Diagram mới (Blank)
2. Bấm nút **"AI"** hoặc **"Generate with AI"** (góc trên bên trái hoặc thanh công cụ)
3. Chọn **"Flowchart"** hoặc **"Custom Diagram"**
4. **Paste** toàn bộ prompt tiếng Anh ở trên vào ô mô tả
5. Bấm **Generate** → Lucidchart sẽ tự động vẽ sơ đồ
6. Chỉnh sửa lại vị trí, màu sắc nếu cần

> **Lưu ý:** Nếu Lucidchart AI không hỗ trợ prompt dài, bạn có thể chia thành 4 lần generate riêng (mỗi lần 1 section) rồi ghép lại trên cùng 1 canvas.
