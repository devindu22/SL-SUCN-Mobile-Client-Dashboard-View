# SL-SUCN Mobile Client

> **Premium Responsive Mobile App UI & Smart City Consumer Dashboard** 
> Dynamic, high-contrast urban telemetry tracking ecosystem for decentralized sustainable energy and localized microclimate mitigation.

https://sl-sucn-mobile-client-dashboard.netlify.app/

<img width="1919" height="917" alt="Screenshot 2026-07-19 191915" src="https://github.com/user-attachments/assets/d8ddba02-8873-4441-8c3c-e32dfd67f9ed" />

---

## 1. Project Overview

The **SL-SUCN Mobile Client** is a cutting-edge, responsive consumer application designed for smart city residents to monitor, interact with, and optimize their green energy footprint and urban microclimate status. Built with a mobile-first, thumb-zone ergonomic layout, the interface effortlessly scales across smartphones, tablets, and desktop displays.

### Visual Identity & Theme Architecture
* **Background:** Premium deep charcoal high-contrast dark mode (`#12141C`).
* **Primary Accents:** Vibrant Emerald Green (Energy metrics, generation status, fully charged indicators).
* **Secondary Accents:** Glowing Neon Cyan (Cooling indicators, active telemetry, grid independence indices).
* **Alert Highlight:** Warning Orange (Ambient heat island baseline benchmarks).

---

## 2. Design Philosophy: "Eco-Transparency & Mobile Ergonomics"

### 📱 Mobile-First Thumb Zone Layout
Citizens typically interact with this app while on the move. To minimize strain and allow seamless one-handed navigation, all primary interactive components, dynamic tab switchers, and pull-to-refresh areas are strictly situated within the **lower two-thirds of the screen viewport**.

### 🍃 Gamified Sustainability
Instead of isolating data into confusing, dry technical figures (such as raw kilowatt-hours or complex bar pressures), the system translates telemetry data into relatable consumer metrics:
* Real-time carbon offsets measured in equivalent weights (`kg`).
* Live financial credits earned in local currency (`LKR`).
* Microclimate thermal relief metrics mapping direct outdoor comfort improvements.

### ⚡ Glanceable Micro-Interactions
The user interface leverages elegant micro-animations (e.g., fluid-filling battery capsules, pulsating active cooling vectors) to instantly communicate the state of the local grid without requiring heavy textual explanations or cognitive overload.

---

## 3. Core Functional UI Modules

### 📊 The Interactive Renewable Hub (Top Screen)
* **Dynamic Source Splitter:** A fluid donut ring chart visualizing the real-time ratio between solar PV arrays and regional wind turbine contributions.
* **Live Battery Capsule:** A vertical battery visualization changing dynamically from amber (low storage) to vibrant emerald green as the household decentralized storage capacities max out.

### 🌡️ The Microclimate Delta Widget (Center Screen)
* **Split Thermal Card:** Provides instant feedback on the automated urban mist cooling network by pitting a warning-orange block ("Baseline Temperature") side-by-side with a cool-cyan block ("Mist-Cooled Ambient Vector").
* **Dynamic Status Overlays:** A subtle, radial blue glow animating behind live readouts when the localized proximity misting nodes are actively pulsing.

### 💡 Household Grid Offset Dashboard (Lower Screen)
* **Grid Reliance Gauge:** A crisp, semi-circular progress arch showing how self-sufficient the household is relative to the national power grid.
* **Economic Tracker:** A ledger component tracking live financial payouts awarded to the consumer for feeding excess green energy back into the municipal grid framework.

---

## 4. Responsive Design & System Architecture

+-------------------------------------------------------------+
|                     SYSTEM TOPOLOGY                         |
+-------------------------------------------------------------+
|                                                             |
|   [ IoT Grid Telemetry ]       [ Urban Climate Sensors ]    |
|             |                              |                |
|             +--------------+---------------+                |
|                            |                                |
|                            v                                |
|                  [ Backend Services ]                       |
|                            |                                |
|                            v                                |
|                 [ Redis Caching Layer ]                     |
|            (Aggregates JSON into light fragments)           |
|                            |                                |
|             +--------------+---------------+                |
|             |                              |                |
|             v                              v                |
|     (Mobile Viewport)              (Web/Tablet Viewport)    |
|     Vertical Stack                 Multi-Column CSS Grid    |
|     Bottom Navigation              Adaptive Left Sidebar    |
|                                                             |
+-------------------------------------------------------------+

