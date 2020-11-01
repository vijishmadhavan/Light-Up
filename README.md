# Light-Up
Image Enhancement

**Note**: Please search in google for **under-exposed** or **low contrast** images before trying the **web-app**.

**Quick Start**: Enhance Low light Images -https://brightenhance.herokuapp.com/ **Low-end version**- https://enhanceimage.herokuapp.com/ [In case of hicupps, please referesh:)]


**Losses**

https://wandb.ai/vijish/uncategorized/reports/Losses---VmlldzoyNjYwNjc

**Generator output (media)**

https://wandb.ai/vijish/uncategorized/reports/Output--VmlldzoyNjYwNzA

----------------------------

## Table of Contents
- [About Light-Up](#about-deoldify)
- [Example Images](#example-images)
- [Almost NoGan](#Almost-NoGan)
- [Technical Details](#technical-details)
- [Docker](#docker)


## About Light-Up
This project is a part of [Data Science Incubator (Summer 2020)](https://madewithml.com/incubator/) organized by Made With ML.

The aim of the project is to enhance under-exposed Images. Before going into technical details I would like to show some pictures.

## Example Images

![Imgur](https://i.imgur.com/Kdd6vjP.jpg)


![Imgur](https://i.imgur.com/QDTkHCT.jpg)



![Imgur](https://i.imgur.com/fejUcvr.jpg)



![Imgur](https://i.imgur.com/uuGB9Sr.jpg)


![Imgur](https://i.imgur.com/QoUcaBy.jpg)


![Imgur](https://i.imgur.com/y0hj08M.jpg)


![Imgur](https://i.imgur.com/FERzcLX.jpg)


![Imgur](https://i.imgur.com/u3DAHXm.jpg)


![Imgur](https://i.imgur.com/UwR0Tfr.jpg)


![Imgur](https://i.imgur.com/oagu5Hb.jpg)


![Imgur](https://i.imgur.com/9c2zha1.jpg)


![Imgur](https://i.imgur.com/7vwIqKk.jpg)


![Imgur](https://i.imgur.com/sj4ULdJ.jpg)


![Imgur](https://i.imgur.com/lxsyBxz.jpg)

## Extremely Dark

![Imgur](https://i.imgur.com/QziZ07y.jpg)


## Almost NoGAN

The steps are as follows: 
- Train the generator with feature loss.
- Train the critic  on distinguishing between those outputs and real images.
- Finally, train the generator and critic together in a GAN.

All the useful GAN training here only takes place within a very small window of time(thanks to DeOldify), This helped me do the whole project in Colab. The GAN training took about 25-30 minutes.


## Technical Details

### [DeOldify](https://github.com/jantic/DeOldify)

### [Self-Attention Generative Adversarial Network](https://arxiv.org/abs/1805.08318)

-Generator is pretrained U-Net

-This has been modified to have spectral normalization along with self attention.

**Note**: Perceptual Loss (or Feature Loss) based on VGG16--(Thanks to #Fast.ai)

### [Perceptual Losses for Real-Time Style Transfer and Super-Resolution](https://arxiv.org/pdf/1603.08155.pdf)

### [Progressive Growing of GANs](https://arxiv.org/pdf/1710.10196.pdf)

Size of the input is progressively Changed and the learning rates are adjusted to make sure that the transitions between sizes happened successfully.

## Docker

Clone the repo and navigate to the repo:
```
git clone https://github.com/vijishmadhavan/Light-Up.git app 
cd app/enhance
```

Build and run the docker image locally:
```
make run
```

Navigate to http://localhost:8501 for the app. (Streamlit runs on port 8501 by default)

Shutdown the server:
```
make stop 
```
### Installation Details

This project is built around the wonderful Fast.AI library.

- **fastai==1.0.61** (and its dependencies).  Please dont install the higher versions
- **PyTorch 1.6.0** Please don't install the higher versions

## Credits

Project - https://github.com/jantic/DeOldify

Copyright (c) 2018 Jason Antic

License (MIT)-https://github.com/jantic/DeOldify/blob/master/LICENSE
