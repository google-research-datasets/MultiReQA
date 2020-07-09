# MultiReQA

We are creating a challenging new benchmark MultiReQA: A Cross-Domain Evaluation for Retrieval Question Answering Models. Retrieval question answering (ReQA) is the task of retrieving a sentence-level answer to a question from an open corpus. MultiReQA is a new multi-domain ReQA evaluation suite composed of eight retrieval QA tasks drawn from publicly available QA datasets from the [MRQA shared task](https://mrqa.github.io/). We believe that MultiReQA tests retrieval QA models’ ability to perform domain transfer tasks.

This repository hosts the codes to convert existing QA datasets from MRQA shared task to the format of MultiReQA benchmark, as well as the sentence boundary annotations for QA datasets to exactly reproduce our work. Note that we are not redistributing the content in the original datasets available on MRQA share task, but just the sentence boundary annotations.

# Data Description
MultiReQA contains the sentence boundary annotation from eight publicly available QA datasets including SearchQA, TriviaQA, HotpotQA, NaturalQuestions, SQuAD, BioASQ, RelationExtraction, and TextbookQA. Five of these datasets, including SearchQA, TriviaQA, HotpotQA, NaturalQuestions, SQuAD, contain both training and test data, and three, in cluding BioASQ, RelationExtraction, TextbookQA, contain only the test data.

## Data Format
All of the datasets of MultiReQA have been adapted to follow a unified format. They are stored as compressed [JSONL](http://jsonlines.org/) files (with file extension `.jsonl.gz`).

The general format is:

```
{
  "candidate_id": <candidate_id>,
  "response_start": <response_start>,
  "response_end": <response_end>
}
...
```
### Fields
- **candidate_id:** The candidate id of the candidate sentence. It consists of the original qid from the MRQA shared task.
- **response_start:** The start index of the sentence with respect to its original context.
- **response_end:** The end index of the sentence with respect to its original context.

## Data Statistics
We show the number of candidate sentences for each dataset in the table below.

|                    | MultiReQA |            |
|--------------------|-----------|------------|
|                    |     train |       test |
|           SearchQA |   629,160 |    454,836 |
|           TriviaQA |   335,659 |    238,339 |
|           HotpotQA |   104,973 |     52,191 |
|              SQuAD |    87,133 |     10,642 |
|   NaturalQuestions |   106,521 |     22,118 |
|             BioASQ |         - |     14,158 |
| RelationExtraction |         - |      3,301 |
|         TextbookQA |         - |      3,701 |

# Reference
If you use this dataset, please cite [[1]](https://arxiv.org/abs/2005.02507):

[1] Mandy Guo, Yinfei Yang, Daniel Cer, Qinlan Shen, Noah Constant (2020). [MultiReQA: A Cross-Domain Evaluation for Retrieval Question Answering Models](https://arxiv.org/abs/2005.02507). arXiv preprint arXiv:2004.05484.
```
@misc{m2020multireqa,
    title={MultiReQA: A Cross-Domain Evaluation for Retrieval Question Answering Models},
    author={Mandy Guo and Yinfei Yang and Daniel Cer and Qinlan Shen and Noah Constant},
    year={2020},
    eprint={2005.02507},
    archivePrefix={arXiv},
    primaryClass={cs.CL}
}
```
