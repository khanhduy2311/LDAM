## Learning Imbalanced Datasets with Label-Distribution-Aware Margin Loss 
_________________

This is the official implementation of LDAM-DRW in the paper [Learning Imbalanced Datasets with Label-Distribution-Aware Margin Loss](https://arxiv.org/pdf/1906.07413.pdf) in PyTorch.

### Dependency

The code is built with following libraries:

- [PyTorch](https://pytorch.org/) 1.2
- [TensorboardX](https://github.com/lanpa/tensorboardX)
- [scikit-learn](https://scikit-learn.org/stable/)

### Dataset

- Imbalanced [CIFAR](https://www.cs.toronto.edu/~kriz/cifar.html). The original data will be downloaded and converted by `imbalancec_cifar.py`.
- The paper also reports results on Tiny ImageNet and iNaturalist 2018. We will update the code for those datasets later.

### Training 

We provide several training examples with this repo:

- To train the ERM baseline on long-tailed imbalance with ratio of 100

```bash
python cifar_train.py --gpu 0 --imb_type exp --imb_factor 0.01 --loss_type CE --train_rule None
```

- To train the LDAM Loss along with DRW training on long-tailed imbalance with ratio of 100

```bash
python cifar_train.py --gpu 0 --imb_type exp --imb_factor 0.01 --loss_type LDAM --train_rule DRW
```