---

### Fluid Component Adaptability
* **Mobile Mode:** Core cards stack vertically into a single-column, bottom-nav-accessible, swipe-friendly feed optimized for iOS and Android layouts.
* **Web/Tablet Mode:** The layout automatically engine-refactors via Tailwind CSS grids into a multi-column desktop control center, mapping bottom navigations into an elegant left-hand persistent menu sidebar.

### 💾 Redis Caching Integration & Data Saving
To guarantee ultra-fast startup metrics and protect consumer mobile data limits on low-bandwidth networks, the ecosystem uses an aggressive Redis caching tier on the API edge. Heavy micro-telemetry data is minified and bundled into tiny JSON structural fragments, eliminating redundant payload exchanges.

### 🚨 Push Notification Framework
Equipped with webhooks hooked into automated alert engines to instantly notify citizens of volatile urban weather indices (e.g., *“Urban Heat Island warning in Colombo Fort. Mist cooling network scaling to max capacity.”*).

---

## 5. Mobile Navigation Matrix

| Viewport Tab | Core Interactive Content | Operational Purpose |
| :--- | :--- | :--- |
| **Tab 1: Home** | Split Thermal Cards & Live Battery Capsule | Instant, glanceable look into microclimates and household power states. |
| **Tab 2: Analytics** | Regional Interactive Trend Charts (Chart.js) | Deep-dive tracking of daily, weekly, and monthly neighborhood grid metrics. |
| **Tab 3: Eco-Wallet**| Accumulation Ledger & Savings Tracker | Detailed accounting of carbon credits, financial payouts, and utility offsets. |
| **Tab 4: Settings** | Geolocation Toggles & Notification Grid | Fine-tuning proximity sensor parameters for hyper-localized thermal updates. |

---

## Screenshots of the Design

<img width="1919" height="910" alt="Screenshot 2026-07-19 192122" src="https://github.com/user-attachments/assets/3085a103-e02f-4cf2-8290-36959a63d003" />

<img width="1919" height="915" alt="Screenshot 2026-07-19 191932" src="https://github.com/user-attachments/assets/57e4f4b9-1a60-454f-830e-ca446e043952" />

<img width="1917" height="916" alt="Screenshot 2026-07-19 191943" src="https://github.com/user-attachments/assets/fb64d258-4bb6-4e91-ad4d-e3a7abb3d8a2" />

<img width="1917" height="910" alt="Screenshot 2026-07-19 191956" src="https://github.com/user-attachments/assets/7927374a-4212-466e-bd70-649dbd304149" />

---

## 6. Real-Time Telemetry JSON Schema

The frontend components digest the following compressed schema structure from API endpoints:

```json
{
  "timestamp": "2026-07-19T12:00:00Z",
  "user_profile": {
    "user_id": "USR-94821",
    "district": "Colombo Fort",
    "household_tier": "RESIDENTIAL_HYBRID"
  },
  "metrics": {
    "regional_grid_contributions": {
      "active_zone": "Colombo Central Sector",
      "total_renewable_generation_kw": 1840.50,
      "solar_pv_array_contribution_kw": 1120.20,
      "wind_turbine_contribution_kw": 720.30,
      "current_storage_reserve_capacity_percent": 74.20
    },
    "personalized_household_offset": {
      "live_consumption_kw": 2.40,
      "live_decentralized_offset_kw": 1.85,
      "national_grid_reliance_percent": 22.90,
      "daily_carbon_saved_kg": 4.20,
      "monthly_credits_earned_lkr": 1450.00
    },
    "microclimate_live_temperatures": {
      "localized_sensor_station": "STN-FORT-04",
      "baseline_ambient_temperature_celsius": 34.2,
      "mist_cooled_temperature_celsius": 29.8,
      "active_cooling_delta_celsius": 4.4,
      "mist_system_status": "PULSING_ACTIVE"
    }
  }
}
