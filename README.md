# RL_Fundamentals
A python package to implement core reinforcement learning strategies. 
Made at SVKM NMIMS Mukesh Patel School of Technology Management and Engineering, Department of Artificial Intelligence
From Reinforcment Learning Course Materials of Dr. Ami Munshi (Professor, Department of Artificial Intelligence)

## Version 0.1 - Current
Here’s a short, README-ready introduction and explanation for your **UCB (Upper Confidence Bound) strategy** function:

---
## 🎯 Upper Confidence Bound (UCB) Bandit Strategy

This script implements the **UCB1** algorithm for solving the **Multi-Armed Bandit problem** — a classic reinforcement learning scenario where you must choose between multiple options (arms) to maximize total reward over time.

### How It Works

1. **Initialization** – Each arm is pulled once to get an initial estimate of its reward probability.
2. **UCB Selection** – At each trial, the algorithm chooses the arm with the highest **Upper Confidence Bound**:

   $$
   \text{UCB} = Q + \sqrt{\frac{2 \log t}{N}}
   $$

   where:

   * $Q$ = estimated average reward for the arm
   * $N$ = number of times the arm has been pulled
   * $t$ = current trial number
3. **Reward Simulation** – A reward is given based on the arm’s probability of winning (`prob_win_eacharm`).
4. **Update Estimates** – The reward estimates $Q$ and counts $N$ are updated incrementally.
5. **Cumulative Tracking** – Keeps track of total rewards over time for plotting and performance analysis.

### Example Usage

```python
rewards, cumulative_rewards, estimated_Q = ucb_strategy(
    trials=1000,
    arms=5,
    prob_win_eacharm=[0.3, 0.5, 0.6, 0.4, 0.8]
)
```

This will print:

* **Estimated rewards** for each arm
* **Total reward** collected
* Arrays for rewards and cumulative rewards over trials (for plotting learning curves)

---
