
## 1. 训练环境准备


```sh
# create conda env
conda create --name faserrcnn python=3.7
conda activate faserrcnn
# install pytorch
conda install pytorch torchvision cudatoolkit=10.2 -c pytorch

# install other dependancy
pip install visdom scikit-image tqdm fire ipdb pprint matplotlib torchnet

# start visdom
start /min python -m visdom.server &

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

3. 调整`utils/config.py`中的 `voc_data_dir`为数据路径



### 2.2 begin training


```bash
python train.py train --env='fasterrcnn' --plot-every=100
```

## 3. 测试模型
运行 `demo.ipynb`                                   
