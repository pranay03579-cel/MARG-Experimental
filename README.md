# MARG — Smart Logistics and Accessibility Intelligence Platform

MARG is an intelligent logistics and route-planning platform designed to support **risk-aware and accessibility-focused route selection** in disaster-prone and geographically challenging regions.

Unlike conventional navigation systems that primarily optimize for distance or travel time, MARG evaluates multiple factors—including **environmental risk, travel time, distance, urgency, and vehicle suitability**—to identify a route that provides a more reliable overall transportation option.

The system is particularly designed for applications in the **North Eastern Region (NER) of India**, where landslides, heavy rainfall, waterlogging, terrain conditions, and road disruptions can significantly affect transportation and logistics.

---

## 1. Objectives

The primary objectives of MARG are to:

* Generate and evaluate alternative routes between an origin and destination.
* Assess environmental and disaster-related risks associated with routes.
* Incorporate landslide and waterlogging risk into route evaluation.
* Calculate an **Accessibility Intelligence Score** for candidate routes.
* Provide route recommendations based on multiple contextual factors.
* Support dynamic rerouting when a route becomes unavailable or unsafe.
* Consider vehicle type and delivery urgency during route evaluation.
* Present route intelligence through an interactive map-based interface.

---

## 2. Core Concept

MARG follows a multi-factor route evaluation approach:

```text
Distance
Travel Time
Environmental Risk
Delivery Urgency
Vehicle Suitability
        │
        ▼
Route Scoring Engine
        │
        ▼
Accessibility Intelligence Score
        │
        ▼
Route Ranking
        │
        ▼
Route Recommendation
```

The **Accessibility Intelligence Score** enables the system to consider overall route accessibility rather than selecting a route solely on the basis of minimum distance.

---

## 3. Key Features

### 3.1 Multi-Route Evaluation

MARG evaluates multiple available routes and compares them using common route-level parameters such as:

* Distance
* Estimated travel time
* Environmental risk
* Landslide risk
* Waterlogging risk
* Delivery urgency
* Vehicle type

The resulting scores are used to rank candidate routes.

### 3.2 Landslide Risk Assessment

The platform includes a machine-learning-based landslide risk component for assessing the potential risk associated with route segments.

Risk is represented using a normalized scale and classified into categories such as:

* Low
* Medium
* High

The resulting risk information is integrated into the route scoring pipeline.

### 3.3 Environmental Risk Analysis

MARG incorporates environmental conditions that can affect road accessibility, including:

* Rainfall
* Terrain characteristics
* Slope
* Waterlogging
* Landslide susceptibility

These factors contribute to the overall environmental risk associated with a route.

### 3.4 Accessibility Intelligence Score

The scoring engine combines route parameters into a single comparative score.

The current scoring pipeline considers:

```text
Urgency
Risk
Time
Distance
```

The resulting value is used as the **Accessibility Intelligence Score**, allowing candidate routes to be ranked according to the operational context.

### 3.5 Emergency Dynamic Rerouting

MARG supports dynamic rerouting when a road disruption or incident is identified.

The emergency workflow consists of:

```text
Current Vehicle Location
          │
          ▼
Incident / Blocked Location
          │
          ▼
Alternative Route Generation
          │
          ▼
Blocked Route Detection
          │
          ▼
Alternative Route Evaluation
          │
          ▼
Route Recommendation
```

Routes affected by the identified disruption can be excluded from the recommendation process, after which alternative routes are evaluated.

### 3.6 Vehicle-Aware Route Evaluation

The system supports vehicle-specific route evaluation. Vehicle type can be incorporated into the decision process to account for differences in route suitability for different transportation requirements.

### 3.7 Interactive Visualization

The frontend provides a map-based interface for visualizing route information and system recommendations.

The interface includes functionality for:

* Route visualization
* Route comparison
* Risk information
* Route recommendations
* Emergency rerouting
* Vehicle simulation
* Decision intelligence

---

## 4. System Architecture

MARG follows a modular architecture consisting of a frontend application, backend services, machine-learning components, route-generation modules, and a route-scoring engine.

```text
                    User
                     │
                     ▼
              React Frontend
                     │
                     ▼
               FastAPI Backend
                     │
       ┌─────────────┼─────────────┐
       │             │             │
       ▼             ▼             ▼
 Route Services  Risk Services  Vehicle Services
       │             │             │
       │             ▼             │
       │       ML Risk Model        │
       │             │             │
       └─────────────┼─────────────┘
                     ▼
              Scoring Engine
                     │
                     ▼
          Recommendation Service
                     │
                     ▼
              Ranked Routes
                     │
                     ▼
              React Interface
```

---

## 5. Project Structure

```text
MARG-Experimental-main/
│
├── api/
│   └── index.py
│
├── backend/
│   ├── main.py
│   ├── requirements.txt
│   │
│   ├── data/
│   │   ├── demo_routes.json
│   │   └── elevation/
│   │
│   ├── integrations/
│   │   ├── person1_routes/
│   │   ├── person2_landslide_model/
│   │   └── person3_scoring_engine/
│   │
│   ├── models/
│   │
│   ├── services/
│   │   ├── environmental_service.py
│   │   ├── recommendation_service.py
│   │   ├── risk_service.py
│   │   ├── route_service.py
│   │   ├── scoring_service.py
│   │   ├── vehicle_service.py
│   │   ├── waterlogging_service.py
│   │   └── weather_service.py
│   │
│   ├── test_backend_suite.py
│   ├── run_comprehensive_validation.py
│   └── verify_reality_check.py
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── demo/
│   │   ├── utils/
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   │
│   ├── package.json
│   ├── package-lock.json
│   ├── vite.config.js
│   └── index.html
│
├── requirements.txt
├── package.json
├── vercel.json
└── .gitignore
```

