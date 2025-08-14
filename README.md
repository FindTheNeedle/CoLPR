# CoLPR

**System-Wide Ransomware Attack Detection via Perturbation-Resilient Representation Learning**  
(*Paper under peer review*)

---

## 📄 About This Repository

This repository accompanies our paper, currently under peer review:

> **System-Wide Ransomware Attack Detection via Perturbation-Resilient Representation Learning**  
> *[Authors omitted for anonymity during review]*

### 📝 Summary of Contributions

Ransomware has evolved into stealthy, system-level attacks that disguise malicious activity among benign applications, rendering process-level detection ineffective.  
We present **CoLPR**, a contrastive self-supervised learning framework for **perturbation-resilient, system-wide ransomware detection**.

Key contributions:
1. **Perturbation-Resilient Representation Learning** – We propose a novel data augmentation strategy that produces strongly perturbed yet realistic behavioral data for training, enabling resilience against interference from other running applications.
2. **Environment-Aware Fine-Tuning** – The learned encoder is adapted to specific deployment environments, achieving accurate detection even under multi-application interference.
3. **Timely Detection** – Across three real-world deployment environments, CoLPR achieved:
   - **100% Recall**
   - **4.58s average detection delay** (well within the 60-second short-term backup window)
   - **98.8% overall Accuracy**
4. **Robustness to Unseen Families** – Successfully detected attacks from 12 previously unseen ransomware families under strong perturbations.

---

## 📂 Purpose of This Repository

This repository releases **supplementary materials** for our paper, specifically:

- **Ransomware executable pool composition**:
  - Ransomware family names
  - SHA-256 hashes
  - MalwareBazaar Database links

The goal is to help the research community **replicate or extend** our work by providing full transparency on the ransomware families we tested.

---

## 🦠 Ransomware Categories

Our ransomware pool covers **96 families** in total, divided into:

- **84 user-privileged families** – Can execute without administrator rights.
- **12 super-privileged families (UNSEEN)** – Require administrator privileges to execute.

### 1️⃣ User-Privileged Families

These ransomware families execute at the **user privilege level** and can encrypt files without elevated permissions. They are safe to evaluate in automated environments, making them suitable for large-scale behavioral dataset generation.  

---

### 2️⃣ Super-Privileged Families (UNSEEN)

Some ransomware families require **administrator privileges** and can inflict severe system damage, including:

- Disabling **Windows Recovery Environment (Windows RE)**
- Destroying hidden disk images

To maintain **full automation**, we mark these as **UNSEEN** and collect their behavioral samples **manually** by restoring the system after each run. This allows us to test CoLPR’s **generalizability** to novel, high-impact threats.

---

## 📊 Ransomware Executable Pool Composition

| Family Name | Privilege Level | SHA-256 | MalwareBazaar Link |
|-------------|----------------|---------|--------------------|
| Abyss | User | `9243bdcbe30fbd430a841a623e9e1bcc894e4fdc136d46e702a94dad4b10dfdc` | [Link](https://bazaar.abuse.ch/sample/9243bdcbe30fbd430a841a623e9e1bcc894e4fdc136d46e702a94dad4b10dfdc/) |
| ...         | ...            | ...     | ...                |
