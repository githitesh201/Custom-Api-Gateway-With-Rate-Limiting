# 🚀 Custom API Gateway with Rate Limiting & Monitoring Dashboard

A **production-ready API Gateway system** with a powerful **React-based monitoring dashboard** that allows admins to **manage routes, API keys, rate limits, and service health** — all in one place.

This project simulates how real-world companies like **AWS, Netflix, or Zomato** manage internal microservices using a **central gateway layer** with traffic control, security, and analytics.

---

## 🧠 Overview

The **Custom API Gateway** acts as a single entry point for all backend services, ensuring secure, efficient, and monitored communication between clients and microservices.  
It includes:
- A **backend gateway service** built with Node.js/Express & Redis for rate limiting.
- A **frontend dashboard** built in React + Tailwind for visual management and analytics.

---

## 🧱 System Architecture
      ┌─────────────┐
      │   Frontend  │  → React Dashboard (Admin UI)
      └──────┬──────┘
             │ REST API Calls
    ┌────────▼────────┐
    │  API Gateway     │ ←→ Redis (Rate Limit)
    │ (Node/Express)   │
    ├──────────────────┤
    │ Auth  |  RateLimiter │
    │ Router|  Logger      │
    └───────┬─────────────┘
            │
┌──────────────┼─────────────────────┐
│ │ │
▼ ▼ ▼
Auth Service User Service Order Service

---

## 🎯 Features

### 🔹 MVP (Core Features)
- **API Routing:** Forwards requests to the correct microservice.
- **Rate Limiting:** Prevents abuse (e.g., 100 req/min per IP or API key).
- **API Key Authentication:** Only verified users can access gateway routes.
- **Unified Error Handling:** Consistent API error messages (401, 429, 500).
- **Basic Logging:** Store request metadata for monitoring.

### 🔹 Frontend Dashboard
- **Admin Login:** JWT or API Key authentication for access.
- **Dashboard Overview:** Total requests, blocked requests, active services, average latency.
- **Services Health Monitor:** Ping backend microservices and show UP/DOWN status.
- **Routes Management:** View/Add/Edit/Delete API routes and rate limits.
- **API Keys Management:** Generate or revoke API keys and assign custom limits.
- **Rate Limit Monitor:** See IPs or users that exceeded thresholds.
- **Logs & Analytics:** Visualize request history, errors, and latency using charts.

---

## ✨ Add-On / Advanced Features

- Real-time health check (auto-refresh every 30 sec)
- WebSocket live log streaming
- Dark/Light mode UI
- Traffic analytics graphs (Chart.js/Recharts)
- IP blacklisting & alerting
- Versioned routes (`/v1`, `/v2`)
- Email/Slack alerts for service downtime
- Centralized logs in ELK or Grafana

---

## ⚙️ Tech Stack

### Backend
- **Node.js / Express**
- **Redis** – rate limiting & caching
- **JWT** – authentication
- **Winston / Morgan** – logging

### Frontend
- **React.js + Vite**
- **Tailwind CSS + ShadCN UI**
- **TanStack React Query** – API data management
- **Recharts / Chart.js** – analytics visualization
- **Lucide Icons** – modern icons

---

## 📁 Project Structure

/api-gateway-backend
│
├── src/
│ ├── index.js
│ ├── middleware/
│ │ ├── rateLimiter.js
│ │ ├── auth.js
│ ├── routes/
│ ├── utils/
│ └── config/
│
/api-gateway-frontend
│
├── src/
│ ├── pages/
│ │ ├── Dashboard.jsx
│ │ ├── Services.jsx
│ │ ├── Routes.jsx
│ │ ├── Keys.jsx
│ │ ├── Logs.jsx
│ ├── components/
│ ├── hooks/
│ ├── api/
│ └── App.jsx



---

## 🚀 Getting Started

### 1️⃣ Clone Repository
```bash
git clone https://github.com/githitesh201/Custom-Api-Gateway-With-Rate-Limiting
.git
cd Custom-Api-Gateway-With-Rate-Limiting
2️⃣ Backend Setup
cd api-gateway-backend
npm install
npm run dev

3️⃣ Frontend Setup
cd api-gateway-frontend
npm install
npm run dev

📊 Example API Endpoints
Endpoint	Method	Description
/gateway/routes	GET	List all API routes
/gateway/keys	POST	Create new API key
/gateway/stats	GET	Dashboard stats
/gateway/health	GET	Service health check

📈 Future Roadmap

✅ Add user roles (Admin / Developer)
✅ Add analytics export to CSV/PDF
✅ Integrate Prometheus metrics
✅ Implement Gateway load balancing
✅ Deploy with Docker + Kubernetes

🪪 License

This project is licensed under the MIT License – feel free to use and modify.

