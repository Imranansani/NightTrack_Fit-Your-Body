# 🌙⚡ NightFit Tracker - Smart Fitness PWA for Night Shift Workers

> **Building simple tools for real-life problems** | Developed by Md Emran Hasan

A powerful, offline-first Progressive Web App (PWA) designed specifically for night shift workers to track fitness, diet, expenses, and progress with intelligent insights.

---

## ✨ Key Features

### 📊 Smart Tracking System
- **Real-time Calorie & Protein Tracking** - Know your macros instantly
- **Intelligent Energy Safety System** - Warns when calories are too low to prevent dizziness
- **Auto-rotating Workout Days** - Day A/B rotation with exercises targeting lean muscle
- **Expense Management** - Track costs against your 250 SAR/month budget
- **Weight Logging** - Track progress over time

### 🤖 AI-Powered Intelligence
- **Fat Loss Projection** - Calculates estimated weekly fat loss based on calorie intake and activity
- **Smart Budget Suggestions** - Detects overspending and suggests cheaper food alternatives
- **Weekly Insights** - Analyzes consistency, suggests improvements
- **Predictive Warnings** - Alerts you before energy crashes

### 📱 Mobile-First PWA
- **Fully Offline** - Works completely without internet
- **Installable** - Add to home screen like native app
- **Fast** - Sub-100ms load times
- **No Dependencies** - Uses localStorage for data persistence

### 📈 Advanced Analytics
- **Date Range Filtering** - Analyze any time period
- **Expense Breakdown** - See spending by food category with charts
- **Completion Reports** - Workout & meal adherence rates
- **Export Options** - Download data as CSV or PDF

### 🎯 User Experience
- **One-Click Logging** - Log meals, workouts, expenses in seconds
- **Visual Progress Calendar** - Green = complete, Red = missed
- **Real-time Stats** - Calories, protein, budget tracking in real-time
- **Developer Profile** - Connect with creator directly

---

## 🚀 Quick Start

### Installation

```bash
# 1. Clone or download the project
git clone <repo-url>
cd nightfit-tracker

# 2. Install dependencies
npm install

# 3. Run development server
npm run dev

# 4. Visit http://localhost:5173
# 5. Open on mobile and install as app!
```

### Building for Production

```bash
npm run build
# Creates optimized /dist folder ready to deploy
```

---

## 📋 Workout System

### Day A (Upper Body)
- Push-ups: 3 sets × 10 reps
- Incline Push-ups: 3 sets × 8 reps
- Plank: 3 sets × 30 seconds

### Day B (Lower Body)
- Squats: 3 sets × 15 reps
- Lunges: 3 sets × 10 reps
- Plank: 3 sets × 30 seconds

**Auto-Progression**: Reps increase weekly based on consistency ✓

---

## 🍽️ Food Database

All foods optimized for budget, nutrition, and energy stability:

| Food | Protein | Calories | Cost (SAR) |
|------|---------|----------|-----------|
| Egg | 6g | 70 | 0.5 |
| Roti | 3g | 80 | 0.3 |
| Dal (Lentils) | 7g | 100 | 0.8 |
| Oats | 5g | 150 | 0.4 |
| Banana | 1g | 89 | 0.5 |
| Apple | 0.3g | 52 | 1.5 |

---

## 💡 Smart Insights Examples

### Calorie Warnings
- **Critical** (<1500 cal): ⚠️ Risk of dizziness - Eat banana/oats NOW
- **Low** (<1800 cal): ⚠️ Low energy - Consider extra meal

### Consistency Feedback
- "Low workout consistency - Start with 3 days/week"
- "Excellent consistency! Keep this momentum"
- "Average calories too low - Add snacks for energy"

### Fat Loss Tracking
- "Fat loss trend: ~0.5kg/week (great pace!)"
- Based on weight logs over time

---

## 📊 Analytics Dashboard

