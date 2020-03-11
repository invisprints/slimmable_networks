## slimmable neture network

```shell script
python ./train_cifar10.py app:apps_c/s_mobilenet_v1_train.yml
```
1. utils.config create FLAGS

```yaml
num_gpus_per_job: 1
num_cpus_per_job: 12
memory_per_job: 380
gpu_type: nvidia-2080ti
dataset: imagenet1k
data_transforms: imagenet1k_mobile
data_loader: imagenet1k_basic
dataset_dir: /home/lxr/disk/ImageNet/ILSVRC2012
data_loader_workers: 8
num_classes: 1000
image_size: 224
topk: [1, 5]
num_epochs: 150
optimizer: sgd
momentum: 0.9
weight_decay: 0.0001
nesterov: True
lr: 0.045
lr_scheduler: exp_decaying
multistep_lr_milestones: [30, 60, 90]
multistep_lr_gamma: 0.1
profiling: ['gpu']
pretrained: 
resume: 
test_only: False
random_seed: 1995
batch_size: 64
model: models.s_mobilenet_v1
reset_parameters: True
log_dir: logs/
slimmable_training: True
width_mult: 1.0
width_mult_list: [0.25, 0.5, 0.75, 1.0]
exp_decaying_lr_gamma: 0.98

```

2. from models folder import specific model

**Different dataset may have different model configures**