# Light-Up
Low-Light Image Enhancement

**Quick Start**: Enhance Low light Images - https://brightenhance.herokuapp.co  **Low-version**- https://enhanceimage.herokuapp.com/

----------------------------

## Table of Contents
- [About Light-Up](#about-deoldify)
- [Example Images](#example-images)
- [Almost NoGan](#Almost-NoGan)
- [Technical Details](#the-technical-details)
- [Docker](#docker)


## About Light-Up
This project is a part of [Data Science Incubator (Summer 2020)](https://madewithml.com/incubator/) organized by Made With ML.

The aim of the project is to enhance under-exposed Images. Before going into technical details I would like show some pictures.

## Example Images

![Imgur](https://i.imgur.com/Kdd6vjP.jpg)


![Imgur](https://i.imgur.com/fejUcvr.jpg)


![Imgur](https://i.imgur.com/uuGB9Sr.jpg)


![Imgur](https://i.imgur.com/QoUcaBy.jpg)


![Imgur](https://i.imgur.com/FERzcLX.jpg)


![Imgur](https://i.imgur.com/u3DAHXm.jpg)


![Imgur](https://i.imgur.com/UwR0Tfr.jpg)


![Imgur](https://i.imgur.com/oagu5Hb.jpg)


![Imgur](https://i.imgur.com/9c2zha1.jpg)


![Imgur](https://i.imgur.com/7vwIqKk.jpg)


![Imgur](https://i.imgur.com/sj4ULdJ.jpg)


![Imgur](https://i.imgur.com/lxsyBxz.jpg)


## Almost NoGAN

The steps are as follows: 
- Train the generator with feature loss.
- Train the critic  on distinguishing between those outputs and real images.
- Finally, train the generator and critic together in a GAN.

All the useful GAN training here only takes place within a very small window of time(thanks to DeOldify), This helped me do the whole project in Colab. The GAN training took about 25-30 minutes.


## Technical Details

### [Self-Attention Generative Adversarial Network](https://arxiv.org/abs/1805.08318)

**Note**: Perceptual Loss (or Feature Loss) based on VGG16--(Thanks to #Fast.ai)

### [Perceptual Losses for Real-Time Style Transfer and Super-Resolution](https://arxiv.org/pdf/1603.08155.pdf)

### [Progressive Growing of GANs](https://arxiv.org/pdf/1710.10196.pdf)


## Docker

Clone the repo and navigate to the repo:
```
git clone https://github.com/vijishmadhavan/Light-Up.git app 
cd app/Enhance
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



