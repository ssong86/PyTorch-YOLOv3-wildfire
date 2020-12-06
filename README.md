# PyTorch-YOLOv3-wildfire
Minimal implementation of YOLOv3 in PyTorch.

## Table of Contents
- [PyTorch-YOLOv3](#pytorch-yolov3-wildfire)
  * [Table of Contents](#table-of-contents)
  * [Installation](#installation)
  * [Inference](#inference)
  * [Video](#video)
  * [Test](#test)
  * [Detect](#detect)
  * [Train](#train)
  * [Credit](#credit)


## THIS repo is forked from [packyan](https://github.com/packyan/PyTorch-YOLOv3-kitti)

## Installation
    $ git clone https://github.com/Wayne122/PyTorch-YOLOv3-wildfire.git
    $ cd PyTorch-YOLOv3-wildfire/
    $ sudo pip3 install -r requirements.txt


##### Download pretrained weights
if you wan use pretrained darknet-53 on IMAGENET weights, please download [darknet53.conv.74](https://pjreddie.com/media/files/darknet53.conv.74),and put it into `checkpoints/`

##### Download Kitti 

[The KITTI Vision Benchmark Suite](http://www.cvlibs.net/datasets/kitti/eval_object.php)

and you should transfrom kitti lable to coco label, by using [label_transform](label_transform/README.md)

## Inference
Uses pretrained weights to make predictions on images. `weights/yolov3-kitti.weights` was trained by kitti data set.
`python3 detect.py --image_folder /data/samples`

<p align="center"><img src="assets/12.png" width="480"\></p>
<p align="center"><img src="assets/20.png" width="480"\></p>
<p align="center"><img src="assets/18.png" width="480"\></p>
<p align="center"><img src="assets/3.png" width="480"\></p>

Small objects detection

<p align="center"><img src="assets/4.png" width="480"\></p>

## Detect

run`detect.py` to detect objects, and please  put samples into `data/samples`
defult weights files is `weights/kitti.weights`

## Video

run `video.py` to detect objects from a webcam or a video file.
On I7 7700 8G GTX1070 FPS is 22 cause some problems, test resized images is really faster than resizeing images and then inference.
## Test

run `test.py`

## Train
Data augmentation as well as additional training tricks remains to be implemented. PRs are welcomed!
```
    train.py [-h] [--epochs EPOCHS] [--image_folder IMAGE_FOLDER]
                [--batch_size BATCH_SIZE]
                [--model_config_path MODEL_CONFIG_PATH]
                [--data_config_path DATA_CONFIG_PATH]
                [--weights_path WEIGHTS_PATH] [--class_path CLASS_PATH]
                [--conf_thres CONF_THRES] [--nms_thres NMS_THRES]
                [--n_cpu N_CPU] [--img_size IMG_SIZE]
                [--checkpoint_interval CHECKPOINT_INTERVAL]
                [--checkpoint_dir CHECKPOINT_DIR]
```

## Credit
```
@article{yolov3,
  title={YOLOv3: An Incremental Improvement},
  author={Redmon, Joseph and Farhadi, Ali},
  journal = {arXiv},
  year={2018}
}
```