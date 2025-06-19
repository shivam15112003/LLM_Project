## 🧠 Methodology: LLM-Based SQL Query System for AtliQ T-Shirts

This project showcases a LangChain-powered LLM application that translates natural language questions into SQL to query a MySQL database containing inventory and pricing data for T-shirts. It leverages few-shot learning, semantic search, and custom prompting.

---

## 1️⃣ Database Setup
- A MySQL database `atliq_tshirts` with two key tables: `t_shirts` and `discounts`.
- Sample data includes brand, size, color, price, stock quantity, and discount percentages.

---

## 2️⃣ Language Model
- **LLM Used:** Google Palm
- **Prompt Strategy:** Few-shot learning via LangChain’s `FewShotPromptTemplate`
- **Similarity Selection:** Top 2 closest examples are selected via sentence embeddings using **HuggingFace + Chroma**.

---

## 3️⃣ Prompt Engineering
- A structured MySQL prompt ensures:
  - Query formation with only relevant columns
  - No SELECT * usage
  - Use of `LIMIT`, `GROUP BY`, `SUM()`, and `JOIN` as required
  - Correct handling of discount logic
- Prompt template includes slots for `Question`, `SQLQuery`, `SQLResult`, `Answer`.

---

## 4️⃣ Few-Shot Learning
- A curated list of Q&A SQL examples is used to guide the LLM.
- Semantic similarity search ensures only relevant examples are chosen for each new query.
- Addresses common LLM errors like:
  - Forgetting `SUM()` over quantity fields
  - Misinterpreting `price` as total vs. per unit
  - Assuming columns like `start_date` exist when they don’t

---

## 5️⃣ Chain Architecture
- LangChain’s `SQLDatabaseChain` is used with:
  - MySQL dialect
  - Verbose debug tracing
  - Intermediate step return (for transparency in Streamlit)

---

## 6️⃣ User Interface (Streamlit)
- A Streamlit app lets users:
  - Input natural language queries
  - View SQL reasoning/steps
  - Try sample questions from the sidebar

---

## 🧪 Example Queries Handled
- "How many Levi’s white shirts are left in stock?"
- "What’s the total revenue post discount for all Nike L-sized T-shirts?"
- "Show me the inventory value for S-size T-shirts"

---

## 🔍 Final Outcome
This system demonstrates:
- Robust translation of NL questions to SQL
- Use of few-shot LLM guidance with real-world DB edge cases
- Seamless UI for non-technical business stakeholders