---

## 6. Technology Stack

### Frontend

* React
* Vite
* JavaScript
* React Leaflet
* Leaflet
* CSS

### Backend

* Python
* FastAPI
* Uvicorn
* Pydantic

### Machine Learning and Data Processing

* Scikit-learn
* Pandas
* SciPy
* Joblib

### Development and Deployment

* Git
* GitHub
* Vercel

---

## 7. Installation

### Prerequisites

Ensure the following are installed:

* Python 3.10 or later
* Node.js
* npm
* Git

### Clone the Repository

```bash
git clone https://github.com/asthanasmriti/MARG.git
cd MARG
```

---

## 8. Backend Setup

Navigate to the backend directory:

```bash
cd backend
```

Create a virtual environment:

```powershell
python -m venv venv
```

Activate the environment on Windows:

```powershell
venv\Scripts\activate
```

Install the required Python packages:

```powershell
pip install -r requirements.txt
```

Start the backend server:

```powershell
uvicorn main:app --reload
```

The API will be available locally at:

```text
http://127.0.0.1:8000
```

FastAPI documentation can be accessed at:

```text
http://127.0.0.1:8000/docs
```

---

## 9. Frontend Setup

Open a new terminal and navigate to the project directory:

```powershell
cd MARG
```

Install the frontend dependencies:

```powershell
npm --prefix frontend install
```

Start the development server:

```powershell
npm run dev
```

The frontend will be available at the local URL provided by Vite, typically:

```text
http://localhost:5173
```

---

## 10. Route Intelligence Pipeline

The primary route evaluation pipeline can be represented as:

```text
Origin + Destination
        │
        ▼
Route Generation
        │
        ▼
Route Validation
        │
        ▼
Environmental Analysis
        │
        ├── Landslide Risk
        ├── Waterlogging Risk
        ├── Terrain
        └── Weather Factors
        │
        ▼
Route Scoring
        │
        ▼
Accessibility Intelligence Score
        │
        ▼
Route Ranking
        │
        ▼
Recommendation
```

A common `route_id` is used to associate route information across different modules of the system.

---

## 11. Module Integration

### Route Generation Module

Responsible for generating and processing candidate routes, including:

* Route alternatives
* Coordinates
* Distance
* Estimated travel time

Location:

```text
backend/integrations/person1_routes/
```

### Landslide Risk Module

Responsible for:

* Landslide dataset processing
* Model training
* Risk prediction
* Risk classification

Location:

```text
backend/integrations/person2_landslide_model/
```

### Scoring Engine

Responsible for calculating route-level accessibility scores using:

* Urgency
* Risk
* Time
* Distance

Location:

```text
backend/integrations/person3_scoring_engine/
```

### Backend Integration

The backend integrates route generation, risk analysis, scoring, and recommendation services.

Location:

```text
backend/
```

### Frontend

The React frontend provides the visualization and interaction layer for the complete route intelligence system.

Location:

```text
frontend/
```

---

## 12. Emergency Dynamic Rerouting

The emergency rerouting workflow is designed to handle route disruptions.

When an incident is identified:

1. The current vehicle location is obtained.
2. The affected incident location is identified.
3. Candidate routes are generated.
4. Routes passing through the affected area are identified.
5. Unsafe or blocked routes are excluded.
6. Remaining routes are evaluated.
7. The most suitable alternative is recommended.

This allows the system to respond to changing road conditions instead of relying exclusively on the original route.

---

## 13. Testing and Validation

The repository contains multiple testing and validation utilities.

Run the backend test suite:

```powershell
python backend/test_backend_suite.py
```

Run comprehensive validation:

```powershell
python backend/run_comprehensive_validation.py
```

Run the reality-check validation:

```powershell
python backend/verify_reality_check.py
```

Run the scoring engine tests:

```powershell
cd backend/integrations/person3_scoring_engine
python test_scoring.py
```

Run the route-service tests:

```powershell
cd backend/integrations/person1_routes
python test_route_service.py
```

---

## 14. Use Cases

MARG can be applied to scenarios involving:

* Disaster-aware logistics
* Emergency transportation
* Supply-chain route planning
* Pharmaceutical logistics
* Remote-region transportation
* Risk-aware fleet management
* Dynamic route recovery
* Infrastructure accessibility analysis

The platform can be further extended for real-world logistics and disaster-management applications.

---

## 15. Future Scope

Future development may include:

* Real-time weather data integration
* Real-time road closure information
* Live traffic data
* Real-time GPS tracking
* Satellite-based landslide detection
* Advanced landslide prediction models
* Improved terrain analysis
* Fleet management capabilities
* Historical route-risk analytics
* Integration with government disaster-management systems
* Real-world road-network datasets for the North Eastern Region

---

## 16. Limitations

The current implementation is primarily intended as a **prototype and proof-of-concept system**.

Some components use demonstration or synthetic data and simulated disruption scenarios. Real-world deployment would require reliable live data sources, extensive model validation, accurate road-network information, and continuous environmental monitoring.

Therefore, the current system should not be considered a replacement for operational navigation or emergency-management systems.

---

## 17. Project Status

**Status:** Prototype / Research & Development

MARG currently demonstrates the integration of:

* Route generation
* Environmental risk assessment
* Landslide risk prediction
* Accessibility scoring
* Route recommendation
* Emergency dynamic rerouting
* Interactive route visualization

---

## 18. License

This project is developed for **academic, research, and demonstration purposes**.

---

## 19. Acknowledgements

MARG was developed as a collaborative project focused on applying artificial intelligence, route intelligence, and environmental risk analysis to logistics challenges in disaster-prone regions.

---

**MARG — Smart Logistics and Accessibility Intelligence Platform**

*Risk-aware route intelligence for resilient transportation and logistics.*
