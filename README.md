🚗 Smart Dynamic Parking Pricing with Real-Time Visualization
📌 Project Overview
This project implements an intelligent, real-time Dynamic Pricing System for urban parking spaces. Prices adjust dynamically based on:
- Real-time demand patterns
- Traffic conditions
- Queue lengths
- Special events
- Vehicle types
- Competitor proximity
The system ensures that price updates are smooth, explainable, and reflect real-world scenarios. Optional rerouting suggestions for overburdened lots are also considered.
🛠 Tech Stack
- Python 3.x
- Pandas – Data processing
- Numpy – Numerical operations
- Pathway – Real-time data streaming & computation
- Bokeh – Interactive real-time visualizations
- Panel – Dashboard integration
🏗 System Architecture
Conceptual workflow of the dynamic pricing system:
Parking Data (Historical & Real-Time)
              │
      Streaming via Pathway
              │
      Data Preprocessing
 (Timestamp parsing, Feature engineering)
              │
      Dynamic Pricing Models
    ┌─────────────┬─────────────┐
Model 1: Linear   Model 2: Demand-Based
              │
  Real-Time Price Output
              │
     Bokeh Visualization
              │
 Interactive Dashboard (Panel)
⚙ Project Workflow
⿡ Data Description:
- 14 urban parking lots
- 73 days of data
- 18 time points daily (30-min intervals, 8:00 AM to 4:30 PM)
Features:
- Location: Latitude, Longitude
- Capacity & Occupancy
- Queue length
- Vehicle Type: Car, Bike, Truck
- Nearby traffic congestion
- Special day indicators (holidays, events)
⿢ Pricing Model Stages:
✅ Model 1: Baseline Linear Price
Price_t+1 = Price_t + α * (Occupancy / Capacity)
✅ Model 2: Demand-Based Pricing
Demand = α*(Occupancy/Capacity) + β*QueueLength - γ*Traffic + δ*SpecialDay + ε*VehicleTypeWeight
Price_t = BasePrice * (1 + λ * NormalizedDemand)
Prices are bounded (e.g., 0.5x to 2x Base Price) to ensure stability.
📊 Visualization Examples
- Real-time price trends per parking lot
- Vehicle-type-specific price comparisons
- Optional competitor price overlays
- Seasonality patterns (e.g., weekday/weekend effects)
📂 Project Structure
.
├── data/                  # Raw and processed data files
├── notebooks/             # Experimentation and visualization notebooks
├── src/                   # Core model and processing scripts
├── README.md              # Project documentation (this file)
└── requirements.txt       # Dependencies
📄 Optional Documentation
Technical reports, experimental results, and analysis PDFs can be added under a /docs directory.
🚀 Getting Started
1. Install dependencies:
   pip install -r requirements.txt
2. Run the pricing pipeline (script or notebook)
3. Launch the Panel dashboard to monitor real-time visualizations
💡 Future Enhancements
- Rerouting suggestions for overburdened lots
- More advanced demand modeling using temporal patterns
- Competitor-aware pricing integration
🤝 Contributions
Feel free to fork this repo and open a pull request or issue!
📄 License
This project is open-source under the MIT License.
🔗 Links
- 📊 Live Dashboard (optional): https://your-dashboard-url.com
- 📁 GitHub Repository: https://github.com/yourusername/your-repo
