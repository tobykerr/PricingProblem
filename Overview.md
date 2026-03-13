# COMP34612: Computational Game Theory - Project Overview

This project tasks you with creating a program to act as the **leader** in a repeated 2-person Stackelberg pricing game under conditions of imperfect information. You will compete against various "follower" agents over a simulated period.

---

## 1. The Game Mechanics
In this Stackelberg setup, the leader moves first, and the follower responds.

* **The Timeline:** The game spans 130 days in total.
* **Historical Data:** Days 1–100 consist of provided historical data for training your models.
* **Active Play:** Days 101–130 are the "live" days where your program must announce prices daily.
* **Daily Flow:** 1. The leader announces a price $u_L$.
    2. The follower responds with a price $u_F$.
    3. The leader receives $u_F$ and can use it to update their strategy for the next day.

## 2. Leader Specifications
Your program must operate within the following mathematical constraints:

* **Unit Cost ($c_L$):** £1.00.
* **Demand Model:** $S_L(u_L, u_F) = 100 - 5u_L + 3u_F$.
* **Daily Profit:** $(u_L - c_L)S_L(u_L, u_F)$.
* **Strategy Space (Price Bounds):**
    * **MK1, MK2, MK4, MK5:** $u_L \in [1.00, +\infty)$.
    * **MK3, MK6:** $u_L \in [1.00, 15.00]$.
* **Objective:** Maximize the accumulated profit from day 101 to day 130.

## 3. The Opponents (Followers)
You will face three known followers and three hidden followers.

* **Known Followers (MK1, MK2, MK3):** Historical data is provided for these.
* **Hidden Followers (MK4, MK5, MK6):** These are variations of the first three (e.g., MK1 is similar to MK4). No data is provided for these; they test the robustness of your learning algorithm.
* **Dynamic Environment:** Parameters in the follower's payoff functions may change daily, meaning your leader must be able to adapt.

## 4. Implementation Options
You can choose one of two structural approaches for your submission:

1.  **Single Leader Approach:** One algorithm that competes against all followers by adapting its strategy based on the opponent.
2.  **Multiple Leaders Approach:** Three distinct leaders, each specifically tailored to play against a specific follower type.

---

## 5. Project Timeline & Assessment
* **Start Date:** Week 7 (16 March).
* **Presentations:** Week 11 (4 May – 8 May).
* **Final Deadline:** 8 May at 14:00.

**Marking Scheme (50% of Total Course Grade):**
* **Content (50% of project mark):** Based on your presentation (originality, integration of course knowledge) and written documentation in your group journal.
* **Performance (50% of project mark):** Based on the actual accumulated profit your code generates on the game platform against all six followers.

## 6. Technical Setup
The project is executed using **Google Colab** to ensure a consistent environment.

* **Required Files:** `comp34612_project.ipynb` and `comp34612.zip`.
* **Environment:** Use the free version of Google Colab.
* **Constraints:** There is a 10-minute execution time limit per run. Avoid external dependencies that are not standard in the Colab environment.