# 🛠️ Predictive Maintenance using Machine Learning

This project leverages data preprocessing, visualization, outlier removal, clustering, and a trained machine learning model to predict **machine failure** in an industrial setting. It also includes a user-friendly **Gradio web interface** for real-time predictions.

## 📁 Dataset

* **Description:** The dataset includes machine operating conditions, tool wear, failure types (TWF, HDF, PWF, OSF, RNF), and the overall machine failure indicator.
* **Target Variable:** `Machine failure` (binary classification)

---

## 🔧 Preprocessing Steps

1. **Column Renaming & Dropping:**

   * Cleaned column names for better readability.
   * Dropped unnecessary identifiers like `UDI` and `Product ID`.

2. **Target Column Creation:**

   * Combined multiple individual failure types (TWF, HDF, PWF, OSF, RNF) into a single binary column `Machine failure`.

3. **Feature Engineering:**

   * Created a new feature `Power` as the product of `Rotational speed` and `Torque`.
   * Converted categorical `Type` values (L, M, H) to numerical (0, 1, 2).

4. **Outlier Removal:**

   * Applied **IQR method** and **Local Outlier Factor (LOF)** to remove extreme values.

5. **Normalization:**

   * Used **Z-score normalization** on continuous features (excluding categorical/target columns).

---

## 📊 Exploratory Data Analysis (EDA)

* Generated distribution plots, box plots, correlation heatmaps, and pair plots to explore feature relationships.
* Used parallel coordinate plots and class distributions to better understand the data.

---

## 🔍 Clustering Analysis

* **K-Means Clustering:** Used `KElbowVisualizer` to determine optimal clusters (`k=4`).
* **Visualization:** Cluster separation visualized via pairplots.
* **Silhouette Score:** Calculated to assess clustering performance.
* **Hierarchical Clustering:** Dendrogram plotted using Ward’s method.

---

## 📈 Model Deployment with Gradio

An interactive **Gradio web app** was developed to predict machine failure probability using real-time inputs.

### 🎛️ User Inputs:

* Air temperature
* Process temperature
* Rotational speed
* Torque
* Tool wear
* Product type (`L`, `M`, `H`)

### 🎯 Outputs:

* Failure probability (as class confidence)
* Maintenance recommendation
* Placeholder for failure type explanation

To run the app:

```bash
pip install gradio scikit-learn==1.1.3
python your_script.py
```

---

## 🧠 Technologies Used

* Python
* Pandas, NumPy, Seaborn, Matplotlib
* Scikit-learn
* Yellowbrick
* YData Profiling
* Gradio

---

## 🚀 How to Use

1. Clone the repository.
2. Place `ai4i2020.csv` in the working directory.
3. Run the notebook or script.
4. Launch the Gradio app and input values to get predictions.

---

## 📌 Notes

* Ensure `scikit-learn==1.1.3` is installed for compatibility with certain components.
* The profiling report (`ydata-profiling`) provides an interactive summary of the dataset.

---
