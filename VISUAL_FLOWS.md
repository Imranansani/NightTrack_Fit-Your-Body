# 📊 NightFit Tracker - Visual Flows & User Journeys

## 🎯 Daily User Journey

```
MORNING (Before sleep after shift)
│
├─→ [ OPEN APP ]
│   └─→ Home Tab → "Today's Status"
│
├─→ [ LOG MEALS ]
│   ├─ Tap "Eggs" button (x2) → +140 cal, +12g protein
│   ├─ Tap "Roti" button (x2) → +160 cal, +6g protein
│   ├─ Tap "Dal" button (x1) → +100 cal, +7g protein
│   └─ Real-time: 400 cal / 2100 target ✓
│
├─→ [ CHECK ENERGY ]
│   ├─ IF calories < 1500 → ⚠️ CRITICAL WARNING
│   │  └─ "Risk of dizziness - Eat banana NOW"
│   ├─ ELSE IF calories < 1800 → ⚠️ WARNING
│   │  └─ "Low energy - Consider extra meal"
│   └─ ELSE → ✓ SAFE
│
├─→ [ COMPLETE WORKOUT ]
│   ├─ See: Push-ups, Incline push-ups, Plank
│   ├─ Do exercises
│   └─ Tap "Mark Done" → Workout logged ✓
│
├─→ [ LOG EXPENSE ]
│   ├─ Type: 15 (spent on food)
│   ├─ Press Enter
│   └─ Budget: 250 - 15 = 235 SAR remaining ✓
│
├─→ [ LOG WEIGHT (Optional) ]
│   ├─ Type: 68.2 (kg)
│   └─ App tracks for fat loss calculation ✓
│
└─→ [ SLEEP HAPPY ]
    └─ Data auto-saved ✓
```

---

## 📱 App Navigation Structure

```
┌──────────────────────────────────┐
│        NightFit Tracker          │
│  (Header with Date & Logo)       │
└──────────────────────────────────┘
         ↓↓↓
┌──────────────────────────────────┐
│  [HOME]  [CALENDAR]  [ANALYTICS] │  ← Bottom Navigation
└──────────────────────────────────┘

HOME TAB (Daily View)
├─ Today's Status
│  ├─ Calories: 400 / 2100 [████░░░░░░░]
│  ├─ Protein: 25g / 120g  [███░░░░░░░░]
│  └─ ⚠️ Energy Warning (if needed)
│
├─ Quick Add Meals
│  ├─ [Eggs] [Roti] [Dal] [Oats]
│  └─ [Banana] [Apple]
│
├─ Workout of the Day
│  ├─ Day A: Push-ups, Incline push-ups, Plank
│  └─ [✓ Mark Done] or [Skip]
│
├─ Log Expense
│  └─ [Input field] [Enter]
│
├─ Log Weight
│  └─ [Input field] [Blur to save]
│
└─ Today's Meals
   ├─ Eggs × 2 @ 22:30
   ├─ Roti × 2 @ 23:15
   └─ Dal × 1 @ 00:45


CALENDAR TAB (Monthly View)
├─ [← April 2024 →]
│
├─ Calendar Grid
│  ├─ ✓ Green = Complete day
│  ├─ ✗ Gray = Incomplete
│  └─ Click day for details
│
└─ Selected Date Details
   ├─ Workout: ✓ Done
   ├─ Meals: Eggs×2, Roti×2, Dal×1
   ├─ Expense: 15.50 SAR
   └─ Weight: 68.2 kg


ANALYTICS TAB (Reports)
├─ Date Range Filter
│  ├─ [Start: 2024-04-01]
│  └─ [End: 2024-04-26]
│
├─ Report Dashboard
│  ├─ Completion Rate: 82.5%
│  ├─ Workout Days: 5
│  ├─ Avg Calories: 1850
│  └─ Total Protein: 456g
│
├─ Expense Summary
│  ├─ Total Spent: 195 SAR
│  ├─ Budget Remaining: 55 SAR
│  └─ [Progress bar]
│
├─ Expense Breakdown
│  ├─ Eggs: 24.50 SAR [████████░]
│  ├─ Roti: 18.20 SAR [██████░░░]
│  └─ Dal: 15.80 SAR [█████░░░░]
│
├─ Smart Insights
│  ├─ 💪 "Low consistency - Start 3 days/week"
│  ├─ 📉 "Fat loss trend: 0.5kg/week"
│  └─ ⚠️ "Calories low - Add snacks"
│
└─ Export
   ├─ [Download CSV]
   └─ [Download PDF]


DEV MODAL
├─ [Close X]
├─ [Dev Icon]
├─ Md Emran Hasan
├─ "Building simple tools for real-life problems"
├─ [📧 Email] → imranansani8@gmail.com
├─ [👥 Facebook] → /Imran.hasan.04
├─ [🔗 LinkedIn] → /in/imran-ansani
└─ Made with ❤️ for night shift workers
```

