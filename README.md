# Object Detection on Thermal Images

Enhancing Object Detection using Thermal Imaging for thin cross-section unidentifiable objects(eg. cyclist, pedestrians).

## Steps to build the package

```bash
$ cd object-detection-thermal 
$ make
```
Set `GPU` vars to `1` if using GPU.

## NOTE: To use pre-trained weights place them in object-detection-thermal/backup/

## Run Prediction
```bash
$ cd object-detection-thermal
```
### To predict on images(thermal)
```bash
$ ./darknet detector test cfg/thermal.data cfg/yolov3-spp-custom.cfg backup/yolov3-spp-thermal.weights <img_path> -dont_show -out result.json 
# Predicted output is saved as prediction.jpg
```

Instead of supplying an <img_path> on the command line, you can leave it blank to try multiple images in a row. Instead you will see a prompt when the config and weights are done loading:
```bash
$ ./darknet detector test cfg/thermal.data object-detection-thermal/cfg/yolov3-spp-custom.cfg backup/yolov3-spp-thermal.weights -dont_show
layer     filters    size              input                output
    0 conv     32  3 x 3 / 1   416 x 416 x   3   ->   416 x 416 x  32  0.299 BFLOPs
    1 conv     64  3 x 3 / 2   416 x 416 x  32   ->   208 x 208 x  64  1.595 BFLOPs
    .......
  104 conv    256  3 x 3 / 1    52 x  52 x 128   ->    52 x  52 x 256  1.595 BFLOPs
  105 conv    255  1 x 1 / 1    52 x  52 x 256   ->    52 x  52 x 255  0.353 BFLOPs
  106 detection
Loading weights from yolov3-spp-thermal.weights...Done!
Enter Image Path:
```
