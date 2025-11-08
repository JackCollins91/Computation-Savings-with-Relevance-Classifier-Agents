# Saving Computation with Relevance Classifiers in Long-Context Filtering

This repository accompanies the paper  
**“Saving Computation with Relevance Classifiers in Long Context Filtering”**,  
and provides a demonstration of how smaller LLM-based classifiers can reduce computational cost in long-context reasoning tasks.

📄 See the full paper:  
[`Saving_computation_with_relevance_classifiers_in_long_context_filtering.pdf`](./Saving_computation_with_relevance_classifiers_in_long_context_filtering.pdf)

---

## 🧠 Abstract
Extremely long context handling is a common application for Large Language
Models (LLMs). Researchers have developed numerous techniques for managing information 
that must be filtered from among long passages of irrelevant text. However, all such
techniques benefit from a mechanism that filters out truly irrelevant text before applying
the LLM. Besides Retrieval-Augmented Generation, which relies on semantic similarity between 
the query and supporting text, the main alternative is to parse the text with another
LLM agent that comprehends the task to detect and retain relevant text while discarding
irrelevant passages. However, for such an agent to perform these reasoning tasks effectively,
it typically must be a fairly large, and therefore computationally expensive, model. This
method stub proposes an alternative process in which this agent effectively labels a subset
of data, which is then used to train a smaller LLM agent with a classification head to serve
as a first-pass classifier. By tuning the classification thresholds to filter out only those text
passages confidently labeled as irrelevant, the smaller agent reduces the number of chunks
that need to be processed by the larger agent, yielding computational savings under the
right conditions. This method stub formalizes the conditions for such savings and provides
a demonstration using Phi-2-Medium as the smaller agent and Phi-3 as the larger agent.
The demonstration yielded a 13.30% reduction in average FLOPs per token.

---

## 🚀 Running the Demo

This notebook is designed for execution on **Google Colab** with an A100 runtime.

### Quick Start

1. Open the notebook [`main.ipynb`](./main.ipynb) in **Google Colab**.
2. Set the **runtime type** to:  
   `Runtime > Change runtime type > GPU > A100`
3. Run all cells to reproduce the relevance-classifier pipeline and performance estimates.

---

## 🧮 Dependencies (TBD)

Local replication is still under development, you may try:

```bash
pip install -r requirements.txt
