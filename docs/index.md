---
title: Home
layout: home
nav_order: 1
---

# Image Classifier

<p>An image classification model from data collection, cleaning, model training, deployment and API integration.</p>

<p>
    <a href="https://huggingface.co/spaces/abir0/charts-classifier" target="_blank" class="btn btn-primary fs-5 mb-4 mb-md-0 mr-2">Use it on Hugging Face</a>
    <a href="https://github.com/abir0/Charts-Classifier" target="_blank" class="btn fs-5 mb-4 mb-md-0">View it on GitHub</a>
</p>

<hr>

{: .warning }
> This website documents the features of the current `main`</code>` branch of the Charts Classifier repo. This is still in the development phase.

## Model Overview

The model can classify 28 different types of charts and diagrams in raster image formats (png, jpg, gif, etc.). <br/>

The types are following: <br/>

1. arc diagram
2. area chart
3. bar chart
4. block diagram
5. boxplot
6. bubble chart
7. cartogram
8. control chart
9. dendrogram
10. flowchart
11. funnel chart
12. gantt chart
13. heatmap
14. histogram
15. line graph
16. matrix diagram
17. mind map
18. network graph
19. neural network diagram
20. organogram
21. phase diagram
22. pie chart
23. radar chart
24. scatter plot
25. snakey chart
26. surface plot
27. timeline chart
28. venn diagram


## Dataset Preparation

**Data Collection:** The image dataset was downloaded from DuckDuckGo search engine API using keywords (28 class names). <br/>

**DataLoaders:** fastai DataBlock API was used to set up the DataLoaders. <br/>

**Data Augmentation:** fastai provides default data augmentation which operates in GPU. <br/>

{: .note }
> Details can be found in `notebooks/data_collection_and_augmentation.ipynb` of the GitHub repo.


## Training and Data Cleaning

**Training:** Training was done on a pre-trained model (`resnet34`) and it was fine-tuned for 6 epochs with accuracy upto ~85% . <br/>

**Data Cleaning:** Since the data was collected from DuckDuckGo search engine API, there were many noises and inconsistencies within the dataset. Hence, the data was cleaned and updated using the fastai ImageClassifierCleaner. The data was cleaned each time after training or fine-tuning until the final iteration of the model. <br/>

{: .note }
> Details can be found in `notebooks/model_training_and_cleaning.ipynb` of the GitHub repo.


## Model Inference

The model was exported as a `.pkl` file and was used for inference.

{: .note }
> Details can be found in `notebooks/model_inference.ipynb` of the GitHub repo.


## Model Deployment

The model was deployed to Hugging Face Spaces as a gradio app. The implementation can be found [here](https://huggingface.co/spaces/abir0/charts-classifier). <br/>


## API integration with GitHub Pages

The deployed model API is integrated [here](https://abir0.github.io/Charts-Classifier/) in GitHub Pages Website. Implementation and other details can be found in `docs` folder.


<hr>

<p><button class="btn js-toggle-dark-mode">Preview dark color scheme</button></p>
