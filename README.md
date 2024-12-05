# Tabular_Data_QA
Evaluate TAPAS, a Tabular QA system on the DataBench bench mark to evaluate its limitations and successes.

Apply these changes to the SemEval Task 8 Subtask 2 (https://jorses.github.io/semeval/) and use DataBench, created and proposed in this task,
to test the performance of the new adjusted TAPAS model. 

Since paper is unpublished we can verify the results of the paper against the DataBench data sets

## Steps to taken:

1. Load in Data
  a. Currently have a sample of the forbes_001 loaded in as sample_df, when we train for real we might want to read from disk
2. Convert that data into a SQA format (
  a. answer coordinates
  b. float answers
  c. questions filtered only to be number and category
4. Finetune TAPAS WTQ model
5. Conduct Inference
6. DataBench Eval

## Current Progress

toy_df.csv
low percentage accuracy
