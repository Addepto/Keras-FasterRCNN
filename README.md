Keras Faster-RCNN
==================================

Faster-RCNN implemented in Keras based on article "Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks":

- simple_parser.py provides a way to input data, using a text file. Simply provide a text file, with each
line containing:

    `filepath,x1,y1,x2,y2,class_name`

    For example:

    /data/imgs/img_001.jpg,837,346,981,456,cow
    
    /data/imgs/img_002.jpg,215,312,279,391,cat

    The classes will be inferred from the file. To use the simple parser
    use the command line option `-o simple`. For example to train a model: 
	
```
python train_frcnn.py -o simple -p my_data.txt
```

- Running `train_frcnn.py` will write weights to disk to an hdf5 file, as well as all the setting of the training run to a `pickle` file. These settings can then be loaded by `test_frcnn.py` for any testing.

- `test_frcnn.py` can be used to perform inference, given pretrained weights and a config file. Specify a path to the folder containing
images:
```
python test_frcnn.py -p /path/to/test_data/
```
- Data augmentation can be applied by specifying `--hf` for horizontal flips, `--vf` for vertical flips and `--rot` for 90 degree rotations
- Both tensorflow and theano backends are available

