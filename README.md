
# Mathematics and Statistics Analysis
# Portfolio Project for AI Training

import statistics
import math

# Sample dataset: study hours and examination scores
study_hours = [1, 2, 2, 3, 3, 4, 4, 5, 5, 6,
               6, 7, 7, 8, 8, 9, 9, 10, 10, 11]

scores = [42, 48, 51, 55, 57, 60, 63, 64, 68, 70,
          72, 74, 77, 80, 82, 85, 87, 89, 91, 94]

# 1. Descriptive Statistics
print("MATHEMATICS AND STATISTICS PROJECT")
print("----------------------------------")

print("Mean score:", statistics.mean(scores))
print("Median score:", statistics.median(scores))
print("Highest score:", max(scores))
print("Lowest score:", min(scores))
print("Score range:", max(scores) - min(scores))
print("Standard deviation:", statistics.stdev(scores))

# 2. Calculate Pearson Correlation
mean_x = statistics.mean(study_hours)
mean_y = statistics.mean(scores)

numerator = sum(
    (x - mean_x) * (y - mean_y)
    for x, y in zip(study_hours, scores)
)

denominator = math.sqrt(
    sum((x - mean_x) ** 2 for x in study_hours) *
    sum((y - mean_y) ** 2 for y in scores)
)

correlation = numerator / denominator

print("\nCORRELATION ANALYSIS")
print("Pearson correlation:", round(correlation, 3))

# 3. Simple Linear Regression
slope = numerator / sum(
    (x - mean_x) ** 2 for x in study_hours
)

intercept = mean_y - slope * mean_x

print("\nLINEAR REGRESSION")
print("Slope:", round(slope, 2))
print("Intercept:", round(intercept, 2))

# 4. Interpretation
print("\nPROJECT INTERPRETATION")
print("The sample shows a positive relationship")
print("between study hours and examination scores.")
print("Correlation does not prove causation.")

