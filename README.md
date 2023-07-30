# LLM Summarization Capability Evaluation
This project is meant for evaluating the summarization capabilities of three Large Language Models (T5-Small, T5-Large and GPT2). 

## Dataset: 
CNN_Daily Mail Dataset [https://huggingface.co/datasets/cnn_dailymail]

## Evaluation Metric

ROUGE: Recall-Oriented Understudy for Gisting Evaluation (ROUGE) is a set of evaluation metrics designed for comparing summaries from Lin et al., 2004.  See [Wikipedia](https://en.wikipedia.org/wiki/ROUGE_&#40;metric&#41;) for more info.  Here, we use the Hugging Face Evaluator wrapper to call into the `rouge_score` package.  This package provides 4 scores:
- `rouge1`: ROUGE computed over unigrams (single words or tokens)
- `rouge2`: ROUGE computed over bigrams (pairs of consecutive words or tokens)
- `rougeL`: ROUGE based on the longest common subsequence shared by the summaries being compared
- `rougeLsum`: like `rougeL`, but at "summary level," i.e., ignoring sentence breaks (newlines)

## Compute Resources
- Single GPU available from Google Colab Free version

### How did I fit three models in Google Colab Free version ###
Deleted and cleaned the gpu memory after every evaluation so the GPU is not full.
```
del model
torch.cuda.empty_cache()
gc.collect() # Garbage Collector
```

### Results
<img width="272" alt="image" src="https://github.com/Cenrax/LLMSummaEvaluation/assets/43017632/a6bb5b04-6dcc-427e-a500-bb663702ab2c">

Model specific results and the summarization results are available in the attached notebook


