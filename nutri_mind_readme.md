# 🥗 NutriMind: An Agentic AI Nutrition Assistant Powered by IBM watsonx

**NutriMind** is an advanced proof-of-concept AI agent designed to deliver **personalized nutritional guidance** using a powerful agentic architecture. Built end-to-end on the **IBM watsonx** platform, this AI assistant intelligently combines **retrieval-augmented generation (RAG)**, reasoning capabilities, and multi-tool decision-making to act as a **virtual nutrition expert** for every user.

> 🚀 Developed as a Capstone Project\
> 🤖 No traditional training — powered by prompt + agent engineering\
> 🔬 Built and deployed on IBM Cloud using watsonx.ai, PromptLab & AgentLab\
> 📊 Backed by a cleaned, vectorized Kaggle dataset\
> 🧠 ReAct + LangGraph-based agent framework

---

## 📌 What This Project Does

- ✅ Generates multi-option, user-specific **meal plans**
- ✅ Recommends intelligent, contextual **food swaps**
- ✅ Integrates **RAG** to answer with verifiable facts
- ✅ Uses **real-time tools** like Google Search and Wikipedia when needed
- ✅ Supports **health goals**, medical conditions, allergies, calorie targets

---

## 💠 Built With

- **IBM watsonx.ai Studio** – End-to-end no-code AI platform
- **Agent Lab** – Assembled NutriMind agent using **LangGraph** and **ReAct**
- **Prompt Lab** – Engineered and validated RAG & prompt workflows
- **Models Used**:
  - 🧠 `llama-3-3-70b-instruct` – core reasoning engine
  - 💬 `granite-3-8b-instruct` – prototyping + food reasoning
  - 🔍 `granite-embedding-278m-multilingual` – RAG embedding
- **Data Pre-processing**: Microsoft Excel
- **Cloud Deployment**: IBM Cloud Lite Tier

---

## 🧠 Technical Architecture

```plaintext
📦 Dataset: Daily Food and Nutrition Dataset (Kaggle)
🔧 Preprocessing: Cleaning, normalization in Excel
📚 Knowledge Base: RAG vector index created using watsonx Embedding Model
🧪 Prompt Engineering: Core logic for meal plan & swaps in Prompt Lab
🧹 Agent Assembly: Agent Lab + LangGraph for tool chaining
🔀 Intelligence: ReAct (Reason + Act) flow for tool decision logic
💠 Tools: RAG DB, Google Search, Wikipedia, Web Crawler
🚀 Deployment: Hosted live on IBM Cloud with testing interface
```

---

## 📁 Project Directory Structure

```plaintext
📁 data/
├── 📄 cleaned_daily_food_nutrition_dataset.pdf
├── 📄 daily_food_nutrition_dataset.csv
📁 notebooks/
├── 🤖 nutrimind_final.ipynb
├── 🧠 rag_vector_index.ipynb
📁 screenshots/
├── 📁 agentlab_output/
│   ├── 🧠 Multi-constraint user query
│   └── 🥗 Context-Aware nutritional advice
├── 📁 deployed_result/
│   └── 🌐 API preview
├── 📁 promptlab_result/
│   ├── ✅ Validation of the RAG pipeline
│   ├── 🍽️ Meal Plan
│   └── 🔄 Food Swap
📄 Capstone.pptx
📄 LICENSE
📄 README.md
```

---

## 🔮 Future Enhancements

- 📷 **Image Input**: Integrate Watson Visual Recognition for food scans
- 🎤 **Voice Input**: Add Watson Speech-to-Text for spoken interaction
- 🔀 **Dynamic Feedback Loop**: Personalize based on preferences + feedback
- 🧬 **Health API Integration**: Pull activity data from smartwatches

---

## 🗏️ References

- 📘 Kaggle Dataset: [Daily Food and Nutrition Dataset](https://www.kaggle.com/datasets/adilshamim8/daily-food-and-nutrition-dataset)
- 📚 RAG Paper: [Lewis et al. (2020)](https://arxiv.org/abs/2005.11401)
- 🧠 ReAct Paper: [Yao et al. (2023)](https://arxiv.org/abs/2210.03629)
- 🔧 IBM Docs: [watsonx.ai Documentation](https://cloud.ibm.com/docs/watsonx-ai)

---

## 👤 Author

**Gurpreet Singh**\
B.Tech CSE, Presidency University, Bengaluru\
Capstone Project | IBM watsonx | AI for Healthcare

