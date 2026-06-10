# MH370 — Personal Fitness App
## Master Plan Document · v3.0

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
### These are non-negotiable rules for how the app behaves.

### Rule 1 — Morning/Evening Session Lock
- When the user opens the app for the first time each day, a modal popup appears.
- Popup says: "Good morning / Good evening — [Day name]. Choose your session for today."
- Two buttons: "Morning Session" and "Evening Session"
- Once the user taps one, a confirmation prompt appears: "Lock in Morning session for today? This cannot be changed."
- User taps Confirm. The choice is saved to localStorage for that date.
- The popup NEVER appears again for that day. The chosen session is locked until midnight.
- At midnight, the lock resets and tomorrow's popup is ready.
- The session toggle shown on the Home tab becomes a display-only indicator, not a button, once locked.

### Rule 2 — Meal Confirmation (Strict, Permanent)
- Every meal in the Meals tab has a "Mark as Done" button.
- When tapped, a confirmation popup appears: "Mark [Meal name] as done? This cannot be undone."
- User taps Confirm. The meal card turns green with a checkmark. Permanently.
- There is no undo. There is no uncheck. Done means done.
- Confirmed meals are saved to localStorage immediately under that day's log.
- This applies to all meals: pre-workout, post-workout, breakfast, lunch, snack, dinner, evening snack.

### Rule 3 — Exercise Completion (Strict, Permanent)
- Every exercise in the Workout tab has set tracker buttons (Set 1, Set 2, Set 3, Set 4).
- Set tracker buttons turn green when tapped — these CAN be toggled (for tracking during the session).
- At the bottom of each exercise card there is a "Mark Exercise Complete" button.
- When tapped: "Confirm exercise complete? This cannot be undone." → Confirm → entire exercise card turns green, locked.
- Once exercise is marked complete, the set tracker buttons are also locked.
- Set tracker resets daily at midnight. Exercise completion resets daily at midnight.

### Rule 4 — Inventory Starts at Zero
- The inventory tab NEVER loads default or fake stock quantities.
- Every item starts at 0 when the app is first installed.
- The user manually adds stock by tapping "+ Add" next to each item after buying food.
- This is the only source of truth. The app never assumes the user has anything.

### Rule 5 — Bottom Padding
- All scrollable tab content must have a minimum bottom padding of 90px.
- This ensures the last item is never hidden behind the bottom navigation bar.
- This applies to every single tab: Home, Workout, Meals, Inventory, Log.

### Rule 6 — Daily Quote Placement
- Today's motivational quote is shown at the BOTTOM of the Home tab.
- Quote rotates based on journey day number: Day 1 = Quote 1, Day 2 = Quote 2, etc.
- Cycles through all 30 built-in quotes plus any custom quotes added by the user.
- The quote is displayed in a distinct card at the bottom, below all other home content.

### Rule 7 — Data Backup Reminder
- Once per week (every Sunday), the app shows a small banner on the Home tab:
  "Back up your data today. Settings → Export JSON."
- This reminds the user to export their localStorage data as a safety backup.

---

## 7. Fitness Terminology — What Everything Means

### Reps (Repetitions)
One complete movement of an exercise — up and back down.
For bench press: push bar up + lower bar down = 1 rep.
"8–10 reps" means you do the movement 8 to 10 times in a row without stopping.

### Sets
A group of reps done in a row, followed by rest.
"4 sets" means you do the exercise 4 separate times with rest in between.

### What "4 × 8–10" means
Do 8–10 reps → rest 2–3 minutes → do 8–10 reps again → rest → again → rest → again.
That is 4 sets. You have now done 32–40 total reps for that exercise.

### Rest Between Sets
- Compound exercises (bench press, squat, deadlift, row): 2–3 minutes
- Isolation exercises (lateral raises, curls, pushdowns): 60–90 seconds

### Progressive Overload
Every week, try to do either more weight or more reps than last week. Even 1 extra rep counts.
Your body only grows when it is forced to adapt to something harder than before.

### Compound Exercise
Uses multiple muscle groups and multiple joints at once.
Examples: bench press, squat, deadlift, overhead press, barbell row.
Always done first in the session.

