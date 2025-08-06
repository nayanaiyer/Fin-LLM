## Notebook 1: rag_qa_single_agent.ipynb — Q&A over SEC Filings


Workflow:
1. Define Ticker and Year

- User inputs the ticker (e.g., MSFT) and fiscal year (e.g., 2023).

2. Load or Fetch SEC 10-K Report

- Downloads and stores the 10-K filing locally if not already cached.

3. Document Chunking and Indexing

- Splits the 10-K text into manageable chunks.

4. Create a RAG Agent

- Combines a retriever with an LLM-based answer generator.

- Configures a custom prompt and interaction logic.

5. User Interaction

- User asks a financial question.

- The agent retrieves relevant 10-K passages and generates a detailed answer.

## Notebook 2: annual_report_single_agent.ipynb — Generate Annual Report

Workflow:

1. Setup Company Context

- User defines company name and fiscal year (e.g., Microsoft, 2023).

- Constructs an instruction message using dedent() to control agent behavior.

2. Launch Assistant Agent

- A SingleAssistant (or subclass) is instantiated.

- Instruction message is passed to the agent with tool access.

3. Tool Usage Begins
The assistant performs the following steps:

- get_sec_report: Downloads 10-K filing from SEC.

- analyze_*: Extracts insights from each section (income, segments, cash flow, risk, etc.)

- summarize: Combines insights into paragraphs.

- get_pe_eps_performance / get_share_performance: Generates charts.

- build_annual_report: Assembles the full PDF.

4. Word Count Enforcement

- Assistant ensures content is between 400–450 words before creating the PDF.

- Report Generation

Final PDF is saved and ready for sharing.