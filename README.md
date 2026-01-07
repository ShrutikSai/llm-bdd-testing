# 🚀 LLM-Assisted BDD Functional Testing Framework

### **NTT DATA Internship Case Study | 2026 Batch**
**Candidate:** [Rachakonda Shrutik Sai]  
**Position:** Internship Case Study - Case Study Round  
**Submission Date:** January 10, 2026

---

## 📌 Project Overview
This project represents an end-to-end automation pipeline that leverages **Generative AI** to bridge the gap between business requirements and technical test execution. By utilizing **Gemini 2.5 Flash**, the system parses plain-English requirements into structured **Gherkin (BDD)** scenarios and executes them via **Playwright**.

---

## 🛠️ Technical Stack
* **LLM Engine:** Google Gemini 2.5 Flash (State-of-the-art reasoning)
* **Automation Library:** Playwright (Asynchronous execution)
* **BDD Framework:** Behave (Python-based Gherkin runner)
* **Execution Environment:** Google Colab / Linux
* **Integration:** nest_asyncio for nested event loop management

---

## ⚙️ Core Features
* **AI Requirement Analysis:** Automatically generates Positive (Happy Path) and Negative test flows from high-level business logic.
* **Gherkin Standardization:** Produces standardized `Given-When-Then` syntax compatible with enterprise BDD tools.
* **Validation & Safety Gate:** Implemented a **"Human-in-the-Loop"** approval process, ensuring no automated tests run without manual verification of the AI's logic.
* **Dynamic Browser Automation:** Uses Playwright to simulate real user interactions, handling modern web elements and asynchronous state changes.
* **Automated Proof of Work:** Generates time-stamped screenshots as evidence of test success/failure.

---

## 🏗️ System Architecture

1. **Input Layer:** Raw business requirements (e.g., "User should be able to login").
2. **Intelligence Layer:** Gemini 2.5 Flash interprets intent and generates Gherkin feature files.
3. **Validation Layer:** A terminal-based approval record that logs the user's decision to proceed.
4. **Execution Layer:** Behave maps Gherkin steps to Playwright Python functions.
5. **Evidence Layer:** Screenshots (`happy_path_success.png`) are captured for the audit trail.

---

## 📂 Repository Structure

```
├── NTT_DATA_LLM_BDD.ipynb    # Complete project source code (Jupyter Notebook)
├── features/                 # BDD Feature folder
│   └── login.feature         # AI-generated Gherkin scenarios
├── features/steps/           # Step definitions folder
│   └── steps.py              # Playwright-based Python automation logic
├── happy_path_success.png    # Visual evidence of successful test execution
└── README.md                 # Project documentation
```

---

## 🚀 Getting Started

### 1. Requirements

* A Google Cloud / AI Studio API Key.
* Python 3.10+ or Google Colab environment.

### 2. Installation

Run the following in your environment to set up the engine:

```bash
pip install playwright behave google-generativeai nest_asyncio
playwright install chromium
```

### 3. Execution

1. Open the `.ipynb` file in Google Colab.  
2. Insert your Gemini API Key in the configuration cell.  
3. Run the cells sequentially.  
4. Type `YES` when prompted to approve the AI-generated scenarios.  
5. Check the file directory for `happy_path_success.png`.  

---

## 🧠 Engineering Challenges & Solutions

### **Challenge 1: Async/Sync Conflict in Colab**

**Issue:** Playwright’s default sync API crashes when run inside an environment already managing an asyncio loop (like Google Colab).

**Solution:** Re-engineered the framework using **Playwright Async API** and utilized `nest_asyncio` to patch the event loop, allowing for stable browser execution within the notebook.

---

### **Challenge 2: Dynamic Element Synchronization**

**Issue:** AI-generated scenarios can be faster than the browser can render pages, leading to "Flaky Tests."

**Solution:** Implemented **Network Idle** wait strategies and **explicit locator assertions**, ensuring the test only proceeds when the UI is truly ready.

---

## 👨‍💻 Author

**[Rachakonda Shrutik Sai]**  
[shrutiksai14@gmail.com]  

---

*Developed for NTT DATA Talent Acquisition — 2026 Internship Batch*
