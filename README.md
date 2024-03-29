# Text-Guided Variational Image Generation for Industrial Anomaly Detection and Segmentation (CVPR2024) <a href="https://arxiv.org/abs/2403.06247v2.pdf"><img src="https://img.shields.io/badge/arXiv-2403.06247-b31b1b.svg" alt="Paper Badge"/></a>


<p align="center">
<img src=".png" width="1000" alt="" class="img-responsive">
</p>

## Abstract ✨

We propose a text-guided variational image generation method to address the challenge of getting clean data for anomaly detection in industrial manufacturing. Our method utilizes text information about the target object, learned from extensive text library documents, to generate non-defective data images resembling the input image. The proposed framework ensures that the generated non-defective images align with anticipated distributions derived from textual and image-based knowledge, ensuring stability and generality. Experimental results demonstrate the effectiveness of our approach, surpassing previous methods even with limited non-defective data. Our approach is validated through generalization tests across four baseline models and three distinct datasets. We present an additional analysis to enhance the effectiveness of anomaly detection models by utilizing the generated images.



## News 📢
- 2024/XX: Code releasing soon.
- 2024/02: 🏆 Accepted paper at [CVPR'24](https://cvpr.thecvf.com/) conference 🎉🎉



## Requirements
- Python >= 3.8
- PyTorch >= 1.12


A suitable [conda](https://conda.io/) environment named `anomalib_new` can be created
and activated with:

```
conda env create -f environment.yaml
conda activate anomalib_new
```


## Datasets 📖

### [[MVTec AD Dataset](https://www.mvtec.com/company/research/datasets/mvtec-ad)]

MVTec AD dataset is one of the main benchmarks for anomaly detection, and is released under the
Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License [(CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/).

### [[MVTec AD LOCO Dataset](https://www.mvtec.com/company/research/datasets/mvtec-loco)]

MVTec AD LOCO dataset is one of the main benchmarks for anomaly detection, and is released under the
Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License [(CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/).

### [[BTAD Dataset](https://avires.dimi.uniud.it/papers/btad/btad.zip)]

BTAD dataset is one of the main benchmarks for anomaly detection, and is released under the
Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License [(CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/).



## Training 📝



## Results 🎯

<img src=".jpg" width="800"/>

### One-shot

| Model           |                |    Avg    |  Carpet   |   Grid    |  Leather  |   Tile    |   Wood    |  Bottle   |   Cable   |  Capsule  | Hazelnut | Metal Nut |   Pill    |   Screw   | Toothbrush | Transistor |  Zipper   |
| --------------- | -------------- | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :------: | :-------: | :-------: | :-------: | :--------: | :--------: | :-------: |
| PatchCore       | ResNet-18      |   0.839   |   0.936   |   0.649   | 1.000     |   0.993   |   0.989   |   1.000   |   0.899   |   0.636   |  0.917   |   0.888   |   0.720   |   0.538   |   0.787    |   0.718    |   0.915   |
| CFlow           | ResNet-18      |   0.842   |   0.968   |   0.538   | 0.946     |   0.965   |   0.990   |   0.991   |   0.777   |   0.736   |  0.964   |   0.796   |   0.610   |   0.796   |   0.711    |   0.737    |   0.921   |
| EfficientAd     | ResNet-18      |   0.713   |   0.995   |   0.743   | 0.548     |   0.974   |   0.814   |   0.951   |   0.619   |   0.517   |  0.759   |   0.621   |   0.732   |   0.743   |   0.634    |   0.585    |   0.528   |
| Reverse-distillation | Wide ResNet-50-2 |   0.831   |   0.994   |   0.797   |   1.000   |   0.994   |   0.996   |   0.980   |   0.650   |   0.674   |  0.999   |  0.627  |   0.812   |   0.540   |   0.920   |   0.704    |   0.780   |

### Few-shot

| Model           |                |    Avg    |  Carpet   |   Grid    |  Leather  |   Tile    |   Wood    |  Bottle   |   Cable   |  Capsule  | Hazelnut | Metal Nut |   Pill    |   Screw   | Toothbrush | Transistor |  Zipper   |
| --------------- | -------------- | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :------: | :-------: | :-------: | :-------: | :--------: | :--------: | :-------: |
| PatchCore       | ResNet-18      |   0.914   |   0.964   |   0.723   |   1.000   |   0.998   |   0.995   |   1.000   |   0.956   |   0.930   |  0.993   |   0.991   |   0.889   |   0.666   |   0.695    |   0.989    |   0.924   |
| CFlow           | ResNet-18      |   0.902   |   0.958   |   0.777   |   0.991   |   0.983   |   0.979   |   0.999  |    0.925   |   0.776   |  0.995   |   0.921   |   0.880   |   0.617   |   0.939    |   0.865    |   0.925   |
| EfficientAd     | ResNet-18      |   0.842   |   0.994   |   0.851   |   0.999   |   0.980   |   0.998   |   0.986   |   0.846   |   0.747   |  1.000   |   0.799   |   0.798   |   0.636   |   0.942    |   0.840    |   0.737   |
| Reverse-distillation | Wide ResNet-50-2 |   0.781   |   0.978   |   0.979   |   0.663   |   0.962   |   0.907   |   0.980   |   0.759   |   0.552   |  0.873   |  0.679  |   0.751   |   0.754   |   0.692   |   0.608    |   0.576   |

### Full-shot

| Model           |                |    Avg    |  Carpet   |   Grid    |  Leather  |   Tile    |   Wood    |  Bottle   |   Cable   |  Capsule  | Hazelnut | Metal Nut |   Pill    |   Screw   | Toothbrush | Transistor |  Zipper   |
| --------------- | -------------- | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :------: | :-------: | :-------: | :-------: | :--------: | :--------: | :-------: |
| PatchCore       | ResNet-18      |   0.978   |   0.967   |   0.943   |   1.000   |   0.999   |   0.997   |   1.000   |   0.988   |   0.972   |  1.000   |   1.000   |   0.925   |   0.961   |   0.957    |   1.000    |   0.957   |
| CFlow           | ResNet-18      |   0.937   |   0.952   |   0.841   |   0.986   |   0.982   |   0.988   |   1.000   |   0.957   |   0.916   |  0.999   |   0.992   |   0.912   |   0.749   |   0.916    |   0.912    |   0.950   |
| EfficientAd     | ResNet-18      |   0.933   |   0.995   |   0.995   |   1.000   |   0.996   |   0.997   |   0.987   |   0.939   |   0.944   |  1.000   |   0.751   |   0.954   |   0.957   |   0.966    |   0.971    |   0.921   |
| Reverse-distillation | Wide ResNet-50-2 |   0.955   |   0.983   |   0.994   |   0.973   |   0.999   |   0.956   |   1.000   |   0.947   |   0.807   |  0.946   |   0.970   |   0.975   |   0.951   |   0.893   |   0.825    |   0.944   |



## Citation 🔍
```

```

