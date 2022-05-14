
## 1. 训练环境准备


```sh
# create conda env
conda create --name yolov3 python=3.7.11
conda activate yolov3
# install dependencies
pip install -r requirements.txt


```
## 2. 训练模型

### 2.1 准备数据

####  VOC2007

1. 

   ```Bash
   wget http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCtrainval_06-Nov-2007.tar
   wget http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCtest_06-Nov-2007.tar
   wget http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCdevkit_08-Jun-2007.tar
   ```

2. 

   ```Bash
   tar xvf VOCtrainval_06-Nov-2007.tar
   tar xvf VOCtest_06-Nov-2007.tar
   tar xvf VOCdevkit_08-Jun-2007.tar
   ```




### 2.2 begin training


```bash
python train.py --img 640 --batch 2 --epochs 4 --data voc.yaml --weights yolov3.pt
```

## 3. 测试模型
                                
    ```Bash
    import torch

    # Model
    model = torch.hub.load('yolov3', 'yolov3')  

    # Images
    img = 'https://ultralytics.com/images/zidane.jpg'  

    # Inference
    results = model(img)

    # Results
    results.show()                                
