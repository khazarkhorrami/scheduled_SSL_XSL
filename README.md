# scheduled_VGS_plus

This repository contains the instructions and scripts to replicate experiments reported in:

Khorrami, K., Blandón, M. A. C., Virtanen, T., & Räsänen, O. (2023, September). Simultaneous or Sequential Training? How Speech Representations Cooperate in a Multi-Task Self-Supervised Learning System. In 2023 31st European Signal Processing Conference (EUSIPCO) (pp. 431-435). IEEE.

[Read the Paper Here](https://ieeexplore.ieee.org/abstract/document/10290051)

# Model Source

This project's model is based on the work from the following repository, and it is essential to acknowledge and credit the creators for their valuable work:

[https://github.com/jasonppy/FaST-VGS-Family](https://github.com/jasonppy/FaST-VGS-Family)

Specifically, the scripts located in the 'datasets,' 'models,' 'steps,' and the 'run_spokencoco.py' file have been derived from the aforementioned repository.

Two main changes have been applied to the original scripts:

1. The scripts in the "models" and "steps" directories are modified to run only for the fast (FaST) version of the original Fast-Slow Transformer model for the purpose of efficiency.
2. The loss weighting function in the "trainer" is controlled by the factor of "alpha" for the relative weighting between VGS and SSL pipelines.


# Data
We utilize SpokenCOCO spoken captions paired with MSCOCO images for training the models. The data can be downloaded from the following link:
[SpokenCOCO Dataset](https://groups.csail.mit.edu/sls/downloads/placesaudio/index.cgi)

Please refer to the model source repository for JSON files containing the names and pairings of the speech and image files in the Karpathy split. 

In this work, we employ the train set of the COCO data for training the models and the test set of COCO data for evaluating the model on the semantic audiovisual retrieval task. To evaluate the model representations on the phonemic level, we apply the ABX phoneme discrimination task using the LibriSpeech clean test set. LibriSpeech can be downloaded from this link: [LibriSpeech Dataset](https://www.openslr.org/12).

# Model Description

The VGS+ model combines a wav2vec 2.0-based speech self-supervised learning (SSL) and a transformer-based visually grounded speech (VGS) learning mechanisms within one model as described in [the original paper by Peng & Harwath.](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9747103&casa_token=n4fGgF6mHrcAAAAA:jI4E13PB2SNrkvPTXxhhNgXiE2BSTVgXwv9UD_GHCeY54vpjHyZiTXdwf4HNqOT937tOyIXv-Q&tag=1)

## Model training and validation