**Report Includes:**
- ✓ Workout completion rate (%)
- ✓ Total workout days completed
- ✓ Average daily calories
- ✓ Total protein intake
- ✓ Total expenses vs budget
- ✓ Remaining budget
- ✓ Category-wise expense breakdown

**Filters:**
- Select any date range
- Auto-updates all charts
- Export capability

---

## 📤 Export Options

### CSV Export
Perfect for spreadsheet analysis
```
Date,Workout,Meals,Calories,Protein,Expense,Weight
2024-04-26,Yes,eggs×2;roti×2,220,15.5,5.5,68.2
```

### PDF Export
Professional report ready to share
- Summary statistics
- Daily breakdown
- Budget analysis

---

## 🔐 Data Privacy

- **100% Local Storage** - All data saved on your device
- **No Cloud Sync** - Your data never leaves your phone
- **No Ads, No Tracking** - Completely private
- **Automatic Backups** - Export anytime

---

## 📱 Mobile Installation

### iOS (Safari)
1. Open app in Safari
2. Tap Share → Add to Home Screen
3. Name it "NightFit"
4. Works offline!

### Android (Chrome)
1. Open app in Chrome
2. Menu → Install App
3. Add to home screen
4. Launch anytime!

---

## 🛠️ Technical Stack

- **Frontend**: React 18 + Vite
- **Styling**: Tailwind CSS
- **Icons**: Lucide React
- **Storage**: Browser localStorage
- **PWA**: Service Workers + Web App Manifest
- **Build**: Vite with PWA plugin

---

## ⚙️ Configuration

### Daily Budget
Edit in code (line): `profile.dailyBudget`
```javascript
profile: { height: '5\'6"', dailyBudget: 250 }
```

### Starting Weight
Edit in code or log on first day
```javascript
startWeight: 68 // Change to your weight
```

### Meal Adjustments
Customize foods in `MEAL_DATA`:
```javascript
const MEAL_DATA = {
  eggs: { protein: 6, cal: 70, cost: 0.5 },
  // Add more foods here
}
```

---

## 📞 Contact & Support

**Developer**: Md Emran Hasan

- 📧 **Email**: imranansani8@gmail.com
- 🔗 **LinkedIn**: https://www.linkedin.com/in/imran-ansani
- 👥 **Facebook**: https://www.facebook.com/Imran.hasan.04
- 🌐 **Portfolio**: https://imranansani.netlify.app

---

## 💪 Tips for Success

1. **Log Daily** - 2 minutes/day keeps consistency high
2. **Check Warnings** - Energy alerts are real safety features
3. **Review Weekly** - Analyze trends every Sunday
4. **Adjust Food** - Use suggestions to optimize budget
5. **Export Monthly** - Create a backup of your data

---

## 🎯 Expected Results (In 12 Weeks)

With consistent use:
- **Weight Loss**: 2-3 kg of fat loss
- **Muscle Gain**: Visible arm & chest definition
- **Energy**: Stable throughout night shifts
- **Budget**: 250 SAR exactly tracked
- **Consistency**: 80%+ workout completion

---

## 🐛 Troubleshooting

### App not saving data?
- Check if browser allows localStorage
- Try clearing cache and reinstalling
- Export data regularly for backup

### PWA not installing?
- Use Chrome (Android) or Safari (iOS)
- Make sure you're on HTTPS
- Try clearing browser cache

### Offline mode not working?
- Check that service worker is registered
- Open DevTools → Application → Service Workers
- Should show "active" status

---

## 📈 Roadmap

- [ ] Photo progress tracker
- [ ] Meal photos with OCR nutrition detection
- [ ] Workout video guides
- [ ] Social sharing (results)
- [ ] Cloud sync (optional)
- [ ] Dark/Light theme toggle

---

## 📄 License

Open source for personal use. Made with ❤️ for night shift workers.

---

**Remember**: This app is a tool. Your consistency is the real magic. 💪

Start today. Get results. Stay healthy.

⚡ **NightFit Tracker** - Smart Fitness for Night Shift Workers