### Isolation Exercise
Targets one specific muscle with one joint moving.
Examples: lateral raises, bicep curls, tricep pushdowns, leg curls.
Done last in the session.

### Warm-Up Set
Before your first working set, do 1 set with 40–50% of your working weight.
This warms the muscle before real load is added.

---

## 8. Warm-Up Protocol — Every Session, Every Day

**Duration: 10 minutes. Do this before touching any weight.**

| Step | Exercise | How To Do It | Time/Reps | YouTube |
|---|---|---|---|---|
| 1 | Light cardio | Walk or jog on the spot. Treadmill at 6 km/h. Get heart rate slightly up. | 3 minutes | [Watch](https://www.youtube.com/results?search_query=warm+up+cardio+before+gym+beginners) |
| 2 | Arm circles | Arms out to side. Large circles forward 10×, backward 10×. | 10 each direction | [Watch](https://www.youtube.com/results?search_query=arm+circles+warm+up+exercise+form) |
| 3 | Hip circles | Hands on hips. Rotate hips in large circle. 10 clockwise, 10 counter-clockwise. | 10 each direction | [Watch](https://www.youtube.com/results?search_query=hip+circles+warm+up+mobility) |
| 4 | Bodyweight squats | Feet shoulder-width. Lower slowly until thighs parallel to floor. Stand back up. No weight. | 10 slow reps | [Watch](https://www.youtube.com/results?search_query=bodyweight+squat+form+beginners+depth) |
| 5 | Shoulder pass-throughs | Hold towel wide with both hands. Swing overhead and behind back. Return same way. | 10 reps | [Watch](https://www.youtube.com/results?search_query=shoulder+pass+through+warm+up+towel) |
| 6 | Warm-up set | First exercise of session at 40–50% working weight. 10–15 slow reps. Not for strength — for warmth and practice. | 1 set × 12 reps | — |

**Leg day extra (after Step 5):**
- 5 leg swings per leg, forward and back
- 5 leg swings per leg, side to side

---

## 9. Exercise Database — Full Guidance

Each exercise: what it is → why it's in your plan → how to do it → most common mistake → starting weight → YouTube.

---

### PUSH DAY — Monday & Thursday (65 min)
**Builds:** Chest thickness. Shoulder roundness. Tricep definition.

#### 1. Barbell Bench Press
**What it is:** Lie on flat bench, push weighted barbell up from chest.
**Why:** The single best exercise for chest mass. Foundation of push day.
**How to do it:**
1. Lie flat. Eyes directly under the bar.
2. Grip slightly wider than shoulders. Thumbs wrapped around bar.
3. Feet flat on floor. Shoulder blades squeezed together into bench.
4. Unrack bar, hold above chest with arms straight.
5. Lower slowly (2–3 seconds) until bar touches middle of chest.
6. Press up explosively until arms straight. Breathe out.
**Mistake:** Elbows flaring out at 90 degrees — destroys shoulders. Keep at 45–75 degrees.
**Starting weight:** Just the bar (20 kg). First 2 weeks — form only.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=barbell+bench+press+proper+form+beginners+chest)

#### 2. Overhead Press (Barbell)
**What it is:** Stand and press barbell from shoulder height straight up overhead.
**Why:** Builds front and side shoulders — the "cap" that makes shoulders look round and wide.
**How to do it:**
1. Feet shoulder-width. Bar at shoulder height, hands slightly wider than shoulders.
2. Bar rests on upper chest/front shoulders before each rep.
3. Look forward. Brace core hard.
4. Press bar straight up. As it clears head, push head slightly forward.
5. Lower back to shoulders slowly. Repeat.
**Mistake:** Leaning back excessively. Keep body vertical. If leaning, weight is too heavy.
**Starting weight:** 20 kg (empty bar).
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=barbell+overhead+press+standing+form+beginners)

#### 3. Incline Dumbbell Press
**What it is:** Bench press at 30–45 degree incline using dumbbells.
**Why:** Targets upper chest — gives the "full chest" look from front.
**How to do it:**
1. Set bench to 30–45 degrees. Sit with dumbbell on each knee.
2. Kick dumbbells up as you lie back.
3. Hold at chest level, palms forward.
4. Press both up until arms extended above upper chest.
5. Lower slowly. Control the movement.
**Mistake:** Bench too steep (above 45 degrees) — shifts work to shoulders.
**Starting weight:** 8–10 kg per hand.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=incline+dumbbell+press+proper+form+upper+chest)

#### 4. Lateral Raises (Dumbbell)
**What it is:** Raise dumbbells out to the side like wings.
**Why:** Isolates lateral shoulder head — creates shoulder width.
**How to do it:**
1. Stand straight, dumbbells at sides.
2. Slight bend in elbows throughout.
3. Raise both arms to side until level with shoulders. T-shape.
4. Lower slowly (3 seconds). Do not let gravity do it.
5. Do not shrug shoulders up. Keep them pressed down.
**Mistake:** Too heavy, swinging body to help. Use light weight, pure arm raising.
**Starting weight:** 5–6 kg.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=dumbbell+lateral+raises+proper+form+no+momentum)

#### 5. Tricep Pushdown (Cable)
**What it is:** Push cable attachment downward by straightening elbows.
**Why:** Triceps = 2/3 of upper arm size. Most important arm exercise.
**How to do it:**
1. Attach rope to top pulley. Stand facing machine.
2. Hold with both hands, elbows at sides.
3. Elbows pinned to sides — do not move them.
4. Push down until arms fully extended. Squeeze tricep.
5. Let cable pull hands back slowly. Control it.
**Mistake:** Elbows flaring out. If elbows move, tricep is not working.
**Starting weight:** Moderate — where you feel tricep working without elbows moving.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=cable+tricep+pushdown+rope+proper+form+elbows)

