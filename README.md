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
- `--train` **required**, run the tool to train the network
- `--impute`  **required**, run the tool to do imputation
  - `--file_d`  required, type=string, the expression matrix file with path, default='sample/d_yg124.csv'
- `--file_c`  required, type=string, the cluster label file with path, default='d_yg124_c5.csv'
- `--n_epochs` optional, type=int, number of epochs of training, default=200
- `--batch_size` optional, type=int, default=64, help='size of the batches'
- `--kt` optional, type=float, default=0, help='kt parameters'
- `--gamma` optional, type=float, default=0.95, help='gamma parameters'
- `--lr` optional, type=float, default=0.0002, help='adam: learning rate'
- `--b1` optional, type=float, default=0.5, help='adam: decay of first order momentum of gradient'
- `--b2` optional, type=float, default=0.999, help='adam: decay of first order momentum of gradient'
- `--n_cpu` optional, type=int, default=20, help='number of cpu threads to use during batch generation'
- `--latent_dim` optional, type=int, default=100, help='dimensionality of the latent space'
- `--img_size` optional, type=int, default=124, help='size of each image dimension'
- `--channels`  optional, type=int, default=1, help='number of image channels'
- `--n_critic`  optional, type=int, default= 1, help='number of training steps for discriminator per iter'
- `--sample_interval` optional, type=int, default=400, help='interval between image sampling'
- `--dpt` optional, type=str, default='', help='load discrimnator model'
- `--gpt` optional, type=str, default='', help='load generator model'
- `--sim_size`  optional, type=int, default=200, help='number of sim_imgs in each type'
- `--ncls`  optional, type=int, default=5, help='number of clusters'
- `--knn_k` optional, type=int, default=10, help='neighours used'
- `--lr_rate` optional, type=int, default=10, help='rate for slow learning'
