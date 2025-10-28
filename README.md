# 🌤️ Weather Now — React App (Open-Meteo API)

### 📋 Overview  
**Weather Now** is a responsive weather application built with **React** that provides **current weather** and **hourly forecasts** for any searched city.  
It uses **Open-Meteo’s Geocoding API** to find coordinates and the **Open-Meteo Forecast API** to display real-time data.  
The app is clean, fast, and optimized for both **mobile** and **desktop** users.

---

### 🚀 Features  
✅ City search with live suggestions (via Geocoding API)  
✅ Real-time current weather data and 24-hour forecast  
✅ Unit toggle — switch between °C and °F instantly  
✅ Responsive UI for all screen sizes  
✅ Error & loading states for better UX  
✅ No API key required — uses free, public APIs  
✅ Built entirely in React with a single CSS file for styling  

---

### 🛠️ Tech Stack  
| Purpose | Technology |
|----------|-------------|
| Frontend Framework | **React (Hooks + Functional Components)** |
| Styling | **Responsive CSS (styles.css)** |
| APIs | **Open-Meteo Geocoding API** & **Open-Meteo Forecast API** |
| Environment | **Vite / CodeSandbox** |
| Deployment | **Vercel / GitHub Pages / CodeSandbox Share Link** |

---

### 🌐 API References  

#### 1. **Geocoding API**  
🔗 `https://geocoding-api.open-meteo.com/v1/search?name={CITY_NAME}`  
- Converts a city name into latitude/longitude.  
- Example:  
  ```
  https://geocoding-api.open-meteo.com/v1/search?name=London
  ```

#### 2. **Forecast API**  
🔗 `https://api.open-meteo.com/v1/forecast?latitude={LAT}&longitude={LON}&current_weather=true&hourly=temperature_2m,weathercode`  
- Returns current and hourly weather data.  
- Example:  
  ```
  https://api.open-meteo.com/v1/forecast?latitude=51.5&longitude=-0.12&current_weather=true&hourly=temperature_2m
  ```

---

### ⚙️ Installation & Setup  

#### 🧩 Option 1 — Run in CodeSandbox  
1. Open [https://codesandbox.io/](https://codesandbox.io/)  
2. Create a **React (Vite)** sandbox.  
3. Copy the following files into it:  
   - `src/App.js` → main React component (WeatherNowApp)  
   - `src/styles.css` → responsive CSS file  
   - `src/main.jsx` & `index.html` → standard Vite setup  
4. Add this line to the top of `App.js`:  
   ```js
   import "./styles.css";
   ```
5. Click **Preview → Open in New Tab** to view your app.

#### 🧩 Option 2 — Run Locally  
```bash
# clone project
git clone https://github.com/your-username/weather-now.git
cd weather-now

# install dependencies
npm install

# run locally
npm run dev
```
Then open your browser at `http://localhost:5173`

---

### 🧠 How It Works  

1. **User Search:**  
   - The app listens for typing in the search bar.  
   - It waits ~350ms before querying Open-Meteo’s geocoding API (debounce effect).  

2. **Suggestions Dropdown:**  
   - Displays matching cities and coordinates.  

3. **Selecting a City:**  
   - On click, it triggers `fetchWeatherForPlace()` with that location’s coordinates.  

4. **Weather Data Fetch:**  
   - Calls Open-Meteo’s forecast API and stores the result in state.  

5. **Rendering Data:**  
   - Shows a summary card (place name, temperature, weather condition).  
   - Shows an hourly forecast row for the next 24 hours.  

6. **Unit Toggle:**  
   - Re-fetches data using `temperature_unit=fahrenheit` or Celsius.  

7. **Responsiveness:**  
   - Uses CSS Grid and Flexbox for adaptive layouts.  
   - Works perfectly on both small (mobile) and large (desktop) screens.

---

### 🧩 Folder Structure  
```
weather-now/
├── public/
│   └── index.html
├── src/
│   ├── App.js
│   ├── styles.css
│   ├── main.jsx
│   └── index.css (optional)
├── package.json
└── README.md
```

---

### 🎨 UI Highlights  
- Clean two-column layout (summary + hourly forecast) on desktop.  
- Single-column stacked layout on mobile.  
- Interactive dropdown search & hover effects.  
- Gradient backgrounds for weather cards.  
- Smooth focus and hover transitions for buttons and inputs.  

---

### 💡 Challenges Solved  
- Implemented **debounced search** to reduce API calls.  
- Managed **loading**, **error**, and **empty** states for smoother UX.  
- Built **responsive design** from scratch without frameworks.  
- Maintained clean separation of logic (data fetching) and presentation (CSS).

---

### 🚧 Future Improvements  
🔹 Add weather icons for each condition.  
🔹 Add 7-day forecast section.  
🔹 Use browser geolocation to auto-detect the user’s current city.  
🔹 Store last searched city in localStorage.  
🔹 Deploy to Vercel for persistent live demo.

---

### 🧾 License  
This project uses publicly available data from [Open-Meteo](https://open-meteo.com/).  
You are free to use, modify, or deploy this app for educational purposes.

---

### 👤 Author  
**Ramesh Bingi**  
📧 Email: bingiramesh49@gmail.com  
