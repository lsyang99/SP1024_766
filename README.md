## Solar Panel Detection on TWCC.


#### Setup an environment for deep learning in terminal:

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


#### Download a TensorFlow model and manually modify the pipline prior to re-training the model.
In this example, we applied [faster_rcnn_inception_resnet_v2_1024x1024](https://tfhub.dev/tensorflow/faster_rcnn/inception_resnet_v2_640x640/1) from TensorFlow Hub for deep learning.



#### Setup an environment for inference in termial:

- Install TensorFlow Object Detection API
```
cd ~/models/research
./bin/protoc object_detection/protos/*.proto --python_out=.
cp object_detection/packages/tf2/setup.py . 
python -m pip install .
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
