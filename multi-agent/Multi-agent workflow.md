# Detailed Workflow for Multi-Agent Investment Analysis System

This workflow is designed to ensure smooth collaboration and execution of tasks among the various agents involved in the analysis and decision-making process. The system is divided into multiple modules, each focusing on a specific area of investment analysis for thorough and efficient evaluation. Below is the detailed workflow:

---

## **1. Initialize System Configuration**

### Components:
1. **`investment_group.py`**
   - Defines the organizational structure, roles, and responsibilities of the different analyst groups.
   - Key modules: 
     - Market Sentiment Analysts
     - Risk Assessment Analysts
     - Fundamental Analysts
     - Chief Investment Officer (CIO)
2. **`quantitative_investment_group_config.json`**
   - Outlines specialized factor researchers focused on quantitative investment strategies.
   - Key roles include:
     - Value, Growth, Momentum, Quality, Volatility, Liquidity, Sentiment, and Macro Factor Researchers.
     - Portfolio Manager, Quantitative Analyst, Data Specialist.
3. **`multi-agent/multi_factor_agents.py`**
   - Defines the multi-agent system to process quantitative investment projects.
   - Assigns tasks to each group member or agent based on instructions provided by a leader.
   - Monitors task progress and manages inter-agent communication.

---

## **2. Task Initialization**

### Key Inputs for Task:
- **Main Objectives:**
  - Evaluate Nvidia (NVDA) as a potential investment.
  - Provide a 6-month target price and an investment recommendation.
- **Task Workflow:**
  1. Coordinate with the **Market Sentiment Analysts** to analyze NVDA's market sentiment.
  2. Work with the **Risk Assessment Analysts** to assess NVDA's financial/operational risks.
  3. Collaborate with the **Fundamental Analysts** for financial statement analysis.
  4. Integrate outputs from all groups to provide a comprehensive evaluation.
  
### Main Group Configuration:
- The **Chief Investment Officer (CIO)** acts as the leader, directing task execution across groups.

---

## **3. Group-Level Execution**

### **A. Market Sentiment Analysts**
#### Responsibilities:
- Track and interpret NVDA's market news and social media trends.
- Analyze sentiment by identifying positive and negative mentions.
  
#### Workflow:
1. Leader assigns tasks for retrieving relevant market sentiment data.
2. Analysts utilize tools like `FinnHubUtils.get_company_news` and `RedditUtils.get_reddit_posts`.
3. Aggregate data and calculate a sentiment score.
   - Formula: Sentiment Score = (Positive Mentions - Negative Mentions) / Total Mentions.
4. Deliverable:
   - Provide a sentiment score based on positive vs. negative mentions.
   - Summarize the sentiment's impact on NVDA's stock.

---

### **B. Risk Assessment Analysts**
#### Responsibilities:
- Assess financial and operational risks in NVDA's annual report.
- Monitor market volatility and legal/regulatory risks.

#### Workflow:
1. Leader assigns tasks for evaluating NVDA's risks using Form 20-F data.
2. Analysts define key variables: debt levels, liquidity, regulatory risks, etc.
3. Calculate a risk score using provided weights and formulas in the task:
   - Formula: Risk Score = 0.5 * Debt-to-Equity + 0.3 * (1 / Current Ratio) - 0.2 * ROE.
4. Deliverable:
   - Provide a risk score and written insights into factors contributing to the overall risk assessment.

---

### **C. Fundamental Analysts**
#### Responsibilities:
- Perform an in-depth analysis of NVDA's financial health.
- Calculate key metrics such as Profit Margin and ROA.

#### Workflow:
1. Leader assigns tasks for reviewing NVDA's financial statements.
2. Key calculations:
   - Profit Margin = (Net Income / Revenue) * 100.
   - Return on Assets (ROA) = (Net Income / Total Assets) * 100.
3. Data accessed using tools: `YFinanceUtils` and `FMPUtils`.
4. Deliverable:
   - Report calculated metrics (Profit Margin and ROA) and financial trends.

---

## **4. Integration Phase**

### Tasks for CIO:
1. Collect findings from all groups:
   - Market Sentiment Analysts: Sentiment Score & news insights.
   - Risk Assessment Analysts: Risk Score and risk insights.
   - Fundamental Analysts: Financial metrics and health indicators.
2. Consolidate Results:
   - Develop a holistic view of NVDA's investment attractiveness.
   - Combine quantitative & qualitative insights into a comprehensive report.

---

## **5. Target Price Calculation**

### Workflow:
1. CIO calculates the 6-month target price for NVDA's stock.
   - Factors considered:
     - Current stock price.
     - Sentiment Score.
     - Risk Score.
     - Financial health metrics (Profit Margin, ROA, etc.).
2. Approaches Used:
   - Weighted average considering inputs from all groups.
   - Ensure alignment with risk management principles.

### Deliverable:
- Provide a 6-month target price for NVDA stock.
- Include a clear rationale for the price target and the underlying assumptions.

---

## **6. Final Recommendation**

### Tasks:
1. Using integrated insights, determine whether to invest in NVDA.
2. CIO provides a recommendation:
   - Invest/Don't Invest in NVDA.
   - Justification:
     - Sentiment trends, financial health, and risk factors.
     - 6-month target price and alignment with investment goals.

### Deliverable:
- Comprehensive evaluation report.
- Explicit recommendation with rationale.

---

## **7. Automation Details**

### Multi-Agent Communication:
- **Group_Leader:** Manages all communication within and across groups, ensuring task progress.
- Agents collaborate via nested chats, adhering to provided instructions.
- Executor evaluates Python code provided by agents for automation tasks.

---

## **8. Project Completion**

### Final Steps:
1. CIO reviews the integrated report and confirms the final output.
2. Mark task as **completed** by responding with "TERMINATE."

---

## **9. Technology & Tools Used**
- **NLP Models:**
  - `moonshotai/kimi-k2-instruct`: Used for processing tasks and communication.
  - `llama-3.3-70b-versatile`: Supports decision-making and coordination processes.
- **Data Sources:**
  - Reddit, FinnHub, YFinance, FMP for sentiment and financial analysis.
- **Python Automation:**
  - Backtesting strategies, metrics computation, and script execution handled programmatically.
- **CIO Coordination Engine:**
  - Governs group activities, monitors progress, and ensures output quality.

---
