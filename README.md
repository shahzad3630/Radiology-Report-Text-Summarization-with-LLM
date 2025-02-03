# Radiology-Report-Text-Summarization-with-Transformers

Using the LLMs to do the text summarization of the medical radiology reports.

## Data:
The data used is of Open-i from where the radiology reports have been retrieved. The dataset in this repository consists of jsonl files that hold the data with the medical report text and its corresponding summarization. There are three jsonl files corresponding to train, test and validation subsets.


## LLMs used:
<li>BART</li>
<li>T5</li>
<li>GPT-2 (Openai)</li>
<li>LLama</li>
<li>Gemma</li>

<br>
The models above were used on the dataset to check their performance for the task of text summarization. The T5 and BART models were fine tuned on the dataset while the rest three were used with prompt engineering. The performance of the models were evaluated using the rouge metric. <br><br>

While using the prompt engineering, various kinds of templates were used like zero shot, one shot, two shot and four shot using zero, one, two and four examples to the model to understand what the context is and trying to give the best possible results.
<br>

## Evaluation:
The rouge values for the models on the test data are as follows:

### Fine Tuning:

|Model          |   Rouge-1 | Rouge-2   | Rouge-L   |
|:---------------:|:-----------:|:-----------:|:-----------:|
|BART           | 0.2498    | 0.1579    | 0.2286    |
|T5-Large       | 0.5948    | 0.5039    | **0.5898**    |   

<br>

### Prompt Engineering:

**Gemma**


|Model          |   Rouge-1 | Rouge-2   | Rouge-L   |
|:---------------:|:-----------:|:-----------:|:-----------:|
| Zero shot     | 0.0982    | 0.0154    | 0.0889    |
| One shot      | 0.1317    | 0.0317    | 0.1181    |
| Two shot      | 0.1321    | 0.0320    | 0.1168    |
| Four shot     | 0.1339    | 0.0446    | **0.1218**    |

<br>

**GPT2**

|Model          |   Rouge-1 | Rouge-2   | Rouge-L   |
|:---------------:|:-----------:|:-----------:|:-----------:|
| Zero shot     | 0.0044    | 0.0007    | 0.0044    |
| One shot      | 0.0089    | 0.0029    | 0.0088    |
| Two shot      | 0.0150    | 0.0047    | 0.0149    |
| Four shot     | 0.0202    | 0.0052    | **0.0186**    |
 
<br>

**Llama**


|Model          |   Rouge-1 | Rouge-2   | Rouge-L   |
|:---------------:|:-----------:|:-----------:|:-----------:|
| Zero shot     | 0.0964    | 0.0098    | 0.0879    |
| One shot      | 0.1704    | 0.0487    | 0.1582    |
| Two shot      | 0.1753    | 0.0588    | **0.1643**    |
| Four shot     | 0.1718    | 0.0498    | 0.1616    |
 
<br>

## Conclusion:
T5 model fine tuned on the test data gives us the best results. One more reason is because the model is pre-trained on the medical dataset that makes the model performance much better compared to other models.