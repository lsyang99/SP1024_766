# Solar Panel Detection on TWCC.

Setup an environment for inference in termial:

1. Install TensorFlow Object Detection API
```
cd ~/models/research
./bin/protoc object_detection/protos/*.proto --python_out=.
cp object_detection/packages/tf2/setup.py . 
python -m pip install .
```

2. Instal essential packages
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
