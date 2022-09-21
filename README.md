# Channel Lipschitzness-based Pruning for Backdoor Defense

Source code of ***Data-free Backdoor Removal based on Channel Lipschitzness***, in European Conference on Computer Vision (**ECCV**), 2022.

![](channel-lips.png "illustration of channel lipschitz constant")

## Abstract
Recent studies have shown that Deep Neural Networks (DNNs) are vulnerable to the backdoor attacks, which leads to malicious behaviors of DNNs when specific triggers are attached to the input images. It was further demonstrated that the infected DNNs possess a collection of channels, which are more sensitive to the backdoor triggers compared with normal channels. Pruning these channels was then shown to be effective in mitigating the backdoor behaviors. To locate those channels, it is natural to consider their Lipschitzness, which measures their sensitivity against worst-case perturbations on the inputs. In this work, we introduce a novel concept called Channel Lipschitz Constant (CLC), which is defined as the Lipschitz constant of the mapping from the input images to the output of each channel. Then we provide empirical evidences to show the strong correlation between an Upper bound of the CLC (UCLC) and the trigger-activated change on the channel activation. Since UCLC can be directly calculated from the weight matrices, we can detect the potential backdoor channels in a data-free manner, and do simple pruning on the infected DNN to repair the model. The proposed Channel Lipschitzness based Pruning (CLP) method is super fast, simple, data-free and robust to the choice of the pruning threshold. Extensive experiments are conducted to evaluate the efficiency and effectiveness of CLP, which achieves state-of-the-art results among the mainstream defense methods even without any data.

## Training

Run the following code to train a poisoned model:
```
python train.py --attack-type badnets --poisoning-rate 0.1 --trigger-size 3 --mannual-seed 0
```
Feel free to change the hyperparameters to adapt to your desired settings.

## Testing

Recover the model with CLP:
```
python test.py --attack-type badnets --poisoning-rate 0.1 --trigger-size 3 --mannual-seed 0
```
Note that the hypereparameters should be consistent with the previous trained model.


## Citation

Please cite with the below bibTex if you find it helpful to your research.

```
@article{zheng2022data,
  title={Data-free Backdoor Removal based on Channel Lipschitzness},
  author={Zheng, Runkai and Tang, Rongjun and Li, Jianze and Liu, Li},
  journal={arXiv preprint arXiv:2208.03111},
  year={2022}
}
```
