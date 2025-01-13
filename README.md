## Getting started

### Preparation

Before executing the project code, please prepare the Python environment according to the `requirement.txt` file. We set up the environment with `python 3.8` and `torch 1.8.1`. 


### How to run

We conduct experiments on three datasets: MNIST,CIFAR10 and CIFAR100. We adopt LeNet  for conducting experiments on MNIST and adopt AlexNet on CIFAR10 and ResNet18 on CIFAR100. The last layer of the model is treated as the auxiliary unlearning module.

There three unlearning modes supported by FedAU:

**1. Unlearn Samples**

```python
python main_zgx.py --num_users 10 --dataset cifar10 --model_name alexnet --epochs 200 --batch_size 128 \
 --proportion 0.01 --num_ul_users 1 --ul_mode 'ul_samples_backdoor' --local_ep 2 --log_folder_name ul_samples/
```

**2. Unlearn Class**

```python
python main_zgx.py --num_users 10 --dataset cifar10 --model_name alexnet --epochs 200 --batch_size 128 \
 --num_ul_users 1 --ul_mode 'ul_class' --local_ep 2 --log_folder_name ul_class/
```

**3. Unlean Client**

```python
python main_zgx.py --num_users 10 --dataset cifar10 --model_name alexnet --epochs 200 --batch_size 128 \
 --num_ul_users 1 --ul_mode 'ul_class' --local_ep 2 --log_folder_name ul_client/
```

