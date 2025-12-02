# ⚽ FIFA World Cup 2026 Countdown

An immersive 3D voxel-style countdown timer and interactive mini-game for the FIFA World Cup 2026. Features a soccer field environment, goal-scoring gameplay, and real-time countdown to the tournament's opening ceremony.

![FIFA World Cup 2026 Countdown](https://img.shields.io/badge/World%20Cup-2026-gold?style=for-the-badge&logo=fifa)
![Three.js](https://img.shields.io/badge/Three.js-r128-black?style=for-the-badge&logo=three.js)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)

## 📸 Page Preview
<a href="https://henrryagc.github.io/soccer-cup/index.html">https://henrryagc.github.io/soccer-cup/index.html</a>

## 🎯 Features

### 🕐 Live Countdown Timer
- Real-time countdown to **June 11, 2026** (World Cup opening ceremony)
- Displays days, hours, minutes, and seconds
- Rotating 3D astrolabe timer on the wall with World Cup colors:
  - 🏆 **Gold** (days ring)
  - ⚪ **White** (hours ring)
  - 💚 **Green** (minutes ring)
  - 🔵 **FIFA Blue** (seconds ring)

### ⚽ Interactive Goal Scoring Game
- **Click the soccer ball** to kick it toward the goal
- Physics-based ball movement with gravity, bounce, and spin
- **Goal detection** - score when ball enters goal area
- **Goal counter** tracks your scores
- **Celebration effects** - "GOAL!" message and counter animation
- Ball automatically resets after each kick

### 🏟️ 3D Voxel Stadium
- Soccer field floor with authentic white line markings:
  - Center line
  - Center circle
  - Penalty boxes
- Goal posts with crossbar
- World Cup trophy on display stand (front-center)
- Corner flags
- Stadium wall with mounted timer

### 📅 Calendar Widget
- June 2026 calendar display
- **June 11** highlighted with:
  - Gold gradient background
  - Trophy emoji decoration 🏆
  - Pulsing glow animation
  - "⚽ World Cup Starts!" label

### 🎨 Premium Design
- World Cup color scheme (gold, green, white, FIFA blue)
- Smooth animations and transitions
- Responsive layout for desktop and mobile
- Interactive 3D camera controls (drag to rotate view)

## 🚀 Quick Start

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Python 3 (for local server) or any HTTP server

### Installation & Running

1. **Clone or download** this repository

2. **Navigate to the project directory**:
   ```bash
   cd web-cup
   ```

3. **Start a local server**:
   ```bash
   python3 -m http.server 8000
   ```

4. **Open in browser**:
   ```
   http://localhost:8000/main.html
   ```

### Alternative Servers

**Node.js**:
```bash
npx http-server -p 8000
```

**PHP**:
```bash
php -S localhost:8000
```

## 🎮 How to Play

1. **View the Countdown**: See time remaining until World Cup 2026
2. **Explore the 3D Scene**: Drag with mouse to rotate camera
3. **Kick the Ball**: Click on the soccer ball to kick it toward the goal
4. **Score Goals**: Ball automatically aims at goal with slight randomness
5. **Track Your Score**: Goal counter in top-right shows your total goals
6. **Enjoy Celebrations**: "GOAL!" message appears when you score

### Goal Scoring Tips
- Ball kicks toward the goal but has randomness for challenge
- Must enter between goal posts
- Must go under the crossbar
- Try to score as many goals as you can!

## 🛠️ Technical Stack

### Core Technologies
- **Three.js r128** - 3D graphics and rendering
- **Vanilla JavaScript (ES6)** - Game logic and interactions
- **HTML5** - Structure
- **CSS3** - Styling and animations
- **Tailwind CSS** - Utility-first CSS framework

### Key Features Implementation
- **Raycasting** - Ball click detection
- **Physics Simulation** - Gravity, friction, bounce
- **Goal Detection** - 3D boundary checking
- **CSS Animations** - Celebration effects
- **OrbitControls** - 3D camera manipulation

## 📁 Project Structure

```
web-cup/
├── main.html          # Main application file
└── README.md          # This file
```

### Code Organization (in main.html)
- **CSS Styles** (lines 25-243)
  - Calendar widget styles
  - Goal counter styles
  - Celebration animations
  
- **HTML Structure** (lines 244-337)
  - UI overlay elements
  - Countdown display
  - Goal counter
  - Calendar widget
  
- **JavaScript** (lines 338-880+)
  - Three.js scene setup
  - Voxel room creation
  - Ball physics
  - Goal detection
  - Event handlers

## 🎨 Customization

### Change Countdown Date
Edit line 359:
```javascript
const targetDate = new Date('2026-06-11T12:00:00-04:00').getTime();
```

### Modify Colors
Edit the `currentTheme` object (lines 372-381):
```javascript
let currentTheme = {
    roomColor: '0x2d8a3e',    // Floor color
    wallColor: '0x4a5568',    // Wall color
    dayColor: '0xffd700',     // Day ring color
    hourColor: '0xffffff',    // Hour ring color
    minuteColor: '0x00ff00',  // Minute ring color
    secondColor: '0x0066cc',  // Second ring color
};
```

### Adjust Ball Physics
Edit physics constants (lines 729-731):
```javascript
const gravity = -0.015;      // Gravity strength
const friction = 0.98;       // Friction coefficient
const groundLevel = 0.5;     // Ground Y position
```

### Change Kick Power
Edit line 830:
```javascript
const power = 0.25; // Kick strength (higher = stronger)
```

## 🎯 Goal Detection Parameters

Goals are detected when the ball enters this 3D region:
- **X**: `x <= -4.0` (past goal line)
- **Z**: `-2 < z < 2` (between goal posts)
- **Y**: `0.3 < y < 1.8` (below crossbar, above ground)

Modify in `updateBallPhysics()` function (line 746-750).

## 🌐 Browser Compatibility

✅ **Fully Supported**:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

⚠️ **Partial Support**:
- Older browsers may have reduced performance
- Mobile browsers work but desktop recommended for best experience

## 📱 Responsive Design

- **Desktop**: Full experience with all features
- **Tablet**: Optimized layout with touch controls
- **Mobile**: Adapted UI with simplified interactions

## 🔧 Performance

- **60 FPS** rendering on modern hardware
- **Efficient raycasting** - only checks ball children
- **Optimized physics** - simple calculations per frame
- **GPU-accelerated animations** - CSS transforms

## 📝 License

This project is open source and available for educational and personal use.

## 🙏 Credits

### Technologies
- [Three.js](https://threejs.org/) - 3D graphics library
- [Tailwind CSS](https://tailwindcss.com/) - CSS framework
- [Google Fonts](https://fonts.google.com/) - Inter & Roboto Mono fonts

### Inspiration
Created for FIFA World Cup 2026 fans to count down to the biggest football event!

## 🤝 Contributing

Feel free to fork this project and add your own features:
- Different stadium designs
- Multiple difficulty levels
- Sound effects
- Multiplayer scoring
- Different ball skins
- More celebration effects

## 📧 Support

For issues or questions, please open an issue in the repository.

## 🎉 Enjoy!

Have fun scoring goals and counting down to the FIFA World Cup 2026! ⚽🏆

---

**Made with ❤️ for football fans worldwide**

🌍 **FIFA World Cup 2026** - USA 🇺🇸 | Canada 🇨🇦 | Mexico 🇲🇽
