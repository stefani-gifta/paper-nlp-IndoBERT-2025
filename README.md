# Sentiment Analysis of Comments Across Different Social Media Using IndoBERT

This paper uses NLP to analyze the sentiments of Indonesian-language social media comments across Twitter, Instagram, and TikTok using a custom fine-tuned IndoBERTweet model.

## Dataset

Comments were scraped from publicly available posts using the hashtag _#KaburAjaDulu_ (#JustRunAwayFirst), a viral Indonesian political hashtag.

Dataset is available in a separate repository: [cross-platform dataset](https://github.com/stefani-gifta/cross-platform-dataset-2025).

## Model

### Pipeline

```
IndoBERTweet (base)
        ↓
Fine-tuned IndoBERTweet (ridho2401/sa-tapera)
        ↓
Transfer learning on cross-platform dataset
        ↓
Custom IndoBERTweet
```

### Hyperparameters

Result of Custom IndoBERTweet's hyperparameter tuning:
 
| Parameter     | Value    |
|---------------|----------|
| Learning rate | 3.5e-5   |
| Epochs        | 6        |
| Weight decay  | 0.025    |
| Scheduler     | linear   |
| Batch size    | 4        |
| F1-score (val)| 0.740    |
| F1-score (test)| 0.745   |
| Accuracy (test)| 75%     |

### Evaluation Results

| Platform  | Model        | Accuracy | F1-Score (Weighted) |
|-----------|-------------|----------|----------------------|
| Twitter   | Fine-tuned   | 66.51%   | 0.66                 |
| Twitter   | **Custom**   | **86.85%** | **0.87**           |
| Instagram | Fine-tuned   | 61.03%   | 0.60                 |
| Instagram | **Custom**   | **89.54%** | **0.89**           |
| TikTok    | Fine-tuned   | 60.29%   | 0.64                 |
| TikTok    | **Custom**   | **90.63%** | **0.91**           |

### Usage

The Custom IndoBERTweet model is available in ZIP within this repository.

If you'd like to run the notebook, you can download the dataset [here](https://github.com/stefani-gifta/cross-platform-dataset-2025).

## Limitations
 
- Comments with only one hashtag ("#KaburAjaDulu"), possibly resulting in sampling bias
- Class imbalance, leading to a weaker model in predicting positive sentiments
- Lack of expertise during manual labeling
- Lack of multimodal data and engagement from passive users

## Citation
 
If you use this paper, please cite:
 
```bibtex
@unpublished{ganda2025sentiment,
  title  = {Sentiment Analysis of Comments Across Different Social Media Using IndoBERT},
  author    = {Ganda, Stefani Gifta and Kenni, Edeline and Sutoyo, Rhio and Jeremy, Nicholaus Hendrik},
  note   = {Undergraduate research, Bina Nusantara University},
  year   = {2025}
}
```

## Contributors

| Name | Role |
|------|------|
| Stefani Gifta Ganda | Lead researcher, methodology, model training |
| Edeline Kenni | Methodology, result analysis |
| Nicholaus Hendrik Jeremy | Supervision (lecturer) |
| Rhio Sutoyo | Supervision, validation (lecturer) |

## License
 
This project is licensed under the MIT License.