#### 6. Overhead Tricep Extension (Cable)
**What it is:** Hold cable behind head, extend arms upward.
**Why:** Targets long head of tricep — gives arm thickness from behind.
**How to do it:**
1. Attach rope to low pulley. Face away from machine.
2. Hold rope behind head. Elbows pointing to ceiling.
3. Upper arms stay vertical and still throughout.
4. Extend arms upward until fully straight. Squeeze.
5. Lower rope slowly back behind head. Feel the stretch.
**Mistake:** Upper arms falling forward. Keep them pointing straight up.
**Starting weight:** Light. Position feels unfamiliar.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=overhead+cable+tricep+extension+long+head+form)

**Thursday variations:**
- Close-Grip Bench Press: Same as bench but hands shoulder-width. More tricep, less chest. [Watch](https://www.youtube.com/results?search_query=close+grip+bench+press+triceps+form+beginners)
- Weighted Tricep Dips: Dip bars, lower by bending elbows behind you. Body upright = tricep focus. [Watch](https://www.youtube.com/results?search_query=tricep+dips+proper+form+bars+beginners)

---

### PULL DAY — Tuesday & Friday (65 min Tuesday / 75 min Friday)
**Builds:** Back width. Back thickness. Bicep peak. V-taper silhouette.

#### 1. Barbell Bent-Over Row
**What it is:** Bend forward holding barbell, row bar up toward stomach.
**Why:** Builds back thickness and lat width. Most effective back exercise.
**How to do it:**
1. Feet shoulder-width. Overhand grip, slightly wider than shoulders.
2. Hinge at hips, torso at ~45 degrees. Back flat — not rounded.
3. Bar hangs straight down.
4. Pull bar up toward lower chest/upper stomach. Lead with elbows.
5. Squeeze shoulder blades at top. Lower slowly.
**Mistake:** Rounding lower back under load — serious injury risk.
**Starting weight:** 40 kg.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=barbell+bent+over+row+proper+form+back+beginners)

#### 2. Lat Pulldown (Wide Grip)
**What it is:** Pull wide bar down from above to chest level at cable machine.
**Why:** Targets lats — creates V-taper (wide back look).
**How to do it:**
1. Sit at machine. Knee pad holds thighs down.
2. Wide overhand grip — beyond shoulder-width.
3. Lean back slightly (15 degrees only).
4. Pull bar to upper chest. Lead with elbows toward hips.
5. Squeeze at bottom. Let bar rise slowly to full stretch.
**Mistake:** Pulling behind the neck — strains cervical spine. Always pull to front.
**Starting weight:** 30–50 kg depending on machine.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=lat+pulldown+wide+grip+proper+form+lats+V+taper)

