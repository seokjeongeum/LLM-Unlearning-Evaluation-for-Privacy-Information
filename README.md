# LLM-Unlearning-Evaluation-for-Privacy-Information
This repository is dedicated to exploring **LLM unlearning**, focusing on privacy risks and strategies to effectively and efficiently "forget" specific data from large language models. 

---
## Key Topics

### Privacy Attack
<div aligncenter><img width="900" alt="image" src="https://github.com/LeeJYg/LLM-Unlearning-for-Privacy-Information/blob/main/privacy_attack.png">  

Privacy attacks target the security and privacy of large language models (LLMs), often aiming to extract sensitive information or infer membership details of the training data. This section categorizes these attacks into two key types: **Extraction Attacks** and **Membership Inference Attacks (MIA)**.

---

#### Extraction Attack
Extraction attacks attempt to retrieve sensitive data, gradients, or model functionalities through various means, including model theft and training data extraction.

- **Maze: Data-free model stealing attack using zeroth-order gradient estimation**  
   - **Description:** Maze introduces a novel data-free model stealing attack that uses zeroth-order gradient estimation to replicate model functionality without access to training data, highlighting vulnerabilities in accessible models.  
   - [Paper Link](https://arxiv.org/abs/2106.03122)

- **A theoretical insight into attack and defense of gradient leakage in transformers**  
   - **Description:** This paper provides theoretical insights into gradient leakage attacks and defenses, showing how attackers can reconstruct sensitive training data by exploiting gradients shared during collaborative learning setups.  
   - [Paper Link](https://arxiv.org/abs/2311.13624)

- **Extracting Training Data from Large Language Models**  
   - **Description:** This paper demonstrate how strategically crafted queries can extract specific training examples from LLMs, exposing risks of private data being unintentionally memorized by models.  
   - [Paper Link](https://arxiv.org/abs/2107.03396)

- **Ethicist: Targeted training data extraction through loss-smoothed soft prompting and calibrated confidence estimation**  
   - **Description:** Ethicist introduces a method combining soft prompting with calibrated confidence estimation to target and extract specific training data, highlighting risks in LLM memorization patterns.  
   - [Paper Link](https://arxiv.org/abs/2307.04401)

- **What Do Code Models Memorize? An Empirical Study on Large Language Models of Code**  
   - **Description:** This paper examines the memorization behaviors of code-based LLMs, demonstrating how training data specific to programming tasks can be extracted and potentially misused.  
   - [Paper Link](https://arxiv.org/abs/2308.09932)

---

#### Membership Inference Attacks (MIA)
Membership inference attacks aim to determine whether a specific data point was part of a model's training set. These attacks are critical in evaluating the privacy vulnerabilities of LLMs.

- **Membership inference attacks against machine learning models**  
   - **Description:** This paper formalizes membership inference attacks against ML models, providing a new framework for attacking ML models
   - [Paper Link](https://arxiv.org/abs/2203.03319)

- **Membership Inference Attacks from First Principles**  
   - **Description:** This paper formalizes membership inference attacks, providing a comprehensive framework for understanding how training data can be detected in model predictions.  
   - [Paper Link](https://arxiv.org/abs/2203.03319)

- **Towards Demystifying Membership Inference Attacks**  
   - **Description:** This study analyzes the underlying mechanisms of membership inference attacks and identifies scenarios where such attacks are most effective.  
   - [Paper Link](https://arxiv.org/abs/1807.09173)

- **Inexact Unlearning Needs More Careful Evaluations to Avoid a False Sense of Privacy**  
   - **Description:** This paper proposes per-example U-MIA, a stronger version of conventional MIA, to be utilized in unlearning evaluation.
   - [Paper Link](https://arxiv.org/abs/2403.01218)
- **Low-Cost High-Power Membership Inference Attacks**
  - **Description:** This paper introduces Robust Membership Inference Attack (RMIA), a statistical test that improves membership inference by leveraging fine-grained likelihood ratio tests. By modeling the null hypothesis with population data and employing pairwise likelihood ratios, RMIA distinguishes member data points from non-members effectively
  - [Paper Link](https://arxiv.org/abs/2312.03262)

- **Membership Inference Attacks against Fine-tuned Large Language Models via Self-prompt Calibration**
  - **Description:** This paper proposes SPV-MIA, a novel attack that uses self-prompting to generate a reference dataset from the target model and introduces a probabilistic variation metric based on memorization rather than overfitting.
  - [Paper Link](https://arxiv.org/abs/2311.06062)

- **Order of Magnitude Speedups for LLM Membership Inference**
   - **Description:** This paper introduces a membership inference attack leveraging an ensemble of lightweight quantile regression models. Unlike traditional shadow model approaches, which are computationally expensive, this method estimates training data membership by directly predicting quantiles of score functions.
   - [Paper Link](https://arxiv.org/abs/2409.14513)

---

## Unlearning Techniques  
<div aligncenter><img width="900" alt="image" src="https://github.com/LeeJYg/LLM-Unlearning-for-Privacy-Information/blob/main/unlearning_methods.png">  

This section categorizes and summarizes the key techniques in unlearning, including **Parameter Optimization Method**, **Parameter Merging Method**, and **Parameter Agnostic Method**. Each technique is described alongside its key methods and referenced works.

---

### Parameter Optimization Method
Parameter optimization involves modifying model parameters to effectively "forget" specific data while maintaining the utility of the remaining model. This category includes gradient-based methods, second-order optimization, and general frameworks.

- **Who’s Harry Potter? Approximate Unlearning in LLMs**  
  - **Description:** Fine-tunes models to erase specific knowledge by swapping unique phrases with generalized alternatives.  
  - **Reference:** [Paper Link](https://arxiv.org/abs/2310.02238)

- **Partitioned Contrastive Gradient Unlearning (PCGU)**  
  - **Description:** Uses first-order gradient approximations to refine weights and efficiently remove biases.  
  - **Reference:** [Paper Link](https://arxiv.org/abs/2311.07568)
 
- **Knowledge unlearning for mitigating privacy risks in language models**  
  - **Description:** Uses gradient ascent for unlearning and propose how to evaluate privacy protection of unlearning method
  - **Reference:** [Paper Link](https://arxiv.org/abs/2210.01504)

- **Negative Preference Optimization: From Catastrophic Collapse to Effective Unlearning**  
  - **Description:** Introduces a preference optimization framework to prevent catastrophic collapse during gradient ascent-based unlearning.  
  - **Reference:** [Paper Link](https://arxiv.org/abs/2404.05868)

- **Second-Order Information Matters**  
  - **Description:** Employs Hessian-based methods for precise parameter adjustments to ensure privacy protection.  
  - **Reference:** [Paper Link](https://arxiv.org/abs/2403.10557)

- **KGA: A General Machine Unlearning Framework**  
  - **Description:** Aligns distribution gaps between learned and unlearned data, effectively applied to various NLP tasks.  
  - **Reference:** [Paper Link](https://arxiv.org/abs/2305.06535)

- **Towards Safer Large Language Models Through Machine Unlearning**  
  - **Description:** Introduces metrics like forget, mismatch, and maintain to optimize unlearning while balancing generalization and utility.  
  - **Reference:** [Paper Link](https://arxiv.org/abs/2402.10058)

- **DEPN: Detecting and Editing Privacy Neurons in Pretrained Language Models**  
  - **Description:** Detects and deactivates neurons associated with private information to perform unlearning.  
  - **Reference:** [Paper Link](https://arxiv.org/abs/2310.20138)

---

### Parameter Merging Method
Parameter merging focuses on reducing computational costs by applying arithmetic operations or selectively pruning model components.

- **Editing Models with Task Arithmetic**  
  - **Description:** Introduced task vectors to define trajectories in weight space for flexible model alterations, including unlearning.  
  - **Reference:** [Paper Link](https://arxiv.org/abs/2203.13124)

- **Composing Parameter-Efficient Modules with Arithmetic Operations**  
  - **Description:** Uses linear arithmetic operations like addition and negation to integrate parameter-efficient modules without retraining.  
  - **Reference:** [Paper Link](https://arxiv.org/abs/2306.14870)

- **Dissecting Language Models: Machine Unlearning via Selective Pruning**  
  - **Description:** Identifies and removes neurons related to specific behaviors, maintaining network efficiency.  
  - **Reference:** [Paper Link](https://arxiv.org/abs/2403.01267)

---

### Parameter Agnostic Method
It focuses on prompt-based methods to guide the model towards forgetting sensitive data dynamically.

- **In-Context Unlearning for LLMs**  
  - **Description:** Uses unlearning samples as prompts to adjust the model's outputs without modifying internal parameters.  
  - **Advantages:**  
    - Reduces computational costs.  
    - Suitable for real-time or on-demand unlearning.  
  - **Reference:** [Paper Link](https://arxiv.org/abs/2310.07579)

---

## Existing Unlearning Evaluation Framework

This section summarizes the evaluation methods for assessing the effectiveness of unlearning techniques in large language models. The evaluation framework includes key tasks such as **knowledge memorization**, **knowledge manipulation**, **membership inference attacks (MIA)**, **query rewriting attack**, and **white-box attacks**. Each method is detailed with its corresponding evaluation scope and benchmarks.

### Evaluation Methods Table

| ID  | Method Name          | Paper Title                                               | Venue  | Year | Targeting Pre-trained Data | Memorization | Manipulation | MIA  | Query Rewrite | White-box Attack | RAG |
|-----|----------------------|----------------------------------------------------------|--------|------|----------------------------|--------------|--------------|------|---------------|------------------|-----|
| 1   | RWKU                | RWKU: Benchmarking Real-World Knowledge Unlearning        | ArXiv  | 2024 | ✅                         | ✅           | ✅           | ✅   | ✅            | ❌               | ❌  |
| 2   | MUSE                | MUSE: Machine Unlearning Six-Way Evaluation               | ArXiv  | 2024 | ❌                         | ✅           | ✅           | ✅   | ❌            | ❌               | ❌  |
| 3   | TOFU                | TOFU: A Task of Fictitious Unlearning                     | ArXiv  | 2024 | ❌                         | ❌           | ✅           | ❌   | ❌            | ❌               | ❌  |
| 4   | WHP                 | Who’s Harry Potter? Approximate Unlearning               | ArXiv  | 2024 | ❌                         | ❌           | ✅           | ❌   | ❌            | ❌               | ❌  |
| 5   | Attack-and-Defence  | Can Sensitive Information Be Deleted From LLMs?           | ICLR   | 2024 | ❌                         | ❌           | ❌           | ❌   | ✅            | ✅               | ❌  |
| 6   | WMDP                | The WMDP Benchmark: Measuring Unlearning Performance      | ICML   | 2024 | ❌                         | ❌           | ✅           | ❌   | ❌            | ❌               | ❌  |

### Detailed Descriptions and Links

- **TOFU: A Task of Fictitious Unlearning**  
   - **Description:** Uses synthetic datasets of author profiles to benchmark unlearning techniques.
   - **Reference:** [Paper Link](https://arxiv.org/abs/2401.06121)

- **WHP: Who’s Harry Potter? Approximate Unlearning**  
   - **Description:** Focuses on unlearning specific copyrighted data (e.g., Harry Potter books) using fine-tuning with alternative labels. It also propose a new task for evaluating unlearning algorithm
   - **Reference:** [Paper Link](https://arxiv.org/abs/2310.02238)
 
- **RWKU: Benchmarking Real-World Knowledge Unlearning**  
   - **Description:** Evaluates real-world knowledge unlearning across various applications. It uses popular figures as unlearning targets and employs rigorous testing methods, including membership inference and adversarial attack probes, to assess unlearning efficacy.  
   - **Reference:** [Paper Link](https://arxiv.org/abs/2406.10890)

- **MUSE: Machine Unlearning Six-Way Evaluation**  
   - **Description:** Defines six desirable properties for unlearning models: verbatim memorization, knowledge memorization, privacy leakage, utility preservation, scalability, and sustainability. It benchmarks unlearning on Harry Potter books and news articles.  
   - **Reference:** [Paper Link](https://arxiv.org/abs/2407.06460)

- **Can Sensitive Information Be Deleted From LLMs? Objectives for Defending Against Extraction Attacks**  
   - **Description:** Investigate methods for deleting sensitive information directly from model weights, proposing an attack-and-defense framework to ensure safety and privacy.
   - **Reference:** [Paper Link](https://arxiv.org/abs/2309.17410)

- **The WMDP Benchmark: Measuring and Reducing Malicious Use With Unlearning**  
   - **Description:** Public benchmark for evaluating hazardous knowledge in LLMs, particularly related to biosecurity, cybersecurity, and chemical security. It also serves as a benchmark for unlearning methods to mitigate malicious capabilities.  
   - **Reference:** [Paper Link](https://arxiv.org/abs/2403.03218)


---

## Future Directions
- Developing faster and more effective unlearning algorithms.
- Establishing standard benchmarks for unlearning evaluation.
