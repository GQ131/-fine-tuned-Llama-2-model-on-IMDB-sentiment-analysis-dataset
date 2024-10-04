---
library_name: transformers
tags: []
---

# Model Card for Model ID

This model is a fine-tuned version of the LLaMA 2 7B model for IMDb movie review sentiment analysis. The model has been adapted to classify movie reviews as either positive or negative using a subset of the IMDb movie reviews dataset. The fine-tuning process included Low-Rank Adaptation (LoRA) to efficiently modify a subset of the model's weights without requiring extensive computational resources.


## Model Details

### Model Description
- **Developed by:** GQ
- **Funded by:** Self-funded
- **Shared by:** GQ
- **Model type:** Transformer-based language model, specifically LLaMA 2 (7 billion parameters)
- **Language(s) (NLP):** English
- **License:** Apache License 2.0
- **Finetuned from model:** meta-llama/Llama-2-7b-hf

### Model Sources [optional]

<!-- Provide the basic links for the model. -->

- **Repository:** [More Information Needed]
- **Paper [optional]:** [More Information Needed]
- **Demo [optional]:** [More Information Needed]

## Uses

<!-- Address questions around how the model is intended to be used, including the foreseeable users of the model and those affected by the model. -->

### Direct Use

This model can be used directly to perform sentiment analysis on English-language movie reviews. Users can classify new reviews into "Positive" or "Negative" categories using the model's predictions.


### Downstream Use [optional]

The model can be extended to related sentiment analysis tasks for other review-based datasets, such as product reviews, book reviews, or restaurant reviews, with minimal adjustments.


### Out-of-Scope Use

This model is not intended for use in 
- Sensitive or high-stakes applications (e.g., medical diagnosis, employment decisions).
- Non-English sentiment analysis without further fine-tuning on relevant datasets.
- Language tasks requiring context-specific understanding beyond the domain of movie reviews.


## Bias, Risks, and Limitations

The model may have inherited biases present in the IMDb dataset, such as biases in the language used for different genders, movie genres, or cultural references. The model might perform poorly on texts that are significantly different from the type of movie reviews it was trained on.

### Recommendations

- Users should conduct further evaluations on their specific datasets before deploying the model.
- Consider fine-tuning on more diverse datasets if you plan to use this for broader applications.

## How to Get Started with the Model

Use the code below to get started with the model.


## Training Details

### Training Data

- Dataset: IMDb Movie Reviews (10% Hold-out Set)

- Description: The dataset contains 50,000 movie reviews split into 25,000 positive and 25,000 negative reviews. The model was trained on a balanced subset and evaluated on a 10% hold-out set for validation.

- Dataset: [IMDb Dataset on Hugging Face](https://huggingface.co/datasets/imdb)


### Training Procedure

<!-- This relates heavily to the Technical Specifications. Content here should link to that section when it is relevant to the training procedure. -->

#### Preprocessing [optional]
- Reviews were preprocessed to remove special characters, HTML tags, and unnecessary whitespaces.
- Text was tokenized using the Hugging Face AutoTokenizer.

#### Training Hyperparameters

- **Training regime:** Mixed precision (fp16)
- **Optimizer:** paged_adamw_32bit
- **Learning Rate:** 2e-4
- **Batch Size:** 2 per device
- **Number of Epochs:** 1
- **Gradient Accumulation Steps:** 1
- **Warmup Ratio:** 0.03
- **Scheduler Type:** Cosine
  
#### Speeds, Sizes, Times [optional]

- **Model Size:** 7 billion parameters
- **Training Time:** ~5 hours on a single NVIDIA A100 GPU
- **Inference Speed:** ~0.3 seconds per review on GPU

## Evaluation

<!-- This section describes the evaluation protocols and provides the results. -->

### Testing Data, Factors & Metrics

#### Testing Data

IMDb Movie Reviews (10% hold-out set): This subset was used for evaluating model performance after fine-tuning.


#### Factors

- **Review Length:** Short (under 50 words), Medium (50-200 words), Long (200+ words)
- **Sentiment Intensity:** Standard (positive/negative) vs. Extreme (very positive/very negative)
- **Writing Style:** Formal, Informal, Slang-heavy
- **Genre Topics:** Action, Comedy, Horror, Drama

#### Metrics

- **Accuracy:** Measures the proportion of correctly classified reviews.
- **Precision:** Measures the proportion of true positive predictions out of all positive predictions.
- **Recall:** Measures the proportion of true positive predictions out of all actual positive samples.
- **F1-Score:** Harmonic mean of precision and recall.

### Results
- **Accuracy:** 90%
- **F1-Score:** 89.7%
- **Precision:** 90.3%
- **Recall:** 89.2%

#### Summary

The model shows strong performance in distinguishing positive and negative reviews, achieving an overall accuracy of 90%. Minor performance drops were observed on extreme sentiments and very short reviews.

## Model Examination [optional]

<!-- Relevant interpretability work for the model goes here -->

[More Information Needed]

## Environmental Impact

<!-- Total emissions (in grams of CO2eq) and additional considerations, such as electricity usage, go here. Edit the suggested text below accordingly -->

Carbon emissions can be estimated using the [Machine Learning Impact calculator](https://mlco2.github.io/impact#compute) presented in [Lacoste et al. (2019)](https://arxiv.org/abs/1910.09700).

- **Hardware Type:** Single NVIDIA A100 GPU
- **Hours used:** ~5 hours
- **Cloud Provider:** [More Information Needed]
- **Compute Region:** us-west-1
- **Carbon Emitted:** Estimated at ~45 kg CO2eq

## Technical Specifications [optional]

### Model Architecture and Objective

[More Information Needed]

### Compute Infrastructure

[More Information Needed]

#### Hardware

[More Information Needed]

#### Software

[More Information Needed]

## Citation [optional]

<!-- If there is a paper or blog post introducing the model, the APA and Bibtex information for that should go in this section. -->

**BibTeX:**

[More Information Needed]

**APA:**

[More Information Needed]

## Glossary [optional]

<!-- If relevant, include terms and calculations in this section that can help readers understand the model or model card. -->

[More Information Needed]

## More Information [optional]

[More Information Needed]

## Model Card Authors [optional]

[More Information Needed]

## Model Card Contact

[More Information Needed]