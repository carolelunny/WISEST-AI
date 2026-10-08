# WISEST AI Project
**WISEST AI (Which Systematic Evidence Synthesis is Best)** is a research project aimed at developing and evaluating artificial intelligence systems for the automated critical appraisal of systematic reviews. The project draws on a curated reference dataset of approximately 200 systematic reviews assessed by trained human reviewers using AMSTAR 2 and ROBIS. The dataset includes item-level judgements, supporting quotations, written rationales, explicit decision rules, and clarity of evidence ratings.

WISEST aims to develop transparent AI-assisted appraisal methods that identify relevant evidence, apply predefined assessment rules, and generate auditable judgements. A key research objective is to evaluate not only the accuracy of AI assessments but also their repeatability and whether the cited evidence supports the judgements. The project seeks to reduce the time and expertise required for critical appraisal while helping researchers, guideline developers, and healthcare decision-makers evaluate the methodological quality and risk of bias of systematic reviews.
---

## 1. Background and Rationale
Systematic reviews are widely used to inform healthcare decisions, clinical guidelines, and health policy. However, reviews addressing the same research question can differ considerably in their methodological quality and risk of bias.

Critical appraisal tools such as **AMSTAR 2** and **ROBIS** help researchers identify these differences. Applying these tools requires substantial time, expertise, and careful interpretation of review methods.

WISEST AI aims to reduce this workload by developing AI-assisted appraisal methods while maintaining transparency, accuracy, and human oversight.

A central concern is that an AI system may produce the correct judgement for the wrong reason, or repeatedly produce an incorrect judgement.

WISEST therefore evaluates not only the final appraisal judgement, but also the evidence and reasoning used to support it.
---

**WISEST AI Project Development**
The WISEST AI project was developed through four stages:
1. Identifying the research problem, 
2. Evaluating existing tools and evidence-user needs, 
3. Selecting appraisal features, and 
4. Developing the human reference dataset.

![WISEST project development](wisest%20history%20background%20flowchart%202026.png)

*Figure 1. Development stages of the WISEST research program.*

## 2. The WISEST Reference Dataset
A major contribution of WISEST is its curated reference dataset of approximately **200 systematic reviews** assessed by trained human reviewers.

### Dataset overview

| Feature | Description |
|---|---|
| Dataset | Approximately 200 systematic reviews |
| Cochrane reviews in dataset | 132 |
| Non-Cochrane reviews in dataset | 68 |
| Appraisal tools | AMSTAR 2 and ROBIS |
| Research team | Approximately 30 assessors, with additional checking and adjudication |
| Assessment level | Item, domain, and overall review |
| Reference standard | Human assessments supported by explicit decision rules and quality assurance |

### Reference dataset components
The dataset is designed to include:

- **Item-level judgements:** Assessments against individual AMSTAR 2 and ROBIS criteria.
- **Supporting evidence:** Relevant quotations extracted from the systematic reviews.
- **Written rationales:** Explanations of why each judgement was assigned.
- **Decision rules:** Explicit instructions to support consistent assessments.
- **Clarity of evidence ratings:** Ratings of how clear the supporting quote is from the review documentation, if available (e.g., very clear, vague)
- **Quality assurance:** Checking, reconciliation, and adjudication of disagreements.

### Published research
The initial 200-review dataset has been described in:
Lunny C, Jain N, Nazari T, et al. Exploring the methodological quality and risk of bias in 200 systematic reviews: a comparative study of ROBIS and AMSTAR-2 tools. Research Synthesis Methods. 2026;17(1):63–92. DOI: https://doi.org/10.1017/rsm.2025.10032

## 3. Development of the AI Appraisal System
WISEST aims to develop an AI-assisted system that reads full-text systematic reviews, identifies relevant evidence, and generates structured critical appraisal assessments.

The proposed approach separates evidence extraction, judgement formation, and final scoring.

**Proposed appraisal workflow**

Full-text systematic review
            |
            v
LLM evidence extraction
Identify passages relevant to
AMSTAR 2 and ROBIS criteria
            |
            v
Evidence-supported judgements
Generate item responses,
supporting quotations, and rationales
            |
            v
Rule-based scoring
Apply predefined rules for
domain and overall assessments
            |
            v
