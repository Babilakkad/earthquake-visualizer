# 🌍 Earthquake Building Visualizer

A comprehensive earthquake analysis and 3D building collapse simulation tool that combines real USGS earthquake data with structural engineering models to visualize how buildings respond to seismic events.

## ✨ Features

### 🔍 **Earthquake Data Integration**
- Real-time USGS earthquake data fetching
- Historical earthquake pattern analysis
- Earthquake statistics and trends
- Location-based earthquake queries

### 🏢 **Building Damage Assessment**
- Multiple building types:
  - Reinforced Concrete
  - Steel Frame
  - Masonry/Brick
  - Wood Frame
  - Adobe
- Soil type effects on ground motion
- Peak Ground Acceleration (PGA) calculation
- Spectral acceleration analysis

### ⏰ **Earthquake Early Warning**
- P-wave/S-wave propagation modeling
- Warning time calculations
- Real-time alert level assessment
- Safety recommendations

### 🎬 **3D Collapse Simulation**
- Real-time building visualization with Three.js
- Progressive collapse animation
- Floor-by-floor damage visualization
- Seismic shaking simulation
- Color-coded damage levels (Green → Red)

### 📊 **Analysis Tools**
- Full scenario analysis
- Vulnerability assessment
- Risk matrix generation
- Collapse probability calculation
- Building-specific damage predictions

## 🚀 Quick Start

### Installation

```bash
# Install backend dependencies
npm install

# Install frontend dependencies
cd client
npm install
cd ..
```

### Running the Application

**Terminal 1 - Backend Server:**
```bash
npm start
# Server runs on http://localhost:5000
```

**Terminal 2 - Frontend (from root directory):**
```bash
cd client
npm start
# Client runs on http://localhost:8000
# Or use: python -m http.server 8000
```

**Open in Browser:**
```
http://localhost:8000
```

## 📡 API Endpoints

### Earthquake Data
- `GET /api/earthquakes/recent?period=all_week` - Recent earthquakes
- `GET /api/earthquakes/magnitude?minMag=5&maxMag=7` - Filter by magnitude
- `GET /api/earthquakes/nearby?lat=40&lon=-75&maxDistance=500` - Earthquakes near location
- `GET /api/earthquakes/stats` - Earthquake statistics

### Building Analysis
- `GET /api/buildings/types` - Available building and soil types
- `POST /api/buildings/analyze` - Damage analysis for specific earthquake
- `POST /api/buildings/collapse-simulation` - Simulate building collapse
- `POST /api/buildings/vulnerability-assessment` - Assess vulnerability across scenarios

### Advanced Analysis
- `POST /api/analysis/early-warning` - Generate early warning
- `POST /api/analysis/wave-propagation` - Analyze wave propagation
- `POST /api/analysis/scenario` - Full scenario analysis
- `POST /api/analysis/risk-matrix` - Generate risk assessment matrix

## 🎮 Usage

1. **Select Building Type** - Choose from 5 different building types
2. **Set Earthquake Parameters**:
   - Magnitude (4.0 - 9.0)
   - Distance from epicenter (1 - 500 km)
   - Depth (1 - 100 km)
3. **Configure Building**:
   - Height (5 - 100 meters)
   - Number of floors (1 - 50)
4. **Choose Soil Type** - Different soil amplification factors
5. **Click Analyze** - See real-time 3D collapse simulation

## 📊 Output Information

### Damage Analysis
- **Damage Level**: None → Minimal → Light → Moderate → Heavy → Very Heavy → Complete Collapse
- **Damage Percentage**: 0-100% structural damage
- **Collapse Probability**: Percentage likelihood of building collapse

### Ground Motion
- **PGA (g)**: Peak Ground Acceleration in gravitational units
- **Spectral Acceleration**: Acceleration at building's natural frequency

### Early Warning
- **Warning Time**: Seconds between S-wave detection and arrival
- **Alert Level**: 1-5 severity scale
- **Safety Recommendations**: Action items based on conditions

## 🔬 Technical Details

### Attenuation Models
Uses Boore et al. (1997) empirical relationships for ground motion calculation:
- Distance decay with magnitude
- Soil amplification factors
- Frequency-dependent effects

### Structural Analysis
- Demand-Capacity Ratio (DCR) methodology
- Ductility-based fragility curves
- Building period calculations
- Material-specific vulnerabilities

### Wave Propagation
- P-wave (Primary): 6.0 km/s
- S-wave (Secondary): 3.5 km/s
- Surface wave: 2.5 km/s

## 🛠 Building Types Specifications

| Type | Vulnerability | Ductility | Max Acceleration |
|------|---|---|---|
| Reinforced Concrete | 0.4 | 0.7 | 1.2g |
| Steel Frame | 0.3 | 0.9 | 1.5g |
| Masonry | 0.8 | 0.2 | 0.4g |
| Wood Frame | 0.5 | 0.6 | 0.8g |
| Adobe | 0.95 | 0.1 | 0.2g |

## 🎨 Visualization

- **Green**: Light damage (< 30%)
- **Yellow**: Moderate damage (30-60%)
- **Orange**: Heavy damage (60-80%)
- **Red**: Critical/Collapse risk (> 80%)

## 📚 Data Sources

- USGS Earthquake Hazards Program
- Building design standards (IBC, NEHRP)
- Seismic hazard assessment research
- Structural dynamics literature

## ⚠️ Disclaimer

This tool is for educational and research purposes. Results are estimates based on simplified models. Real earthquake damage depends on many additional factors not captured here. Always consult qualified structural engineers for real design decisions.

## 📝 License

MIT License - Feel free to use and modify

## 👤 Author

Developed as an earthquake science visualization tool

## 🤝 Contributing

Contributions welcome! Areas for enhancement:
- More building types and soil profiles
- Advanced material properties
- Liquefaction analysis
- Tsunami simulation
- Multiple building interactions

---

**Remember**: The best defense against earthquakes is preparation and education! 🛡️
