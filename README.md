# Awesome Trustworthy Medical MLLMs

> A curated collection of medical multimodal large language models, trustworthiness methods, evaluation protocols, and benchmarks.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#contributing)

This repository accompanies the ongoing survey **“Trustworthy Medical Multimodal Large Language Models: A Survey of Taxonomy, Evaluation, and Benchmarks.”** It organizes the field along two complementary axes:

- **Clinical scale:** tissue, organ, individual, and population.
- **Trustworthiness:** truthfulness, robustness, fairness, safety, privacy, and explainability.

The paper link and formal citation will be added when the preprint is publicly released.

## News

- **2026-08-10:** Initial public release with the survey taxonomy, curated seed papers, evaluation resources, and contribution rules.

## Table of Contents

- [About](#about)
- [Taxonomy](#taxonomy)
- [Clinical Landscape](#clinical-landscape)
  - [Tissue Scale](#tissue-scale)
  - [Organ Scale](#organ-scale)
  - [Individual Scale](#individual-scale)
  - [Population Scale](#population-scale)
- [Trustworthiness](#trustworthiness)
- [Evaluation and Benchmarks](#evaluation-and-benchmarks)
- [Contributing](#contributing)
- [Citation](#citation)
- [License](#license)

## About

Medical MLLMs combine language with one or more clinically meaningful modalities, such as pathology slides, radiology images, retinal images, endoscopy video, physiological signals, or longitudinal health records. This list focuses on resources that help researchers understand where these systems are used, how their trustworthiness is studied, and how they are evaluated.

### Scope

An entry is in scope when it satisfies at least one of the following:

1. It proposes or evaluates a multimodal model for a medical or healthcare setting.
2. It studies a trustworthiness property of a medical multimodal system.
3. It introduces an evaluation method or benchmark directly useful for trustworthy medical MLLMs.
4. It is an adjacent general-domain or unimodal resource with a clearly stated methodological connection to this field.

### Curation Principles

- **Classification first:** every entry must be assigned to the most specific clinical scale, specialty, and/or trustworthiness dimension.
- **Reason required:** contributors must explain why the proposed classification is appropriate.
- **Primary sources:** link the paper and official code, model, dataset, or project page whenever available.
- **Uniform fields:** use the labels `Paper`, `Code`, `HF`, `Data`, `Project`, and `Notes` consistently.
- **Neutral notes:** describe the resource without unsupported claims such as “first,” “best,” or “clinically validated.”
- **Explicit adjacency:** general-domain or unimodal work is marked **Adjacent** and must include a medical-MLLM relevance rationale.

## Taxonomy

![Survey taxonomy spanning clinical scales and trustworthiness dimensions](assets/overview.png)

| Axis | Categories | Organizing question |
|---|---|---|
| Clinical scale | Tissue · Organ · Individual · Population | At what level of the healthcare system is the model applied? |
| Trustworthiness | Truthfulness · Robustness · Fairness · Safety · Privacy · Explainability | Which property of reliable and responsible deployment is studied? |
| Evaluation | Automated metrics · Model-based judging · Expert assessment · Dynamic/workflow evaluation | How is trustworthy behavior measured? |

## Clinical Landscape

The entries below are an initial curated seed set from the current manuscript. They are not intended to be exhaustive; contributions are welcome under the rules in [Contributing](#contributing).

### Tissue Scale

#### Pathology

| Model or resource | Venue | Links | Modality and task | Notes |
|---|---|---|---|---|
| **Prov-GigaPath** | Nature, 2024 | [Paper](https://doi.org/10.1038/s41586-024-07441-w) | Whole-slide pathology; representation learning | Foundation model trained on real-world digital pathology data. |
| **TITAN** | Nature Medicine, 2025 | [Paper](https://doi.org/10.1038/s41591-025-03982-3) | Whole-slide pathology and language | Multimodal whole-slide foundation model for pathology tasks. |
| **CPath-Omni** | CVPR, 2025 | [Paper](https://doi.org/10.1109/CVPR52734.2025.00969) | Pathology images and language | General-purpose pathology MLLM resource. |

#### Dermatology

| Model or resource | Venue | Links | Modality and task | Notes |
|---|---|---|---|---|
| **Derm1M** | Preprint, 2025 | [Paper](https://arxiv.org/abs/2503.14911) | Dermatology images and language | Vision-language foundation model resource for dermatology. |

### Organ Scale

#### Radiology

| Model or resource | Venue | Links | Modality and task | Notes |
|---|---|---|---|---|
| **LLaVA-Med** | NeurIPS Datasets and Benchmarks, 2023 | [Paper](https://arxiv.org/abs/2306.00890) · [Project](https://papers.nips.cc/paper/2023/hash/5abcdf8ecdcacba028c6662789194572-Abstract-Datasets_and_Benchmarks.html) | Biomedical images and instruction following | Biomedical visual instruction-tuning resource. |
| **RadFM** | Nature Communications, 2025 | [Paper](https://doi.org/10.1038/s41467-025-62385-7) · [Code](https://github.com/chaoyi-wu/RadFM) | 2D/3D radiology and language | Generalist radiology foundation model across imaging settings. |
| **CT2Rep** | MICCAI, 2024 | [Paper](https://doi.org/10.1007/978-3-031-72390-2_45) | 3D chest CT report generation | Uses 3D CT volumes for radiology report generation. |

#### Ophthalmology

| Model or resource | Venue | Links | Modality and task | Notes |
|---|---|---|---|---|
| **INSIGHT** | MICCAI, 2024 | [Paper](https://doi.org/10.1007/978-3-031-72378-0_66) | Ophthalmic images and language | Ophthalmology-focused multimodal foundation model. |
| **VisionUnite** | IEEE TPAMI, 2025 | [Paper](https://doi.org/10.1109/TPAMI.2025.3598734) | Multi-modal ophthalmic imaging and language | Generalist foundation model for ophthalmic applications. |
| **RetiZero** | Nature Communications, 2025 | [Paper](https://doi.org/10.1038/s41467-025-60577-9) | Retinal images; zero-shot analysis | Retinal foundation model evaluated across diseases and imaging modalities. |

#### Gastroenterology and Endoscopy

| Model or resource | Venue | Links | Modality and task | Notes |
|---|---|---|---|---|
| **ColonGPT** | Preprint, 2024 | [Paper](https://arxiv.org/abs/2410.17241) | Colonoscopy images and language | Instruction-following vision-language model for colonoscopy. |
| **EndoKED** | Nature Biomedical Engineering, 2025 | [Paper](https://doi.org/10.1038/s41551-025-01500-x) | Endoscopy images; diagnostic assistance | Knowledge-enhanced distillation framework for endoscopic analysis. |

#### Surgical Operation

| Model or resource | Venue | Links | Modality and task | Notes |
|---|---|---|---|---|
| **LLM-assisted surgical VQA** | ICRA, 2024 | [Paper](https://doi.org/10.1109/ICRA57147.2024.10610603) | Surgical video and question answering | Studies language-model assistance for surgical visual question answering. |
| **Surgical embodied intelligence** | Science Robotics, 2025 | [Paper](https://doi.org/10.1126/scirobotics.adt3093) | Surgical perception, language, and action | Connects multimodal reasoning with embodied surgical tasks. |

### Individual Scale

#### Electronic Health Records

| Model or resource | Venue | Links | Modality and task | Notes |
|---|---|---|---|---|
| **BEHRT** | Scientific Reports, 2020 | [Paper](https://doi.org/10.1038/s41598-020-62922-y) | Longitudinal EHR modeling | **Adjacent:** foundational transformer representation learning for structured health records. |
| **Med-BERT** | npj Digital Medicine, 2021 | [Paper](https://doi.org/10.1038/s41746-021-00455-y) | Structured EHR and disease prediction | **Adjacent:** contextualized EHR representations used in later patient-level systems. |
| **Foresight** | The Lancet Digital Health, 2024 | [Paper](https://doi.org/10.1016/S2589-7500%2824%2900025-6) | Longitudinal records and clinical forecasting | Generative modeling of patient timelines for future-event prediction. |
| **Digital-twin GPT** | npj Digital Medicine, 2025 | [Paper](https://doi.org/10.1038/s41746-025-02004-3) | Longitudinal patient records and simulation | Uses generative modeling to construct patient digital twins. |
| **GAMENet** | AAAI, 2019 | [Paper](https://doi.org/10.1609/aaai.v33i01.33011126) | EHR and medication recommendation | **Adjacent:** graph-augmented medication recommendation from longitudinal records. |
| **SafeDrug** | IJCAI, 2021 | [Paper](https://doi.org/10.24963/ijcai.2021/514) | EHR and medication recommendation | **Adjacent:** medication recommendation with drug-interaction constraints. |

#### Continuous Physiological Monitoring

| Model or resource | Venue | Links | Modality and task | Notes |
|---|---|---|---|---|
| **SensorLM** | COLING, 2025 | [Paper](https://doi.org/10.52202/085713-1559) | Wearable sensor signals and language | Language-model interface for interpreting wearable sensor data. |
| **SuPreME** | Findings of EMNLP, 2025 | [Paper](https://doi.org/10.18653/v1/2025.findings-emnlp.633) | Physiological signals and language | Multimodal representation learning for physiological monitoring. |
| **K-MERL** | Findings of EMNLP, 2025 | [Paper](https://doi.org/10.18653/v1/2025.findings-emnlp.385) | ECG and language | Knowledge-enhanced multimodal representation learning for ECG. |
| **Thought2Text** | Findings of NAACL, 2025 | [Paper](https://doi.org/10.18653/v1/2025.findings-naacl.207) | EEG and text generation | Decodes natural-language text from brain activity signals. |
| **SzXAI** | MICCAI, 2025 | [Paper](https://doi.org/10.1007/978-3-032-05185-1_33) | EEG and seizure analysis | Explainability-oriented multimodal resource for seizure analysis. |

#### Multimodal Integration and Clinical Agents

| Model or resource | Venue | Links | Modality and task | Notes |
|---|---|---|---|---|
| **MedAgentBench** | NEJM AI, 2025 | [Paper](https://doi.org/10.1056/AIdbp2500144) | Clinical records, tools, and workflow tasks | Benchmark for agents interacting with clinical environments. |

### Population Scale

| Model or resource | Venue | Links | Population-level setting | Notes |
|---|---|---|---|---|
| **PromptCast** | IEEE TKDE | [Paper](https://doi.org/10.1109/TKDE.2023.3342137) | Time-series forecasting through language prompting | **Adjacent:** connects forecasting tasks with language-model prompting. |
| **Med-Gemini** | Preprint, 2024 | [Paper](https://arxiv.org/abs/2404.18416) | Broad medical reasoning and multimodal assistance | Generalist medical AI family spanning multiple healthcare tasks and modalities. |
| **Agent Hospital** | Preprint, 2024 | [Paper](https://arxiv.org/abs/2405.02957) | Simulated hospital and clinical workflow | Multi-agent simulation of healthcare interactions for training and evaluation. |

## Trustworthiness

The six dimensions are treated as distinct classification targets. A paper may appear in multiple dimensions when each assignment is justified by an explicit evaluation, method, or stated objective.

| Dimension | Working definition | Representative resources |
|---|---|---|
| **Truthfulness** | Factual and clinically grounded outputs that avoid unsupported or contradictory content. | [CARES](https://arxiv.org/abs/2406.06007) |
| **Robustness** | Stable behavior under distribution shifts, corruptions, prompt variations, and adversarial or missing inputs. | [PromptSmooth](https://doi.org/10.1007/978-3-031-72390-2_65) · [CARES](https://arxiv.org/abs/2406.06007) |
| **Fairness** | Comparable quality and error behavior across patient groups, sites, diseases, and acquisition conditions. | [FairCLIP](https://doi.org/10.1109/CVPR52733.2024.01168) · [CARES](https://arxiv.org/abs/2406.06007) |
| **Safety** | Avoidance of harmful guidance and unsafe behavior, with attention to clinical risk and refusal behavior. | [MedSafetyBench](https://arxiv.org/abs/2403.03744) · [CARES](https://arxiv.org/abs/2406.06007) · [SafeBench](https://doi.org/10.1007/s11263-025-02613-1) |
| **Privacy** | Protection against memorization, leakage, re-identification, and misuse of sensitive health information. | [CARES](https://arxiv.org/abs/2406.06007) · [Privacy review](https://doi.org/10.3390/info15110697) |
| **Explainability** | Human-interpretable evidence, localization, rationales, or reasoning traces that can be examined in context. | [PathVG](https://doi.org/10.1007/978-3-032-05169-1_44) · [MedVLM-R1](https://doi.org/10.1007/978-3-032-04981-0_32) · [ScanReason](https://doi.org/10.1007/978-3-031-73242-3_9) |

### Trustworthiness Methods and Resources

| Method or resource | Venue | Links | Clinical context | Focus and classification rationale |
|---|---|---|---|---|
| **CARES** | NeurIPS Datasets and Benchmarks, 2024 | [Paper](https://arxiv.org/abs/2406.06007) · [Project](https://cares-ai.github.io/) · [Code](https://github.com/richard-peng-xia/CARES) | Medical vision-language models | Directly evaluates multiple responsible-AI dimensions in medical MLLMs. |
| **PromptSmooth** | MICCAI, 2024 | [Paper](https://doi.org/10.1007/978-3-031-72390-2_65) | Medical vision-language models | Studies robustness to prompt variation through prompt smoothing. |
| **FairCLIP** | CVPR, 2024 | [Paper](https://doi.org/10.1109/CVPR52733.2024.01168) | Medical image-text representation learning | Explicitly optimizes and evaluates fairness in medical vision-language learning. |
| **MedSafetyBench** | COLING, 2025 | [Paper](https://arxiv.org/abs/2403.03744) · [Proceedings](https://doi.org/10.52202/079017-1054) | Medical language models | **Adjacent:** medical safety benchmark whose risk taxonomy can inform multimodal evaluation. |
| **SafeBench** | IJCV, 2025 | [Paper](https://doi.org/10.1007/s11263-025-02613-1) | General multimodal models | **Adjacent:** general MLLM safety benchmark relevant to medical stress testing. |
| **PathVG** | MICCAI, 2025 | [Paper](https://doi.org/10.1007/978-3-032-05169-1_44) | Pathology vision-language grounding | Uses visual grounding as inspectable evidence for pathology outputs. |
| **MedVLM-R1** | MICCAI, 2025 | [Paper](https://doi.org/10.1007/978-3-032-04981-0_32) | Medical images and reasoning | Studies reasoning behavior in medical vision-language models. |
| **ScanReason** | MICCAI, 2024 | [Paper](https://doi.org/10.1007/978-3-031-73242-3_9) | 3D medical imaging and language | Connects volumetric image understanding with explicit reasoning. |

## Evaluation and Benchmarks

### Evaluation Paradigms

| Paradigm | Typical evidence | Main limitation to report |
|---|---|---|
| **Automated metrics** | Exact match, overlap, semantic similarity, calibration, subgroup gaps, and perturbation sensitivity | Proxy metrics may not reflect clinical correctness or patient risk. |
| **Model-based judging** | Structured rubrics scored by an LLM or MLLM judge | Judge bias, prompt sensitivity, and agreement with clinicians require validation. |
| **Expert assessment** | Clinician ratings, pairwise preference, error severity, and workflow usefulness | Expensive, specialty-dependent, and sensitive to study design. |
| **Dynamic/workflow evaluation** | Tool use, longitudinal state changes, interactive cases, and simulated environments | Reproducibility and environment realism can be difficult to establish. |

### Seed Evaluation Resources

| Benchmark or resource | Venue | Links | Primary target | Notes |
|---|---|---|---|---|
| **CARES** | NeurIPS Datasets and Benchmarks, 2024 | [Paper](https://arxiv.org/abs/2406.06007) · [Project](https://cares-ai.github.io/) · [Code](https://github.com/richard-peng-xia/CARES) | Trustworthiness of medical vision-language models | Multi-dimensional evaluation resource for responsible medical MLLMs. |
| **MedAgentBench** | NEJM AI, 2025 | [Paper](https://doi.org/10.1056/AIdbp2500144) | Clinical agent behavior | Evaluates interaction with clinical records, tools, and workflows. |
| **MedSafetyBench** | COLING, 2025 | [Paper](https://arxiv.org/abs/2403.03744) | Medical safety | **Adjacent:** language-only benchmark with a medically grounded safety taxonomy. |
| **PromptSmooth** | MICCAI, 2024 | [Paper](https://doi.org/10.1007/978-3-031-72390-2_65) | Prompt robustness | Evaluates stability under prompt variation. |
| **FairCLIP** | CVPR, 2024 | [Paper](https://doi.org/10.1109/CVPR52733.2024.01168) | Group fairness | Measures and mitigates fairness gaps in medical vision-language learning. |

## Contributing

Contributions are welcome through pull requests. To keep the list consistent and reviewable, every proposed entry must include both a normalized record and a short classification justification.

### Required Entry Format

```markdown
| **Resource name** | Venue, Year | [Paper](URL) · [Code](URL) · [HF](URL) · [Data](URL) | Modality and task | Neutral one-sentence note. |
```

Omit unavailable links rather than adding empty placeholders. Use only official or primary URLs.

### Required Pull Request Information

1. **Proposed section:** the most specific clinical scale/specialty, trustworthiness dimension, or evaluation category.
2. **Classification reason:** one or two sentences explaining why the entry belongs there.
3. **Evidence:** a primary paper link and, when available, official code, weights, dataset, or project links.
4. **Neutral note:** what the resource contributes, without promotional or unsupported claims.
5. **Adjacency statement:** required when the work is not itself a medical MLLM.

### Classification Checks

- **Clinical landscape:** a medical or healthcare application is explicit, and at least one non-text modality plays a substantive role.
- **Trustworthiness:** the paper explicitly studies, evaluates, or mitigates at least one of the six dimensions.
- **Evaluation/benchmark:** the evaluated capability, population, setting, metrics, and reference answers or procedures are described.
- **Multiple sections:** duplicate placement is allowed only when each classification has separate supporting evidence.
- **Preprints:** mark them as `Preprint` and update the venue after publication.

Before opening a pull request, check that every URL resolves and that the entry is not already listed under another name.

## Citation

The manuscript is in preparation. The BibTeX entry will be added after the preprint receives a permanent public identifier.

If this repository helps your work before then, please cite the repository URL and access date.

## License

The curated list and repository maintenance materials are released under the [MIT License](LICENSE). The survey overview figure in `assets/overview.png` is excluded from the MIT License and remains copyright of the manuscript authors; see [LICENSE](LICENSE) for details.
