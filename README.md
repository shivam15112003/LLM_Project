# 🧠 AtliQ T-Shirts: LLM-Powered SQL Assistant

A full-stack LangChain + Google Palm LLM project that translates **natural language** questions into SQL to query a **MySQL database** for business insights about AtliQ's T-shirt inventory and pricing.

---

## 🚀 Features

* 🔍 Ask natural language questions (e.g., *"How many Levi’s white shirts do we have left?"*)
* 🧠 Powered by **Google Palm + LangChain** for intelligent SQL generation
* 🧾 Uses **few-shot learning** to improve query accuracy
* 📦 Embedding-based **semantic example selection** with HuggingFace + Chroma
* 📈 Streamlit frontend with live query results and reasoning steps
* ✅ Works with real MySQL database (schema included)

---

## 📊 Sample Questions

* "Total inventory value of small-size T-shirts"
* "Revenue from Levi’s sales post discount"
* "Stock of white Adidas shirts"

---

## 🧱 Stack

* **LLM**: Google Palm (LangChain wrapper)
* **Database**: MySQL (`atliq_tshirts` with `t_shirts` and `discounts`)
* **LangChain**: `SQLDatabaseChain`, `FewShotPromptTemplate`, `Chroma`
* **UI**: Streamlit

---

## ⚙️ Setup

1. **Install dependencies**:

```bash
pip install -r requirements.txt
```

2. **Create `.env` file**:

```
GOOGLE_API_KEY=your-key-here
```

3. **Ensure MySQL is running** with the provided schema:

```sql
-- See schema in methodology file
```

4. **Run Streamlit app**:

```bash
streamlit run app.py
```

---

## 📂 File Structure

```
├── app.py                # Streamlit frontend
├── langchain_helper.py  # Main LLM + chain setup
├── few_shots.py         # Sample SQL QA examples
├── .env                 # API key
├── requirements.txt     # All dependencies
└── README.md            # You are here
```

---

## 🧪 Evaluation

Tested on 10+ NL-to-SQL queries.

* ✔ Correct column usage enforced
* ✔ SUM + JOIN patterns learned via prompt
* ✔ Queries handle brand, size, color, discount cases accurately

---

## 👔 Why This Matters

This project is a practical demo of how **LLMs + LangChain** can power natural-language BI tools, helping non-technical users access database insights.

---

## 🛠 Future Enhancements

* Add SQL schema viewer in UI
* Allow voice-based questions
* Support multi-table joins with richer context

---

Made with 💡 by Shivam — integrating LLMs for real-world data intelligence.