Transparent appraisal report
Judgements, source evidence,
rationales, and audit trail

**Core design principles**
Evidence grounding: Judgements should be supported by evidence from the systematic review.

Transparent reasoning: Each judgement should include an explanation that can be checked.

Explicit decision rules: Predefined scoring rules should be applied consistently.

Reproducibility: Inputs, model configurations, and assessment procedures should be documented.

Human verification: Researchers should be able to inspect and verify AI-generated assessments.

The proposed system will generate structured outputs that can support independent checking, including item-level judgements, evidence quotations, rationales, and machine-readable audit records.

## 4. Evaluation and Validation
WISEST places particular emphasis on evaluating AI systems beyond conventional accuracy measures.

A model may produce an apparently correct judgement while relying on incorrect evidence or an unsupported explanation. Repeated runs may also produce different judgements under identical conditions.

The evaluation framework therefore examines several complementary dimensions.

**Evaluation dimensions**
Dimension

Evaluation question

Judgement accuracy

Does the AI judgement agree with the adjudicated human reference judgement?

**Repeatability**
Does the AI reach the same judgement when the identical task is repeated under fixed conditions?

Evidence identification

Does the AI identify the relevant supporting passages in the systematic review?

**Evidence support**
Does the cited evidence actually justify the judgement?

**Rationale quality**
Is the explanation consistent with the evidence and appraisal decision rules?

Planned evaluation methods

The evaluation framework includes:
Item-level and review-level comparisons against human reference assessments.

Classification performance measures, including precision, recall, and Matthews correlation coefficient (MCC).

**Agreement and reliability measures**
Repeated-run experiments under specified model and evaluation conditions.

Evaluation of the relevance and accuracy of supporting quotations.

Assessment of whether rationales support the assigned judgements.

Analysis of disagreements and error patterns.

**Two important reliability concerns**
Repeat-run variability: The same model may produce different judgements when the same read-and-evaluate task is repeated under fixed conditions, when available to the user.

Hidden judgement failure: Repeated assessments may agree, but a problem in the judgement process can still make the results misleading. For example, a model may repeatedly assign a judgement based on evidence that does not support it.

WISEST aims to investigate both concerns rather than relying on a single accuracy estimate.

## 5. Intended Applications
WISEST is designed to support several research and healthcare applications.

**AI-assisted critical appraisal**
Support researchers conducting methodological quality and risk-of-bias assessments using AMSTAR 2 and ROBIS.

**Overviews of systematic reviews**
Help overview authors assess multiple systematic reviews, identify methodological limitations, and compare the quality of available evidence.

**Clinical guidelines and health technology assessment**
Support guideline developers and health technology assessment organisations in evaluating systematic reviews used to inform healthcare decisions.

**AI benchmarking and validation**
Provide a human-assessed reference dataset for developing, comparing, and validating AI systems that perform evidence-based evaluation tasks.

**Research on LLM reliability**
Enable experiments investigating judgement accuracy, repeatability, evidence support, and mechanisms that can produce misleading AI assessments.

## 6. Relationship to the Broader AI Reliability Research Programme
WISEST is connected to a broader programme investigating how LLMs perform read-and-evaluate tasks and how their judgements can be independently verified.

The programme includes three complementary projects.

**WISEST Dataset**
Built a human reference dataset and provided a real-world testbed for AI-assisted critical appraisal.

**FAILS taxonomy**
Identifies mechanisms that can cause repeat-run variability or hidden judgement failures in LLM read-and-evaluate tasks.

**REPROSYS**
Proposes infrastructure for independently evaluating and verifying AI judgements, including their repeatability and evidence support.

## How the projects connect

**FAILS taxonomy** → **WISEST Dataset** → REPROSYS

FAILS identifies mechanisms that can cause AI judgements to vary or become misleading.

WISEST Dataset provides systematic reviews, human reference assessments, and appraisal tasks to investigate these mechanisms.

REPROSYS proposes a broader framework for independent verification, benchmarking, and reporting of AI evaluation performance.

Together, these projects aim to improve how researchers develop, evaluate, and verify AI systems used for evidence-based judgements.

## Project status
WISEST includes an established human-assessed reference dataset and published methodological research. Development of the automated AI appraisal system and further validation experiments are ongoing or planned.
