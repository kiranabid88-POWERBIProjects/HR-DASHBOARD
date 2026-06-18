# HR-DASHBOARD
A 4-page Power BI dashboard analyzing workforce demographics, attrition, and employee satisfaction for a fictional UK tech company, Nexoria Technologies. Built on a star schema with 25+ DAX measures.
DASHBOARD PAGES

Overview — Total/active employees, attrition rate, average income, experience, age, tenure, headcount by department, gender split. Synced slicers: Department, Gender, Age Group.

Screenshorts/Overview.png

Attrition — 167 employees lost, 17% attrition rate, average tenure lost (5.28 yrs), breakdown by department, job role, gender, marital status, business travel.

Screenshorts/Attrition.png

Workforce — Age distribution, education field/level, job level split, marital status, average commute distance.

Screenshorts/Workforce.png

Growth Metrics — Satisfaction heatmap (department × metric), satisfaction score breakdown, performance by department, training time averages, overtime impact on work-life balance.(Growth Metrics.png)
DATA MODEL

Star schema — 1 fact table, 4 dimension tables:

Fact_Employee — satisfaction scores, performance, income, attrition, tenure
Dim_Department, Dim_Level, Dim_Location, Dim_Date

Star schema avoids many-to-many conflicts and keeps filter context predictable.

DAX MEASURES
Attrition Rate = DIVIDE([Total Attrition], [Total Employees])

Average tenure lost (avg YearsAtCompany for leavers).

Satisfaction averages (Job, Environment, WLB, Relationship).

Performance by department using AVERAGE on PerformanceRating.

Overtime impact on WLB — CALCULATE with boolean filters.

Dual-format measures (numeric + text) — FORMAT() breaks native data bars, so each metric needed two separate measures.

DATA PREPRATIONS

Excel — initial cleaning and validation on the raw IBM HR dataset.

Power Query (M) — custom Exit Date column (handles nulls, zeros, future dates), custom date table, duplicated queries when reshaping data for specific visuals

Power BI / DAX — modeling, measures, conditional formatting
Tools

Power BI Desktop · DAX · Power Query (M) · Microsoft Excel · PowerPoint (custom backgrounds)