#### 3. Seated Cable Row
**What it is:** Sit at cable machine, row handle toward stomach.
**Why:** Builds mid-back thickness — the muscle between shoulder blades.
**How to do it:**
1. Sit at row machine. Feet on pad, legs slightly bent.
2. Lean forward to grip handle. Back straight.
3. Sit upright — this is start position.
4. Pull handle to stomach. Elbows behind you. Squeeze shoulder blades.
5. Extend arms forward slowly. Let shoulder blades separate for full stretch.
**Mistake:** Rocking back and forth with lower back momentum.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=seated+cable+row+proper+form+mid+back+beginners)

#### 4. Cable Face Pulls
**What it is:** Pull rope toward face, splitting rope apart at end.
**Why:** Targets rear delts — critical for shoulder health and posture.
**How to do it:**
1. Cable at face height. Rope attachment.
2. Hold rope, thumbs pointing away from you.
3. Pull rope directly toward face. Hands go to either side of head.
4. Elbows at shoulder height, flaring out — not dropping.
5. Return slowly. Keep tension throughout.
**Mistake:** Elbows dropping below shoulder height — loses rear delt focus.
**Starting weight:** 10–15 kg.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=cable+face+pulls+rear+delts+proper+form+elbows+high)

#### 5. Barbell Curl
**What it is:** Curl barbell up toward chest by bending elbows.
**Why:** Primary bicep mass builder. Builds the "peak" when arm is flexed.
**How to do it:**
1. Stand straight. Underhand grip, shoulder-width.
2. Elbows pinned to sides. They do not move.
3. Curl bar up toward chest. Squeeze bicep at top.
4. Lower slowly — 3 full seconds. Do not drop.
5. Fully extend arms at bottom before next rep.
**Mistake:** Swinging back to help. Weight too heavy. Drop weight and use strict form.
**Starting weight:** 30 kg.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=barbell+curl+strict+form+no+swinging+bicep)

#### 6. Hammer Curl (Dumbbell)
**What it is:** Bicep curl with neutral grip (thumbs up, like holding a hammer).
**Why:** Builds brachialis — pushes bicep up from below. Adds forearm thickness.
**How to do it:**
1. Dumbbell in each hand, palms facing each other throughout.
2. Keep elbows at sides.
3. Curl both up together (or alternating). Full contraction.
4. Lower slowly. Neutral grip the entire time.
**Mistake:** Rotating wrist to palm-up position. Keeps palms facing each other always.
**Starting weight:** 10–12 kg per hand.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=hammer+curl+neutral+grip+brachialis+forearm+form)

