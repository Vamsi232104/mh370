# MH370 — Personal Fitness App
## Master Plan Document · v4.0

> "One day I'll find the plane. One day I'll become the fittest version of myself."

---

## 1. Personal Profile

| Field | Value |
|---|---|
| Age | 24 years old |
| Weight (start) | 58 kg |
| Height | 165 cm |
| Goal | Build full-body muscle (thighs, biceps, shoulders, chest, face definition) |
| Location | Mauritius |
| Cooking | Self-cooked |
| Gym | Commercial gym — full equipment |
| Phone | Android |
| Training days | Monday to Saturday |
| Rest day | Sunday only |

---

## 2. App Identity

| Field | Value |
|---|---|
| Name | MH370 |
| Tagline | "still flying" |
| Type | Progressive Web App (PWA) |
| Hosting | GitHub Pages |
| GitHub username | Vamsi232104 |
| Repository | mh370 |
| Live URL | https://vamsi232104.github.io/mh370 |
| Storage | localStorage key: mh370_v1 |
| Install | Android Chrome → "Add to Home Screen" |
| Start date | June 11, 2026 (birthday — Day 1) |

---

## 3. Daily Non-Negotiables

| Target | Value | Rule |
|---|---|---|
| Calories | 2,700 kcal | Skinny guys do not grow on low calories. Period. |
| Protein | 140 g/day | 2.4g per kg bodyweight. Muscle cannot be built without this. |
| Water | 3.5 L/day | Muscle is 75% water. Dehydration kills performance. |
| Sleep | 8 hours minimum | Muscle is built during sleep, not during the workout. |
| Training | Mon–Sat | Sunday is the only rest day. This is not negotiable. |

---

## 4. Training Split — Push / Pull / Legs × 2 Per Week

| Day | Session | Primary Muscles | Duration |
|---|---|---|---|
| Monday | Push | Chest · Shoulders · Triceps | 65 min |
| Tuesday | Pull | Back · Biceps | 65 min |
| Wednesday | Legs | Quads · Hamstrings · Glutes · Calves | 75 min |
| Thursday | Push (heavier) | Chest · Shoulders · Triceps | 65 min |
| Friday | Pull (deadlift focus) | Back · Biceps | 75 min |
| Saturday | Legs (volume) | Quads · Glutes · Hamstrings · Calves | 75 min |
| Sunday | Full Rest | Recovery | — |

---

## 5. Session Timing

### Morning Session (Target: 5:30 AM)

| Time | Action |
|---|---|
| 5:30 AM | Wake up |
| 5:45 AM | Pre-workout meal |
| 6:00 AM | Workout begins |
| 7:05–7:15 AM | Workout ends |
| 7:30 AM | Post-workout meal |
| 12:30 PM | Lunch |
| 4:00 PM | Snack |
| 7:00 PM | Dinner |
| 10:00 PM | Sleep |

### Evening Session

| Time | Action |
|---|---|
| 7:00 AM | Breakfast |
| 12:30 PM | Lunch |
| 4:00 PM | Pre-workout snack |
| 6:00 PM | Workout begins |
| 7:05–7:15 PM | Workout ends |
| 7:30 PM | Post-workout dinner |
| 9:00 PM | Small evening meal |
| 10:30 PM | Sleep |

---

## 6. CRITICAL UI BEHAVIOUR RULES

### Rule 1 — Morning/Evening Session Lock
- When the user opens the app for the first time each day, a full-screen modal appears before anything else.
- Modal says: "Today is [Day] — [Push/Pull/Legs] Day. Choose your session:"
- Two large buttons: "Morning Session" and "Evening Session"
- Tapping one shows confirmation: "Lock Morning session for today? Cannot be changed until tomorrow."
- Confirm = modal closes, session locked, toggle on Home replaced with plain locked text "🔒 Morning Session" — not tappable.
- At midnight the lock clears automatically and tomorrow's modal is ready.

### Rule 2 — Meal Confirmation (Strict, Permanent)
- Every meal card in Meals tab has a "Mark as Done ✓" button.
- Tapping shows: "Mark [Meal name] as done? This cannot be undone."
- Confirm = card turns green with checkmark, button disappears, saved to localStorage permanently.
- No undo. No uncheck. Done means done.

### Rule 3 — Exercise Completion (Strict, Permanent)
- Every exercise has set tracker buttons (Set 1, Set 2, Set 3, Set 4) — toggleable during session.
- Below the set buttons: "Mark Exercise Complete" button.
- Tapping shows: "Confirm exercise complete?" → Confirm → card turns green, locked.
- Set tracker buttons also lock once exercise is marked complete.
- Resets daily at midnight.

### Rule 4 — Inventory Starts at Zero
- Every inventory item starts at 0 stock when app is first installed.
- User fills in manually after buying food.
- App never assumes the user has anything.

### Rule 5 — Bottom Padding
- All scrollable tab content has minimum 90px bottom padding.
- The bottom navigation bar must never hide any content.
- Applies to every tab.

### Rule 6 — Daily Quote + Scripture Placement
- Shown at the BOTTOM of the Home tab in a distinct card.
- Rotates daily through the combined pool: 30 built-in gym quotes + 15 Christian scriptures.
- Day 1 of journey = entry 1, Day 2 = entry 2, cycling through all 45.
- Custom quotes added via Settings merge into this pool.

