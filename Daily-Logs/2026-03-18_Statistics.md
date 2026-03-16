# Data Science Learning: March 18, 2026

## 1. Core Concepts: Descriptive & Inferential Statistics

### What is Data?
* **The Fuel for AI:** It is believed that more data leads to more "truth."
* **Snapshots:** Data is actually just a series of snapshots; it provides clues, not absolute truth.
* **Critical Thinking:** Always consider how data was created, who created it, and what it might be missing.

### Populations vs. Samples
* **Population:** The entire group of interest (e.g., every student in India).
* **Sample:** A subset of the population (e.g., students at SKIT). Ideally, this should be **random and unbiased**.

### Measures of Central Tendency
1.  **Mean ($\mu$ or $\bar{x}$):** The "Center of Gravity" for a data set.
    * **Sample Mean:** $\bar{x} = \frac{\sum x_i}{n}$
    * **Population Mean:** $\mu = \frac{\sum x_i}{N}$
2.  **Weighted Mean:** Used when certain values contribute more to the average than others (e.g., a final exam vs. a quiz).
    $$Weighted \ Mean = \frac{\sum (x_i \cdot w_i)}{\sum w_i}$$
3.  **Median:** The middle value of an ordered set. It is highly effective when data is skewed by **outliers** (extreme values).
4.  **Mode:** The most frequent value. If two values are equally frequent, the data is **Bimodal**.

### Measures of Variation & Distribution
* **Variance ($\sigma^2$):** The average squared distance of each data point from the mean.
* **Standard Deviation ($\sigma$):** The square root of variance; it defines the "spread" of the data.
* **Normal (Gaussian) Distribution:** A symmetrical bell-shaped curve where the Mean = Median = Mode.
    * **PDF (Probability Density Function):** Defines the likelihood of a specific continuous value.
    * **CDF (Cumulative Distribution Function):** The total area under the curve up to a specific point (probability of being $\le$ x).
    * **Inverse CDF (PPF):** Given a probability (like 0.95), it returns the exact x-value for that percentile.

---

## 2. Python Implementation (From Scratch & SciPy)

```python
from collections import defaultdict
from math import sqrt
from scipy.stats import norm

# --- 1. Weighted Mean ---
# Example: Grades with different weightage
sample_data = [90, 80, 63, 87]
weights = [20, 20, 20, 40]
w_mean = sum(s * w for s, w in zip(sample_data, weights)) / sum(weights)
print(f"Weighted Mean: {w_mean}")

# --- 2. Median (From Scratch) ---
def get_median(values):
    ordered = sorted(values)
    n = len(ordered)
    mid = n // 2
    if n % 2 == 0:
        return (ordered[mid - 1] + ordered[mid]) / 2
    else:
        return ordered[mid]

# --- 3. Mode (From Scratch) ---
def get_mode(values):
    counts = defaultdict(lambda: 0)
    for v in values:
        counts[v] += 1
    max_count = max(counts.values())
    return [v for v, count in counts.items() if count == max_count]

# --- 4. Variance & Standard Deviation (From Scratch) ---
def get_variance(values):
    mu = sum(values) / len(values)
    return sum((v - mu)**2 for v in values) / len(values)

def get_std_dev(values):
    return sqrt(get_variance(values))

# --- 5. Normal Distribution Analysis (Using SciPy) ---
# Parameters: Mean = 64.43, Std Dev = 2.99
mean_val = 64.43
std_val = 2.99

# CDF: Probability of a value being <= 64.43
prob_cdf = norm.cdf(64.43, mean_val, std_val)
print(f"CDF at Mean (Probability <= 64.43): {prob_cdf}")

# Inverse CDF (PPF): Find the value at the 95th percentile
val_95th = norm.ppf(0.95, loc=mean_val, scale=std_val)
print(f"95th Percentile Value: {val_95th}")
