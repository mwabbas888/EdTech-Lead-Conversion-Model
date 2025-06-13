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

The dataset provided contains various attributes of leads and their interaction details with ExtraaLearn. It includes 4612 observations and 15 columns, with no missing values.

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

Here are some of the key insights derived from the exploratory data analysis and model interpretation, supported by visualizations:

### 1. Understanding Lead Demographics and Behavior

**Age Distribution:**
*Insight:* The majority of ExtraaLearn's leads fall within the 55-60 age range, indicating a significant portion of their audience is likely composed of experienced professionals.
<img src="./visualizations/Customer Age vs count.png" alt="Customer Age Distribution"/>

**Website Engagement Metrics:**
*Insight:* While most leads visit the website only a few times, a considerable portion spends significant time, with two noticeable peaks in engagement duration. Page views per visit also show varied engagement patterns.
<img src="./visualizations/Time spent on website vs count.png" alt="Time Spent on Website Distribution"/>
<img src="./visualizations/Website visits vs count.png" alt="Website Visits Distribution"/>
<img src="./visualizations/Page views per visit vs count.png" alt="Page Views Per Visit Distribution"/>

### 2. Key Drivers of Lead Conversion

**Correlation with Conversion Status:**
*Insight:* The correlation heatmap highlights `time_spent_on_website` (0.30) and `age` (0.12) as the strongest positive correlations with lead conversion, indicating these are critical factors to focus on.
<img src="./visualizations/Heatmap.jpg" alt="Correlation Heatmap of Numerical Features"/>

**First Interaction Channel Impact:**
*Insight:* Leads whose first interaction was via the **Website** show a significantly higher conversion rate compared to those interacting through the Mobile App. This suggests the website is a more effective initial touchpoint.
<img src="./visualizations/First interaction vs percentage conversion.png" alt="Conversion Rate by First Interaction"/>

**Current Occupation and Conversion:**
*Insight:* **Professional** leads demonstrate the highest conversion rates, reinforcing the idea that ExtraaLearn's programs highly appeal to this demographic.
<img src="./visualizations/Status vs occupation.png" alt="Conversion Rate by Current Occupation"/>

**Profile Completion as an Indicator:**
*Insight:* Leads who complete a **'High'** percentage of their profile are considerably more likely to convert, indicating a strong level of engagement and motivation.
<img src="./visualizations/Profile Completed vs percentage conversion.png" alt="Conversion Rate by Profile Completion"/>

**Last Activity Channel Impact:**
*Insight:* Leads with **Website Activity** as their last interaction show the highest conversion rates, further emphasizing the importance of the website in the conversion funnel.
<img src="./visualizations/Last activity vs percentage conversion.png" alt="Conversion Rate by Last Activity"/>

### 3. Machine Learning Model Insights

**Decision Tree Visualization:**
*Insight:* A pruned Decision Tree model (max_depth=7) was built to predict lead conversion. The visual representation helps in understanding the decision rules and splits that the model uses based on various lead attributes.
<img src="./visualizations/Decision Tree.jpg" alt="Visualized Decision Tree Model"/>

**Feature Importances from Models:**
*Insight:* Both Decision Tree and Random Forest models consistently identify `time_spent_on_website`, `first_interaction_Website`, `profile_completed_Medium`, `page_views_per_visit`, and `age` as the most influential features for predicting lead conversion. These align well with the EDA findings.
<img src="./visualizations/Feature Importance.png" alt="Decision Tree Feature Importances"/>
<img src="./visualizations/RF Feature Importance.png" alt="Random Forest Feature Importances"/>

---

## Actionable Recommendations

Based on the analysis and predictive modeling, ExtraaLearn can implement the following strategies:

* **Prioritize Website Optimization & Marketing:** Given that website interaction and time spent are major drivers of conversion, ExtraaLearn should continue to invest heavily in its website user experience, content, and website-focused marketing campaigns. This includes directing marketing funds towards the website until the mobile app experience is significantly improved.
* **Enhance Mobile App Experience:** The mobile app's lower conversion rate suggests a need for improvement. The company should investigate missing critical information or user experience gaps on the app that might be hindering conversion.
* **Target Professionals & Adapt for Students:** The high conversion rate among professionals indicates that current program content strongly appeals to this demographic. ExtraaLearn should explore developing programs and pricing structures (e.g., payment plans) that are more tailored and affordable for students to expand its customer base.
* **Incentivize Profile Completion:** Since more complete profiles correlate with higher conversion, consider introducing incentives (e.g., discount codes, exclusive content) for leads who complete a significant portion (e.g., >50%) of their profile.
* **Focus Sales Efforts:** Utilize the developed ML model to identify leads most likely to convert, allowing sales representatives to prioritize their outreach efforts and allocate resources more efficiently to high-potential prospects. This also helps identify leads less likely to convert, indicating areas where the business is losing potential customers.

---

## Technical Details

* **Language:** Python
* **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn (for various algorithms, metrics, and preprocessing).
* **Dataset:** `edtech_leads.csv` (original data was processed from a CSV file).
* **Analysis Notebook:** `EdTech_Lead_Conversion.ipynb` (the Jupyter Notebook containing all the code).
* **Machine Learning Models Implemented:**
    * Decision Tree Classifier (with hyperparameter tuning)
    * Random Forest Classifier (with hyperparameter tuning)
* **Model Evaluation Metrics:** Precision, Recall, F1-score, Accuracy, Confusion Matrix, ROC AUC Score, Classification Report.
* **Key Techniques:**
    * Exploratory Data Analysis (EDA)
    * Data Preprocessing (handling categorical variables, dropping ID)
    * Feature Importance Analysis
    * Hyperparameter Tuning with GridSearchCV
    * Splitting data into training and testing sets.

---

### 3. Organize Your Project Files (Final Check)

Please ensure your repository has this exact structure and filenames:
