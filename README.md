<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Dynamic Parking Pricing with Real-Time Visualization</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            max-width: 900px;
            margin: 40px auto;
            padding: 20px;
            background: #f4f4f4;
            color: #333;
        }
        h1, h2, h3 {
            color: #1a73e8;
        }
        code {
            background: #e8e8e8;
            padding: 2px 4px;
            border-radius: 4px;
        }
        pre {
            background: #e8e8e8;
            padding: 10px;
            border-radius: 4px;
            overflow-x: auto;
        }
        .section {
            margin-bottom: 30px;
        }
    </style>
</head>
<body>

    <h1>🚗 Smart Dynamic Parking Pricing with Real-Time Visualization</h1>

    <div class="section">
        <h2>📌 Project Overview</h2>
        <p>
            This project implements an intelligent, real-time <strong>Dynamic Pricing System</strong> for urban parking spaces. 
            Prices adjust dynamically based on:
        </p>
        <ul>
            <li>Real-time demand patterns</li>
            <li>Traffic conditions</li>
            <li>Queue lengths</li>
            <li>Special events</li>
            <li>Vehicle types</li>
            <li>Competitor proximity</li>
        </ul>
        <p>
            The system ensures price updates are smooth, explainable, and reflect real-world scenarios. Optional rerouting suggestions for overburdened lots are considered.
        </p>
    </div>

    <div class="section">
        <h2>🛠 Tech Stack</h2>
        <ul>
            <li>Python 3.x</li>
            <li>Pandas – Data processing</li>
            <li>Numpy – Numerical operations</li>
            <li>Pathway – Real-time data streaming & computation</li>
            <li>Bokeh – Interactive real-time visualizations</li>
            <li>Panel – Dashboard integration</li>
        </ul>
    </div>

    <div class="section">
        <h2>🏗 System Architecture</h2>
        <p><em>Conceptual workflow of the dynamic pricing system:</em></p>
        <pre>
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
        </pre>
    </div>

    <div class="section">
        <h2>⚙ Project Workflow</h2>

        <h3>⿡ Data Description</h3>
        <ul>
            <li>14 urban parking lots</li>
            <li>73 days of data</li>
            <li>18 time points daily (30-min intervals, 8:00 AM to 4:30 PM)</li>
        </ul>
        <p><strong>Features:</strong></p>
        <ul>
            <li>Location: Latitude, Longitude</li>
            <li>Capacity & Occupancy</li>
            <li>Queue length</li>
            <li>Vehicle Type: Car, Bike, Truck</li>
            <li>Nearby traffic congestion</li>
            <li>Special day indicators (holidays, events)</li>
        </ul>

        <h3>⿢ Pricing Model Stages</h3>

        <p><strong>✅ Model 1: Baseline Linear Price</strong></p>
        <pre>
Price_t+1 = Price_t + α * (Occupancy / Capacity)
        </pre>

        <p><strong>✅ Model 2: Demand-Based Pricing</strong></p>
        <pre>
Demand = α*(Occupancy/Capacity) + β*QueueLength - γ*Traffic + δ*SpecialDay + ε*VehicleTypeWeight

Price_t = BasePrice * (1 + λ * NormalizedDemand)
        </pre>
        <p>Prices are bounded (e.g., 0.5x to 2x Base Price) to ensure stability.</p>
    </div>

    <div class="section">
        <h2>📊 Visualization Examples</h2>
        <ul>
            <li>Real-time price trends per parking lot</li>
            <li>Vehicle-type-specific price comparisons</li>
            <li>Optional competitor price overlays</li>
            <li>Seasonality patterns (e.g., weekday/weekend effects)</li>
        </ul>
    </div>

    <div class="section">
        <h2>📂 Project Structure</h2>
        <pre>
.
├── data/                  # Raw and processed data files
├── notebooks/             # Experimentation and visualization notebooks
├── src/                   # Core model and processing scripts
├── README.html            # Project documentation (this file)
└── requirements.txt       # Dependencies
        </pre>
    </div>

    <div class="section">
        <h2>📄 Optional Documentation</h2>
        <p>Technical reports, experimental results, and analysis PDFs can be added under a <code>/docs</code> directory.</p>
    </div>

    <div class="section">
        <h2>🚀 Getting Started</h2>
        <ol>
            <li>Install dependencies:
                <pre>pip install -r requirements.txt</pre>
            </li>
            <li>Run the pricing pipeline script or notebook</li>
            <li>Launch the Panel dashboard to monitor real-time visualizations</li>
        </ol>
    </div>

    <div class="section">
        <h2>💡 Future Enhancements</h2>
        <ul>
            <li>Rerouting suggestions for overburdened lots</li>
            <li>More advanced demand modeling using temporal patterns</li>
            <li>Competitor-aware pricing integration</li>
        </ul>
    </div>

    <footer>
        <p><em>For questions or contributions, feel free to raise a GitHub Issue or Pull Request.</em></p>
    </footer>

</body>
</html>
