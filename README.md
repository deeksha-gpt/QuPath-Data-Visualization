
<img width="398" height="294" alt="Screenshot 2026-03-10 170540" src="https://github.com/user-attachments/assets/eb8f5d86-5610-4af7-8d87-13df67a94e0d" />
<img width="549" height="298" alt="Screenshot 2026-01-31 184113" src="https://github.com/user-attachments/assets/c64ce3bf-745a-494a-b58c-1e33a6612b09" />
# 📊 CD68 Macrophage Analysis in Decidua Tissue

## 📌 Overview

This project visualizes and compares **CD68 macrophage levels** between two groups:

* Healthy Controls
* Patients

The analysis uses **R** and **ggplot2** to create a clear, publication-style plot showing:

* Individual sample variation (jitter points)
* Group-level summary (median crossbar)

---

## 📂 Dataset

The dataset is manually defined in R:

```r
data <- data.frame(
  Group = rep(c("Healthy Control", "Patient"), each = 8),
  Value = c(
    0.467, 0.584, 0.632, 0.718, 0.543, 0.684, 0.466, 0.589,
    0.783, 0.856, 0.681, 0.978, 0.847, 0.764, 0.638, 0.859
  )
)
```

### 🧾 Description

* **Group**: Experimental condition (Control vs Patient)
* **Value**: Proportion of CD68 macrophages (cells per total cells)

---

## 📈 Visualization

The plot is generated using **ggplot2**:

```r
library(ggplot2)

ggplot(data, aes(x = Group, y = Value, color = Group)) +
  geom_jitter(width = 0.15, size = 3, alpha = 0.8) +
  stat_summary(
    fun = median,
    geom = "crossbar",
    width = 0.4,
    color = "black"
  ) +
  guides(color = "none") +
  theme_classic() +
  labs(
    title = "CD68 Macrophages in Decidua Tissue",
    x = "Samples",
    y = "Cells per Total Number of Cells"
  )
```

---

## 🔍 Key Features of the Plot

* **Jittered Points**
  Shows individual sample variability while avoiding overlap

* **Median Crossbar**
  Highlights central tendency for each group

* **Clean Theme (`theme_classic`)**
  Suitable for academic/publication use

* **Color Encoding**
  Distinguishes groups visually (legend removed for simplicity)

---

## 📊 Interpretation

* Patient samples appear to have **higher CD68 macrophage levels** compared to healthy controls
* There is **visible variability within both groups**
* Median values provide a robust comparison against outliers

---

## 🛠️ Requirements

Install required package:

```r
install.packages("ggplot2")
```

Load library:

```r
library(ggplot2)
```

---

## 🚀 How to Run

1. Copy the dataset and plotting code into an R script or RStudio
2. Run the script
3. The plot will be displayed in the Plots panel

---

## 📤 Output

* A scatter + summary plot comparing macrophage levels between groups
* Useful for:

  * Biological interpretation
  * Reports and presentations
  * Publication figures

---

## 💡 Possible Extensions

* Add statistical testing (e.g., **t-test / Wilcoxon test**)
* Include boxplots or violin plots
* Export high-resolution figures (`ggsave`)
* Increase sample size for stronger inference

---

## 🧪 Conclusion

This project provides a simple yet effective way to:

* Visualize biological differences between groups
* Combine raw data transparency with summary statistics
* Generate publication-quality figures in R

---
