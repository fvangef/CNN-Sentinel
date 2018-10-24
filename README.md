# Satellite data is for everyone: insights into modern remote sensing research with open data and Python

## Scripts you will find here
* 01\_split\_data\_to\_train\_and\_validation.py: split complete dataset into train and validation
* 02\_train\_rgb\_finetuning.py: train VGG16 or DenseNet201 using RGB data with pretrained weights on ImageNet
* 03\_train\_rgb\_from\_scratch.py: train VGG16 or DenseNet201 from scratch using RGB data 
* 04\_train\_ms\_finetuning.py: train VGG16 or DenseNet201 using multisprectral data with pretrained weights on ImageNet
* 04\_train\_ms\_finetuning\_alternative.py: an alternative way to train VGG16 or DenseNet201 using multisprectral data with pretrained weights on ImageNet
* 05\_train\_ms\_from\_scratch.py: train VGG16 or DenseNet201 from scratch using multisprectral data
* 06\_classify\_image.py: a simple implementation to classify images with trained models
* image\_functions.py: functions for image normalization and a simple generator for training data augmentation
* statistics.py: a simple implementation to calculate mormalization parameters (i.e. mean and std of training data)

Addtionally you will find the following notebooks:

* Image\_functions.ipynb: notebook of image\_functions.py
* Train\_from\_Scratch.ipynb: notebook of 05\_train\_ms\_from\_scratch.py
* Transfer\_learning.ipynb: notebook of 02\_train\_rgb\_finetuning.py

## Setup Environment

Append conda-forge to your Anaconda channels:
```bash
conda config --append channels conda-forge
```

Create new environment:
```bash
conda create -n pycon scikit-image gdal tqdm
conda activate pycon 
pip install tensorflow-gpu
pip install keras
```
(or use tensorflow version of keras, i.e. `from tensorflow import keras`)

See also:
* Keras: https://keras.io/

## Links
* DeepHyperX - Deep learning for Hyperspectral imagery: https://gitlab.inria.fr/naudeber/DeepHyperX/


## How to get Sentinel-2 data
1. Register at Copernicus [Open Access Hub](https://scihub.copernicus.eu/dhus/#/home) or [EarthExplorer[(https://earthexplorer.usgs.gov/)]
2. Find your region
3. Choose tile(s) (→ area) and date
    * Less tiles makes things easier
    * Less clouds in the image are better
    * Consider multiple dates for classes like “annual crop”
4. Download L1C data
5. Decide of you want to apply L2A atmospheric corrections
    * Your CNN might be able to do this by itself
    * If you want to correct, use [Sen2Cor](http://step.esa.int/main/third-party-plugins-2/sen2cor/)
6. Have fun with the data


## Datasets

**This talk:**
* EuroSAT Data ([Link](http://madm.dfki.de/downloads))


**Platforms for datasets:**

- HyperLabelMe: a Web Platform for Benchmarking Remote Sensing Image Classifiers ([Link](http://hyperlabelme.uv.es/))
- GRSS Data and Algorithm Standard Evaluation (DASE) website ([Link](http://dase.ticinumaerospace.com/))


**Datasets:**

- UC Merced Land Use Dataset ([Link](http://weegee.vision.ucmerced.edu/datasets/landuse.html))
- AID: A Benchmark Dataset for Performance Evaluation of Aerial Scene Classification ([Link](https://captain-whu.github.io/AID/))
- NWPU-RESISC45 (RGB, [Link](http://www.escience.cn/people/JunweiHan/NWPU-RESISC45.html))
- Zurich Summer Dataset (RGB, [Link](https://sites.google.com/site/michelevolpiresearch/data/zurich-dataset))

## Requirements (what we used):
- python 3.6.6
- tensorflow-gpu (1.11) with Cuda Toolkit 9.0
- keras (2.2.4)
- scikit-image (0.14.1)
- gdal (2.2.4) for `06_classify_image.py`


