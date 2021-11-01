## 飞桨论文复现: DGCNN Paddle Version

Original paper: [Dynamic Graph CNN for Learning on Point Clouds](https://arxiv.org/abs/1801.07829)
Dataset: ShapeNet
验收标准: ShapeNet 85.2%
Original Pytorch Implementation: [DGCNN-Pytorch](https://github.com/WangYueFt/dgcnn/tree/master/pytorch)

## Introduction

Our code is tested on PaddlePaddle 2.2.0, so you need to install paddlepaddle first.

We provide our trained model and put it in the folder 'pretrained'.

The 'pipeline' folder includes the comparison of relevant results between pytorch and paddle according to [论文复现指南](https://github.com/littletomatodonkey/models/blob/dev%2Fadd_reprod_doc_v1.0/docs/ThesisReproduction_CV.md)

## Getting Started

* Run the training script:

```1024 points
python main.py --exp_name=dgcnn_1024 --model=dgcnn --num_points=1024 --k=20 --use_sgd=True
```

```2048 points
python main.py --exp_name=dgcnn_2048 --model=dgcnn --num_points=2048 --k=40 --use_sgd=True
```

* Run the evaluation script after training finished:

```1024 points
python main.py --exp_name=dgcnn_1024_eval --model=dgcnn --num_points=1024 --k=20 --use_sgd=True --eval=True --model_path=checkpoints/dgcnn_1024/models/model.pdparams
```

```2048 points
python main.py --exp_name=dgcnn_2048_eval --model=dgcnn --num_points=2048 --k=40 --use_sgd=True --eval=True --model_path=checkpoints/dgcnn_2048/models/model.pdparams
```

* Run the evaluation script with pretrained models:

```1024 points
python main.py --exp_name=dgcnn_1024_eval --model=dgcnn --num_points=1024 --k=20 --use_sgd=True --eval=True --model_path=pretrained/model.pdparams
```
