# **Laboratory Specimen Journey Dashboard**

## **Overview**

This project presents an interactive dashboard for analyzing laboratory specimen workflows within a hospital system. The dashboard visualizes the **average specimen journey timeline**, supports **A/B comparisons across temporal conditions** (e.g., weekday vs. weekend, day vs. night shift), and displays the **likelihood of key events** such as cancellations and delayed results.

The goal of this tool is to help stakeholders—such as hospital administrators and laboratory managers—identify inefficiencies, compare operational conditions, and better understand workflow performance.

---

## **Project Structure**

```
├── dash_code.ipynb              # Main notebook containing data processing + calculations for dashboard
├── specimen_dashboard.ipynb     # Notebook to execute dashboard
├── 2025_specimen_time_series_events_no_phi.tsv   # Dataset (not included if large/sensitive)
├── README.md                   # Setup and run instructions
```

---

## **Setup Instructions**

### **1. Clone or download the repository**

```bash
git clone <your-repo-link>
cd <repo-folder>
```

---

### **2. Install required libraries**

Open the notebook (`dash_code.ipynb`) and **uncomment the `%pip install` lines at the top** if needed, or manually install the following:

```bash
pip install nbformat pandas plotly ipywidgets voila IPython
```

---

### **3. Launch Jupyter Notebook**

```bash
jupyter notebook
```

Open `dash_code.ipynb`.

---

## **Running the Dashboard**

### **Option 1: Run inside Jupyter (quick preview)**

* Run all cells in `dash_code.ipynb` and then in `specimen_dashboard.ipynb`
* The interactive dashboard (with dropdowns and charts) will appear directly in the `specimen_dashboard.ipynb` notebook

---

### **Option 2: Launch as a standalone dashboard (recommended)**

This project uses **Voila** to turn the notebook into a clean interactive app.

#### Run:

```bash
voila specimen_dashboard.ipynb
```

* This will open the dashboard in your browser
* Removes code cells and shows only the interactive UI

---

## **Using the Dashboard**

The dashboard includes interactive controls:

* **Test Code** — filter by specific lab test
* **Department** — filter by performing department
* **Compare By** — toggle between:

  * Weekday vs. Weekend
  * Day Shift vs. Night Shift

### **Visualizations**

1. **Average Timeline**

   * Shows average time (hours from order) across specimen stages

2. **A/B Comparison + Event Likelihood**

   * Grouped bar chart comparing:

     * Cancellation rates
     * Delayed result rates (>4 hours)

3. **Drop-off Visualization**

   * Shows % of specimens lost between stages

---

## **Notes**

* The dashboard excludes **canceled orders from the timeline visualization** to reflect complete workflows
* However, cancellations are included in **event likelihood analysis**
* Time values are displayed as **relative durations (hours from order)** for comparability

---

## **Dependencies**

* Python 3.x
* pandas
* plotly
* ipywidgets
* voila

---

## **Troubleshooting**

* If widgets do not render:

  ```bash
  pip install ipywidgets
  jupyter nbextension enable --py widgetsnbextension
  ```

* If Voila is not recognized:

  ```bash
  pip install voila
  ```
