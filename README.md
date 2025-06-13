# EdTech: Lead Conversion Prediction for ExtraaLearn

This repository contains the analysis and machine learning model developed for ExtraaLearn, an EdTech startup, aimed at identifying leads most likely to convert into paid customers. This project demonstrates skills in exploratory data analysis (EDA), feature engineering, predictive modeling, and deriving actionable business insights.

---

## Business Objective

ExtraaLearn, an EdTech startup offering programs on cutting-edge technologies, generates a large number of leads regularly. The primary objective of this project was to **develop a machine learning model to identify which leads are more likely to convert into paid customers**, enabling the company to allocate its resources more effectively. 

---

## Key Questions Addressed

This analysis was driven by the following key business questions:

1.  Which attributes and behaviors define leads that are more likely to convert to paid customers? 
2.  What are the key factors driving the lead conversion process for ExtraaLearn? 
3.  How do different lead interaction channels (website, mobile app, email, phone) impact conversion rates? 
4.  What role do marketing channels (print media, digital media, educational channels, referrals) play in lead conversion? 
5.  Does the completeness of a lead's profile correlate with their likelihood of conversion? 

---

## Data Overview

The dataset provided contains various attributes of leads and their interaction details with ExtraaLearn.  It includes 4612 observations and 15 columns, with no missing values. 

Key features include:
* `age`: Age of the lead. 
* `current_occupation`: Professional, Unemployed, or Student. 
* `first_interaction`: How the lead first interacted (Website, Mobile App). 
* `profile_completed`: Percentage of profile filled (Low, Medium, High). 
* `website_visits`: Number of website visits. 
* `time_spent_on_website`: Total time spent on the website. 
* `page_views_per_visit`: Average page views per visit. 
* `last_activity`: Last interaction type (Email, Phone, Website Activity). 
* `print_media_type1`, `print_media_type2`, `digital_media`, `educational_channels`, `referral`: Flags for various marketing channels. 
* `status`: Target variable indicating lead conversion (0 = Not Converted, 1 = Converted). 

---

## Key Findings & Visualizations

Here are some of the key insights derived from the exploratory data analysis and model interpretation:

**1. Website Interaction and Time Spent are Crucial for Conversion**
*Insight:* "Time spent on the website" and "first interaction on website" show the strongest positive correlation with a successful lead conversion.  This highlights the website as a highly effective initial touchpoint. Leads who initiated contact via the website show the highest conversion rates compared to the mobile app. 
<img src="./visualizations/status_vs_first_interaction.png" alt="Conversion Rate by First Interaction Channel"/>
*(You can also embed a histogram of 'time_spent_on_website' if you export one to visualize the distribution.)*

**2. Professionals Drive Highest Conversion Rates**
*Insight:* Leads identified as 'Professional' in their current occupation demonstrate the highest lead conversion rates, significantly outperforming 'Unemployed' and 'Student' leads. 
<img src="./visualizations/status_vs_occupation.png" alt="Conversion Rate by Current Occupation"/>

**3. Profile Completion Signals Higher Intent**
*Insight:* Leads who complete a higher percentage of their profile (e.g., 'High' completion) show a greater likelihood of conversion. []This suggests that motivated leads are more invested in providing personal details. 
<img src="./visualizations/status_vs_profile_completed.png" alt="Conversion Rate by Profile Completion"/>

**4. Feature Importance for Lead Conversion**
*Insight:* The machine learning models consistently identified `time_spent_on_website`, `first_interaction_Website`, `profile_completed_Medium` (or `High` depending on encoding), `page_views_per_visit`, and `age` as the most influential factors in predicting lead conversion. 
<img src="./visualizations/rf_feature_importance.png" alt="Feature Importances from Random Forest Model"/>
*(You can also include `dt_feature_importance.png` here.)*

**5. Other Notable Observations**
* **Age Distribution:** The majority of leads are aged between 55-60 years, which aligns with a high proportion of 'Professional' leads. 
* **Website Usage:** While most customers only visit the website 2 times, the average time spent on the website is 376 seconds, with some leads spending up to 2537 seconds. 
* **Last Activity:** Website activity is the most common "last activity" for leads that convert successfully. 
<img src="./visualizations/status_vs_last_activity.png" alt="Conversion Rate by Last Activity"/>
* **Marketing Channels:** Print and digital media, educational channels, and referrals contribute to lead generation, but are not as strongly correlated with conversion as website engagement. 

---

## Actionable Recommendations

Based on the analysis and predictive modeling, ExtraaLearn can implement the following strategies:

* **Prioritize Website Optimization & Marketing:** Given that website interaction and time spent are major drivers of conversion, ExtraaLearn should continue to invest heavily in its website user experience, content, and website-focused marketing campaigns. This includes directing marketing funds towards the website until the mobile app experience is significantly improved. 
* **Enhance Mobile App Experience:** The mobile app's lower conversion rate suggests a need for improvement. The company should investigate missing critical information or user experience gaps on the app that might be hindering conversion. 
* **Target Professionals & Adapt for Students:** The high conversion rate among professionals indicates that current program content strongly appeals to this demographic. ExtraaLearn should explore developing programs and pricing structures (e.g., payment plans) that are more tailored and affordable for students to expand its customer base. 
* **Incentivize Profile Completion:** Since more complete profiles correlate with higher conversion, consider introducing incentives (e.g., discount codes, exclusive content) for leads who complete a significant portion (e.g., >50%) of their profile. 
* **Focus Sales Efforts:** Utilize the developed ML model to identify leads most likely to convert, allowing sales representatives to prioritize their outreach efforts and allocate resources more efficiently to high-potential prospects.  This also helps identify leads less likely to convert, indicating areas where the business is losing potential customers. 

---

## Technical Details

* **Language:** Python 
* **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn (for various algorithms, metrics, and preprocessing). 
* **Dataset:** `edtech_leads.csv` (original data was processed from a CSV file).
* **Analysis Notebook:** `EdTech_Lead_Conversion.ipynb` (the Jupyter Notebook containing all the code).
* **Machine Learning Models Implemented:**
    * Decision Tree Classifier 
    * Random Forest Classifier 
* **Model Evaluation Metrics:** Precision, Recall, F1-score, Accuracy, Confusion Matrix, ROC AUC Score, Classification Report. 
* **Key Techniques:**
    * Exploratory Data Analysis (EDA) 
    * Data Preprocessing (handling categorical variables, dropping ID) 
    * Feature Importance Analysis 
    * Hyperparameter Tuning with GridSearchCV 
    * Splitting data into training and testing sets. 

---