**Friday variations:**
- Conventional Deadlift: Pick barbell off floor. The most important lift for overall mass. Learn form before loading. [Watch](https://www.youtube.com/results?search_query=conventional+deadlift+form+beginners+alan+thrall)
- Pull-Ups (or Assisted): Hang from bar, pull up until chin above bar. Use assisted machine if needed. [Watch](https://www.youtube.com/results?search_query=how+to+do+pull+ups+beginners+assisted+lat)
- Single-Arm Dumbbell Row: One knee on bench, row dumbbell toward hip with other arm. [Watch](https://www.youtube.com/results?search_query=single+arm+dumbbell+row+proper+form+back)

---

### LEGS DAY — Wednesday & Saturday (75 min)
**Builds:** Thigh size. Glute development. Calf muscle. 50% of total body muscle.

#### 1. Barbell Back Squat
**What it is:** Bar on upper back, lower entire body by bending hips and knees, stand back up.
**Why:** King of all exercises. Trains quads, hamstrings, glutes, core, lower back simultaneously.
**How to do it:**
1. Bar on squat rack at upper chest height. Step under, rest across upper traps. NOT on neck.
2. Step back. Feet shoulder-width or slightly wider, toes out slightly.
3. Take breath, brace core. Push hips back and bend knees simultaneously.
4. Lower until thighs at least parallel to floor. Knees track over toes.
5. Drive through heels to stand. Push floor away. Breathe out on way up.
**Mistake:** Knees caving inward on way up — knee injury. Push knees outward always.
**Starting weight:** Empty bar (20 kg). First week — depth and knee tracking only.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=barbell+back+squat+form+beginners+depth+knees)

#### 2. Romanian Deadlift
**What it is:** Hold barbell, lower along legs by hinging at hips, feeling hamstring stretch, stand back up.
**Why:** Targets hamstrings and glutes. Fixes the quad/hamstring imbalance most beginners have.
**How to do it:**
1. Overhand grip, hip-width. Stand tall.
2. Slight knee bend — stays fixed throughout.
3. Push hips back, lower bar slowly along legs. Bar stays close to body.
4. Lower until strong hamstring stretch — roughly mid-shin level.
5. Drive hips forward to stand. Squeeze glutes at top.
**Mistake:** Bending knees too much, turning it into a regular deadlift. Movement is all hip hinge.
**Starting weight:** 40 kg.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=romanian+deadlift+hamstrings+hip+hinge+form+beginners)

#### 3. Leg Press (Machine)
**What it is:** Sit in machine, push weighted platform away with legs.
**Why:** Heavy leg volume without balance demands of squat. Great for quad mass.
**How to do it:**
1. Back and head against pad. Feet shoulder-width on platform, toes out.
2. Release safety handles.
3. Lower platform slowly until knees at 90 degrees.
4. Push through entire foot to extend. Do not lock knees at top.
**Mistake:** Lower back peeling off seat at bottom. Stop where back stays flat.
**Starting weight:** 40–60 kg.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=leg+press+machine+proper+form+foot+placement+beginners)

#### 4. Leg Curl (Machine)
**What it is:** Lie face-down, curl pad toward glutes by bending knees.
**Why:** Only way to isolate hamstrings without loading lower back.
**How to do it:**
1. Face-down on machine. Ankle pad just above heel.
2. Hold handles under machine.
3. Curl pad up toward glutes. Go as high as possible.
4. Squeeze hamstring at top. Lower slowly — 3 seconds.
**Mistake:** Hips rising off pad — weight too heavy.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=lying+leg+curl+machine+hamstrings+proper+form)

#### 5. Walking Lunges
**What it is:** Step forward into long stride, lower back knee, step through and repeat.
**Why:** Works each leg independently. Fixes strength imbalances. Trains balance and glutes.
**How to do it:**
1. Stand tall, feet together. Bodyweight or dumbbells.
2. Step forward ~70–80 cm.
3. Lower back knee toward floor until front thigh parallel. Front knee over ankle.
4. Push through front heel to stand, bring back foot forward.
5. Repeat opposite leg. Each step = one rep.
**Mistake:** Front knee past toes. Long step keeps shin vertical.
**Starting weight:** Bodyweight first 2 weeks.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=walking+lunges+proper+form+knee+tracking+beginners)

