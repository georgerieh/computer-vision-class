# computer-vision-class

## Intro
This repository contains code submission for competion in class on Computer Vision on prediction the right emoji vendor from 7 available options: Apple, Samsung, Google, etc. There is 9000 pictures in the training data, and 9000 pictures in the test data.

The pictures are colored PNG images in different sizes, so some data transformation is required, including grayscaling and resizing. Additionally, this notebook specifically features the training on macbook M1 (or newer) chips

In this report, we cover our solution to achieve 96% of accuracy on the test set with fine-tuned
Visual Transformer pretrained by Google and also we tried to achieve the same score with Random Weights initialized CNN Model.
## Stack

| Package | Version |
|---|---|
| python | 3.13.15 |
| tensorflow | 2.20.0 |
| tf-keras | 2.20.1 |
| transformers | 4.57.1 |
| scikit-learn | 1.6.1 |
| kagglehub | 1.0.2 |
| numpy | 2.1.3 |
| pandas | 2.2.3 |
| pillow | 11.3.0 |
| matplotlib | 3.10.0 |

## How to run:

```git clone https://github.com/georgerieh/computer-vision-class.git```

```cd computer-vision-class```

```uv sync```

```Choose computer-vision-class kernel in the top right corner of the submission.ipynb notebook```

```The cleaned version available at emoji_vit_colab_v2_FINAL_REPORT.ipynb```

## Approach

In our case, fine-tuning process was represented by adding Dense layer with 7 neurons to the fixed model weights. 

Preprocessing: transparent background filled with white, resized to 224x224, normalised with the model's mean/std; no augmentation 

Class imbalance: class-weighted cross-entropy (apple: 0.73, google: 0.75, whatsapp: 0.86, facebook: 0.85, samsung: 0.79, mozilla: 3.55, messenger: 2.43)

Validation: stratified 80/20 train/validation split, seed 42

## Notebooks

```submission.ipynb``` is human-made notebook to explore notions of CV and different architectures in order to get the best score.

```emoji_vit_colab_v2_FINAL_REPORT.ipynb``` is a 'cleaned' notebook to satisfy criteria of unviresity project.