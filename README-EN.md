# 📊 Document Compliance and Regulatory Review Dashboard

<p align="center">
  <strong>Power BI • DAX • ETL • SharePoint • Business Intelligence</strong>
</p>

> ⚠️ This project was developed for portfolio purposes.
>
> Some information has been anonymized and adapted to preserve the confidentiality of organizational data, processes, and business information.

---

## 📑 Table of Contents

- About the Project
- Business Context and Challenge
- First Version of the Solution
- Complete Redesign and Optimization
- Data Refresh Automation
- Dashboard Structure
- Data Transformation and Preparation
- Data Modeling
- Calculated Columns
- Metrics and KPIs
- Dashboard Features
- Challenges and Solutions
- Results Achieved
- Technologies Used
- Key Learnings
- Author
- License

---

# 📖 About the Project

This project was developed by **Rennan de Oliveira Penga** during my experience working in Governance, Risk Management, Internal Controls, and Security.

The objective was to create a Power BI solution capable of monitoring document compliance, tracking the regulatory review cycle, and providing business indicators that support decision-making.

The project transformed data spread across multiple Excel spreadsheets into a centralized analytical platform, enabling the identification of expired documents, monitoring records without expiration dates, highlighting critical areas, and analyzing the evolution of compliance indicators over time.

In addition to providing an executive view of document compliance, the dashboard also enables operational and historical analyses in a practical and intuitive way.

---

# 🎯 Business Context and Challenge

The data used in this project was extracted periodically from Excel files.

Although the files contained similar information, they presented several issues that made analysis difficult:

- Different structures across data extracts;
- Inconsistent column names;
- Duplicate records;
- Missing values;
- Inconsistent information;
- Documents without expiration dates;
- Need for historical comparison between periods.

These inconsistencies increased the manual effort required to consolidate the data and made it difficult to generate reliable business indicators.

The main challenge was transforming this process into a scalable, automated, and maintainable solution capable of delivering strategic insights.

---

# 🏗️ First Version of the Solution

The first version of the dashboard was built using three historical datasets collected at different points in time.

Because each dataset had structural differences, several transformations were required before the information could be consolidated.

To support historical analysis, an **Analysis Date** column was created to identify the extraction period associated with each document.

After consolidating the data, DAX measures, KPIs, filters, and reports were developed to monitor document compliance.

Although the solution initially met business requirements, the model gradually became more complex than necessary as new adjustments and fixes were implemented.

Over time, duplicated tables and additional merge operations were created to address data-specific issues. While functional, these solutions increased file size, refresh time, and overall maintenance complexity.

---

# 🚀 Complete Redesign and Optimization

During maintenance activities, it became clear that rebuilding the solution from scratch would be more effective than continuously applying fixes.

The redesigned version focused on:

- Reducing model complexity;
- Improving performance;
- Simplifying maintenance;
- Automating data refresh processes;
- Increasing scalability for future growth.

The entire architecture was reviewed, including data transformations, relationships, calculations, and refresh processes.

Unnecessary tables, redundant processes, and excessive merge operations were removed, resulting in a cleaner and more efficient solution.

---

# 🔄 Data Refresh Automation

One of the most significant improvements implemented was the automation of the refresh process.

In the original version, updating the dashboard could take approximately **4 hours**, including data import, transformation, validation, and report refresh.

The redesigned solution introduced SharePoint integration.

The refresh process now consists of only three steps:

1. Download the latest data extract;
2. Upload the file to a designated SharePoint folder;
3. Refresh the Power BI dataset.

A query was developed to automatically retrieve all files stored in the SharePoint folder.

Additionally, the SharePoint file creation date became the reference date for analysis.

Since files are uploaded on the same day they are extracted, there was no longer a need to manually create an Analysis Date column for every new dataset.

As a result, the refresh process became significantly faster, simpler, and easier to maintain.

---

# 📊 Dashboard Structure

The solution was developed with a focus on monitoring document compliance and regulatory indicators.

The dashboard consists of four main sections:

### 📈 Executive Overview

Provides a consolidated view of compliance indicators and executive-level performance metrics.

### ⚠️ Expired Documents

Dedicated page for analyzing documents that are out of compliance due to expired validity dates.

### 🔥 Top 50 Most Viewed Documents

Highlights the most frequently accessed documents and their compliance status.

### 📄 Documents Without Expiration Dates

Focuses on identifying records missing expiration dates and supporting data quality improvement initiatives.

---

# 🧹 Data Transformation and Preparation

Data preparation was performed using Power Query.

The main transformation steps included:

- Automated file import;
- Column name standardization;
- Data type corrections;
- Null value handling;
- Duplicate removal;
- Historical dataset consolidation;
- Adjustments for legacy files with different structures;
- Simplification of existing merges and transformations.

One of the historical datasets had a different structure from the others and required a dedicated transformation process to maintain compatibility with the overall model.

During the dashboard redesign, a more efficient data organization approach was implemented, reducing unnecessary dependencies between queries and making future updates easier to manage.

---

# 🗂️ Data Modeling

After consolidating the data, a cleaner and more efficient data model was designed.

A dedicated dimension table was created containing:

- Document ownership areas;
- Corresponding executive management units;
- Relationships required for filtering and reporting.

This approach reduced data redundancy, improved model organization, and simplified user navigation throughout the dashboard.

The new structure also enabled hierarchical filtering and better overall performance.

