# Player Engagement & Newsletter Subscription Prediction

## 🔹 Project Overview

This project investigates **player behavior in a Minecraft server** to predict **subscription to a game-related newsletter**. Using demographic data and in-game metrics, we explored how **experience level, hours spent gaming, and age** influence the likelihood of newsletter subscription.  

**Main objectives:**  

- Understand key characteristics of subscribers vs. non-subscribers.  
- Develop a predictive model for newsletter subscription.  
- Generate actionable insights for game developers and marketers.  

---

## 📊 Dataset

- **Source:** Survey and in-game activity logs from a Minecraft server.  
- **Observations:** 196 players  
- **Features:**  

| Variable | Type | Description |
|----------|------|-------------|
| `experience` | Categorical | Player experience level (Beginner → Pro) |
| `subscribe` | Logical | Newsletter subscription status |
| `played_hours` | Numeric | Total hours played |
| `Age` | Numeric | Player age |
| `gender` | Categorical | Player gender (Male/Female/Non-binary) |
| `name` | Character | Player name |
| `hashedEmail` | Character | Encrypted email |

**Key data issues:**  
- Missing age values  
- Missing gender information  
- Extreme outliers in `played_hours`  
- Potential sampling bias  

---

## 🔹 Exploratory Data Analysis

- **Subscription Patterns:**  
  - ~85% of subscribers are aged 17–25.  
  - Subscribed players averaged **7.88 hours** played, compared to **0.50 hours** for non-subscribers.  



---

## 🔹 Methodology

1. **Data Wrangling:**  
   - Removed non-predictive features (`hashedEmail`, `name`, `gender`)  
   - Handled missing values  
   - Converted subscription status to `Yes`/`No`  

2. **Modeling Approach:**  
   - **Algorithm:** K-Nearest Neighbors (K-NN)  
   - **Predictors:** `played_hours`, `Age`  
   - **Training/Test Split:** 80/20  
   - **Cross-validation:** 5-fold to choose optimal K  

3. **K-NN Model Selection:**  
   - Tested K = 1 to 30  
   - Optimal K chosen = 5 for stability and performance  
   - Upsampling used to address class imbalance  

---

## 🔹 Results

- **Test Accuracy:** 72.5%  
- **Confusion Matrix:**

| Prediction | Yes | No |
|------------|-----|----|
| **Yes** | 26 | 8 |
| **No**  | 3  | 3 |

**Insights:**  
- Age (17–25) and hours played are strong predictors of subscription.  
- K-NN achieved reasonable accuracy with limited features.  
- Longer gameplay is strongly correlated with subscription likelihood.  

---

## 🔹 Discussion & Impact

**Practical Implications:**  
- Marketing campaigns should target **younger, more active players**.  
- Encourage longer gameplay with **achievements or reward systems** to increase subscription rates.  

**Future Directions:**  
- Explore additional predictors like **gender or experience level** to improve accuracy.  
- Investigate causality: Do subscribers play more, or do players who play more subscribe?  
- Apply other classification algorithms (e.g., logistic regression, random forest) for comparison.  
