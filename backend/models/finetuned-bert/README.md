---
tags:
- sentence-transformers
- sentence-similarity
- feature-extraction
- generated_from_trainer
- dataset_size:184
- loss:CosineSimilarityLoss
base_model: sentence-transformers/all-mpnet-base-v2
widget:
- source_sentence: Experienced Cloud Engineer with 8 years of experience in AWS, Docker,
    Kubernetes, Linux. Delivered projects and collaborated across teams.
  sentences:
  - 'We are hiring a Business Analyst. Required skills: Requirements Gathering, SQL,
    Power BI, Stakeholder Management. Relevant industry experience preferred.'
  - 'We are hiring a ML Engineer. Required skills: Python, TensorFlow, Machine Learning,
    NLP. Relevant industry experience preferred.'
  - 'We are hiring a Cloud Engineer. Required skills: AWS, Docker, Kubernetes, Linux.
    Relevant industry experience preferred.'
- source_sentence: Experienced Cloud Engineer with 3 years of experience in AWS, Docker,
    Kubernetes, Linux. Delivered projects and collaborated across teams.
  sentences:
  - 'We are hiring a Data Analyst. Required skills: SQL, Python, Power BI, Excel.
    Relevant industry experience preferred.'
  - 'We are hiring a Data Analyst. Required skills: SQL, Python, Power BI, Excel.
    Relevant industry experience preferred.'
  - 'We are hiring a Cloud Engineer. Required skills: AWS, Docker, Kubernetes, Linux.
    Relevant industry experience preferred.'
- source_sentence: Experienced Business Analyst with 5 years of experience in Requirements
    Gathering, SQL, Power BI, Stakeholder Management. Delivered projects and collaborated
    across teams.
  sentences:
  - 'We are hiring a Cybersecurity Analyst. Required skills: SIEM, SOC, Network Security,
    Threat Detection. Relevant industry experience preferred.'
  - 'We are hiring a Business Analyst. Required skills: Requirements Gathering, SQL,
    Power BI, Stakeholder Management. Relevant industry experience preferred.'
  - 'We are hiring a Business Analyst. Required skills: Requirements Gathering, SQL,
    Power BI, Stakeholder Management. Relevant industry experience preferred.'
- source_sentence: Experienced Business Analyst with 2 years of experience in Requirements
    Gathering, SQL, Power BI, Stakeholder Management. Delivered projects and collaborated
    across teams.
  sentences:
  - 'We are hiring a Data Analyst. Required skills: SQL, Python, Power BI, Excel.
    Relevant industry experience preferred.'
  - 'We are hiring a Cloud Engineer. Required skills: AWS, Docker, Kubernetes, Linux.
    Relevant industry experience preferred.'
  - 'We are hiring a Business Analyst. Required skills: Requirements Gathering, SQL,
    Power BI, Stakeholder Management. Relevant industry experience preferred.'
- source_sentence: Experienced Full Stack Developer with 2 years of experience in
    React, Node.js, JavaScript, SQL. Delivered projects and collaborated across teams.
  sentences:
  - 'We are hiring a Data Analyst. Required skills: SQL, Python, Power BI, Excel.
    Relevant industry experience preferred.'
  - 'We are hiring a Full Stack Developer. Required skills: React, Node.js, JavaScript,
    SQL. Relevant industry experience preferred.'
  - 'We are hiring a Full Stack Developer. Required skills: React, Node.js, JavaScript,
    SQL. Relevant industry experience preferred.'
pipeline_tag: sentence-similarity
library_name: sentence-transformers
metrics:
- pearson_cosine
- spearman_cosine
model-index:
- name: SentenceTransformer based on sentence-transformers/all-mpnet-base-v2
  results:
  - task:
      type: semantic-similarity
      name: Semantic Similarity
    dataset:
      name: Unknown
      type: unknown
    metrics:
    - type: pearson_cosine
      value: -0.5023280870662461
      name: Pearson Cosine
    - type: spearman_cosine
      value: -0.3036962494663696
      name: Spearman Cosine
---

# SentenceTransformer based on sentence-transformers/all-mpnet-base-v2

