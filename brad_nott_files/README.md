# Overview

**Note:** All work in this directory was done on Windows 10 within a virtual environment with the following setup

* Python: 3.6
* Tensorflow-gpu: 1.13.1
* CUDA toolkit: 10.0
* cuDNN: 7.4.1
* visual studio: community 2015
* Ref instructions: https://towardsdatascience.com/installing-tensorflow-with-cuda-cudnn-and-gpu-support-on-windows-10-60693e46e781<br><br>

* Also added jupyter notebook to the virtual environment

## Virtual Environment System Specs:
* Intel i7-8700k
* 32 GB RAM
* GeForce GTX 1070 ti (8 GB RAM)

## File Creation
The files in this directory were generated in a separate folder structure than the main repo. You will see references in the notebooks of where I stored, loaded, named, etc. various subsets of the main train/dev/test splits of the dataset. If you want to recreate what I have done, the best way to begin is:

1. Download the json train/dev/test splits of the original data set; wherever you see my directories in the code, change them to the file path(s) on your machine.<br><br>

2. Load the training set json file with `cluster_label_train.ipynb`<br><br>

3. Complete all cells until you get to the one where you pickle `train_hvar_list`<br><br>

4. Complete all steps in `cleanup_book_cutoffs.ipynb`<br><br>

5. Load the `cluster_label_dev` and `cluster_label_test` notebooks and complete all cells until you pickle off `dev_hvar_list` and `test_hvar_list`<br><br>

6. Joins those pickled lists using `per_book_min_max.ipynb` and pickle off `global_min_max`<br><br>

7. Go back to `cluster_label_train.ipynb`, and proceed with the step that loads `global_min_max.pkl`<br><br>

This is a complex workflow because I gathered values from the split files. If system memory permits, this process could be simplified by joining all files together, doing necessary operations against all of the data, and **_then_** splitting.

Please direct any questions to: bradley.nott@gmail.com
