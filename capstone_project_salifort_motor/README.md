> **Disclaimer:**  
> This project was completed as part of the **Google Advanced Data Analytics Professional Certificate on Coursera**. The dataset and business scenario are provided through the course for educational purposes.
> 
> **Author:** Tan Shi Wei  
> **Date:** 2025-06-30  
> **Project:** Salifort Motor Employee Churn Prediction

# Project Structure

## 📌 Context and Objective

The project focuses on developing a predictive model to identify employees at risk of leaving Salifort Motors, with the aim of improving employee retention, enhancing job satisfaction, and reducing turnover-related costs.

By analyzing employee survey and HR data, this project aims to:

* **Identify** which employees are most likely to leave the company (churn)

* **Understand** key factors driving employee turnover

* **Recommend** targeted strategies to improve retention

The goal is to build a predictive model that flags at-risk employees, enabling Salifort Motors to take proactive steps that enhance employee satisfaction, support professional development, and reduce turnover-related costs.

### Data Dictionary

<div style="text-align: center;">
  <div style="display: inline-block; overflow-x: auto;">
    <table border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; margin: auto;">
      <thead style="background-color: #f2f2f2;">
        <tr>
          <th>Column Name</th>
          <th>Type</th>
          <th>Description</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>satisfaction_level</td>
          <td>int64</td>
          <td>The employee’s self-reported satisfaction level [0–1]</td>
        </tr>
        <tr>
          <td>last_evaluation</td>
          <td>int64</td>
          <td>Score of employee's last performance review [0–1]</td>
        </tr>
        <tr>
          <td>number_project</td>
          <td>int64</td>
          <td>Number of projects employee contributes to</td>
        </tr>
        <tr>
          <td>average_monthly_hours</td>
          <td>int64</td>
          <td>Average number of hours employee worked per month</td>
        </tr>
        <tr>
          <td>time_spend_company</td>
          <td>int64</td>
          <td>How long the employee has been with the company (years)</td>
        </tr>
        <tr>
          <td>work_accident</td>
          <td>int64</td>
          <td>Whether or not the employee experienced an accident while at work</td>
        </tr>
        <tr>
          <td>left</td>
          <td>int64</td>
          <td>Whether or not the employee left the company</td>
        </tr>
        <tr>
          <td>promotion_last_5years</td>
          <td>int64</td>
          <td>Whether or not the employee was promoted in the last 5 years</td>
        </tr>
        <tr>
          <td>department</td>
          <td>str</td>
          <td>The employee's department</td>
        </tr>
        <tr>
          <td>salary</td>
          <td>str</td>
          <td>The employee's salary (low, medium, or high)</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>


<div style="text-align: center;">
  <a href="https://github.com/shiweitan0/Python/blob/main/capstone_project_salifort_motor/salifort_motor_project.ipynb" target="_blank">
    🔗 View Full Analysis Notebook
  </a>
</div>