---

# ⚙️ Calculated Columns

During the model redesign, several transformations that were previously developed in Power Query were moved to DAX, reducing ETL complexity and simplifying maintenance.

### Expiration Date Information

Identifies whether a document has a defined expiration date.

Classifications:

- With Expiration Date
- Indefinite

### Days Overdue

Calculates the number of days a document has remained expired relative to the analysis date.

This column helps identify critical documents and prioritize corrective actions.

### Document Type

Extracts the prefix from the document identifier.

Example:

```text
AB-0001
```

Result:

```text
AB
```

### Sequential Number

Extracts the numeric portion of the document identifier.

Result:

```text
0001
```

### Document Category

Translates document prefixes into their corresponding document categories.

Example:

```text
AB → Biological Analysis
```

### Validity Status

Automatically classifies document compliance conditions.

Categories:

- Up to Date;
- Expires Within 30 Days;
- Expired for More Than 12 Months;
- Expired for More Than 6 Months;
- Expired for More Than 3 Months;
- Expired for More Than 1 Month;
- Expired for Less Than 1 Month;
- Indefinite.

These classifications were used across indicators, visualizations, and conditional formatting rules to improve readability and business interpretation.

---

# 📏 Metrics and KPIs

Several DAX measures were developed throughout the project to support business requirements.

### ICCRNC

Indicator used to calculate the percentage of documents that remain within their validity period.

### ICCRNC Non-Compliance

Indicator used to calculate the percentage of expired documents.

### Top 50 Most Viewed Documents

Ranking designed to identify the most frequently accessed documents and monitor their compliance status.

### Criticality Indicators

Metrics created to identify areas with the highest number and percentage of expired documents.

### Conditional Formatting

Measures responsible for dynamically modifying:

- Indicator colors;
- Text labels;
- KPI cards;
- Tables;
- Visual elements.

This approach automatically highlights critical situations and improves decision-making.

---

# 📊 Dashboard Features

## 📈 Executive Overview

Provides a consolidated view of the organization's document compliance status.

Features:

- Overall compliance indicators;
- Area filters;
- Executive management filters;
- Percentage of valid and expired documents;
- Historical trend analysis;
- Ranking of critical areas.

---

## ⚠️ Expired Documents Analysis

Dedicated page focused on documents that are no longer compliant.

Features:

- Ranking of areas with the highest number of expired documents;
- Classification by overdue period;
- Identification of critical documents;
- Number of overdue days by document.

---

## 🔥 Top 50 Most Viewed Documents

Designed to identify the most relevant documents for the business.

Features:

- Ranking of the 50 most accessed documents;
- Visual compliance status identification;
- Unique document identifier display.

---

## 📄 Documents Without Expiration Dates

Created to identify documentation records with missing validity information.

Features:

- Number of documents without expiration dates;
- Distribution by document category;
- Classification by document type;
- Support for data quality improvement initiatives.

---

# 💡 Challenges and Solutions

One of the main challenges involved presenting document details through tooltips.

The initial idea was to display large lists of documents directly within visual tooltips.

However, due to the volume of information, navigation became limited and negatively impacted usability.

To solve this issue, dedicated detail pages were created and connected through navigation buttons, allowing users to access complete information without compromising dashboard performance or user experience.

Additionally, the complete redesign of the solution became an important opportunity to improve skills related to data model optimization, ETL simplification, and process automation.

---

# 📈 Results Achieved

✅ Refresh process reduced from approximately 4 hours to just a few minutes.

✅ Near fully automated update process.

✅ Automated SharePoint integration.

✅ Significant reduction in model complexity.

✅ Improved report performance.

✅ Reduced maintenance effort.

✅ Better organized and scalable architecture.

✅ Improved user experience.

✅ Increased reliability of business indicators.

✅ Greater flexibility for future enhancements.

The project evolved from a functional reporting solution into a scalable and maintainable business intelligence platform.

---

# 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| Power BI | Dashboard development |
| DAX | Calculations and KPIs |
| Power Query | ETL and data transformation |
| SharePoint | Automation and storage |
| Excel | Data source |
| SQL | Data querying and manipulation |
| Python | Automation and supplementary analysis |
| Data Modeling | Analytical structure |
| Data Visualization | Dashboard design and reporting |

---

# 📚 Key Learnings

During this project, I strengthened my knowledge in:

- Power BI;
- DAX;
- Power Query;
- ETL Processes;
- Data Modeling;
- SharePoint Integration;
- Process Automation;
- Performance Optimization;
- KPI Development;
- Data Governance;
- Data Visualization;
- Dashboard User Experience (UX);
- Data-Driven Decision Making.

Beyond the technical aspects, this project reinforced the importance of designing scalable solutions from the beginning and maintaining a balance between performance, usability, and maintainability.

---

# 👨‍💻 Author

**Rennan de Oliveira Penga**

Systems Analysis and Development (ADS) student focused on Data Analytics, Business Intelligence, and Process Automation.

Experienced in Power BI, SQL, Python, data modeling, ETL processes, and the development of data-driven solutions that support decision-making and organizational improvement.

### 🔗 Contact

- GitHub: https://github.com/rehkkj
- LinkedIn: https://linkedin.com/in/rennan-oliveira-426320283
- Email: rennanpenga@gmail.com

---

# 📄 License

This project is licensed under the **MIT License**.

See the `LICENSE` file for more information.
