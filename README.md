## Solar Panel Detection on TWCC.
This repository demonstrates an example of solar panel detection on [TWCC](https://www.twcc.ai)(Taiwan Computing Cloud). The size of dataset is 766 with a resolution of 1024x1024 pixels. Dataset is split into train and test sets with ratios 0.8 and 0.2. Please note that the raw dataset, with a GeoTIFF and a XML file for each image, is extracted from objects labeling in ArcGIS Pro. Prior to performing deep learning, the raw dataset should be transformed as described in [this repository](https://github.com/lsyang99/Solar-Panel-Detection-Samples).

#### 1. Setup an environment for deep learning in terminal:

- Install TensorFlow Object Detection API
```
cd ~/models/research
./bin/protoc object_detection/protos/*.proto --python_out=.
cp object_detection/packages/tf2/setup.py . 
python -m pip install .
```

- Install "protobuf"
```
cd ~/models/research
wget https://github.com/protocolbuffers/protobuf/releases/download/v3.17.3/protoc-3.17.3-linux-x86_64.zip
unzip protoc-3.17.3-linux-x86_64.zip
```




#### 2. Download a TensorFlow model and manually modify the pipline prior to re-training the model.
In this example, we applied [faster_rcnn_inception_resnet_v2_1024x1024](https://tfhub.dev/tensorflow/faster_rcnn/inception_resnet_v2_640x640/1) from TensorFlow Hub for deep learning.




#### 3. Setup an environment for inference in termial:

- Install TensorFlow Object Detection API
```
cd ~/models/research
./bin/protoc object_detection/protos/*.proto --python_out=.
cp object_detection/packages/tf2/setup.py . 
pip install . --use-deprecated=legacy-resolver
```

- Install essential packages
```
# For "GDAL"
sudo apt update
sudo apt upgrade
sudo apt install gdal-bin libgdal-dev
pip install --global-option=build_ext --global-option="-I/usr/include/gdal" GDAL==`gdal-config --version`

# For "cv2"
pip install opencv-python

# For others
pip install pandas geopandas shapely google.colab tensorflow_hub
```



- Resolve other error messages in terminal: `ImportError: libGL.so.1: cannot open shared object file: No such file or directory`

```
sudo apt update
sudo apt install libgl1-mesa-glx
```


