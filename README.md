
# Integrating LLMs with Process Mining to Enhance Internal Audit Insights

> **A case study repository for auditors and data scientists**  
> Turning complex warehouse event data into defensible, decision-ready audit insights using **Process Mining (pm4py)** and **LLM-assisted narratives**.

---

## 🎯 Purpose

This repository accompanies the master’s thesis **“Integrating LLMs with Process Mining to Enhance Internal Audit Insights: A case study.”** It demonstrates a **lightweight, auditable workflow** that 
1. models SAP EWM warehouse movements into a **Process Mining event log**, 
2. and deploys **LLM-driven tasks** to summarize discovery results, surface semantic anomalies, and cluster process variants

**What you get**

- Reproducible **data modeling** to transform system records into a clean event log fit for mining.  
- **Task deployment** that feeds textual abstractions (DFGs, variants) to an LLM for **process descriptions, anomaly cues, and variant clustering** to speed up audit preparation and fieldwork.

---

## 🧩 Key Features

- **Evidence-grounded insights:** Process Mining (pm4py) provides traceable, system-generated artifacts; the LLM turns these into clear narratives and hypotheses for auditors.  
- **Designed for Internal Audit:** Focus on **Discovery**, **Conformance**, and **Variant Analysis** tasks that map directly to the audit engagement lifecycle.  
- **Pragmatic & secure:** Works in a **private Azure setup** with **Azure OpenAI**—no model fine‑tuning; minimal ops overhead.

---

## 📦 Repository Structure

```
.
├─ /src
│  ├─ 01_data_modeling.ipynb    # Build event log from prepared warehouse movements
│  └─ 02_task_deployment.ipynb  # Generate LLM-assisted insights from pm4py 
├─ requirements.txt
└─ README.md
```

> 🔒 **Note:** Upstream ETL (e.g., ADF → ADLS → Delta bronze/silver) is not included due to proprietary content. The repo starts from curated tables needed to build the **event log** and run **LLM tasks**.

---

## ⚙️ Requirements

### Runtime
- **Python** ≥ 3.10
- **Optional (recommended at scale):** Databricks Runtime or local **PySpark** with Delta support

### Main Python packages
- `pm4py` (for the Process Mining features, especially the creation of abstractions)
- `pyspark`, `delta-spark` (if reading Delta tables)
- `openai` (or other LLM service)

### Parameters

Please check the **`Requirements/Parameters`**-section in each script to provide your custom parameters, such as path to input- and output-locations as well as credentials for LLM-service.

---

## 📜 Scripts Explained

### `data_modeling.ipynb`
Transforms curated warehouse tasks into a **fit‑for‑mining event log**.

### `task_deployment.ipynb`
Runs **pm4py** to produce abstractions and executes **RISEN‑structured prompts** via Azure OpenAI.

---

## 🧪 Reproducibility

Every run stores artifacts in defined `output` locations. Originally, the deployment is done in Databricks by using the data versioning and governance features of Unity Catalog.

---

## 📄 License
See **LICENSE** file.

---

## 📚 Citation
Zumpf, C. (2026). *Integrating LLMs with Process Mining to Enhance Internal Audit Insights: A case study.*
