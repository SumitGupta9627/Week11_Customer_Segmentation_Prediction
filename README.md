# Week 11 — Customer Segmentation & Prediction

## Project overview
This project segments customers using unsupervised learning, compares K-Means, Hierarchical clustering, and DBSCAN, then trains a separate Random Forest churn classifier for each K-Means segment where the segment has enough samples and both target classes. It summarizes segment profiles, model metrics, feature importance, and practical business actions.

## Dataset
- Source file supplied with the task: `customer_churn.csv` (500 rows, 9 columns).
- Target: `Churn` (0 = retained, 1 = churned).
- `CustomerID` is an identifier and is excluded from clustering/model features.
- Data quality checks are performed in the notebook. The supplied dataset has no missing values or duplicate rows at the time of analysis.

## Quick start
1. Install Python 3.10+.
2. Open a terminal in this project folder.
3. Create/activate a virtual environment (optional but recommended).
4. Install dependencies: `pip install -r requirements.txt`
5. Open `customer_segmentation.ipynb` in Jupyter or VS Code and run all cells from top to bottom.

## Files
- `customer_segmentation.ipynb` — full workflow and explanations.
- `segmentation_data.csv` — supplied data plus `SegmentID` and `SegmentName`.
- `data/customer_churn.csv` — original supplied dataset.
- `data/customer_segmentation_output.csv` — enriched segmentation output.
- `segment_profiles.md` — profile summary and interpretation.
- `model_evaluation_results.csv` — segment-level model evaluation.
- `business_recommendations.pdf` — formatted business report.
- `reports/` — clustering scores, profile table, feature importance, and recommendation CSV.
- `screenshots/` — placeholder checklist for adding genuine screenshots from your local notebook run.

## Methodology
1. Validate shape, missing values, duplicates, and target distribution.
2. Exclude customer ID and target from clustering; impute, scale numeric variables, and one-hot encode categorical variables.
3. Use an Elbow table (inertia) and silhouette scores for K-Means k=2..6; use k=3 for interpretable segment-specific models as required by the brief.
4. Compare K-Means, Agglomerative/Hierarchical clustering, and DBSCAN.
5. Create segment profiles using average tenure/charges, churn rate, and common categorical values.
6. Fit and tune a Random Forest per segment with GridSearchCV when the segment has enough data and class diversity.
7. Report accuracy, precision, recall, F1 and ROC-AUC, and derive business recommendations from observed profiles.

## Important limitations
- The dataset is small (500 rows) and churn is imbalanced. Segment-level metrics may be unavailable for segments with too few positive/negative examples; the project records this rather than inventing results.
- This is a demonstration analysis, not a production-ready churn system. Use temporal validation, cost-sensitive evaluation, and an A/B test before acting on recommendations.
- Business impact is presented as testable hypotheses, not guaranteed revenue or savings.

## Documentation checklist
- [x] Project overview and objectives
- [x] Setup instructions and requirements
- [x] Code structure and algorithm descriptions
- [x] Visual analysis charts generated in notebook
- [x] Test/validation assertions in notebook
- [x] Segment-specific business recommendations
- [ ] Add screenshots of your actual notebook execution in `screenshots/` before final submission if your portal specifically requires image files.
