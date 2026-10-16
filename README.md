# 🥗 NutriMind: An LLM Nutrition Assistant Prototype on IBM watsonx

**NutriMind** is a capstone **proof-of-concept** AI agent that generates personalized meal-plan and food-swap suggestions. It was prototyped on the **IBM watsonx** platform and combines **retrieval-augmented generation (RAG)** over a nutrition dataset with a **ReAct** tool-calling agent.

> 🎓 Developed as a capstone project (Edunet Foundation / IBM SkillsBuild)
> 🤖 No model training: built with prompt engineering and agent configuration
> 🔬 Prototyped in watsonx Prompt Lab & Agent Lab and deployed to a watsonx deployment space (IBM Cloud Lite tier; no longer live)
> 📊 Knowledge base: a Kaggle food-nutrition dataset indexed as a vector index (see *Known Limitations* below)
> 🧠 ReAct agent built with LangGraph

---

## 📌 What This Prototype Demonstrates

* Generates multi-option, user-specific **meal plans** from a natural-language request
* Suggests **food swaps** with short explanations
* Retrieves dataset records through **RAG** to ground answers in the indexed data
* Is configured with **Google Search, Wikipedia, and WebCrawler** tools alongside the RAG tool
* Accepts **health goals, allergies, and calorie targets** as prompt constraints (no condition-specific medical logic)

---

## 💠 Built With

* **IBM watsonx.ai Studio**: low-code AI platform
* **Agent Lab**: assembled the NutriMind agent (**LangGraph** `create_react_agent`, **ReAct** pattern)
* **Prompt Lab**: prototyped the RAG and prompt workflows
* **Models Used**:

  * 🧠 `llama-3-3-70b-instruct`: agent reasoning model
  * 💬 `granite-3-8b-instruct`: prompt prototyping and RAG Q&A
  * 🔍 `granite-embedding-278m-multilingual`: RAG embedding
* **Data Pre-processing**: manual cleanup in Microsoft Excel (see limitations)
* **Deployment**: watsonx deployment space on IBM Cloud Lite tier

> ℹ️ The notebooks in `notebooks/` are **auto-generated exports** from watsonx Agent Lab and Prompt Lab (IBM boilerplate). They require a watsonx project, an API key, and the project's vector index, so they don't run standalone.

---

## 🧠 Technical Architecture

```plaintext
📦 Dataset: Daily Food and Nutrition Dataset (Kaggle)
🔧 Preprocessing: Manual cleanup in Excel
📚 Knowledge Base: RAG vector index created using a watsonx embedding model
🧪 Prompt Engineering: Meal-plan & food-swap prompts in Prompt Lab
🧹 Agent Assembly: Agent Lab + LangGraph for tool calling
🔀 Reasoning: ReAct (Reason + Act) loop for tool selection
💠 Tools: RAG vector index, Google Search, Wikipedia, Web Crawler
🚀 Deployment: Deployed to a watsonx deployment space during the capstone
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
📄 Capstone.pdf
📄 LICENSE
📄 Problem_Statement.png
📄 README.md
```

---

## ⚠️ Known Limitations & Lessons Learned

A post-project review found the following issues. They are documented here rather than hidden.

1. **The source data is not realistic.** The Kaggle dataset appears to be synthetic. Every food spans roughly 50–600 kcal. In about 58% of rows, the stated calories differ by more than 50% from the standard estimate (4 kcal/g protein, 4 kcal/g carbs, 9 kcal/g fat).
2. **The Excel cleanup misaligned rows.** De-duplicating on the food-name column shifted food names out of line with their nutrient values in `cleaned_daily_food_nutrition_dataset.pdf`. For example, the "Oats" row carries another row's values and is labelled "Fruits".
3. **RAG retrieved the data faithfully, including the errors.** The retrieval demo answers "egg contains 42.4 g protein", which matches the dataset row; a real egg has about 6 g. Grounding only helps when the indexed data is correct.
4. **LLM arithmetic is unreliable.** In the showcased "2000-calorie" plan, the listed items add up to about 2800 kcal. Totals in the deployed meal plan also don't match the stated target.
5. **There was no quantitative evaluation.** Testing was qualitative (manual queries). There are no automated tests or metrics.
6. **The Prompt Lab outputs are truncated.** The Meal Plan and Food Swap screenshots stop at the 200-token limit.

**Lessons learned**
* Validate data before indexing it: schema checks, one category per food, and a calorie-vs-macros consistency check.
* Use deterministic tools for arithmetic and constraint checks (calorie totals, allergens) instead of trusting the LLM.
* Evaluate against a fixed set of test queries with expected answers, not only ad-hoc demos.

---

## 🔮 Future Enhancements

* 🧪 **Validated data pipeline**: a reproducible Python cleaning script with tests, ideally on a real source such as USDA FoodData Central
* 🧮 **Calculator & constraint tool**: deterministic calorie/macro totals and allergen checks exposed to the agent as a tool
* 📏 **Evaluation harness**: a fixed query set scored for factual accuracy, calorie-target adherence, and allergen violations
* 📷 **Image input**: food photos via a vision model
* 🎤 **Voice input**: speech-to-text interaction
* 🔀 **Feedback loop**: personalize based on stored preferences and feedback

---

## 🗏️ References

* 📘 Kaggle Dataset: [Daily Food and Nutrition Dataset](https://www.kaggle.com/datasets/adilshamim8/daily-food-and-nutrition-dataset)
* 📚 RAG Paper: [Lewis et al. (2020)](https://arxiv.org/abs/2005.11401)
* 🧠 ReAct Paper: [Yao et al. (2023)](https://arxiv.org/abs/2210.03629)
* 🔧 IBM Docs: [watsonx.ai Documentation](https://cloud.ibm.com/docs/watsonx-ai)

---

## 👤 Author

**Gurpreet Singh**
B.Tech CSE, Presidency University, Bengaluru
Capstone Project | IBM watsonx | AI for Healthcare