### Rule 7 — Sunday Backup Reminder
- Every Sunday a small amber banner appears at top of Home tab.
- Text: "Sunday — back up your data. Settings → Export JSON"
- Has X button to dismiss for that day only.

### Rule 8 — Distraction-Free Workout Screen
- When the user is in the Workout tab, the bottom navigation bar hides completely.
- Full screen is given to the workout content.
- A small back arrow appears at the top left to return to Home.
- No distractions during training. Full focus.

### Rule 9 — Rest Timer After Each Set
- When any set tracker button is tapped (Set 1, Set 2, etc.), a rest timer automatically starts.
- Compound exercises (bench, squat, deadlift, row, overhead press): timer = 2 minutes.
- Isolation exercises (lateral raises, curls, pushdowns, calf raises): timer = 90 seconds.
- Timer shown as a countdown at the bottom of the screen during rest.
- When timer ends, phone vibrates (if supported) and a "Rest done — go!" message appears.
- User can dismiss timer early by tapping it.

---

## 7. Goal Card — Home Tab (NEW)

### Purpose
Show the actual physical goal every single day. Not just numbers and streaks — the real reason this app exists.

### Display
A permanent card shown near the top of the Home tab, always visible, that reads:

**"YOUR GOAL"**
Build thighs, biceps, shoulders, chest and face definition.
This takes 18–24 months of non-negotiable discipline.
You started June 11, 2026. You will not stop.

### Design
- Dark card with amber border
- Bold heading "YOUR GOAL"
- Text below in clean readable font
- Cannot be dismissed or hidden
- Always the first thing visible after the session lock modal

---

## 8. Fitness Terminology — What Everything Means

### Reps (Repetitions)
One complete movement of an exercise — up and back down.
For bench press: push bar up + lower bar down = 1 rep.
"8–10 reps" means you do the movement 8 to 10 times without stopping.

### Sets
A group of reps done in a row, followed by rest.
"4 sets" means you do the exercise 4 separate times with rest in between.

### What "4 × 8–10" means
Do 8–10 reps → rest 2–3 minutes → repeat. That is 4 sets total.

### Rest Between Sets
- Compound exercises (bench, squat, deadlift, row): 2–3 minutes
- Isolation exercises (laterals, curls, pushdowns): 60–90 seconds

### Progressive Overload
Every week, try to do more weight or more reps than last week. Even 1 extra rep counts.
Your body only grows when forced to adapt to something harder.

### Compound Exercise
Uses multiple muscle groups. Examples: bench press, squat, deadlift, overhead press, row.
Always done first in the session.

### Isolation Exercise
Targets one specific muscle. Examples: lateral raises, curls, pushdowns, calf raises.
Done last in the session.

### Warm-Up Set
Before your first working set, do 1 set at 40–50% of working weight to warm the muscle.

---

## 9. Warm-Up Protocol — Every Session, Every Day

**Duration: 10 minutes. Before any weight.**

