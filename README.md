# Infectious Disease Monitoring Website

**Capstone Project: AI-Powered Infectious Disease Monitoring Platform**

A privacy-focused web application for monitoring infectious diseases through photo analysis and medical report processing.

## 🚀 Features

- **Photo Upload & Analysis**: Upload photos of symptoms for AI-powered analysis
- **Medical Report Processing**: Process and analyze medical reports
- **Disease Classification**: Machine learning-based disease identification
- **Data Visualization**: Interactive charts showing disease trends
- **Privacy-First**: All processing happens client-side, no data leaves your device

## 🏗️ Project Structure

```
infectious-disease-monitor/
├── index.html              # Main application page
├── css/                    # Stylesheets
│   ├── main.css           # Main styles
│   └── components.css     # Component-specific styles
├── js/                    # JavaScript files
│   ├── app.js            # Main application logic
│   ├── upload.js         # File upload handling
│   ├── analysis.js       # AI analysis functions
│   ├── visualization.js  # Data visualization
│   └── privacy.js        # Privacy and security features
├── data/                  # Sample datasets
│   ├── diseases.json     # Disease definitions
│   ├── symptoms.json     # Symptom mappings
│   └── sample-reports/   # Sample medical reports
├── models/                # Pre-trained ML models
├── assets/                # Images and other assets
└── docs/                  # Documentation
```

## 🛠️ Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/circuitseeker/Infectious-disease-monitoring.git
   cd Infectious-disease-monitoring
   ```

2. **Open in browser**
   - Simply open `index.html` in a modern web browser
   - Or use a local server: `python -m http.server 8000`

3. **Deploy to GitHub Pages**
   - Push to GitHub repository
   - Enable GitHub Pages in repository settings
   - Select source branch (usually `main` or `gh-pages`)

## 🔒 Privacy & Security

- **Client-Side Processing**: All data analysis happens in your browser
- **No Server Storage**: Medical data never leaves your device
- **Local Storage**: Data stored locally with encryption
- **HIPAA Compliant**: Designed with healthcare privacy standards in mind

## 📊 Data Sources

- **Synthetic Data**: Generated realistic medical scenarios
- **Public Datasets**: Anonymized health data (properly licensed)
- **Simulated Cases**: Diverse disease presentations for testing

## 🚧 Development Status

- [x] Project structure setup
- [x] Frontend UI components
- [x] File upload functionality
- [x] Photo analysis integration
- [x] Medical report processing
- [x] Data visualization
- [x] Privacy features
- [x] Testing and validation

