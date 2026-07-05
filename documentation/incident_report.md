# AI Risk & Compliance Incident Report
**Document ID:** INC-2026-0705  
**Classification:** Internal Compliance / Regulatory Audit Trail  
**Applicable Frameworks:** UK Equality Act 2010 | NIST AI RMF (Mitigate Function) | ISO/IEC 42001  

---

## 1. Executive Summary & Incident Detection
On 05 July 2026, the automated runtime governance pipeline triggered a critical compliance alert (`NON-COMPLIANT`) during a routine batch audit of the automated consumer loan underwriting system. The pipeline evaluated live model inference data against historical training baselines using distributed statistical monitoring. 

The system flagged a severe violation of the **Disparate Impact Ratio (DIR)**, indicating a systemic demographic bias that directly violates the **UK Equality Act 2010** regarding unfair algorithmic discrimination against protected characteristics (Gender and Age).

## 2. Statistical Findings & Evidence
The automated PySpark audit engine isolated the following operational performance metrics from the production Delta Table (`default.loan_applications_raw`):

*   **Privileged Group (Male) Approval Rate:** [Insert Cell 3 Male % here]%
*   **Protected Group (Female) Approval Rate:** [Insert Cell 3 Female % here]%
*   **Calculated Disparate Impact Ratio (DIR):** [Insert Cell 3 Ratio here]
*   **Legal Threshold:** 0.80 (The 80% Rule)

**Analysis:** The DIR falls significantly below the regulatory threshold of 0.80. This proves that an otherwise qualified female applicant is being disproportionately denied credit compared to an identically qualified male applicant. The audit trail, metadata, and runtime parameters have been permanently logged into **MLflow (Run ID: Loan_Underwriting_Bias_Audit)** as immutable evidence for regulatory review.

## 3. Immediate Containment & Long-Term Remediation
Upon logging the `NON-COMPLIANT` tag, the pipeline executed the following technical governance protocol:

1. **Automated Isolation:** The model production tag was locked via MLflow to prevent further upstream automated decision-making.
2. **Operational Fallback:** Credit underwriting was reverted to a human-in-the-loop (HITL) manual review process or a pre-approved legacy baseline model.
3. **Root Cause Correction Plan:** Future remediation requires data engineering teams to execute **pre-processing reweighing techniques** on training datasets, audit the system for proxy variables (such as postal codes or shopping habits that correlate strongly with gender), and re-submit the model for sandbox validation before deployment.