| Step | Exercise | How To Do It | Time/Reps | YouTube |
|---|---|---|---|---|
| 1 | Light cardio | Jog on spot or treadmill at 6 km/h. Get heart rate up slightly. | 3 minutes | [Watch](https://www.youtube.com/results?search_query=warm+up+cardio+before+gym+beginners) |
| 2 | Arm circles | Arms out to side. Large circles forward 10×, backward 10×. | 10 each direction | [Watch](https://www.youtube.com/results?search_query=arm+circles+warm+up+exercise+form) |
| 3 | Hip circles | Hands on hips. Rotate hips in large circle. 10 each direction. | 10 each direction | [Watch](https://www.youtube.com/results?search_query=hip+circles+warm+up+mobility) |
| 4 | Bodyweight squats | Full depth, no weight, slow and controlled. | 10 slow reps | [Watch](https://www.youtube.com/results?search_query=bodyweight+squat+form+beginners+depth) |
| 5 | Shoulder pass-throughs | Towel overhead and behind back, return. | 10 reps | [Watch](https://www.youtube.com/results?search_query=shoulder+pass+through+warm+up+towel) |
| 6 | Warm-up set | First exercise at 40–50% weight. 10–15 slow reps. | 1 set × 12 reps | — |

**Leg day extra:** 5 leg swings per leg forward/back, then side to side.

---

## 10. Exercise Database — Full Guidance

### PUSH DAY — Monday & Thursday (65 min)

#### 1. Barbell Bench Press
**What it is:** Lie on flat bench, push barbell up from chest.
**Why:** Best exercise for chest mass. Foundation of push day.
**How:** Lie flat, eyes under bar. Grip wider than shoulders. Feet flat. Lower bar slowly to chest. Press up explosively.
**Mistake:** Elbows flaring at 90 degrees — keep at 45–75 degrees.
**Start weight:** 20 kg (bar only).
**YouTube:** [Watch](https://www.youtube.com/results?search_query=barbell+bench+press+proper+form+beginners+chest)

#### 2. Overhead Press (Barbell)
**What it is:** Stand, press barbell from shoulders straight up overhead.
**Why:** Builds shoulder roundness and width.
**How:** Feet shoulder-width. Bar at shoulder height. Brace core. Press bar straight up. Lower slowly.
**Mistake:** Leaning back — keep body vertical.
**Start weight:** 20 kg.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=barbell+overhead+press+standing+form+beginners)

#### 3. Incline Dumbbell Press
**What it is:** Bench press at 30–45 degree angle with dumbbells.
**Why:** Targets upper chest — gives the full chest look.
**How:** Set bench to 30–45 degrees. Kick dumbbells up as you lie back. Press up above upper chest. Lower slowly.
**Mistake:** Bench too steep — shifts work to shoulders.
**Start weight:** 8–10 kg per hand.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=incline+dumbbell+press+proper+form+upper+chest)

#### 4. Lateral Raises (Dumbbell)
**What it is:** Raise dumbbells out to the side like wings.
**Why:** Creates shoulder width.
**How:** Stand straight. Slight elbow bend. Raise arms to shoulder level. Lower slowly 3 seconds.
**Mistake:** Too heavy, swinging body. Use light weight, pure arm raising.
**Start weight:** 5–6 kg.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=dumbbell+lateral+raises+proper+form+no+momentum)

#### 5. Tricep Pushdown (Cable)
**What it is:** Push cable attachment downward by extending elbows.
**Why:** Triceps = 2/3 of arm size. Most important arm exercise.
**How:** Elbows pinned to sides. Push down until arms fully straight. Squeeze. Let cable rise slowly.
**Mistake:** Elbows flaring — pin them to sides throughout.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=cable+tricep+pushdown+rope+proper+form+elbows)

#### 6. Overhead Tricep Extension (Cable)
**What it is:** Hold cable behind head, extend arms upward.
**Why:** Targets long head of tricep — arm thickness from behind.
**How:** Rope at low pulley, face away. Hold rope behind head, elbows to ceiling. Extend arms up. Lower slowly.
**Mistake:** Upper arms falling forward — keep them pointing up.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=overhead+cable+tricep+extension+long+head+form)

**Thursday variations:**
- Close-Grip Bench Press [Watch](https://www.youtube.com/results?search_query=close+grip+bench+press+triceps+form+beginners)
- Weighted Tricep Dips [Watch](https://www.youtube.com/results?search_query=tricep+dips+proper+form+bars+beginners)

---

### PULL DAY — Tuesday & Friday (65/75 min)

#### 1. Barbell Bent-Over Row
**What it is:** Bend forward, row barbell up toward stomach.
**Why:** Builds back thickness and width.
**How:** Hinge at hips, back flat, torso at 45 degrees. Pull bar to lower chest, lead with elbows. Squeeze shoulder blades.
**Mistake:** Rounding lower back — serious injury risk.
**Start weight:** 40 kg.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=barbell+bent+over+row+proper+form+back+beginners)

#### 2. Lat Pulldown (Wide Grip)
**What it is:** Pull wide bar from above down to chest level.
**Why:** Builds the V-taper — wide back look.
**How:** Wide overhand grip. Lean back 15 degrees. Pull to upper chest, lead elbows toward hips. Full stretch at top.
**Mistake:** Pulling behind neck — always pull to front.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=lat+pulldown+wide+grip+proper+form+lats+V+taper)

#### 3. Seated Cable Row
**What it is:** Sit at cable machine, row handle toward stomach.
**Why:** Builds mid-back thickness.
**How:** Sit upright, pull handle to stomach, elbows behind you, squeeze shoulder blades. Extend forward slowly.
**Mistake:** Rocking body with momentum.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=seated+cable+row+proper+form+mid+back+beginners)

#### 4. Cable Face Pulls
**What it is:** Pull rope toward face, splitting it apart at end.
**Why:** Targets rear delts — critical for shoulder health.
**How:** Cable at face height. Pull rope to face, hands each side of head. Elbows at shoulder height.
**Mistake:** Elbows dropping below shoulder height.
**Start weight:** 10–15 kg.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=cable+face+pulls+rear+delts+proper+form+elbows+high)

#### 5. Barbell Curl
**What it is:** Curl barbell up by bending elbows.
**Why:** Primary bicep mass builder.
**How:** Elbows pinned to sides. Curl bar to chest. Squeeze at top. Lower 3 full seconds.
**Mistake:** Swinging back to help — drop weight and use strict form.
**Start weight:** 30 kg.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=barbell+curl+strict+form+no+swinging+bicep)

#### 6. Hammer Curl (Dumbbell)
**What it is:** Bicep curl with thumbs-up neutral grip.
**Why:** Builds brachialis — pushes bicep up from below.
**How:** Palms facing each other throughout. Curl up, squeeze, lower slowly.
**Mistake:** Rotating wrist to palm-up during curl.
**Start weight:** 10–12 kg per hand.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=hammer+curl+neutral+grip+brachialis+forearm+form)

