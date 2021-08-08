# A PyTorch implementation of MPIIGaze and MPIIFaceGaze


## Requirements

* Linux (Tested on Ubuntu only)
* Python >= 3.7


## Download the dataset and preprocess it

### MPIIFaceGaze


```bash
bash scripts/download_mpiigaze_dataset.sh
```
Save this dataset. 
Now run the MPIIGaze_1_1.ipynb notebook cell by cell with a.py given in the repo. 
Now run the Output.ipynb notebook cell by cell.

### Resnet
Update ~/pytorch_mpiigaze/gaze_estimation/models/mpiigaze/resnet_preact.py by code in resnet_preact_1.py
```bash
python3 tools/preprocess_mpiifacegaze.py --dataset datasets/MPIIFaceGaze_normalized -o datasets/
python3 tools/preprocess_mpiifacegaze.py --dataset datasets/MPIIFaceGaze_normalized -o datasets/
python train.py --config configs/mpiigaze/resnet_train.yaml
python evaluate.py --config configs/mpiigaze/resnet_eval.yaml
```

Note that we have to set test index and saved model path in both resnet_train.yaml and resnet_eval.yaml


### Combined Model


Restore the previous ~/pytorch_mpiigaze/gaze_estimation/models/mpiigaze/resnet_preact.py if the above model is run.
```bash
python3 tools/preprocess_mpiifacegaze.py --dataset datasets/MPIIFaceGaze_normalized -o datasets/
python3 tools/preprocess_mpiifacegaze.py --dataset datasets/MPIIFaceGaze_normalized -o datasets/
python train2.py --config configs/mpiigaze/resnet_train.yaml
python evaluate.py --config configs/mpiigaze/resnet_eval.yaml
```

Note that we have to set test index and saved model path in both resnet_train.yaml and resnet_eval.yaml





