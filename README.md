# Structure-preserved Superpixel Perception for Referring Image Segmentation

## Requirements
The code is verified with Python 3.8 and PyTorch 1.11. Other dependencies are listed in `requirements.txt`.

## Datasets
Please follow the instruction in [.refer](./refer/README.md) to download annotations of RefCOCO/RefCOCO+/RefCOCOg. We provide the combined annotations as refcocom [here](https://drive.google.com/file/d/1_WnCziCIVHXpWYDsIsHbxzH_KCiYhflo/view?usp=sharing).

Download images from [COCO](https://cocodataset.org/#download). Please use the first downloading link *2014 Train images [83K/13GB]*, and extract the downloaded `train_2014.zip` file. 

Data paths should be as follows:
```
.{YOUR_REFER_PATH}
├── refcoco
├── refcoco+
├── refcocog
├── refcocom

.{YOUR_COCO_PATH}
├── train2014
```

## Usage
### Train
```
sh scripts/train_refcoco.sh
```
You can change `DATASET` to `refcoco+`/`refcocog`/`refcocom` for training on different datasets. 
Note that for RefCOCOg, there are two splits (umd and google). You should add `--splitBy umd` or `--splitBy google` to specify the split.

### Test
```
sh scripts/test_refcoco.sh
```
You can change `DATASET` and `SPLIT` to evaludate on different splits of each dataset. 
Note that for RefCOCOg, there are two splits (umd and google). You should add `--splitBy umd` or `--splitBy google` to specify the split. 
For the models trained on `refcocom`, you can directly evaluate them on the splits of `refcoco`/`refcoco+`/`refcocog(umd)`.

## References
This repo is mainly built based on [LAVT](https://github.com/yz93/LAVT-RIS), [mmdetection](https://github.com/open-mmlab/mmdetection) and [CARIS](https://github.com/lsa1997/CARIS). Thanks for their great works!

