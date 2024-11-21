# Tabular_Data_QA
Expand upon the data synthesizing technique in the “TabuLa: Harnessing Language Models for Tabular Data Synthesis” paper 
and apply it to the DataBench QA format. We hope to evaluate the quality of TabuLa data synthesis on Tabular Data QA, evaluated
by the DataBench benchmark

Apply these changes to the SemEval Task 8 Subtask 2 (https://jorses.github.io/semeval/) and use DataBench, created and proposed in this task,
to test the performance of the new adjusted TabuLa model. 

Since paper is unpublished we can verify the results of the paper against the DataBench data sets

## Steps to take:

1. Load in Data
  a. Currently have a sample of the forbes_001 loaded in as sample_df, when we train for real we might want to read from disk
2. Convert that data into a TabuLa style format (
  a. X Y for each column X and value Y
  b. middle padding
  c. this might be in their code somewhere
3. If doing In-Context, format all of the inputs to give for training
  a. question /sep/ df /sep/ cols used /sep/ maybe return type
  b. instinctually this feels way to big but IDK
4. Train on data
5. DataBench Eval

## Other possible strategies

- adapt DataBench data to work with TAPAS or TaBERT 