---

## 🧠 Smart Algorithm Flow

```
DATA INPUT
    ↓
    ├─ Meals logged
    ├─ Workouts done
    ├─ Expenses entered
    └─ Weight recorded
    
    ↓
    
CALCULATION ENGINE
    ├─ Calorie Math
    │  └─ Sum all meals × calorie/portion
    │
    ├─ Protein Calculation
    │  └─ Sum all meals × protein/portion
    │
    ├─ Budget Tracking
    │  └─ Sum all expenses vs 250 SAR limit
    │
    ├─ Fat Loss Projection
    │  └─ (Old weight - New weight) / weeks = kg/week
    │
    └─ Energy Detection
       ├─ IF cal < 1500 → CRITICAL
       ├─ ELSE IF cal < 1800 → WARNING
       └─ ELSE → SAFE
    
    ↓
    
INSIGHTS GENERATION
    ├─ Consistency Check
    │  ├─ Count workout days
    │  └─ Compare to total days
    │
    ├─ Trend Analysis
    │  ├─ Weight trend (up/down)
    │  ├─ Calorie trend
    │  └─ Spending trend
    │
    └─ Smart Suggestions
       ├─ "Consistency low" if <50%
       ├─ "Great pace" if weight loss visible
       └─ "Calories too low" if avg <1500
    
    ↓
    
DISPLAY TO USER
    ├─ Real-time stats (calories, protein, budget)
    ├─ Visual warnings (green/yellow/red)
    ├─ Calendar indicators (✓/✗)
    ├─ Analytics dashboard
    └─ Actionable insights
```

---

## 📈 Data Flow Diagram

```
USER INPUT
    ↓
    ├─ [Add Meal] → MEAL_DATA lookup
    │  └─ {type, quantity, time}
    │
    ├─ [Log Workout] → WORKOUTS lookup
    │  └─ {dayA/dayB, sets, reps}
    │
    ├─ [Log Expense] → expense value
    │  └─ {amount, date}
    │
    └─ [Log Weight] → weight value
       └─ {kg, date}

    ↓
    
STORAGE
    └─ localStorage.nightfit_data
       {
         days: {
           "2024-04-26": {
             meals: [...],
             workoutDone: bool,
             expense: number,
             weight: number
           }
         }
       }

    ↓
    
PROCESSING
    ├─ calculateCalories(meals)
    ├─ calculateProtein(meals)
    ├─ calculateExpense(meals, expenses)
    ├─ estimateFatLoss(start, current, days)
    ├─ getEnergyWarning(calories)
    └─ getAnalytics()

    ↓
    
RENDERING
    ├─ Home Tab
    │  ├─ Real-time calorie bar
    │  ├─ Energy warning
    │  └─ Meal buttons
    │
    ├─ Calendar Tab
    │  ├─ Color-coded dates
    │  └─ Click for details
    │
    └─ Analytics Tab
       ├─ Filtered metrics
       ├─ Breakdown charts
       └─ Export buttons

    ↓
    
SERVICE WORKER
    ├─ Cache on install
    ├─ Serve from cache if offline
    └─ Update when online
```

---

## 💪 Workout Progression Timeline

```
WEEK 1-2: Foundation
Day A: Push-ups (10 reps) - Build form
Day B: Squats (15 reps) - Test legs

WEEK 3-4: Adaptation
Day A: Push-ups (12 reps) - Getting easier
Day B: Squats (17 reps) - Legs stronger

WEEK 5-6: Growth
Day A: Push-ups (14 reps) - Definition visible
Day B: Squats (19 reps) - More strength

WEEK 7-8: Challenge
Day A: Push-ups (15 reps) - Arm gains!
Day B: Squats (21 reps) - Solid legs

WEEK 9-10: Building
Day A: Push-ups (17 reps) - Getting hard
Day B: Squats (23 reps) - Endurance

WEEK 11-12: Peak
Day A: Push-ups (18+ reps) - Strong!
Day B: Squats (25+ reps) - Powerful!

RESULT: 8x more reps = Major muscle gain!
```

---

## 🏆 12-Week Transformation

