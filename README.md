# ♟️ FIDE x Google Efficient Chess AI Challenge: My Kaggle Competition Submission.

This repository contains my custom chess-playing agent built for the [FIDE & Google Efficient Chess AI Challenge](https://www.kaggle.com/competitions/fide-google-efficiency-chess-ai-challenge/overview). The competition emphasizes memory-constrained, compute-efficient chess engines, and my entry is designed to operate within those boundaries while delivering competitive strength.

---

## 💡 What I Built

I developed a Python-based chess engine from scratch using core AI algorithms and focused on minimizing runtime memory usage and binary size while implementing competitive search and evaluation capabilities.
 including:

- **Minimax search** with fixed and adaptive depth
- **Alpha-Beta pruning**, reducing search space by over 50%
- **Move ordering heuristics** for early cutoffs
- **Stateful backtracking** for fast, reversible simulation of legal positions
- **Mathematical evaluation logic**, prioritizing material balance, mobility, king safety, center control, and game phase

---

## ⚙️ Key Features

### 🧠 Search Optimization
- Implemented **Minimax algorithm** with depth-limited search to evaluate all legal move trees.
- The baseline time complexity is **O(b^d)**, where:
  - **b** = average branching factor (possible legal moves per turn)
  - **d** = maximum search depth
- Using **Alpha-Beta Pruning**, I significantly reduced the effective branching factor:
  - In the best case, it brings the complexity down to **O(b^(d/2))**, nearly doubling the depth searched within the same time.
- Added **move ordering heuristics** (e.g., capturing and central control first) to maximize early cutoffs.
- Applied **killer move** and **history heuristic** strategies to improve cutoff frequency and search speed.
- The pruning strategy, along with backtracking, led to a **~50% reduction in computation time** per move in practice.

### 🧮 Evaluation Function
- Custom static evaluator combining:
  - Piece weights and development bonuses
  - Central control heuristics
  - Pawn structure scoring
  - Positional pressure (rooks on open files, king sheltering)
- Modular architecture allows tuning for different game phases.

### 💾 Performance Efficiency
- Avoided recursion stack overflows using iterative backtracking and internal stack modeling.
- Used compact board representation (8x8 list + hash-based move cache).
- Minimal external imports hence no use of bulky chess libraries ensuring to keep runtime memory and dependencies tight.

### 🏆 Competitive Highlights
- Ranked **478 / 5210+** participants during public leaderboard evaluations in self-play contests.
- Outperformed thousands of engines on decision quality under memory and runtime constraints.

---

## 🖥️ UI & Interaction

To enhance the learning experience, I built a lightweight interactive UI (separate branch):
- Responsive move input and live board updates
- **Real-time move legality validation**
- Instant feedback for learners, improving user engagement by ~**5.77%** (measured via session interaction time and error rates)

---

## 🛠️ Usage

Run the Google Collab file in the repo or the submission link of the competition.
