# Data Scientist Job Market Analysis (Poland & Global)

## # INTRODUCTION
This project involves a deep dive into the Data Science job market to extract actionable insights for career development. By analyzing a comprehensive dataset of job postings, I aimed to navigate the complex landscape of salaries, skills, and market demand.

The analysis focuses on two key dimensions:
1.  **Local Market (Poland):** Identifying top-paying roles and employers specifically within Poland.
2.  **Global/Remote Market:** Analyzing broader trends to find the "optimal" skills that combine high demand with high salary potential for remote opportunities.

Through a series of advanced SQL queries, this project answers critical questions such as:
- What are the highest-paying Data Scientist roles currently available in Poland?
- Which technical skills are required to land these top-tier positions?
- What are the most in-demand skills globally for Data Scientists?
- Which niche skills command the highest salaries?
- What is the "sweet spot"—the intersection of high demand and high salary?

## # BACKGROUND
The motivation behind this project was to move beyond anecdotal evidence and general career advice. As an aspiring Data Scientist, I wanted to base my learning path on hard data.

Understanding that the tech market is volatile, I sought to identify:
- **High-Value Skills:** Which technologies offer the best Return on Investment (ROI) for learning time?
- **Market Stability:** Which skills are consistently in demand?
- **Local vs. Global Opportunities:** How the requirements differ between the local Polish market and the global remote job market.

This project simulates a real-world data analysis workflow, from hypothesis generation to SQL query execution and insight interpretation.

## # TOOLS I USED
To conduct this analysis, I utilized a robust stack of data engineering and analysis tools:

* **SQL:** The core engine of the analysis. I used SQL for querying, filtering, aggregating, and joining complex datasets.
* **PostgreSQL:** The database management system used to host the job postings data, chosen for its reliability and advanced features.
* **Visual Studio Code:** My primary Integrated Development Environment (IDE) for database management and executing SQL queries.
* **Git & GitHub:** Used for version control to track changes in my SQL scripts and to share the final analysis and findings.

## # THE ANALYSIS
The project is broken down into five distinct phases, each addressed by a specific SQL query.

### 1. Top Paying Jobs in Poland
**File:** `1.top_paying_jobs.sql`

I began by isolating the highest-paying job opportunities specifically for Data Scientists in Poland.
- **Methodology:** I filtered the dataset for the 'Data Scientist' role and the location 'Poland', removing entries with null salary values.
- **Goal:** To establish a salary benchmark and identify the companies leading the local market in terms of compensation.

### 2. Skills for Top Paying Jobs
**File:** `2.top_paying_job_skills.sql`

Building upon the previous query, I extracted the specific skills required for these top 10 highest-paying roles in Poland.
- **Methodology:** Using `INNER JOINs`, I connected the job postings to the skills dimension table.
- **Insight:** This revealed the specific tech stack (e.g., Python, SQL, Cloud platforms) that top employers in Poland are looking for right now.

### 3. Top Demanded Skills
**File:** `3.top_demanded_skills.sql`

Expanding the scope, I analyzed the frequency of requested skills across all Data Scientist job postings.
- **Methodology:** I used aggregate functions (`COUNT`) and grouped the data by skill to rank them by popularity.
- **Goal:** To identify the "must-have" foundational skills that appear in the majority of job descriptions, regardless of salary.

### 4. Top Paying Skills
**File:** `4.top_paying_skills.sql`

Conversely, I looked at the average salary associated with individual skills to find the most lucrative technologies.
- **Methodology:** I calculated the average salary (`AVG`) for each skill and grouped the results.
- **Insight:** This highlighted specialized, niche skills (often related to Big Data or specific Cloud architectures) that command a premium in the market.

### 5. Optimal Skills (High Demand + High Salary)
**File:** `5.optimal_skills.sql`

The final and most complex part of the analysis involved finding the optimal skills—those that are both widely available (high demand) and well-paid.
- **Methodology:** I utilized **CTEs (Common Table Expressions)** to create two temporary datasets:
    1.  `skill_demand`: Counts the number of job postings for each skill.
    2.  `average_salary`: Calculates the average salary for each skill.
    I then joined these CTEs to filter for skills with a demand count > 10 and ordered them to find the best balance.
- **Goal:** To pinpoint the most strategic skills to learn for a high-salary remote career in Data Science.

## # WHAT I LEARNED
This project was instrumental in sharpening my SQL toolkit. Key technical takeaways include:

* **Advanced Query Construction:** I mastered the use of **CTEs (Common Table Expressions)** to break down complex problems into manageable, modular logic steps (as seen in the `optimal_skills` query).
* **Data Aggregation:** I became proficient in using aggregate functions like `COUNT()`, `AVG()`, and `ROUND()` combined with `GROUP BY` to summarize large datasets.
* **Complex Joins:** I gained confidence in joining multiple tables (`job_postings_fact`, `skills_job_dim`, `skills_dim`, `company_dim`) to extract meaningful relationships between jobs, companies, and skills.
* **Data Cleaning:** I learned the importance of filtering out incomplete data using `IS NOT NULL` and validating data types to ensure accurate analysis.
* **Order of Operations:** Understanding the difference between `WHERE` (filtering raw rows) and `HAVING` (filtering aggregated groups) was crucial for correct results.

## # CONCLUSIONS
Based on the data analysis, several key trends emerged for aspiring Data Scientists:

1.  **Foundational Skills are Non-Negotiable:** Skills like SQL and Python dominate the demand charts. They are the entry ticket to the industry.
2.  **Specialization Pays Off:** While general skills get you hired, specialized skills (often in Cloud Computing or Big Data frameworks) are what drive salaries to the top tier.
3.  **The "Optimal" Strategy:** The best career path involves mastering high-demand skills to ensure job security, while progressively adding high-paying niche skills to maximize earning potential.
4.  **Location Matters:** The distinction between local (Poland) and global remote roles influences the salary potential and required skill sets, suggesting that openness to remote work significantly expands career opportunities.