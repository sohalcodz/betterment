# Financials: A Commitment-Stake Model

> *Step counting is used as the demonstration metric. Screen time tracking is planned for a future implementation.*

---

## Overview

Players put money on the line to form a competition around a shared daily goal. The model is designed to reward consistency, penalize failure, and redistribute value among participants in a way that encourages healthy behavior.

---

## Game Parameters

| Parameter | Description |
|---|---|
| **Bet** | The dollar amount each user commits to the competition. Recommended buy-in data will be surfaced to the user to optimize habit-formation outcomes. |
| **Initial Fee** | A percentage of the Bet taken upfront to host the competition. This percentage is optimized to keep users comfortable while sustaining the platform. |
| **Lock** | The portion of the Bet held in escrow until the player completes the competition goal. |
| **Game Length** | Duration of the competition in days. Recommended discrete values: **15, 30, 60, 365**. |
| **Daily Goal** | The number of steps the round organizer sets for all players. |
| **Daily Limit** | The maximum steps that count toward any player's score in a single day. Currently set at **15,000 steps** — steps beyond this threshold are ignored to encourage healthy behavior. |
| **Daily Grade** | The percentage of the Daily Goal a player accomplished on a given day. |
| **Daily Pass Rate** | The minimum Daily Grade percentage required to avoid failure. |

---

## Mechanics

### Extra Credit
Steps left unaccomplished by one player on a given day become available as **Extra Credit** for other players the following day. This pool is split evenly among eligible players. Players may claim Extra Credit up to the Daily Limit. Unclaimed Extra Credit steps are retained by the platform.

### Expulsion
A player is **expelled** if their average Daily Grade falls below the Daily Pass Rate at the end of the game. Upon expulsion, that player's locked funds are distributed to remaining players proportionally based on their scores.

---

## Test Game

**Game Setup**

| Parameter | Value |
|---|---|
| Bet | $12.00 |
| Game Length | 10 days |
| Daily Goal | 10,000 steps |
| Pass Rate | 70% (0.70) |
| Daily Limit | 15,000 steps |
| Number of Players | 5 |
| Total Money In | $60.00 |

---

### Daily Steps Log

#### Player A
| | Day 1 | Day 2 | Day 3 | Day 4 | Day 5 | Day 6 | Day 7 | Day 8 | Day 9 | Day 10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Steps | 10,000 | 10,000 | 10,000 | 10,000 | 10,000 | 10,000 | 10,000 | 10,000 | 10,000 | 10,000 |
| Extra Credit Available | 0 | 2,250 | 2,250 | 2,250 | 2,250 | 2,250 | 2,250 | 2,250 | 2,250 | 2,250 |
| Extra Credit Performed | 0 | 2,250 | 2,250 | 2,250 | 2,250 | 2,250 | 2,250 | 2,250 | 2,250 | 2,250 |

#### Player B
| | Day 1 | Day 2 | Day 3 | Day 4 | Day 5 | Day 6 | Day 7 | Day 8 | Day 9 | Day 10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Steps | 10,000 | 10,000 | 10,000 | 10,000 | 10,000 | 10,000 | 10,000 | 10,000 | 10,000 | 10,000 |
| Extra Credit Available | 0 | 2,250 | 3,375 | 3,937.5 | 4,218.75 | 4,359.38 | 4,429.69 | 4,464.84 | 4,482.42 | 4,491.21 |
| Extra Credit Performed | 0 | 1,125 | 1,687.5 | 1,968.75 | 2,109.38 | 2,179.69 | 2,214.84 | 2,232.42 | 2,241.21 | 2,245.61 |

#### Player C
| | Day 1 | Day 2 | Day 3 | Day 4 | Day 5 | Day 6 | Day 7 | Day 8 | Day 9 | Day 10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Steps | 9,000 | 9,000 | 9,000 | 9,000 | 9,000 | 9,000 | 9,000 | 9,000 | 9,000 | 9,000 |
| Extra Credit Available | 0 | 2,000 | 4,000 | 6,000 | 8,000 | 10,000 | 12,000 | 14,000 | 16,000 | 18,000 |
| Extra Credit Performed | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

#### Player D
| | Day 1 | Day 2 | Day 3 | Day 4 | Day 5 | Day 6 | Day 7 | Day 8 | Day 9 | Day 10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Steps | 7,000 | 7,000 | 7,000 | 7,000 | 7,000 | 7,000 | 7,000 | 7,000 | 7,000 | 7,000 |
| Extra Credit Available | 0 | 1,500 | 3,000 | 4,500 | 6,000 | 7,500 | 9,000 | 10,500 | 12,000 | 13,500 |
| Extra Credit Performed | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

#### Player E
| | Day 1 | Day 2 | Day 3 | Day 4 | Day 5 | Day 6 | Day 7 | Day 8 | Day 9 | Day 10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Steps | 5,000 | 5,000 | 5,000 | 5,000 | 5,000 | 5,000 | 5,000 | 5,000 | 5,000 | 5,000 |
| Extra Credit Available | 0 | 1,000 | 2,000 | 3,000 | 4,000 | 5,000 | 6,000 | 7,000 | 8,000 | 9,000 |
| Extra Credit Performed | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

---

### Final Results

| Player | Avg Daily Grade | Competition Payout | Expulsion Bonus | **Total Payout** | Status |
|---|---|---|---|---|---|
| A | 120.25% | $12.03 | $1.51 | **$13.53** | ✅ Passed |
| B | 118.00% | $11.80 | $1.48 | **$13.28** | ✅ Passed |
| C | 90.00% | $9.00 | $1.13 | **$10.13** | ✅ Passed |
| D | 70.00% | $7.00 | $0.88 | **$7.88** | ✅ Passed (Borderline) |
| E | 50.00% | — | — | **$0.00** | ❌ Expelled |

---

### Round Economics

| Metric | Value |
|---|---|
| Total Money In | $60.00 |
| Total Payout | $44.83 |
| **Platform Revenue** | **$15.17** |
| **Margin** | **~25.3%** |
| Interest on Held Funds *(est. 3%/yr, very conservative)* | ~$0.05 |

> **Note:** Player E was expelled for finishing with an average daily grade of 50%, which falls below the 70% pass rate. Their locked funds were redistributed to the other players proportionally by score. The platform retains any unclaimed Extra Credit steps and collects the Initial Fee, generating the round margin.
