# 🧠 Multi-Agent RFP Automation System

### Automated Tender Discovery, Specification Matching & Pricing Using Google ADK + Gemini

---

## 🚀 Overview

This project demonstrates a **fully autonomous AI-powered workflow** that automates the end-to-end process of:

* Discovering **active RFPs** using web search
* Extracting tender requirements
* Matching OEM product SKUs to RFP specifications
* Generating complete cost estimations

It uses **Google’s Agent Development Kit (ADK)** to build a coordinated multi-agent system with sequential and parallel workflows, memory, and tool-based execution.

The result is a production-grade architecture for **procurement teams**, **manufacturers**, and **supply-chain businesses** that want to automate their tender response lifecycle.

---

## 🧩 System Architecture

### **🔹 1. Sales Agent (RFP Discovery)**

* Uses **Google Search Tool**
* Extracts only **active** tenders due within the next 90 days
* Removes duplicates & expired tenders
* Outputs structured JSON:

  * Title
  * Authority
  * Due Date
  * Product Requirements

---

### **🔹 2. Technical Agent (Spec Matching)**

* Reads product requirements from the RFP
* Matches each item to **top 3 OEM SKUs**
* Uses a Spec-Match percentage formula
* Builds a comparison table
* Selects Best-Fit SKU for each item

---

### **🔹 3. Pricing Agent (Cost Estimation)**

* Uses synthetic pricing tables:

  * Product prices
  * Test charges
  * Logistics multipliers
* Computes:

  * Material Cost
  * Testing Cost
  * Logistics Cost
  * Total Cost
* Outputs strict JSON pricing summary

---

### **🔹 4. Orchestration Layer**

* A **SequentialAgent** runs the Sales Agent first
* A **ParallelAgent** executes Technical + Pricing agents simultaneously
* The final output is fully structured and ready for further business logic

---

## 🏗️ Tech Stack

| Component            | Technology              |
| -------------------- | ----------------------- |
| LLM                  | Gemini 2.5 Flash-Lite   |
| Agent System         | Google ADK              |
| Tools                | Google Search Tool      |
| Runner               | InMemoryRunner (Kaggle) |
| Notebook Environment | Kaggle Notebook         |
| Language             | Python                  |

---

## ⚙️ How It Works

### **Step 1 — User Input**

The user provides a natural-language query such as:

> Find active RFPs in India for office supplies, printers, IT peripherals, or furniture with deadlines within 3 months.

---

### **Step 2 — Sales Agent**

* Searches the web
* Filters & structures RFPs
* Stores results in session memory

---

### **Step 3 — Technical Agent (Parallel Execution)**

* Analyzes RFP requirements
* Matches with OEM catalog SKUs

---

### **Step 4 — Pricing Agent (Parallel Execution)**

* Calculates complete cost breakdown

---

### **Step 5 — Final Output**

A single, consolidated JSON containing:

* RFP Summary
* Spec Matching
* SKU Recommendations
* Pricing Summary

---

## 📘 Example Output (Shortened)

```json
{
  "RFPs": [...],
  "TechnicalAgent": {
    "Top_Matches": [...]
  },
  "PricingAgent": {
    "Grand_Total": 31250
  }
}
```

---

## 🧪 Running the Project

### **1. Add Gemini API Key**

Add `GOOGLE_API_KEY` to Kaggle Secrets.

### **2. Install Dependencies**

Kaggle already has required dependencies for ADK, but if running locally:

```bash
pip install google-genai google-adk
```

### **3. Run the Notebook**

Just execute all cells in your Kaggle environment.

---

## 🎯 Key Features

* **End-to-End Automation** of RFP pipeline
* **Multi-Agent Collaboration** using ADK
* **Tool-Based Web Search**
* **Spec Matching Engine**
* **Full Pricing Computation**
* **Strict JSON Outputs**
* **Scalable Architecture**

---

## 📌 Future Improvements

* Add long-running workflow with human approval
* Add tender PDF reader & parser
* Integrate vendor qualification agent
* Add auto-generated proposal document (PDF)

---

## 🏁 Conclusion

This project demonstrates how **AI agents can automate enterprise workflows**, especially in procurement and tender management.
Using Google ADK, the system becomes modular, scalable, and production-ready.