#### 6. Standing Calf Raises
**What it is:** Stand on raised surface, push onto toes, lower heels below surface.
**Why:** Builds gastrocnemius — the visible calf muscle. Only activated with straight knee.
**How to do it:**
1. Stand on step or calf raise machine. Heels hanging off edge.
2. Push onto toes as high as possible. Squeeze at top.
3. Lower heels as far below step as possible. Full stretch.
4. Pause 1 second at bottom. Pause 1 second at top.
**Mistake:** Partial range — only halfway down. Calves need full stretch to grow.
**YouTube:** [Watch tutorial](https://www.youtube.com/results?search_query=standing+calf+raises+full+range+of+motion+squeeze+stretch)

**Saturday variations:**
- Bulgarian Split Squat: Back foot elevated on bench, squat on front leg. [Watch](https://www.youtube.com/results?search_query=bulgarian+split+squat+proper+form+beginners)
- Sumo Deadlift: Wide stance, toes out. More inner thigh and glutes. [Watch](https://www.youtube.com/results?search_query=sumo+deadlift+form+wide+stance+inner+thigh+glutes)
- Leg Extension: Sit in machine, extend legs forward to straight. Pure quads. [Watch](https://www.youtube.com/results?search_query=leg+extension+machine+proper+form+quads+beginners)
- Seated Calf Raise: Targets soleus — deeper calf muscle. [Watch](https://www.youtube.com/results?search_query=seated+calf+raise+machine+soleus+proper+form)

---

## 10. Food Alternatives

### When you are out of beef (Monday, Friday):
| Alternative | How to use | Notes |
|---|---|---|
| Mutton | Same quantity | Same creatine and zinc profile. Common in Mauritius. Best substitute. |
| Chicken thigh | 1.3× the quantity | Less creatine but calorie-dense. Works. |
| Eggs (extra) | 5–6 eggs = 100g beef | Emergency only. |

### When you are out of chicken breast (Tuesday, Thursday, Saturday):
| Alternative | How to use | Notes |
|---|---|---|
| Chicken thigh | Same quantity | More fat, slightly less protein. Still good. |
| Mutton | Same quantity | More creatine than chicken. Strong alternative. |
| Eggs + tuna | 3 eggs + 1 can tuna | Comparable protein quality combined. |

### When you are out of tuna (Wednesday, Friday):
| Alternative | How to use | Notes |
|---|---|---|
| Fish fillet (any) | 200g = 2 cans tuna | Keeps omega-3 benefit. |
| Mackerel (canned) | 2 cans = 2 cans tuna | Higher omega-3 than tuna. Available in Mauritius. |

### Mutton — Profile
- Protein: ~26g per 100g (similar to beef)
- Creatine: Similar to beef — best beef alternative
- Days to use: Monday (Push), Friday (Pull/deadlift)
- How to cook: Curry, mince with spices, grilled chops

### Carbohydrate Substitutes
| Original | Alternative | Notes |
|---|---|---|
| White rice | Regular potato | Similar calories |
| White rice | Bread (2–3 slices) | Emergency only |
| Sweet potato | Pumpkin | Available in Mauritius |
| Oats | Corn flakes | Lower fiber, acceptable pre-workout |
| Pasta | Extra rice | Thursday only if no pasta |

---

## 11. Weekly Meal Plan

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

**Why beef/mutton:** Highest creatine (5g/kg). Fuels explosive pressing on bench and overhead press.

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

## 12. Food WHY Reference

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
| Pasta | Lower GI. Sustained energy on depleted glycogen (Thursday). | Thu, Fri |
| Banana | Fast glucose + potassium. Pre-workout energy. | Every day |
| Peanut butter | 90 kcal/tbsp. Dense sustained fuel. | Every day |
| Olive oil | Anti-inflammatory. Calorie-dense healthy fat. | Every day |
| Broccoli | Sulforaphane reduces muscle damage. Vitamin C for joints. Daily non-negotiable. | Every day |
| Spinach | Iron for oxygen delivery. Nitrates improve performance 3–5%. | Every day |
| Almonds | Vitamin E antioxidant. Magnesium for muscle contraction. | Tue, Thu |
| Coffee | Caffeine raises strength 3–7%. No sugar. Pre-workout only. | Pre-workout |

---

## 13. Weight Tracker Specification

### Purpose
Track bodyweight progress from starting weight of 58 kg toward the goal physique.

### Rules
- Weigh-in once per week only — every Sunday morning, before eating, after waking.
- Daily weighing is NOT used — daily weight fluctuates 1–2 kg from water/food and discourages progress.
- First entry on the day the user starts the app (June 11, 2026) — 58.0 kg as baseline.

### Display
- Current weight shown prominently (large number)
- Starting weight: 58.0 kg
- Total change: +X.X kg (shown in green if gained, since goal is to gain muscle)
- A simple line graph showing all weekly entries from start to now
- Each data point is tappable — shows the date and weight logged

### Input
- One button: "Log this week's weight"
- Number input field (e.g. 58.5)
- Confirm button
- Once confirmed — saved permanently to localStorage. Cannot be edited.

### Placement
- Weight tracker lives in the Log tab, above the calendar.

### localStorage structure
```json
"weight_log": [
  { "date": "2026-06-11", "kg": 58.0 },
  { "date": "2026-06-18", "kg": 58.4 },
  { "date": "2026-06-25", "kg": 58.9 }
]
```

---

## 14. Inventory System Specification

### Critical Rule
**Inventory starts at zero for every item.** The app never pre-loads any stock values. The user fills it in manually after buying food.

### Status Logic
- 🟢 Green — enough stock for 2 or more days
- 🟡 Yellow — enough for today but not tomorrow
- 🔴 Red — not enough for today
- Sunday shopping view shows: weekly need vs current stock vs buy quantity

### User Actions
- "+ Add" button per item — tap, enter quantity bought, stock increases
- "Mark day complete" — system subtracts today's session consumption automatically
- Sunday shopping list — shows full week requirement and exact buy quantity per item

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

## 15. Calendar System Specification

### Daily Checklist (4 items — determines color)
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
| Sunday | ⬜ Grey | Rest — no check required, never breaks streak |

### Streak Rules
- Counts consecutive days where at least 2/4 checks completed
- A red day breaks the streak and resets to 0
- Sunday never breaks the streak

---

## 16. Progress Timeline & Target Dates

| Phase | Timeline | What changes | Target date |
|---|---|---|---|
| Phase 1 — Noticeably Different | 3 months | Face less gaunt. Shirts fit differently. First people notice. +3–5 kg lean mass. | September 11, 2026 |
| Phase 2 — Clearly Training | 6 months | Biceps visible when flexed. Chest definition starting. Thighs noticeably larger. +5–8 kg. | December 11, 2026 |
| Phase 3 — Strong Foundation | 12 months | Clear muscle definition everywhere. People ask if you train. +8–12 kg lean mass. | June 11, 2027 |
| Ultimate Goal | 18–24 months | Full physique transformation. The version you are training toward. | December 2027 |

### Home Screen Shows Permanently
- "Day X of your journey" — total days since June 11, 2026
- "Training days done: X" — days with at least 2 checks
- "Current streak: X" — consecutive non-red days
- "Phase 1 target: September 11, 2026" — nearest milestone
- "Days to Phase 1: X" — countdown

---

## 17. App Features — Complete List

### Core — All Must Work on Day 1

| Feature | Description |
|---|---|
| Session lock popup | On first open each day — Morning or Evening choice, confirmed and locked until midnight |
| Auto-detect today | Loads correct day plan automatically |
| Warm-up section | 6-step protocol with YouTube links, collapsible, top of Workout tab |
| Exercise guidance | What it is + how to do + mistake + YouTube. Tap to expand. |
| Set tracker | Numbered buttons per exercise (Set 1, 2, 3, 4). Tap = green. Resets daily. |
| Exercise completion | "Mark Complete" button per exercise. Confirmed = permanently green for the day. |
| Meal timeline | Exact meals, times, quantities for chosen session |
| Meal confirmation | "Mark as Done" per meal. Confirmed = permanently green. Cannot undo. |
| Food WHY panel | Tap any food item to see why it's in today's plan |
| Streak counter | Prominent on home screen |
| Daily log | 4 checkboxes + water tracker (+250ml / +500ml) + free-text note |
| Calendar | Monthly view with 🟢🟠🔴 color blocks. Tap past day to review. |
| Weight tracker | Weekly entry, line graph from 58 kg, in Log tab |
| Progress counter | Day X + Phase countdown + training days done |
| Inventory tracker | All items start at 0. Add stock manually. Status colors. Sunday shopping list. |
| Daily quote | Shown at bottom of Home tab. Rotates by day number. |
| Sunday backup reminder | Banner on Home tab every Sunday reminding to export JSON |

### Settings Panel

| Setting | Description |
|---|---|
| Add custom quote | Saved to localStorage, merges with 30 built-in quotes |
| Master food editor | Edit any day's meal → inventory requirements auto-update |
| Start date override | Set past start date for accurate streak counting |
| Export data | Downloads full localStorage as JSON file |
| Import data | Restore JSON on new device |

---

## 18. App Navigation

```
[ 🏠 Home ] [ 💪 Workout ] [ 🍽 Meals ] [ 📦 Inventory ] [ 📋 Log ]
```

All tabs have minimum 90px bottom padding so content never hides behind the tab bar.

**Home:** Date + day type + session indicator (locked after morning/evening choice) + streak + Day X + Phase countdown + inventory warnings (red items only) + daily quote at bottom

**Workout:** Collapsible warm-up section + exercise list with set trackers and completion buttons

**Meals:** Full meal timeline for chosen session. Each meal has Mark as Done button. Tap food for WHY.

**Inventory:** All items listed. All start at 0. Add stock. Sunday shopping list.

**Log:** 4 checkboxes + water tracker + weight tracker + free-text note + monthly calendar

---

## 19. Technical Specification

| Property | Value |
|---|---|
| App name | MH370 |
| GitHub username | Vamsi232104 |
| Repository | mh370 |
| URL | https://vamsi232104.github.io/mh370 |
| File structure | Single index.html (all HTML + CSS + JS) + manifest.json + sw.js |
| Framework | Vanilla JS only |
| Storage | localStorage key: mh370_v1 |
| Start date | 2026-06-11 |
| Offline | Service worker |

### Full localStorage Schema

```json
{
  "start_date": "2026-06-11",
  "last_opened": "2026-06-11",
  "streak": 0,
  "weight_log": [
    { "date": "2026-06-11", "kg": 58.0 }
  ],
  "session_locks": {
    "2026-06-11": "am"
  },
  "daily_logs": {
    "2026-06-11": {
      "session": "am",
      "checks": {
        "workout": false,
        "protein": false,
        "sleep": false,
        "water": false
      },
      "water_ml": 0,
      "meals_done": {
        "pre_workout": false,
        "post_workout": false,
        "lunch": false,
        "snack": false,
        "dinner": false
      },
      "exercises_done": {
        "0": false,
        "1": false,
        "2": false,
        "3": false,
        "4": false,
        "5": false
      },
      "sets_done": {
        "0": [],
        "1": [],
        "2": [],
        "3": [],
        "4": [],
        "5": []
      },
      "note": ""
    }
  },
  "inventory": {
    "banana":         { "unit": "pieces", "stock": 0 },
    "eggs":           { "unit": "pieces", "stock": 0 },
    "chicken_breast": { "unit": "grams",  "stock": 0 },
    "chicken_thigh":  { "unit": "grams",  "stock": 0 },
    "ground_beef":    { "unit": "grams",  "stock": 0 },
    "beef_steak":     { "unit": "grams",  "stock": 0 },
    "mutton":         { "unit": "grams",  "stock": 0 },
    "tuna_cans":      { "unit": "cans",   "stock": 0 },
    "fish_fillet":    { "unit": "grams",  "stock": 0 },
    "rice_dry":       { "unit": "grams",  "stock": 0 },
    "oats":           { "unit": "grams",  "stock": 0 },
    "sweet_potato":   { "unit": "grams",  "stock": 0 },
    "pasta_dry":      { "unit": "grams",  "stock": 0 },
    "bread_slices":   { "unit": "slices", "stock": 0 },
    "greek_yogurt":   { "unit": "grams",  "stock": 0 },
    "milk":           { "unit": "ml",     "stock": 0 },
    "peanut_butter":  { "unit": "grams",  "stock": 0 },
    "almonds":        { "unit": "grams",  "stock": 0 },
    "olive_oil":      { "unit": "ml",     "stock": 0 },
    "broccoli":       { "unit": "grams",  "stock": 0 },
    "spinach":        { "unit": "grams",  "stock": 0 },
    "mixed_salad_veg":{ "unit": "grams",  "stock": 0 }
  },
  "meal_config_overrides": {},
  "custom_quotes": [],
  "settings": {
    "theme": "dark",
    "quote_index": 0
  }
}
```

---

## 20. Design Direction

| Property | Decision |
|---|---|
| Theme | Dark — near-black background (#0a0a0a) |
| Accent | Amber #f59e0b — energy, heat, focus |
| Typography | Strong sans-serif headings. Clean monospace for times and data. |
| Style | Precision instrument. Every element earns its place. Not a wellness app. |
| Bottom padding | Minimum 90px on all scrollable content — tab bar must never hide anything |
| Calendar | Compact colored blocks — no decoration, just information |

---

## 21. Motivational Quotes Bank — 30 built-in

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

---

*Document version: 3.0*
*Updated: 2026-06-10*
*Status: Final — ready for Claude Code update build*
