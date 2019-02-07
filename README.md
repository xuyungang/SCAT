# SCAT
A novel tool package for single-cell RNA sequencing analysis with graph theory and deep networks. It consit of two-step analysis:

## 1. ReadsImpute: Accurate quantification of transcript for scRNA-seq with read imputation. 
Refer to https://github.com/xuyungang/readsImpute for source code and manual.

## 2. scIGANs:recover drop-out events in scRNA-seq using Generative Adversarial Networks (GANs) 

### (1) train scIGANs:

python scIGANs.py [options] --train

### (2) impute expression matrix

python scIGNAs.py [options] --impute

### Options
- `--n_epochs` type=int, default=200, help='number of epochs of training'
- `--batch_size` type=int, default=64, help='size of the batches'
- `--kt` type=float, default=0, help='kt parameters'
- `--gamma`  type=float, default=0.95, help='gamma parameters'
- `--lr` type=float, default=0.0002, help='adam: learning rate'
- `--b1` type=float, default=0.5, help='adam: decay of first order momentum of gradient'
- `--b2` type=float, default=0.999, help='adam: decay of first order momentum of gradient'
- `--n_cpu`  type=int, default=20, help='number of cpu threads to use during batch generation'
- `--latent_dim` type=int, default=100, help='dimensionality of the latent space'
- `--img_size` type=int, default=124, help='size of each image dimension'
- `--channels`  type=int, default=1, help='number of image channels'
- `--n_critic`  type=int, default= 1, help='number of training steps for discriminator per iter'
- `--sample_interval` type=int, default=400, help='interval between image sampling'
- `--dpt` type=str, default='', help='load discrimnator model'
- `--gpt` type=str, default='', help='load generator model'
- `--train` help='train the network', action='store_true'
- `--impute`   help='do imputation', action='store_true'
- `--sim_size`  type=int, default=200, help='number of sim_imgs in each type'
- `--file_d`  type=str, default='d_yg124.csv', help='path of data file'
- `--file_c`  type=str, default='d_yg124_c5.csv', help='path of cls file'
- `--ncls`  type=int, default=5, help='number of clusters'
- `--knn_k` type=int, default=10, help='neighours used'
- `--lr_rate` type=int, default=10, help='rate for slow learning'
