# Enterprise AI Governance & Automated Audit Pipeline
An end-to-end automated compliance and risk mitigation pipeline built in Databricks (PySpark, Delta Lake, and MLflow) mapping to the **UK Equality Act 2010** and **NIST AI RMF**.

## 📊 The Live Dashboard (Results)
*   **Male Approval Rate:** [Insert your Cell 3 percentage here, e.g., 72.4%]
*   **Female Approval Rate:** [Insert your Cell 3 percentage here, e.g., 41.2%]
*   **Disparate Impact Ratio:** [Insert your DIR here, e.g., 0.57]
*   **Compliance Status:** ❌ FAIL (Violates the legal 80% rule threshold)

## 🏗️ Architecture & Governance Workflow
1. **Ingestion & Lakehouse Isolation:** Raw consumer loan applications are filtered and stored as an enterprise Delta Table.
2. **Algorithmic Risk Emulation:** Simulates a black-box model decision that unfairly penalizes vulnerable demographic groups.
3. **Automated Mathematical Audit:** Runs distributed PySpark commands to calculate the Disparate Impact Ratio.
4. **Immutable Audit Trail:** Automatically logs the compliance failure, parameters, and metadata directly to MLflow for external auditors.

## 🛠️ Tech Stack
*   **Databricks / Apache Spark:** Multi-node distributed data processing.
*   **Delta Lake:** ACID-compliant, auditable data storage.
*   **MLflow:** Immutable governance logging and model tracking.
*   **Python (PySpark SQL):** Statistical audit calculations.
