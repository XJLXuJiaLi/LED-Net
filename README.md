# LED-Net
## Preparation
- Ubuntu 18.04
- Python 3.6 
- Anaconda3
- Pytorch 0.3.1
- CMake   2.8
- CUDA 10.1 + cuDNN 7.6
### Build
- cd LED-Net
- mkdir build && cd build
- cmake .. && make
### Dataset
__Shape Classification__

Download and unzip [ModelNet40](https://shapenet.cs.stanford.edu/media/modelnet40_ply_hdf5_2048.zip) (415M). Replace `$data_root$` in `cfgs/config_cls.yaml` with the dataset parent path.

__ShapeNet Part Segmentation__

Download and unzip [ShapeNet Part](https://shapenet.cs.stanford.edu/media/shapenetcore_partanno_segmentation_benchmark_v0_normal.zip) (674M). Replace `$data_root$` in `cfgs/config_seg.yaml` with the dataset path.

## Training
### Shape Classification
```bash
$ python train_cls.py
```

### Shape Part Segmentation
```bash
$ python train_seg.py
```
If you want to visualize and save the results during the training process, you can do so by modifying `save_freq_train` and `vis_path` in `cfgs/config_seg.yaml`

## Evaluation
### Shape Classification
```bash
$ python voting_evaluate_cls.py
```

### Shape Part Segmentation
```bash
$ python voting_evaluate_partseg.py
```
If you want to visualize and save the results during the validationg process, you can do so by modifying `save_freq_train` and `vis_path` in `cfgs/config_seg.yaml`




