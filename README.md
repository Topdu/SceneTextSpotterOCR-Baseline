# 粤港澳街景图像中店面招牌文字识别比赛

店面招牌是街景图像中的重要信息，自然场景下的文字识别也是计算机视觉的重要研究方向，两者结合的街景店面招牌文字识别技术正在大规模应用在地图导航及推荐、智能城市规划分析、商业区商业价值分析等实际落地领域，具有很高的研究价值和业务使用价值。  

比赛网址: https://www.cvmart.net/race/10351/des 

本项目基于国产框架计图 Jittor，实现了粤港澳街景图像中店面招牌文字识别比赛的 Baseline，整体采用了 **‘JDet-PixelLink-CRNN’** 的模型组合。

### *总体思路：*
>    Step 1. 使用 **JDet** 检测出街景图像中的店面招牌；  
>
>    Step 2. 使用 **PixelLink** 从招牌图像中检测出文本框位置，并选择最大的文本框作为候选；  
> 
>    Step 3. 使用 **CRNN** 从文本框图像中识别出文字。


### *示例：*

![image](https://user-images.githubusercontent.com/73881739/182287493-a53ecba5-6b74-487e-bba8-2712d2771f9a.png)


## 训练与评测

### 模型训练
请移步到各模型目录下阅读 ```README.md```。

### 评测
第一步，根据街景图像，进行预测。请执行：
```bash
python prediction.py --image_dir [街景图片目录] --save_dir [保存预测文件目录]
```

或许，您需要重新指定模型参数路径，则可按以下方式执行：
```bash
python prediction.py -i [街景图片目录] -s [保存预测文件目录] -j [JDet模型参数路径] -p [PixelLink模型参数路径] -c [CRNN模型参数路径]
```

第二步，根据预测结果，进行评测。请执行：
```bash
python evaluation.py --pred_dir [预测文件目录] --gt_dir [真实值文件目录]
```

## 模型参数

已训练好的模型参数可通过以下地址进行下载：


**JDet 模型参数**:  
https://cloud.tsinghua.edu.cn/f/0b1ed1cc311245ed901c/?dl=1


**PixelLink 模型参数**:  
https://cloud.tsinghua.edu.cn/f/4e7e633085e241729e14/?dl=1


**CRNN 模型参数**:  
https://cloud.tsinghua.edu.cn/f/2fc669b2dd6e475b9511/?dl=1


**CRNN 预训练模型参数**:   
https://cloud.tsinghua.edu.cn/f/80825967dd344a91a2da/?dl=1