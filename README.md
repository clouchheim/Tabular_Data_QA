# Tabular Data Question-Answering: Integrating DataBench and TAPAS

**Author:** Carter Louchheim, Williams College
**Email:** chl2@williams.edu

## Abstract

This paper addresses a subsection of SemEval Task 8 SubTask 2, which focuses on developing the most effective Question Answering (QA) system for tabular data using the newly created DataBench dataset. Leveraging TAPAS, a BERT-based model specifically designed for tabular data QA, I fine-tuned the weakly supervised WTQ version of TAPAS on a subset of number and category-answer questions from DataBench. 

Preliminary results demonstrate that the TAPAS WTQ model, not finetuned on the DataBench data, outperforms Z-ICL and Code Prompt strategies in these answer types. However, the study is constrained by the manual annotation of answer coordinates, essential for TAPAS training, and the limited diversity of the annotated dataset, raising concerns about potential overfitting. These findings highlight TAPAS's promise in tabular data QA while emphasizing the need for broader datasets and automated annotation tools to improve scalability and generalization.

## Introduction

Accurately answering questions based on tabular data is a critical challenge in natural language processing (NLP), with applications spanning domains such as medicine, finance, and other data-rich industries. While humans often find it difficult to quickly parse complex tables, natural language interfaces that bridge this gap can significantly improve accessibility and decision-making. 

To address this need, the SemEval 2025 Task 8 introduced the DataBench benchmark, a novel dataset comprising real-world tables with diverse data types, domains, and question formats. This dataset serves as a standard for evaluating systems capable of answering numerical, categorical, boolean, and list-based questions.

Despite advances in tabular question-answering (QA) systems, current state-of-the-art models achieve only approximately 75% accuracy on number and category-based questions and struggle further—achieving just about 35% accuracy—on tasks that do not require Python interpreters.

## Performance Metrics Table

| MODEL | altered questions | overall accuracy | number accuracy | category accuracy |
|-------|-------------------|-----------------|----------------|------------------|
| Z-ICL Prompt 2 | FALSE | 0.342 | 0.315 | 0.368 |
| TAPAS WTQ | FALSE | **0.483** | **0.482** | 0.484 |
| TAPAS WTQ | TRUE | 0.467 | 0.396 | **0.531** |
| Model 1-alter | FALSE | **0.483** | **0.482** | 0.484 |
| Model 1-alter | TRUE | **0.483** | 0.448 | 0.515 |
| Model 1 | FALSE | 0.426 | **0.482** | 0.375 |
| Model 1 | TRUE | 0.409 | 0.465 | 0.359 |

*Note: Accuracies for Z-ICL Prompt 2 act as a baseline for DataBench accuracies, calculated on the true DataBench test set that was not available during this project*

## Key Findings

1. The TAPAS models outperformed In-Context Prompt models by at least 9% in overall accuracy.
2. TAPAS WTQ and Model 1-alter achieved 48.2% overall accuracy.
3. For number questions, models achieved 48.2% accuracy on the unaltered test set.
4. On the altered test set, categorical questions showed improved performance.

## Conclusion

This research explores the potential of TAPAS in addressing tabular question-answering challenges. While not outperforming the Code-Prompt approach, the project demonstrates significant improvements over In-Context Learning strategies, consistently achieving around 48% accuracy.

The most critical insight is the pathway towards more accessible, human-readable tabular data question-answering systems that eliminate the need for complex code interpreters.

## Limitations

1. Manual annotation of answer coordinates is labor-intensive.
2. Limited training and development set size.
3. Potential for perpetuating historical biases in source datasets.

## Future Work

1. Develop automated annotation techniques
2. Expand dataset diversity
3. Create more sophisticated natural language understanding techniques