**Friday variations:**
- Conventional Deadlift [Watch](https://www.youtube.com/results?search_query=conventional+deadlift+form+beginners+alan+thrall)
- Pull-Ups or Assisted [Watch](https://www.youtube.com/results?search_query=how+to+do+pull+ups+beginners+assisted+lat)
- Single-Arm Dumbbell Row [Watch](https://www.youtube.com/results?search_query=single+arm+dumbbell+row+proper+form+back)

---

### LEGS DAY — Wednesday & Saturday (75 min)

#### 1. Barbell Back Squat
**What it is:** Bar on upper back, lower body by bending hips and knees, stand back up.
**Why:** King of all exercises. Trains quads, hamstrings, glutes, core simultaneously.
**How:** Bar on upper traps, not neck. Feet shoulder-width, toes out. Push hips back and bend knees. Lower until thighs parallel. Drive through heels to stand.
**Mistake:** Knees caving inward — push knees out always.
**Start weight:** Empty bar (20 kg).
**YouTube:** [Watch](https://www.youtube.com/results?search_query=barbell+back+squat+form+beginners+depth+knees)

#### 2. Romanian Deadlift
**What it is:** Lower barbell along legs by hinging at hips, stand back up.
**Why:** Targets hamstrings and glutes.
**How:** Slight knee bend stays fixed. Push hips back, lower bar along legs. Lower until hamstring stretch. Drive hips forward to stand.
**Mistake:** Bending knees too much — movement is all hip hinge.
**Start weight:** 40 kg.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=romanian+deadlift+hamstrings+hip+hinge+form+beginners)

#### 3. Leg Press (Machine)
**What it is:** Push weighted platform away with legs.
**Why:** Heavy quad volume without squat balance demands.
**How:** Feet shoulder-width on platform. Lower until 90 degrees. Push through entire foot. No knee lockout at top.
**Mistake:** Lower back peeling off seat — stop where back stays flat.
**Start weight:** 40–60 kg.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=leg+press+machine+proper+form+foot+placement+beginners)

#### 4. Leg Curl (Machine)
**What it is:** Curl pad toward glutes by bending knees.
**Why:** Only way to isolate hamstrings without loading lower back.
**How:** Face-down. Curl pad to glutes. Squeeze at top. Lower 3 seconds.
**Mistake:** Hips rising off pad — weight too heavy.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=lying+leg+curl+machine+hamstrings+proper+form)

#### 5. Walking Lunges
**What it is:** Step forward, lower back knee, step through and repeat.
**Why:** Works each leg independently. Fixes imbalances. Trains balance and glutes.
**How:** Step 70–80cm forward. Lower back knee toward floor. Front thigh parallel. Push through front heel to stand.
**Mistake:** Front knee past toes — take a longer step.
**Start weight:** Bodyweight first 2 weeks.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=walking+lunges+proper+form+knee+tracking+beginners)

