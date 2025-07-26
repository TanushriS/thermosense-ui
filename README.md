# 🔋 ThermoSense – Battery Health Monitoring & Advisory System

ThermoSense is a real-time React-based battery health monitoring tool integrated with a machine learning API powered by FastAPI and GPT-2. It intelligently predicts battery stress levels based on sensor data and gives safety advice for your device.
### 📡 Live Link 
👉 [https://thermosense.com](https://thermosense-ui-psi.vercel.app/)

### 🖥️ Dashboard
![Dashboard](https://github.com/TanushriS/assets/blob/main/dashboard.png)

---

## 🚀 Features

- 🌡️ Predicts battery health impact using ML
- 🤖 Provides GPT-2 powered natural language advisory
- 📊 Real-time charts for battery and ambient temperature
- 🚨 Alerts & Notifications based on risk levels
- 📁 Export sensor logs
- 🎛️ Toggle views: Live Dashboard, Real-Time Chart, Alerts

---

## 📂 Project Structure

```
├── backend/
│   ├── api.py                 # FastAPI backend with ML model + GPT-2
│   ├── main.py                # Prediction logic
│   ├── transformer_t5_test.py # GPT-2 advisory generator
│   └── thermosense_test_data.csv
├── frontend/
│   ├── index.html             # Loads the React App
│   ├── app.js                 # Main React logic
│   ├── style.css              # Styling
│   └── images/                # Assets like screenshots
```

---

## 🛠️ Tech Stack

- Frontend: **React (CDN), Chart.js, Axios**
- Backend: **FastAPI, Scikit-learn, Transformers (GPT-2)**
- Model: **Random Forest Regressor + GPT-2**
- Deployment: **Render (Backend)** + **Vercel (Frontend)**

---

## 🧪 How It Works

1. The user submits sensor data (battery temperature, ambient temperature, and device state).
2. The backend predicts the battery health impact using the ML model.
3. GPT-2 generates a contextual safety tip based on the prediction.
4. The UI displays:
   - Health impact score
   - Alert level (`safe`, `warning`, or `danger`)
   - Natural language advisory

---

## 🖼️ Screenshots

### 📊 Dashboard
![Live Dashboard](https://github.com/TanushriS/assets/blob/main/dashboard.png)

### 📈 Real-Time Chart
![Chart](https://github.com/TanushriS/assets/blob/main/chart%20views.png)

### 🚨 Alerts
![Alerts](https://github.com/TanushriS/assets/blob/main/alerts.png)

---

## 🚧 How to Run Locally

### ⚙️ Backend (FastAPI)

```bash
cd backend
pip install -r requirements.txt
uvicorn api:app --reload
```

### 🌐 Frontend (Vercel-compatible React via CDN)

No build setup needed. Simply open `index.html` in your browser or deploy to Vercel.

---

## 🌍 Deployment

### ✅ Backend on Render

1. Push backend files to a GitHub repo.
2. Go to [Render](https://render.com).
3. Create a **Web Service**.
4. Build command:
   ```bash
   uvicorn api:app --host 0.0.0.0 --port 10000
   ```

### ✅ Frontend on Vercel

1. Upload frontend (`index.html`, `app.js`, `style.css`) to a new GitHub repo.
2. Deploy on [Vercel](https://vercel.com).
3. Make sure API URLs in `app.js` point to your Render backend.

---

## 📬 API Endpoint Example

**POST** `/api/advice`

```json
{
  "battery_temp": 38.5,
  "ambient_temp": 32.2,
  "device_state": "charging"
}
```

**Response**
```json
{
  "predicted_health_impact": 0.07852,
  "alert_level": "danger",
  "natural_language_tip": "Critical: High battery stress detected.",
  "optional_action": "Stop using device immediately and allow cooling"
}
```

---



## 📄 License

This project is licensed under the MIT License.
