> **Disclaimer:**  
> This project was completed as part of the **Google Advanced Data Analytics Professional Certificate on Coursera**. The dataset and business scenario are provided through the course for educational purposes.
> 
> **Author:** Tan Shi Wei  
> **Date:** 2025-06-04  
> **Project:** Waze User Churn Prediction
> 
> _📑 Tip: Use GitHub’s Outline tab to quickly navigate through the sections of this README._

# Project Structure

## 📌 Context and Objective

<p align="center">
  <img src="https://github.com/user-attachments/assets/955e8943-b5e6-4aa4-a70c-fc4c311d5f45" alt="Waze Logo" width="200" height="200" />
</p>

This project focuses on predicting monthly user churn for Waze, a community-driven navigation app that partners with users, map editors, and organizations worldwide to improve the driving experience. It supports Waze’s broader effort to boost user growth and increase retention.

### Key Stakeholders

<div align="center">
  <table border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; text-align: center;">
    <thead>
      <tr>
        <th>Name</th>
        <th>Role</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Harriet Hadzic</td>
        <td>Director of Data Analysis</td>
      </tr>
      <tr>
        <td>May Santner</td>
        <td>Data Analysis Manager</td>
      </tr>
      <tr>
        <td>Chidi Ga</td>
        <td>Senior Data Analyst</td>
      </tr>
      <tr>
        <td>Sylvester Esperanza</td>
        <td>Senior Project Manager</td>
      </tr>
      <tr>
        <td>Emrick Larson</td>
        <td>Finance & Administration Head</td>
      </tr>
      <tr>
        <td>Ursula Sayo</td>
        <td>Operations Manager</td>
      </tr>
    </tbody>
  </table>
</div>

> **Note:** All names, characters, and events in this project are fictional. No identification with actual persons (living or deceased) is intended or should be inferred. The data shared in this project has been altered for pedagogical purposes.

By analyzing user behavior data and building a predictive model, this project aims to:

* **Identify** which users are most likely to churn  
* **Uncover** when churn typically occurs  
* **Understand** potential reasons behind churn  

**The goal is to build a machine learning model that identifies users at risk of leaving, enabling Waze to engage them proactively with targeted retention strategies that enhance user satisfaction and drive business growth.**

### Data Dictionary

<div>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th>Column Name</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>label</td>
      <td>obj</td>
      <td>Binary target variable (“retained” vs “churned”) for if a user has churned anytime during the course of the month</td>
    </tr>
    <tr>
      <td>sessions</td>
      <td>int</td>
      <td>The number of occurrences of a user opening the app during the month</td>
    </tr>
    <tr>
      <td>drives</td>
      <td>int</td>
      <td>An occurrence of driving at least 1 km during the month</td>
    </tr>
    <tr>
      <td>device</td>
      <td>obj</td>
      <td>The type of device a user starts a session with</td>
    </tr>
    <tr>
      <td>total_sessions</td>
      <td>float</td>
      <td>A model estimate of the total number of sessions since a user has onboarded</td>
    </tr>
    <tr>
      <td>n_days_after_onboarding</td>
      <td>int</td>
      <td>The number of days since a user signed up for the app</td>
    </tr>
    <tr>
      <td>total_navigations_fav1</td>
      <td>int</td>
      <td>Total navigations since onboarding to the user’s favorite place 1</td>
    </tr>
    <tr>
      <td>total_navigations_fav2</td>
      <td>int</td>
      <td>Total navigations since onboarding to the user’s favorite place 2</td>
    </tr>
    <tr>
      <td>driven_km_drives</td>
      <td>float</td>
      <td>Total kilometers driven during the month</td>
    </tr>
    <tr>
      <td>duration_minutes_drives</td>
      <td>float</td>
      <td>Total duration driven in minutes during the month</td>
    </tr>
    <tr>
      <td>activity_days</td>
      <td>int</td>
      <td>Number of days the user opens the app during the month</td>
    </tr>
    <tr>
      <td>driving_days</td>
      <td>int</td>
      <td>Number of days the user drives (at least 1 km) during the month</td>
    </tr>
  </tbody>