```
BASELINE (Week 0)
├─ Weight: 68.0 kg
├─ Belly: Visible
├─ Double chin: Present
├─ Energy: Unstable
├─ Budget: Not tracked
└─ Consistency: ?

↓

PROGRESS TRACKING
Week 1: Establish habit (start logging)
Week 2: Find meal rhythm (adequate calories)
Week 3: Workout routine (consistency)
Week 4: Review patterns (see trends)

↓

Week 4 CHECKPOINT
├─ Weight: 67.2 kg (-0.8 kg)
├─ Workouts: 70% completion
├─ Budget: On track
├─ Energy: More stable
└─ Insight: "Keep going!"

↓

CONTINUED FOCUS
Week 5-8: Muscle building phase
├─ Increase protein intake
├─ Consistent workouts (5/week)
├─ Visible arm definition
└─ Stronger core

↓

Week 8 CHECKPOINT
├─ Weight: 66.4 kg (-1.6 kg)
├─ Muscles: Visible gains
├─ Belly: Noticeably smaller
├─ Budget: 250 SAR exactly
└─ Insight: "Halfway there!"

↓

FINAL PUSH
Week 9-12: Definition phase
├─ Optimize calories (stay in deficit)
├─ Increase reps (muscle consolidation)
├─ Build consistency (90%+ workouts)
└─ Track everything

↓

FINAL RESULT (Week 12)
├─ Weight: 65.0 kg (-3.0 kg pure fat)
├─ Belly: Significantly reduced
├─ Double chin: Much less visible
├─ Arms: Defined and stronger
├─ Chest: Visible muscle development
├─ Core: Strong, visible abs
├─ Energy: Stable throughout shifts
├─ Budget: 250 SAR tracked daily
├─ Workouts: 85% completion rate
├─ Consistency: Habit formed ✓
└─ Result: TRANSFORMATION! 💪
```

---

## 💰 Budget Breakdown Example (Monthly)

```
250 SAR Budget
   ↓
Week 1: Eggs (24 pcs @ 0.5 each)
├─ Cost: 12.00 SAR
├─ Protein: 144g
├─ Calories: 1680
└─ Remaining: 238 SAR

Week 2: Roti (30 pcs @ 0.3 each)
├─ Cost: 9.00 SAR
├─ Protein: 90g
├─ Calories: 2400
└─ Remaining: 229 SAR

Week 3: Dal (15 portions @ 0.8 each)
├─ Cost: 12.00 SAR
├─ Protein: 105g
├─ Calories: 1500
└─ Remaining: 217 SAR

Week 4: Oats + Fruits (misc)
├─ Cost: 12.00 SAR
├─ Protein: 35g
├─ Calories: 800
└─ Remaining: 205 SAR ✓

TOTAL SPENT: 45 SAR (18% of budget!)
REMAINING: 205 SAR (82%)

Why so low?
✓ Basic foods only
✓ No premium items
✓ Bulk buying
✓ Self cooking
✓ No waste
```

---

## 🎯 Feature Usage Frequency

```
DAILY (Every Day)
├─ Log meals: 1-2 minutes
├─ Check calories: 30 seconds
├─ Complete workout: 20 minutes
├─ Log expenses: 1 minute
└─ Check energy warnings: Real-time

WEEKLY (Sunday)
├─ Review calendar: 2 minutes
├─ Check analytics: 3 minutes
├─ Read insights: 1 minute
├─ Note trends: 2 minutes
└─ Adjust meal plan: 2 minutes

MONTHLY (1st of month)
├─ Export full report: 1 minute
├─ Archive data: 1 minute
├─ Plan next month: 5 minutes
└─ Reset if needed: 1 minute

QUARTERLY (Every 3 months)
├─ Export and review: 5 minutes
├─ Calculate fat loss rate: 2 minutes
├─ Adjust targets: 5 minutes
└─ Celebrate progress: Priceless! 🎉
```

---

## 🔄 Data Lifecycle

```
INPUT
  ↓
  Meal logged at 22:30
  └─ {type: "eggs", quantity: 2, time: "22:30"}
  
STORAGE
  ↓
  Saved to localStorage instantly
  └─ nightfit_data.days["2024-04-26"].meals[0]
  
CALCULATION
  ↓
  Auto-calculated (real-time)
  ├─ Calories: 140
  ├─ Protein: 12g
  └─ Cost: 1 SAR
  
DISPLAY
  ↓
  Shows instantly on screen
  ├─ Calorie bar updates: 400 / 2100
  ├─ Protein updates: 25g / 120g
  └─ Budget updates: 249 SAR remaining
  
PERSISTENCE
  ↓
  Survives app close/reopen
  └─ Works offline forever
  
SYNC
  ↓
  When online
  └─ Service worker confirms cached
  
EXPORT
  ↓
  On demand (CSV/PDF)
  └─ Download to computer for backup
  
RETENTION
  ↓
  Kept forever (unlimited storage)
  └─ Delete manually if needed
```

---

## 🚨 Warning System

```
CALORIE MONITORING
  ↓
  Real-time as meals logged
  ↓
  calc = Sum(meals * calorie per portion)
  
  IF calc < 1500
    → CRITICAL ⚠️
    → Message: "Risk of dizziness - Eat banana NOW"
    → Color: Red
    → Action: Quick fix suggestion
    
  ELSE IF calc < 1800
    → WARNING ⚠️
    → Message: "Low energy - Consider extra meal"
    → Color: Yellow
    → Action: Add snack suggestion
    
  ELSE
    → SAFE ✓
    → Color: Green
    → Message: None (showing is encouraging)
```

---

**Visual Documentation Complete** ✓

All flows, journeys, and diagrams mapped for clarity.

Made to understand, built to transform. ⚡
