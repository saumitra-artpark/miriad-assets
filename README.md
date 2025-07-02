# miriad-assets

## Reference
- Paper link: [MIRIAD: Augmenting LLMs with millions of medical query-response pairs](https://arxiv.org/abs/2506.06091)
- Github repository: [eth-medical-ai-lab/MIRIAD](https://github.com/eth-medical-ai-lab/MIRIAD)

## 📋 Documentation Overview

This repository contains comprehensive documentation and visual flowcharts for the **MIRIAD** (Medical Information Retrieval with Intelligent Answer Discovery) dataset creation process. The documentation is organized into three main files that should be reviewed in the following order:

### 📖 Recommended Reading Order

1. **[Overview.md](Overview.md)** - Start here for the complete dataset creation pipeline
2. **[Segmentation.md](Segmentation.md)** - Deep dive into article processing and segmentation
3. **[Human Eval.md](Human%20Eval.md)** - Understanding quality validation through expert evaluation

---

## 🔍 File Descriptions

### 1. 📊 Overview.md
**Purpose**: Provides the complete end-to-end view of MIRIAD dataset creation

**Flowchart Overview**: This comprehensive flowchart illustrates the entire MIRIAD dataset pipeline from initial data collection to final validation. It shows three main phases:
- **Dataset Generation**: Starting from 2.5M medical papers from Semantic Scholar's S2ORC, filtering and processing to create 10.6M raw QA pairs
- **Quality Control**: Rule-based filtering and LLM-based classification using GPT-4 and Mistral-7B to produce 4.4M high-confidence QA pairs
- **Human Validation**: Expert review process confirming the effectiveness of automated quality control

**Key Metrics**: 
- Final dataset: 4.4M+ QA pairs from 800K+ papers across 56 medical disciplines
- Quality scores: 92.3% groundedness, 88.6% factuality, 78.4% relevance agreement

### 2. ✂️ Segmentation.md
**Purpose**: Details the critical article segmentation and sentence filtering process

**Flowchart Overview**: This technical flowchart breaks down how 894K medical papers are processed into clean, manageable passages. The process involves:
- **Article Processing**: Splitting articles into sentences and accumulating them into passages ≤1,000 tokens
- **Quality Filtering**: Sophisticated sentence-level filtering based on token length analysis
- **Noise Reduction**: Excluding sentences >400 tokens due to high irrelevant content (67% noise in 500-600 token range)

**Key Innovation**: The segmentation strategy balances passage coherence with quality, ensuring each passage contains meaningful medical content while maintaining computational efficiency.

### 3. 👥 Human Eval.md
**Purpose**: Documents the human expert validation methodology and results

**Flowchart Overview**: This validation flowchart shows the rigorous evaluation process involving 5 medical experts who assessed 168 QA pairs across 56 passages. The process includes:
- **Expert Recruitment**: Selection of domain specialists for annotation
- **Multi-dimensional Evaluation**: Assessment across relevance, factuality, and groundedness
- **Agreement Analysis**: Both inter-annotator agreement among humans and comparison with GPT-4 annotations
- **Validation Results**: Demonstrating that GPT-4 shows stronger agreement with humans than humans do with each other

**Key Finding**: The validation confirms that LLM-supervised filtering is more reliable than purely human-based approaches for large-scale dataset curation.

---

## 🎯 Quick Start

1. Begin with **Overview.md** to understand the overall MIRIAD creation process
2. Review **Segmentation.md** to understand how medical texts are processed and cleaned  
3. Examine **Human Eval.md** to see how quality validation was performed

Each file contains detailed Mermaid flowcharts that visualize the respective processes, making complex methodologies easy to understand and follow.

---

## 📈 Dataset Statistics

- **Total QA Pairs**: 4,487,542 (high-confidence)
- **Source Papers**: 812,384 medical papers  
- **Medical Disciplines**: 56 specialties covered
- **Time Range**: 98.4% from 1970-2021
- **Question Length**: 15-20 words average
- **Answer Length**: 60-80 words average
