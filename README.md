# Dynamic Spuriosity Bias Harmonizer (PAKDD 2025)
Our code is implemented upon [miro](https://github.com/khanrc/miro).

## Preparation
### Environments
```
Python: 3.6.13
PyTorch: 1.7.1+cu110
Torchvision: 0.8.2+cu110
CUDA: 11.0
CUDNN: 8005
NumPy: 1.19.5
PIL: 8.4.0
```

### Dataset
Download the datasets
```
python -m domainbed.scripts.download --data_dir {your data_path}
```

### Train a model
```
python train_all.py --data_dir {your data_path} --algorithm DSBH \
    --dataset {data} \
    --lr {input} \
    --resnet_dropout {input} \
    --weight_decay {input} \
    --trial_seed 0
```
Our hyperparameters:
|                     | PACS  | VLCS  | OfficeHome | TerraIn | DomainNet |
|-------------------- |------ |------ |-----------|---------|-----------|
| **Learning rate**   | 3e-5  | 8e-6  | 1e-5      | 3e-5    | 2e-5      |
| **Weight decay**    | 9e-6  | 1e-6  | 3e-6      | 5e-6    | 1e-6      |
| **Dropout**         | 0.2   | 0.5   | 0.0       | 0.25    | 0.2       |
| **λ_grad**         | 0.9   | 0.4   | 0.4       | 0.6     | 0.4       |
| **λ_logit**        | 0.1   | 0.4   | 1.0       | 0.4     | 0.3       |

## Main results
Comparison with the existing domain generalization methods. The results are shown in accuracy (%), which are the average with three random seed runs.