</table>
</div>

## 🧭 Roadmap

This project followed the P.A.C.E framework of *Plan*, *Analyze*, *Construct* and *Execute* for a clear and structured analysis.

<details>
  <summary><em>Click to see detailed task-stage mapping</em></summary>

### Milestones and Deliverables

<div align="center">
  <table border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; text-align: center;">
    <thead>
      <tr>
        <th>Milestone</th>
        <th>Tasks</th>
        <th>P.A.C.E</th>
        <th>Deliverables / Reports</th>
        <th>Stakeholder(s)</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><strong>1</strong></td>
        <td>Establish structure for project workflow</td>
        <td>Plan</td>
        <td>Global-level project document</td>
        <td>
          • May Santner
        </td>
      </tr>
      <tr>
        <td><strong>1a</strong></td>
        <td>Write a project proposal</td>
        <td>Plan</td>
        <td></td>
        <td>
          • Sylvester Esperanza
        </td>
      </tr>
      <tr>
        <td><strong>2</strong></td>
        <td>Compile summary information about the data</td>
        <td>Analyze</td>
        <td>Data files ready for EDA</td>
        <td>
          • Chidi Ga
        </td>
      </tr>
      <tr>
        <td><strong>2a</strong></td>
        <td>Begin exploring the data</td>
        <td>Analyze</td>
        <td></td>
        <td>
          • Chidi Ga
        </td>
      </tr>
      <tr>
        <td><strong>3</strong></td>
        <td>Data exploration and cleaning</td>
        <td>Plan and Analyze</td>
        <td>EDA report</td>
        <td>
          • Chidi Ga
        </td>
      </tr>
      <tr>
        <td><strong>3a</strong></td>
        <td>Visualization building</td>
        <td>Analyze and Construct</td>
        <td>Tableau dashboard / visualizations</td>
        <td>
          • Sylvester Esperanza
        </td>
      </tr>
      <tr>
        <td><strong>4</strong></td>
        <td>Compute descriptive statistics</td>
        <td>Analyze</td>
        <td>Analysis of testing results between two important variables</td>
        <td>
          • Chidi Ga
        </td>
      </tr>
      <tr>
        <td><strong>4a</strong></td>
        <td>Conduct hypothesis testing</td>
        <td>Analyze and Construct</td>
        <td></td>
        <td>
          • May Santner
        </td>
      </tr>
      <tr>
        <td><strong>5</strong></td>
        <td>Build a regression model</td>
        <td>Analyze and Construct</td>
        <td></td>
        <td>
          • May Santner
        </td>
      </tr>
      <tr>
        <td><strong>5a</strong></td>
        <td>Evaluate the model</td>
        <td>Execute</td>
        <td>Determine the success of the model</td>
        <td>
          • Harriet Hadzic
        </td>
      </tr>
      <tr>
        <td><strong>6</strong></td>
        <td>Build a machine learning model</td>
        <td>Construct</td>
        <td>Final model</td>
        <td>
          • Harriet Hadzic
        </td>
      </tr>
      <tr>
        <td><strong>6a</strong></td>
        <td>Communicate final insights with stakeholders</td>
        <td>Execute</td>
        <td>Final report presentation</td>
        <td>
          • Harriet Hadzic<br>
          • Emrick Larson<br>
          • Ursula Sayo
        </td>
      </tr>
    </tbody>
  </table>
</div>

---

### Estimated Timeline

- **Milestone 1**: 1–2 days  
- **Milestone 2**: 2–3 weeks  
- **Milestone 3**: 1 week  
- **Milestone 4**: 1 week  
- **Milestone 5**: 1–2 weeks  

</details>


## [🧹 Data Cleaning](./01_data_cleaning.ipynb)

Handles missing values, fixes data types, and removes inconsistencies.

## [📊 Exploratory Data Analysis](./02_exploratory_data_analysis.ipynb)

Includes visualizations and statistical summaries to uncover insights.

## [⚖️ Statistical Hypothesis Testing](./03_hypothesis_testing.ipynb)

Performs t-tests to assess group differences in user behavior.

