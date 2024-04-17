# scheduled_VGS_plus

This repository contains the instructions and scripts to replicate experiments reported in:

Khorrami, K., Blandón, M. A. C., Virtanen, T., & Räsänen, O. (2023, September). Simultaneous or Sequential Training? How Speech Representations Cooperate in a Multi-Task Self-Supervised Learning System. In 2023 31st European Signal Processing Conference (EUSIPCO) (pp. 431-435). IEEE.

[https://eurasip.org/Proceedings/Eusipco/Eusipco2023/pdfs/0000431.pdf](https://ieeexplore.ieee.org/abstract/document/10290051)

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

# How to Use

## Model training and validation
