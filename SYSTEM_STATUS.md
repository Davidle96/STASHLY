# STASHLY - SYSTEM STATUS & ARCHITECTURE CONTEXT

> **Lưu ý quan trọng cho AI Assistant & Developer:**  
> File này lưu trữ toàn bộ bức tranh kiến trúc, hiện trạng công nghệ và trạng thái phát triển của dự án STASHLY.  
> **Quy tắc:** Trước khi thực hiện tác vụ, hãy đọc file này để nắm ngữ cảnh mà **không cần quét lại toàn bộ source code** nhằm tối ưu token và thời gian. Khi thêm hoặc cập nhật tính năng lớn, **bắt buộc cập nhật lại file này**.

*Lần cập nhật gần nhất: 2026-09-18*

---

## 1. Tổng quan dự án (Project Overview)
- **Tên dự án:** STASHLY (Smart Home & Personal Storage Inventory Management System)
- **Mục tiêu:** Hệ thống quản lý lưu trữ cá nhân & gia đình thông minh. Biến các thùng đồ vật lý thành kho số tra cứu được bằng QR Code & Reverse Search.
- **Mô hình kinh doanh:** Freemium (Free vs Pro Plan).
- **Cấu trúc Repository:**
  ```
  STASHLY/
  ├── backend/          # API Service (Node.js, Express/Fastify, Prisma ORM, PostgreSQL)
  ├── frontend/         # Web Dashboard (React 19, TypeScript, Vite)
  ├── mobile/           # Mobile App (Flutter, mobile_scanner cho Android & iOS)
  ├── README.md         # Giới thiệu sản phẩm & feature specs
  └── SYSTEM_STATUS.md  # Ngữ cảnh kiến trúc & hiện trạng hệ thống
  ```

---

## 2. Kiến trúc & Công nghệ (Tech Stack)

| Component         | Công nghệ chính                      | Mục đích & Thư viện chủ đạo                                           |
|-------------------|--------------------------------------|-----------------------------------------------------------------------|
| **Database**      | PostgreSQL                           | Quan hệ dữ liệu chặt chẽ, Full-text Search, Relational Integrity      |
| **Backend**       | Node.js, Prisma ORM, Express/Fastify | RESTful API, sinh Type-safe models, Auth JWT, Quản lý nghiệp vụ       |
| **Web Frontend**  | React 19, TypeScript, Vite           | Web Dashboard quản lý kho đồ, in tem nhãn QR code PDF hàng loạt       |
| **Mobile App**    | Flutter (Dart SDK ^3.11.4)           | Scan QR xem nhanh đồ bên trong hộp (Scan-to-Peek), chụp ảnh, tìm kiếm |
| **Storage**       | Cloudflare R2 / S3 (Dự kiến)         | Lưu trữ hình ảnh đồ đạc và container                                  |

---

## 3. Bản đồ Nghiệp vụ & Data Model (Hierarchy)

Luồng phân cấp dữ liệu vật lý:
```
Household (Gia đình/Tổ chức)
  └── Storage Area (Vị trí/Khu vực: vd Kệ ban công, Phòng kho)
        └── Container / Box (Hộp chứa có mã QR: vd BOX-001)
              └── Item (Vật dụng: Tên, Mô tả, Số lượng, Ảnh, Tags)
```

### Các Entities chính dự kiến:
1. **User:** ID, email, passwordHash, fullName, avatarUrl, createdAt.
2. **Household:** ID, name, plan (`FREE` | `PRO`), createdAt.
3. **HouseholdMember:** userId, householdId, role (`OWNER` | `ADMIN` | `MEMBER` | `VIEWER`).
4. **StorageArea:** ID, householdId, name, description.
5. **Container (Box):** ID, code (vd `BOX-001`), qrCodeHash, storageAreaId, name, description, isLocked.
6. **Item:** ID, containerId, name, description, quantity, imageUrl, tags, expiryDate, warrantyDate.
7. **ActivityLog / Audit:** Ghi lại lịch sử ai thêm, sửa, di chuyển đồ vật nào giữa các hộp.

---

## 4. Trạng thái hiện tại các phân hệ (Component Status)

### 4.1. Backend (`/backend`)
- **Trạng thái:** Đã khởi tạo `package.json`.
- **Việc cần làm tiếp:**
  1. Cài đặt TypeScript, Express (hoặc Fastify), Prisma, dotenv, cors, bcrypt, jsonwebtoken.
  2. Viết file `schema.prisma` chuẩn hóa các entities trên.
  3. Tạo migration đầu tiên kết nối PostgreSQL.

### 4.2. Frontend (`/frontend`)
- **Trạng thái:** Khung chuẩn React 19 + TypeScript + Vite 8.
- **Việc cần làm tiếp:** Xây dựng Design system & Dashboard xem danh sách Container/Item.

### 4.3. Mobile (`/mobile`)
- **Trạng thái:** Khung chuẩn Flutter 3.x.
- **Việc cần làm tiếp:** Tích hợp `mobile_scanner` để quét QR, dựng luồng màn hình Scan & Search.

---

## 5. Nhật ký cập nhật hệ thống (System Changelog)
- **2026-09-18 (Lần 1):** Khởi tạo `SYSTEM_STATUS.md`.
- **2026-09-18 (Lần 2):** Đồng bộ chi tiết nghiệp vụ quản lý kho thông minh (Household -> Area -> Box -> Item) và tech stack (PostgreSQL + Prisma + Node.js + Flutter + React) từ `README.md`. Bỏ file khỏi `.gitignore` để lưu trữ trên GitHub.