#### 6. Standing Calf Raises
**What it is:** Push onto toes, lower heels below surface level.
**Why:** Builds gastrocnemius — the visible calf muscle.
**How:** Heels hanging off step. Push onto toes fully. Lower heels as far below step as possible. Pause at top and bottom.
**Mistake:** Partial range — full stretch is required for growth.
**YouTube:** [Watch](https://www.youtube.com/results?search_query=standing+calf+raises+full+range+of+motion+squeeze+stretch)

**Saturday variations:**
- Bulgarian Split Squat [Watch](https://www.youtube.com/results?search_query=bulgarian+split+squat+proper+form+beginners)
- Sumo Deadlift [Watch](https://www.youtube.com/results?search_query=sumo+deadlift+form+wide+stance+inner+thigh+glutes)
- Leg Extension [Watch](https://www.youtube.com/results?search_query=leg+extension+machine+proper+form+quads+beginners)
- Seated Calf Raise [Watch](https://www.youtube.com/results?search_query=seated+calf+raise+machine+soleus+proper+form)

---

## 11. Food Alternatives

### When out of beef (Monday, Friday):
| Alternative | How to use | Notes |
|---|---|---|
| Mutton | Same quantity | Same creatine profile. Best substitute. Common in Mauritius. |
| Chicken thigh | 1.3× quantity | Less creatine but calorie-dense. |
| Eggs (extra) | 5–6 eggs = 100g beef | Emergency only. |

### When out of chicken breast (Tuesday, Thursday, Saturday):
| Alternative | How to use | Notes |
|---|---|---|
| Chicken thigh | Same quantity | More fat, slightly less protein. Still good. |
| Mutton | Same quantity | More creatine than chicken. Strong alternative. |
| Eggs + tuna | 3 eggs + 1 can tuna | Comparable protein combined. |

### When out of tuna (Wednesday, Friday):
| Alternative | How to use | Notes |
|---|---|---|
| Fish fillet | 200g = 2 cans tuna | Keeps omega-3 benefit. |
| Mackerel (canned) | 2 cans = 2 cans tuna | Higher omega-3 than tuna. Available in Mauritius. |

### Carbohydrate Substitutes
| Original | Alternative |
|---|---|
| White rice | Regular potato |
| Sweet potato | Pumpkin |
| Oats | Corn flakes (emergency) |
| Pasta | Extra rice (Thursday only) |

---

## 12. Weekly Meal Plan

### Food substitution: ❌ Sardines → ✅ 2 cans tuna + 1 glass milk

---

### MONDAY — Push Day (Protein: Beef or Mutton)

**Morning session:**
| Time | Meal | Items |
|---|---|---|
| 5:45 AM | Pre-workout | 2 bananas + black coffee |
| 6:00 AM | **WORKOUT** | Push · 65 min |
| 7:30 AM | Post-workout | 3 scrambled eggs + 1.5 cups rice + 100g ground beef + spinach |
| 12:30 PM | Lunch | 200g ground beef + 1 cup rice + broccoli + 1 tbsp olive oil |
| 4:00 PM | Snack | 150g Greek yogurt + 1 banana + 30g peanut butter |
| 7:00 PM | Dinner | 150g beef steak or mutton chops + 200g sweet potato + mixed salad |
| 10:00 PM | **SLEEP** | 8 hours |

**Evening session:**
| Time | Meal | Items |
|---|---|---|
| 7:00 AM | Breakfast | 3 eggs + 2 slices whole wheat toast + 1 glass milk |
| 12:30 PM | Lunch | 200g ground beef or mutton mince + 1.5 cups rice + spinach + olive oil |
| 4:00 PM | Pre-workout | 2 bananas + black coffee |
| 6:00 PM | **WORKOUT** | Push · 65 min |
| 7:30 PM | Post-workout dinner | 200g beef mince + 1.5 cups rice + broccoli + olive oil |
| 9:00 PM | Snack | 150g Greek yogurt + oats + banana |
| 10:30 PM | **SLEEP** | 8 hours |

**Why beef/mutton:** Highest creatine (5g/kg). Fuels explosive pressing.

---

### TUESDAY — Pull Day (Protein: Chicken)

**Morning session:**
| Time | Meal | Items |
|---|---|---|
| 5:45 AM | Pre-workout | 1 banana + 20g almonds |
| 6:00 AM | **WORKOUT** | Pull · 65 min |
| 7:30 AM | Post-workout | 200g chicken breast + 1.5 cups rice + 2 boiled eggs + spinach |
| 12:30 PM | Lunch | 250g chicken thigh + 1 cup rice + mixed salad + olive oil |
| 4:00 PM | Snack | 200g Greek yogurt + 1 banana + 3 tbsp oats |
| 7:00 PM | Dinner | 200g chicken breast + 200g sweet potato + broccoli |
| 10:00 PM | **SLEEP** | 8 hours |

**Evening session:**
| Time | Meal | Items |
|---|---|---|
| 7:00 AM | Breakfast | 60g oats + milk + 1 banana + 2 boiled eggs |
| 12:30 PM | Lunch | 250g chicken breast + 1.5 cups rice + mixed salad + olive oil |
| 4:00 PM | Pre-workout | 1 banana + 30g peanut butter + black coffee |
| 6:00 PM | **WORKOUT** | Pull · 65 min |
| 7:30 PM | Post-workout dinner | 250g chicken breast + 2 cups rice + broccoli + olive oil |
| 9:00 PM | Snack | 1 glass milk + 3 tbsp oats + peanut butter |
| 10:30 PM | **SLEEP** | 8 hours |

---

### WEDNESDAY — Legs Day (Protein: Tuna + Fish)

**Morning session:**
| Time | Meal | Items |
|---|---|---|
| 5:45 AM | Pre-workout | 2 bananas + 2 tbsp peanut butter |
| 6:00 AM | **WORKOUT** | Legs · 75 min |
| 7:30 AM | Post-workout | 2 cans tuna + 2 cups rice + 2 eggs + spinach + olive oil |
| 12:30 PM | Lunch | 2 cans tuna + 250g sweet potato + salad + olive oil |
| 4:00 PM | Snack | 200g Greek yogurt + 1 banana + 3 tbsp oats |
| 7:00 PM | Dinner | 200g fish fillet + 1.5 cups rice + broccoli |
| 10:00 PM | **SLEEP** | 8 hours |

**Evening session:**
| Time | Meal | Items |
|---|---|---|
| 7:00 AM | Breakfast | 3 eggs + 60g oats + milk + 1 banana |
| 12:30 PM | Lunch | 2 cans tuna + 250g sweet potato + salad + olive oil |
| 4:00 PM | Pre-workout | 2 bananas + black coffee |
| 6:00 PM | **WORKOUT** | Legs · 75 min |
| 7:30 PM | Post-workout dinner | 200g fish fillet + 2 cups rice + broccoli + olive oil |
| 9:00 PM | Snack | 1 glass milk + peanut butter + 1 banana |
| 10:30 PM | **SLEEP** | 8 hours |

---

### THURSDAY — Push Day Heavy (Protein: Eggs + Chicken + Pasta)

**Morning session:**
| Time | Meal | Items |
|---|---|---|
| 5:45 AM | Pre-workout | 2 bananas + black coffee |
| 6:00 AM | **WORKOUT** | Push heavy · 65 min |
| 7:30 AM | Post-workout | 3 eggs + 200g chicken breast + 1.5 cups rice + spinach |
| 12:30 PM | Lunch | 200g chicken breast + 80g dry pasta + tomato + olive oil |
| 4:00 PM | Snack | 3 boiled eggs + 1 banana + 20g almonds |
| 7:00 PM | Dinner | 200g chicken breast + 80g dry pasta + broccoli |
| 10:00 PM | **SLEEP** | 8 hours |

**Evening session:**
| Time | Meal | Items |
|---|---|---|
| 7:00 AM | Breakfast | 3-egg omelette + 2 slices toast + 1 glass milk |
| 12:30 PM | Lunch | 200g chicken + 80g dry pasta + tomato sauce + olive oil |
| 4:00 PM | Pre-workout | 2 bananas + black coffee |
| 6:00 PM | **WORKOUT** | Push heavy · 65 min |
| 7:30 PM | Post-workout dinner | 3 eggs + 200g chicken + 80g dry pasta + broccoli |
| 9:00 PM | Snack | 200g Greek yogurt + banana + oats |
| 10:30 PM | **SLEEP** | 8 hours |

---

### FRIDAY — Pull Day Deadlift (Protein: Beef or Mutton + Tuna)

**Morning session:**
| Time | Meal | Items |
|---|---|---|
| 5:45 AM | Pre-workout | 2 bananas + black coffee |
| 6:00 AM | **WORKOUT** | Pull deadlift · 75 min |
| 7:30 AM | Post-workout | 2 cans tuna + 150g ground beef + 2 cups rice + spinach |
| 12:30 PM | Lunch | 200g beef steak or mutton chops + 1 cup rice + 150g sweet potato + salad |
| 4:00 PM | Snack | 2 cans tuna on 2 slices toast + 1 glass milk + Greek yogurt |
| 7:00 PM | Dinner | 200g ground beef or mutton mince + 80g dry pasta + broccoli + olive oil |
| 10:00 PM | **SLEEP** | 8 hours |

**Evening session:**
| Time | Meal | Items |
|---|---|---|
| 7:00 AM | Breakfast | 3 eggs + 2 slices toast + 1 glass milk + 1 banana |
| 12:30 PM | Lunch | 200g beef steak or mutton + 1.5 cups rice + salad + olive oil |
| 4:00 PM | Pre-workout | 2 cans tuna + banana + black coffee |
| 6:00 PM | **WORKOUT** | Pull deadlift · 75 min |
| 7:30 PM | Post-workout dinner | 200g ground beef or mutton + 2 cups rice + broccoli + olive oil |
| 9:00 PM | Snack | 1 glass milk + 2 cans tuna + Greek yogurt |
| 10:30 PM | **SLEEP** | 8 hours |

---

### SATURDAY — Legs Day Volume (Protein: Chicken + Eggs)

**Morning session:**
| Time | Meal | Items |
|---|---|---|
| 5:45 AM | Pre-workout | 60g oats + milk + 1 banana |
| 6:00 AM | **WORKOUT** | Legs volume · 75 min |
| 7:30 AM | Post-workout | 3 eggs + 200g chicken breast + 2 cups rice + spinach |
| 12:30 PM | Lunch | 250g chicken thigh + 250g sweet potato + broccoli + olive oil |
| 4:00 PM | Snack | 3 boiled eggs + 1 banana + 200g Greek yogurt |
| 7:00 PM | Dinner | 200g chicken breast + 1.5 cups rice + mixed vegetables + olive oil |
| 10:00 PM | **SLEEP** | 8 hours |

**Evening session:**
| Time | Meal | Items |
|---|---|---|
| 7:00 AM | Breakfast | 60g oats + milk + 2 eggs + 1 banana |
| 12:30 PM | Lunch | 250g chicken breast + 250g sweet potato + broccoli + olive oil |
| 4:00 PM | Pre-workout | 2 bananas + 30g oats + black coffee |
| 6:00 PM | **WORKOUT** | Legs volume · 75 min |
| 7:30 PM | Post-workout dinner | 3 eggs + 200g chicken + 2 cups rice + broccoli |
| 9:00 PM | Snack | 1 glass milk + peanut butter + banana |
| 10:30 PM | **SLEEP** | 8 hours |

---

## 13. Food WHY Reference

| Food | Why it's here | When |
|---|---|---|
| Beef / Mutton | Highest creatine (5g/kg). Fuels explosive pressing. | Mon, Fri |
| Chicken breast | 31g protein/100g. Highest protein-to-calorie ratio. | Tue, Thu, Sat |
| Tuna | Omega-3 for joint protection on leg days. | Wed, Fri |
| Fish fillet | Additional omega-3. Anti-inflammatory for squat recovery. | Wed |
| Eggs | BV 100 — perfect protein. Choline for muscle nerve signals. | Every day |
| Greek yogurt | Casein protein — slow release, feeds muscle for hours. | Every day |
| Milk | Complete protein + calcium for bone density under load. | Every day |
| White rice | Fast carb post-workout — drives nutrients into muscle. | Every day |
| Oats | Beta-glucan fiber — slow glucose for sustained energy. | Sat + mornings |
| Sweet potato | Highest potassium. Prevents cramping. | Wed, Thu, Fri, Sat |
| Pasta | Lower GI. Sustained energy on depleted glycogen. | Thu, Fri |
| Banana | Fast glucose + potassium. Pre-workout energy. | Every day |
| Peanut butter | 90 kcal/tbsp. Dense sustained fuel. | Every day |
| Olive oil | Anti-inflammatory. Calorie-dense healthy fat. | Every day |
| Broccoli | Sulforaphane reduces muscle damage. Vitamin C for joints. | Every day |
| Spinach | Iron for oxygen delivery. Nitrates improve performance 3–5%. | Every day |
| Almonds | Vitamin E antioxidant. Magnesium for muscle contraction. | Tue, Thu |
| Coffee | Caffeine raises strength 3–7%. No sugar. Pre-workout only. | Pre-workout |

---

## 14. Weight Tracker Specification

### Rules
- Weigh-in once per week only — every Sunday morning before eating.
- First entry: June 11, 2026 — 58.0 kg as baseline.
- Once confirmed — saved permanently. Cannot be edited.

### Display
- Current weight shown large in amber
- Starting weight: 58.0 kg
- Total change: shown in green (gaining = good)
- Simple line graph of all weekly entries from start to now
- Each point tappable — shows date and weight

### Placement
- Log tab, above the calendar.

---

## 15. Inventory System Specification

### Critical Rule
All items start at 0. User fills manually after buying food. App never pre-loads values.

### Status Logic
- 🟢 Green — enough for 2+ days
- 🟡 Yellow — enough for today only
- 🔴 Red — not enough for today

### Ingredient List (all start at 0)

| Ingredient | Unit |
|---|---|
| banana | pieces |
| eggs | pieces |
| chicken_breast | grams |
| chicken_thigh | grams |
| ground_beef | grams |
| beef_steak | grams |
| mutton | grams |
| tuna_cans | cans |
| fish_fillet | grams |
| rice_dry | grams |
| oats | grams |
| sweet_potato | grams |
| pasta_dry | grams |
| bread_slices | slices |
| greek_yogurt | grams |
| milk | ml |
| peanut_butter | grams |
| almonds | grams |
| olive_oil | ml |
| broccoli | grams |
| spinach | grams |
| mixed_salad_veg | grams |

---

## 16. Calendar System Specification

### Daily Checklist (4 items)
| Check | Label |
|---|---|
| ✅ | Did the workout |
| ✅ | Hit protein target (140g) |
| ✅ | Slept 8 hours |
| ✅ | Drank 3.5L water |

### Color Rules
| Score | Color | Meaning |
|---|---|---|
| 4 / 4 | 🟢 Green | Perfect day |
| 2–3 / 4 | 🟠 Orange | Partial day |
| 0–1 / 4 | 🔴 Red | Day missed |
| Future | ⬜ Empty | Not yet |
| Today | 🔵 Blue ring | Current day |
| Sunday | Grey | Rest — never breaks streak |

### Calendar Tap — Past Day Review (NEW)
- Tapping any past day in the calendar opens a review panel.
- Shows: which session was chosen, which of the 4 checks were done, the free-text note written, weight if logged that day.
- Read-only — cannot edit past entries.

### Streak Rules
- Counts consecutive days where at least 2/4 checks completed.
- Red day breaks streak and resets to 0.
- Sunday never breaks streak.

---

## 17. Progress Timeline & Target Dates

| Phase | Timeline | What changes | Target date |
|---|---|---|---|
| Phase 1 — Noticeably Different | 3 months | Face less gaunt. Shirts fit differently. +3–5 kg lean mass. | September 11, 2026 |
| Phase 2 — Clearly Training | 6 months | Biceps visible when flexed. Chest definition. Thighs larger. +5–8 kg. | December 11, 2026 |
| Phase 3 — Strong Foundation | 12 months | Clear definition everywhere. People ask if you train. +8–12 kg. | June 11, 2027 |
| Ultimate Goal | 18–24 months | Full physique transformation. The version you are training toward. | December 2027 |

### Phase Progress Bar (NEW)
- Home tab shows a visual progress bar between Phase start and Phase 1 target.
- Fills with amber color as days pass.
- Shows percentage complete toward next phase.
- Below it: "X days to Phase 1 · September 11, 2026"

### Home Screen Shows Permanently
- Goal card (see Section 7)
- "Day X of your journey"
- "Training days done: X"
- "Current streak: X"
- Phase progress bar
- "Days to Phase 1: X"

---

## 18. App Features — Complete List

### Core — All Working

| Feature | Status | Description |
|---|---|---|
| Session lock popup | ✅ | Full-screen modal on first open each day |
| Auto-detect today | ✅ | Loads correct day plan automatically |
| Warm-up section | ✅ | 6-step protocol with YouTube links |
| Exercise guidance | ✅ | Tap to expand full guidance + YouTube |
| Set tracker | ✅ | Numbered buttons, tap = green, resets daily |
| Rest timer | NEW | Auto-starts after each set tap. 2 min compound, 90s isolation. Vibrates when done. |
| Exercise completion | ✅ | Mark Complete button, permanently green |
| Meal timeline | ✅ | Exact meals and times for chosen session |
| Meal confirmation | ✅ | Mark as Done, permanent, cannot undo |
| Food WHY popup | NEW | Tap any food item in Meals tab — popup explains why this food is in today's plan |
| Distraction-free workout | NEW | Bottom nav hides in Workout tab. Full screen for training. |
| Goal card | NEW | Permanent card on Home showing physical goal |
| Phase progress bar | NEW | Visual fill bar showing progress to Phase 1 |
| Streak counter | ✅ | Prominent on home screen |
| Daily log | ✅ | 4 checkboxes + water tracker + free-text note |
| Calendar | ✅ | Monthly colored blocks |
| Calendar tap review | NEW | Tap past day to see what was logged |
| Weight tracker | ✅ | Weekly entry, line graph from 58 kg |
| Progress counter | ✅ | Day X + Phase countdown |
| Inventory tracker | ✅ | Starts at 0, add stock, status colors, shopping list |
| Quote + Scripture | NEW | Combined pool rotating daily |
| Sunday reminder | ✅ | Backup banner every Sunday |

### Settings Panel

| Setting | Description |
|---|---|
| Add custom quote | Merges with built-in pool |
| Master food editor | Edit any day's meal, inventory auto-updates |
| Start date override | For accurate streak if started before installing |
| Export data | Downloads full localStorage as JSON |
| Import data | Restore JSON on new device |

---

## 19. App Navigation

```
[ 🏠 Home ] [ 💪 Workout ] [ 🍽 Meals ] [ 📦 Inventory ] [ 📋 Log ]
```

All tabs: minimum 90px bottom padding.
Workout tab: bottom nav hidden for distraction-free training.

---

## 20. Technical Specification

| Property | Value |
|---|---|
| App name | MH370 |
| GitHub username | Vamsi232104 |
| Repository | mh370 |
| URL | https://vamsi232104.github.io/mh370 |
| Working folder | C:\Users\vamsi\mh370 |
| File structure | Single index.html + manifest.json + sw.js |
| Framework | Vanilla JS only |
| Storage | localStorage key: mh370_v1 |
| Start date | 2026-06-11 |
| Offline | Service worker |

---

## 21. Daily Quote + Christian Scripture Bank

### 30 Built-in Gym Quotes

01. "The plane is still out there. So are you."
02. "58 kg is where you start. Not where you stay."
03. "Discipline is remembering what you want."
04. "You showed up. That already makes you different."
05. "Pain is just data. Process it and move on."
06. "The body you want is built in the days you don't feel like it."
07. "Every rep is a message to your future self."
08. "You don't need motivation. You need a locked-in plan."
09. "The weak version of you skips. The MH370 version doesn't."
10. "Nobody finds the plane by standing still."
11. "Rest Sunday. Attack Monday. Repeat until different."
12. "Trust the program. The program is right."
13. "140g of protein. 8 hours of sleep. No exceptions."
14. "You chose this. Honor it."
15. "Muscle is built by showing up when it's inconvenient."
16. "Distraction cost you 30 days. The gym gives them back."
17. "Your body is keeping score. Make sure it's a good one."
18. "Hard days are the ones that count."
19. "Same plan next week. Heavier weights."
20. "The plan doesn't care how you feel. Neither does the barbell."
21. "One year from today, this will all be obvious."
22. "The food is fuel. The sleep is construction. The gym is the blueprint."
23. "You are not behind. You are at the start."
24. "Commitment is deciding in advance so you don't have to decide again."
25. "What you do at 6 AM defines the rest of the day."
26. "This is not a phase. This is the direction."
27. "Two years is nothing. Twelve months is nothing. Start now."
28. "Skipping is a negotiation you lose every time."
29. "MH370 — still flying."
30. "The version of you that stops was never the real one."

### 15 Christian Scriptures

S1. "I can do all things through Christ who strengthens me." — Philippians 4:13
S2. "No, I strike a blow to my body and make it my slave." — 1 Corinthians 9:27
S3. "For physical training is of some value, but godliness has value for all things." — 1 Timothy 4:8
S4. "For God gave us a spirit not of fear but of power and love and self-control." — 2 Timothy 1:7
S5. "Those who hope in the Lord will renew their strength. They will soar on wings like eagles; they will run and not grow weary." — Isaiah 40:31
S6. "Do you not know that your bodies are temples of the Holy Spirit? Therefore honor God with your bodies." — 1 Corinthians 6:19–20
S7. "Be strong and courageous. Do not be afraid; do not be discouraged, for the Lord your God will be with you wherever you go." — Joshua 1:9
S8. "The soul of the sluggard craves and gets nothing, while the soul of the diligent is richly supplied." — Proverbs 13:4
S9. "Whatever you do, work at it with all your heart, as working for the Lord, not for human masters." — Colossians 3:23
S10. "Let us not become weary in doing good, for at the proper time we will reap a harvest if we do not give up." — Galatians 6:9
S11. "Commit your work to the Lord, and your plans will be established." — Proverbs 16:3
S12. "For we are God's handiwork, created in Christ Jesus to do good works." — Ephesians 2:10
S13. "Run in such a way as to get the prize. Everyone who competes trains with strict discipline." — 1 Corinthians 9:24–25
S14. "The plans of the diligent lead to profit as surely as haste leads to poverty." — Proverbs 21:5
S15. "Be watchful, stand firm in the faith, act like men, be strong." — 1 Corinthians 16:13

*All 45 entries rotate together daily. Custom quotes added in Settings merge into this pool.*

---

## 22. Design Direction

| Property | Decision |
|---|---|
| Theme | Dark — near-black background (#0a0a0a) |
| Accent | Amber #f59e0b — energy, heat, focus |
| Typography | Strong sans-serif headings. Monospace for times and data. |
| Style | Precision instrument. Every element earns its place. |
| Bottom padding | Minimum 90px on all tabs |
| Workout screen | Distraction-free — nav bar hidden |
| Calendar | Compact colored blocks — information only |

---

*Document version: 4.0*
*Updated: 2026-06-10*
*Status: Final — ready for Claude Code build*
