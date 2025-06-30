Full Project Report: [Summary of my work.docx](https://github.com/user-attachments/files/20902824/Summary.of.my.work.docx)

# 📊🚚⚡️ Data-Driven Analysis of Heavy-Duty EV Adoption Barriers

*A multi-stage strategic analysis project using Python and the Best-Worst Method (BWM) to identify and prioritize the operational challenges facing commercial fleet operators in the transition to electric vehicles.*

---

## 1. Problem Statement

While passenger electric vehicle (EV) adoption is accelerating, the transition for heavy-duty (HD) commercial fleets is slow and fraught with uncertainty. Fleet operators face a complex web of technological, infrastructural, and economic barriers, forcing them to make high-stakes decisions with limited empirical data. Anecdotal evidence is insufficient for strategic planning.

The goal of this project is to move beyond speculation and create a **statistically robust, prioritized ranking of the most critical operational inconveniences** for HD EV adoption. This framework provides a clear, data-driven roadmap for policymakers, manufacturers, and fleet operators to guide investment and accelerate the transition to sustainable transportation.

## 2. The Data: A Multi-Source Approach

To build a comprehensive view of the problem, this analysis integrated **five distinct, publicly available datasets** covering different facets of EV operations. The raw data files are available in the `/data/` directory of this repository.

The datasets cover:
- **EV Adoption & Costs:** Longitudinal data comparing operational costs between EVs and gasoline vehicles.
- **Charging Station Usage:** Extensive records of charging sessions, including timing, duration, and energy consumption.
- **Predictive Maintenance:** Data on battery health (SoH), Remaining Useful Life (RUL), and component failure probabilities.
- **Infrastructure Density:** Geographic distribution and availability of charging stations in the Cleveland area.
- **EV Population & Policy:** Data on vehicle registrations and their correlation with government incentives.

## 3. Tech Stack

This project employed a hybrid set of analytical tools to ensure both statistical rigor and sophisticated decision modeling.

| Category | Technologies |
|---|---|
| **Data Analysis & Visualization** | Python (Pandas, NumPy, Matplotlib, Seaborn) |
| **Decision-Making & Modeling** | Microsoft Excel (for Weighted Scoring and BWM Solver implementation) |
| **Core Tools** | Jupyter Notebook, Git, VS Code |

## 4. Analytical Framework: A Three-Stage Methodology

This project's key innovation is its structured, three-stage approach to transform raw data into a validated, actionable strategy.

### Stage 1: Quantitative Data Analysis (EDA & Correlation)

The first stage involved a deep dive into the five datasets to uncover empirical trends and relationships using Exploratory Data Analysis (EDA).

**Key Findings from EDA:**
- **Cost & Emissions:** Confirmed that while EVs have higher upfront costs, their operational costs are significantly lower and less volatile than gasoline vehicles.
- **Charging Patterns:** Identified clear peak usage on weekdays (Wednesday/Friday) and during midday hours, highlighting potential infrastructure bottlenecks.
- **Maintenance & Reliability:** Revealed weak or negligible linear correlations between Remaining Useful Life (RUL) and operational factors, suggesting that simple predictive maintenance models are insufficient and more complex, non-linear factors influence component health.
![ev_vs_gasoline_cost_comparison](https://github.com/user-attachments/assets/62b3dbfd-f0b0-496a-b3d7-350fd2ac237c)

 <!-- ### TODO: UPDATE THIS LINK (from your PDF's Figure 4.1) ### -->
> *Fig 1: Trend analysis showing the narrowing cost gap between EVs and gasoline vehicles over time.*

### Stage 2: Weighted Scoring Method (WSM)

The insights from Stage 1 were used to develop a preliminary prioritization framework. The WSM translated the qualitative and quantitative findings into a structured scoring model, assigning initial weights and impact scores to each identified operational inconvenience. This step provided a transparent and comparable basis for ranking the challenges.

### Stage 3: Best-Worst Method (BWM) Prioritization

To refine the preliminary ranking with mathematical rigor, the **Best-Worst Method (BWM)** was employed. BWM is a robust multi-criteria decision-making (MCDM) technique that produces highly consistent and reliable weightings by minimizing the number of required pairwise comparisons.

By comparing all criteria against the "best" (most critical) and "worst" (least critical) factors, the BWM model calculates an optimized set of priority weights. This approach reduces cognitive bias and ensures the final ranking is logically sound.
![image](https://github.com/user-attachments/assets/cf65b7cc-cd4d-4b31-8686-24d7a38e59c6)

<!-- ### TODO: UPDATE THIS LINK (from your PDF's Figure 4.12) ### -->
> *Fig 2: Final priority weights calculated by the BWM, highlighting the dominant barriers.*

overall methodology
![image](https://github.com/user-attachments/assets/5bbe48bf-a983-401b-be81-9520e6d2a17e)


## 5. Prioritized Findings & Actionable Recommendations

The BWM analysis produced a clear, data-validated hierarchy of the most significant barriers to HD EV adoption for fleet operators in Cleveland.

| Rank | Barrier | Final BWM Weight | Primary Implication |
|---|---|---|---|
| **1** | **Charging Infrastructure** | **0.376** | The most dominant and immediate deterrent. Lack of accessible, reliable, high-capacity charging is the primary bottleneck. |
| **2** | **Upfront Costs of EVs** | **0.216** | A major financial barrier limiting adoption, especially for small-to-medium-sized fleets. |
| **3** | **Charging Time Efficiency** | **0.216** | Tied with cost, long charging durations directly impact fleet productivity and create operational downtime. |
| **4** | **Vehicle Range** | **0.144** | An important but secondary concern, likely due to improving battery technology and localized route patterns. |
| **5** | **Other Factors** | **0.048** | Includes battery health, incentives, and maintenance predictability, which are less critical during the pre-adoption phase. |

Based on these findings, the core recommendations are to:
1.  **Strategically Expand DC Fast Charging Infrastructure** in underserved industrial and commercial zones.
2.  **Strengthen and Target Financial Incentives** to close the upfront cost gap for commercial fleet operators.
3.  **Invest in Technologies and Software** that optimize charging schedules and minimize operational downtime.

## 6. How to Reproduce This Analysis

This repository contains the necessary data and analytical artifacts to review and reproduce the findings.

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/shafiatunnurshimu23/operational-inconveniences-ev-data-analysis.git
    cd operational-inconveniences-ev-data-analysis
    ```
2.  **Explore the Data Analysis:**
    - The Python-based Exploratory Data Analysis and correlation analyses can be found in the Jupyter Notebooks located in the `/notebooks/` directory.
    - All raw and processed datasets are available in the `/data/` directory.

3.  **Review the Prioritization Model:**
    - The final, decisive prioritization using the Best-Worst Method was implemented in the **`BWM-Solver.xlsx`** file.
    - This Excel file contains the structured pairwise comparisons, the linear programming model setup, and the final calculated weights and consistency ratio, providing full transparency into the decision-making process.
