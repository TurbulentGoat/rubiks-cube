# Rubik's Cube Speed Tracker

A comprehensive web-based timer and analytics dashboard for tracking Rubik's cube solving progress. This application provides detailed insights into your solving performance with multiple visualization charts and real-time statistics.

## Features

### Timer Functionality
- **Spacebar Controls**: Press spacebar to start/stop the timer
- **Precision Timing**: Millisecond-accurate timing using performance.now()
- **Persistent Storage**: All solve times are automatically saved to localStorage
- **Undo Function**: Remove the last solve if you made a mistake

### Analytics Dashboard
The application displays six different charts to analyze your solving performance:

1. **Solve Times**: Line chart showing all your individual solve times
2. **Moving Average (5 solves)**: Smoothed trend line using a 5-solve rolling average
3. **Progress Tracker**: Dual-line chart displaying personal best progression and monthly averages (last 30 solves)
4. **Weekly Calendar**: Bar chart showing your average solve time for each day of the week (Monday-Sunday)
5. **Time Distribution**: Histogram showing the frequency distribution of your solve times
6. **Improvement Streaks**: Tracks consecutive improvements and sub-personal-best streaks

### Visual Design
- **Modern Interface**: Glassmorphism design with gradient background
- **Responsive Charts**: Interactive charts with hover tooltips
- **Color-Coded Sections**: Each chart has unique color coding for easy identification
- **Export Functionality**: Export any chart as a PNG image

## Usage

### Getting Started
1. Open `rubiks.html` in any modern web browser
2. Press spacebar to start your first solve
3. Press spacebar again to stop the timer when finished
4. Your solve time will be automatically recorded and charts updated

### Timer Controls
- **Start/Stop**: Spacebar
- **Reset All Data**: Red "Reset Data" button (clears all stored times)
- **Undo Last**: Red "Undo Last" button (removes the most recent solve)

### Chart Features
- **Hover Tooltips**: Move your mouse over data points to see exact values
- **Export Charts**: Click the "Export" button on any chart to download as PNG
- **Auto-Update**: All charts update automatically after each solve

### Daily Tracking
The Weekly Calendar chart intelligently tracks your performance by day of the week:
- Each solve is categorized by the day it was completed
- Running averages are maintained for each day (Mon-Sun)
- Data persists across browser sessions

## Technical Details

### Data Storage
- **Solve Times**: Stored as JSON array in localStorage under 'cubeTimes'
- **Daily Averages**: Stored as JSON array in localStorage under 'dailyAverages'
- **Daily Counts**: Stored as JSON array in localStorage under 'dailyCounts'

### Chart Library
Built using Chart.js v4.3.0 for responsive, interactive visualizations.

### Browser Compatibility
Works in all modern browsers that support:
- ES6 JavaScript features
- localStorage API
- Canvas API
- CSS Grid and Flexbox

## File Structure
```
rubiks/
├── rubiks.html    # Main application file (self-contained)
└── README.md      # This documentation file
```

## Customization

### Modifying Chart Colors
Colors are defined in CSS custom properties at the top of the file:
```css
:root {
  --red: #e74c3c;
  --green: #2ecc71;
  --blue: #3498db;
  /* ... other colors */
}
```

### Adjusting Moving Average Window
Change the `windowSize` variable in the JavaScript section:
```javascript
const windowSize = 5; // Change this number
```

### Modifying Monthly Average Period
Update the monthly average calculation in the Progress Tracker section:
```javascript
const monthStart = Math.max(0, i - 29); // Change 29 to desired number of solves
```

## Data Privacy
All data is stored locally in your browser's localStorage. No data is transmitted to external servers or services.

## Installation
No installation required. Simply download the `rubiks.html` file and open it in your web browser.

## Contributing
This is a self-contained HTML file. To modify:
1. Open `rubiks.html` in a text editor
2. Make your changes to the HTML, CSS, or JavaScript
3. Save and refresh in your browser to test

## License
This project is provided as-is for personal use.
