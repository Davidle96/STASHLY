# STASHLY - SYSTEM STATUS & ARCHITECTURE CONTEXT

> **Lưu ý quan trọng cho AI Assistant & Developer:**  
> File này lưu trữ toàn bộ bức tranh kiến trúc, hiện trạng công nghệ và trạng thái phát triển của dự án STASHLY.  
> **Quy tắc:** Trước khi thực hiện tác vụ, hãy đọc file này để nắm ngữ cảnh mà **không cần quét lại toàn bộ source code** nhằm tối ưu token và thời gian. Khi thêm hoặc cập nhật tính năng lớn, **bắt buộc cập nhật lại file này**.

*Lần cập nhật gần nhất: 2026-09-18*

---

## 1. Tổng quan dự án (Project Overview)
- **Tên dự án:** STASHLY
- **Mô tả ngắn:** Hệ sinh thái ứng dụng đa nền tảng gồm Web Dashboard, Mobile App và Backend API.
- **Cấu trúc Monorepo / Multi-project:**
  ```
  STASHLY/
  ├── backend/     # API Service (Node.js)
  ├── frontend/    # Web App (React + Vite + TypeScript)
  ├── mobile/      # Mobile App (Flutter)
  └── SYSTEM_STATUS.md # File lưu trạng thái và kiến trúc hệ thống
  ```

---

## 2. Trạng thái các phân hệ (Component Status)

### 2.1. Backend (`/backend`)
- **Runtime & Ngôn ngữ:** Node.js
- **Framework:** *Chưa khởi tạo* (hiện tại mới chỉ có `package.json` trắng)
- **Database & ORM đề xuất:** Chưa cài đặt (Đang ở giai đoạn quyết định Schema / Tech stack)
- **Hiện trạng code:**
  - `package.json` cơ bản (`"version": "1.0.0"`).
- **Việc cần làm tiếp theo:**
  1. Thống nhất cơ sở dữ liệu (PostgreSQL / MySQL / MongoDB).
  2. Chọn framework (NestJS / Express / Fastify) và ORM (Prisma / Drizzle).
  3. Thiết kế bảng dữ liệu và tạo Migration đầu tiên.

### 2.2. Frontend (`/frontend`)
- **Runtime & Công nghệ:** React 19 + TypeScript + Vite 8
- **Styling:** CSS mặc định / Vanilla CSS (chưa tích hợp design system cụ thể)
- **Routing & State:** Chưa cài đặt
- **Hiện trạng code:**
  - Khung chuẩn của Vite React TypeScript (`App.tsx`, `main.tsx`, `index.css`).
- **Việc cần làm tiếp theo:**
  1. Cấu hình theme/styling theo quy chuẩn giao diện.
  2. Tích hợp Axios/Fetch client kết nối Backend API khi API sẵn sàng.

### 2.3. Mobile (`/mobile`)
- **Framework & Ngôn ngữ:** Flutter (Dart SDK `^3.11.4`)
- **Platform hỗ trợ:** Android, iOS
- **State Management:** Chưa cài đặt (đề xuất: Bloc / Riverpod / Provider)
- **Hiện trạng code:**
  - Template Counter mặc định của Flutter (`lib/main.dart`).
- **Việc cần làm tiếp theo:**
  1. Lựa chọn thư viện quản lý State & Http Client (Dio).
  2. Dựng luồng màn hình UI theo business flow.

---

## 3. Bản đồ Dữ liệu & Nghiệp vụ (Data & Business Models)
*(Sẽ được cập nhật chi tiết ngay khi thiết kế schema database hoàn tất)*

- **Entities chính (Dự kiến):**
  - `User`: Quản lý tài khoản, xác thực, phân quyền.
  - *(Đang chờ định nghĩa nghiệp vụ chi tiết của Stashly từ người dùng)*.

---

## 4. Nhật ký cập nhật hệ thống (System Changelog)
- **2026-09-18:** Khởi tạo file `SYSTEM_STATUS.md`. Dự án hiện ở trạng thái khởi tạo scaffold cho cả 3 phân hệ `backend`, `frontend`, và `mobile`.