This is a [sentence-transformers](https://www.SBERT.net) model finetuned from [sentence-transformers/all-mpnet-base-v2](https://huggingface.co/sentence-transformers/all-mpnet-base-v2). It maps sentences & paragraphs to a 768-dimensional dense vector space and can be used for retrieval.

## Model Details

### Model Description
- **Model Type:** Sentence Transformer
- **Base model:** [sentence-transformers/all-mpnet-base-v2](https://huggingface.co/sentence-transformers/all-mpnet-base-v2) <!-- at revision e8c3b32edf5434bc2275fc9bab85f82640a19130 -->
- **Maximum Sequence Length:** 384 tokens
- **Output Dimensionality:** 768 dimensions
- **Similarity Function:** Cosine Similarity
- **Supported Modality:** Text
<!-- - **Training Dataset:** Unknown -->
<!-- - **Language:** Unknown -->
<!-- - **License:** Unknown -->

### Model Sources

- **Documentation:** [Sentence Transformers Documentation](https://sbert.net)
- **Repository:** [Sentence Transformers on GitHub](https://github.com/huggingface/sentence-transformers)
- **Hugging Face:** [Sentence Transformers on Hugging Face](https://huggingface.co/models?library=sentence-transformers)

### Full Model Architecture

```
SentenceTransformer(
  (0): Transformer({'transformer_task': 'feature-extraction', 'modality_config': {'text': {'method': 'forward', 'method_output_name': 'last_hidden_state'}}, 'module_output_name': 'token_embeddings', 'architecture': 'MPNetModel'})
  (1): Pooling({'embedding_dimension': 768, 'pooling_mode': 'mean', 'include_prompt': True})
  (2): Normalize({})
)
```

## Usage

### Direct Usage (Sentence Transformers)

First install the Sentence Transformers library:

```bash
pip install -U sentence-transformers
```
Then you can load this model and run inference.
```python
from sentence_transformers import SentenceTransformer

# Download from the 🤗 Hub
model = SentenceTransformer("sentence_transformers_model_id")
# Run inference
sentences = [
    'Experienced Full Stack Developer with 2 years of experience in React, Node.js, JavaScript, SQL. Delivered projects and collaborated across teams.',
    'We are hiring a Full Stack Developer. Required skills: React, Node.js, JavaScript, SQL. Relevant industry experience preferred.',
    'We are hiring a Full Stack Developer. Required skills: React, Node.js, JavaScript, SQL. Relevant industry experience preferred.',
]
embeddings = model.encode(sentences)
print(embeddings.shape)
# [3, 768]

# Get the similarity scores for the embeddings
similarities = model.similarity(embeddings, embeddings)
print(similarities)
# tensor([[1.0000, 0.5523, 0.5523],
#         [0.5523, 1.0000, 1.0000],
#         [0.5523, 1.0000, 1.0000]])
```
<!--
### Direct Usage (Transformers)

<details><summary>Click to see the direct usage in Transformers</summary>

</details>
-->

<!--
### Downstream Usage (Sentence Transformers)

You can finetune this model on your own dataset.

<details><summary>Click to expand</summary>

</details>
-->

<!--
### Out-of-Scope Use

*List how the model may foreseeably be misused and address what users ought not to do with the model.*
-->

## Evaluation

### Metrics

#### Semantic Similarity

* Evaluated with [<code>EmbeddingSimilarityEvaluator</code>](https://sbert.net/docs/package_reference/sentence_transformer/evaluation.html#sentence_transformers.sentence_transformer.evaluation.EmbeddingSimilarityEvaluator)

| Metric              | Value       |
|:--------------------|:------------|
| pearson_cosine      | -0.5023     |
| **spearman_cosine** | **-0.3037** |

<!--
## Bias, Risks and Limitations

*What are the known or foreseeable issues stemming from this model? You could also flag here known failure cases or weaknesses of the model.*
-->

<!--
### Recommendations

*What are recommendations with respect to the foreseeable issues? For example, filtering explicit content.*
-->

## Training Details

### Training Dataset

#### Unnamed Dataset

* Size: 184 training samples
* Columns: <code>sentence_0</code>, <code>sentence_1</code>, and <code>label</code>
* Approximate statistics based on the first 100 samples:
  |          | sentence_0                                                                         | sentence_1                                                                         | label                                                            |
  |:---------|:-----------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------|:-----------------------------------------------------------------|
  | type     | string                                                                             | string                                                                             | float                                                            |
  | modality | text                                                                               | text                                                                               |                                                                  |
  | details  | <ul><li>min: 27 tokens</li><li>mean: 30.03 tokens</li><li>max: 32 tokens</li></ul> | <ul><li>min: 26 tokens</li><li>mean: 29.03 tokens</li><li>max: 31 tokens</li></ul> | <ul><li>min: 0.04</li><li>mean: 0.65</li><li>max: 0.95</li></ul> |
* Samples:
  | sentence_0                                                                                                                                                      | sentence_1                                                                                                                                    | label             |
  |:----------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------|:------------------|
  | <code>Experienced Full Stack Developer with 3 years of experience in React, Node.js, JavaScript, SQL. Delivered projects and collaborated across teams.</code>  | <code>We are hiring a Full Stack Developer. Required skills: React, Node.js, JavaScript, SQL. Relevant industry experience preferred.</code>  | <code>0.39</code> |
  | <code>Experienced Data Analyst with 2 years of experience in SQL, Python, Power BI, Excel. Delivered projects and collaborated across teams.</code>             | <code>We are hiring a Data Analyst. Required skills: SQL, Python, Power BI, Excel. Relevant industry experience preferred.</code>             | <code>0.27</code> |
  | <code>Experienced ML Engineer with 5 years of experience in Python, TensorFlow, Machine Learning, NLP. Delivered projects and collaborated across teams.</code> | <code>We are hiring a ML Engineer. Required skills: Python, TensorFlow, Machine Learning, NLP. Relevant industry experience preferred.</code> | <code>0.13</code> |
* Loss: [<code>CosineSimilarityLoss</code>](https://sbert.net/docs/package_reference/sentence_transformer/losses.html#cosinesimilarityloss) with these parameters:
  ```json
  {
      "loss_fct": "torch.nn.modules.loss.MSELoss",
      "cos_score_transformation": "torch.nn.modules.linear.Identity"
  }
  ```

### Training Hyperparameters
#### Non-Default Hyperparameters

- `per_device_train_batch_size`: 16
- `per_device_eval_batch_size`: 16
- `num_train_epochs`: 10
- `multi_dataset_batch_sampler`: round_robin

#### All Hyperparameters
<details><summary>Click to expand</summary>

- `do_predict`: False
- `prediction_loss_only`: True
- `per_device_train_batch_size`: 16
- `per_device_eval_batch_size`: 16
- `gradient_accumulation_steps`: 1
- `eval_accumulation_steps`: None
- `torch_empty_cache_steps`: None
- `learning_rate`: 5e-05
- `weight_decay`: 0.0
- `adam_beta1`: 0.9
- `adam_beta2`: 0.999
- `adam_epsilon`: 1e-08
- `max_grad_norm`: 1
- `num_train_epochs`: 10
- `max_steps`: -1
- `lr_scheduler_type`: linear
- `lr_scheduler_kwargs`: None
- `warmup_ratio`: None
- `warmup_steps`: 0
- `log_level`: passive
- `log_level_replica`: warning
- `log_on_each_node`: True
- `logging_nan_inf_filter`: True
- `enable_jit_checkpoint`: False
- `save_on_each_node`: False
- `save_only_model`: False
- `restore_callback_states_from_checkpoint`: False
- `use_cpu`: False
- `seed`: 42
- `data_seed`: None
- `bf16`: False
- `fp16`: False
- `bf16_full_eval`: False
- `fp16_full_eval`: False
- `tf32`: None
- `local_rank`: -1
- `ddp_backend`: None
- `debug`: []
- `dataloader_drop_last`: False
- `dataloader_num_workers`: 0
- `dataloader_prefetch_factor`: None
- `disable_tqdm`: False
- `remove_unused_columns`: True
- `label_names`: None
- `load_best_model_at_end`: False
- `ignore_data_skip`: False
- `fsdp`: []
- `fsdp_config`: {'min_num_params': 0, 'xla': False, 'xla_fsdp_v2': False, 'xla_fsdp_grad_ckpt': False}
- `accelerator_config`: {'split_batches': False, 'dispatch_batches': None, 'even_batches': True, 'use_seedable_sampler': True, 'non_blocking': False, 'gradient_accumulation_kwargs': None}
- `parallelism_config`: None
- `deepspeed`: None
- `label_smoothing_factor`: 0.0
- `optim`: adamw_torch_fused
- `optim_args`: None
- `group_by_length`: False
- `length_column_name`: length
- `project`: huggingface
- `trackio_space_id`: trackio
- `ddp_find_unused_parameters`: None
- `ddp_bucket_cap_mb`: None
- `ddp_broadcast_buffers`: False
- `dataloader_pin_memory`: True
- `dataloader_persistent_workers`: False
- `skip_memory_metrics`: True
- `push_to_hub`: False
- `resume_from_checkpoint`: None
- `hub_model_id`: None
- `hub_strategy`: every_save
- `hub_private_repo`: None
- `hub_always_push`: False
- `hub_revision`: None
- `gradient_checkpointing`: False
- `gradient_checkpointing_kwargs`: None
- `include_for_metrics`: []
- `eval_do_concat_batches`: True
- `auto_find_batch_size`: False
- `full_determinism`: False
- `ddp_timeout`: 1800
- `torch_compile`: False
- `torch_compile_backend`: None
- `torch_compile_mode`: None
- `include_num_input_tokens_seen`: no
- `neftune_noise_alpha`: None
- `optim_target_modules`: None
- `batch_eval_metrics`: False
- `eval_on_start`: False
- `use_liger_kernel`: False
- `liger_kernel_config`: None
- `eval_use_gather_object`: False
- `average_tokens_across_devices`: True
- `use_cache`: False
- `prompts`: None
- `batch_sampler`: batch_sampler
- `multi_dataset_batch_sampler`: round_robin
- `router_mapping`: {}
- `learning_rate_mapping`: {}

</details>

### Training Logs
| Epoch | Step | spearman_cosine |
|:-----:|:----:|:---------------:|
| 1.0   | 12   | -0.2927         |
| 2.0   | 24   | -0.3327         |
| 3.0   | 36   | -0.3444         |
| 4.0   | 48   | -0.3448         |
| 5.0   | 60   | -0.3731         |
| 6.0   | 72   | -0.3650         |
| 7.0   | 84   | -0.3446         |
| 8.0   | 96   | -0.3309         |
| 9.0   | 108  | -0.3403         |
| 10.0  | 120  | -0.3414         |
| 1.0   | 12   | -0.3037         |


### Training Time
- **Training**: 2.3 minutes

### Framework Versions
- Python: 3.12.13
- Sentence Transformers: 5.5.1
- Transformers: 5.0.0
- PyTorch: 2.11.0+cpu
- Accelerate: 1.13.0
- Datasets: 4.0.0
- Tokenizers: 0.22.2

## Citation

### BibTeX

#### Sentence Transformers
```bibtex
@inproceedings{reimers-2019-sentence-bert,
    title = "Sentence-BERT: Sentence Embeddings using Siamese BERT-Networks",
    author = "Reimers, Nils and Gurevych, Iryna",
    booktitle = "Proceedings of the 2019 Conference on Empirical Methods in Natural Language Processing",
    month = "11",
    year = "2019",
    publisher = "Association for Computational Linguistics",
    url = "https://arxiv.org/abs/1908.10084",
}
```

<!--
## Glossary

*Clearly define terms in order to be accessible across audiences.*
-->

<!--
## Model Card Authors

*Lists the people who create the model card, providing recognition and accountability for the detailed work that goes into its construction.*
-->

<!--
## Model Card Contact

*Provides a way for people who have updates to the Model Card, suggestions, or questions, to contact the Model Card authors.*
-->