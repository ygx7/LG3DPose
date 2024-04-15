# Local-Global Feature Fusion for Enhancing 3D Human Pose Estimation

This work is based on the [MotionAGFormer](https://github.com/TaatiTeam/MotionAGFormer/tree/master) and [P-STMO](https://github.com/paTRICK-swk/P-STMO), and you can get more help there.

## Environment

The code is conducted under the following environment:

* Ubuntu 20.04
* Python 3.9.16
* PyTorch 1.13.1
* CUDA 11.7

## Dataset

The dataset setting follow the [MotionAGFormer](https://github.com/TaatiTeam/MotionAGFormer/tree/master).
Please refer to it to set up datasets (under ./data directory).

# Evaluation

* Download our pretrained model from [Google Drive](https://drive.google.com/drive/folders/1Atbnv39J3_EhFrRv7pA4EHNs1QQf9hu6?usp=drive_link);

Then run the command below (evaluate on 243 frames input):

* Human3.6M
```bash
python train.py --eval-only --checkpoint checkpoint --checkpoint-file 37.7h36m.pth.tr --config configs/h36m/LG3DPose.yaml
```

* MPI-INF-3DHP
```bash
python train.py --eval-only --checkpoint checkpoint --checkpoint-file 16.4mpi.pth.tr --config configs/mpi/LG3DPose.yaml
```

# Training from scratch

Training our model with GPU:

* Human3.6M
```bash
python train.py --config configs/h36m/LG3DPose.yaml --use-wandb --wandb-name LG3DPose
```

* MPI-INF-3DHP
```bash
python train.py --config configs/mpi/LG3DPose.yaml --use-wandb --wandb-name LG3DPose-MPI
```

## Acknowledgement

Thanks for the baselines, we construct the code based on them:

* MotionAGFormer
* P-STMO

