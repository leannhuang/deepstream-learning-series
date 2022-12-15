## Steps
1. google Ngc nvidia
2. Open the terminal
```
docker run --gpus all -it --rm --net=host --privileged -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY -w /opt/nvidia/deepstream/deepstream-6.1 nvcr.io/nvidia/deepstream:6.1-samples
```
3. 
```
cd samples/configs/deepstream-app
```
4. 
```
apt-get update
```
5. 
```
apt-get install wget
```
6. 
```
apt-get install unzip
```
7. 
```
wget https://leannazdeepstream.blob.core.windows.net/learningseries/MyCustomThings.zip
```

8. 
```
unzip MyCustomThings
```

9. 
```
cd MyCustomThings
```
10. 
```
cp config_infer_custom_vision.txt /opt/nvidia/deepstream/deepstream-6.1/samples/configs/deepstream-app/
```

11. 
```
cd ..
```
12. 
```
apt-get install vim
```
13. 
```
vim source4_1080p_dec_infer-resnet_tracker_sgie_tiled_display_int8.txt
```
14. 
```
Modify the value uri=file://MyCustomThings/IMG_0695.mp4
Set [sink0] enable=0
Set [sink1] enable=1
[primary-gie] config-file=config_infer_custom_vision.txt
```

15. 
```
deepstream-app -c source4_1080p_dec_infer-resnet_tracker_sgie_tiled_display_int8.txt
```