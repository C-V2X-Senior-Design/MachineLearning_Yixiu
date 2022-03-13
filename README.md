# MachineLearning_Yixiu

## Environment Specified:
1. Python == 3.6.0
2. Tensorflow == 2.0.0
3. Tensorflow_gpu == 2.0.0
4. CUDA == 11.6
5. keras == 2.3.1

## Current data Loading (creation) issues (Guide to use dataset_generator):

1. In the folder "dataset_generation", the file generate_RML2016.10a.py is still not working on my side.(Our GNU generated data is unreadable and cannot load in.)

## Guides to run Robust_CNN_Model method:

1. Dataset perparation. Our main reference dataset is RADIOML 2016.10A dataset, which can be downloaded from https://www.deepsig.ai/datasets. (We also need to convert our signals into comaprable formats, which is still under progress).

2. run **"extract_tarfile.py"** once you have dataset ready as a tar file. This step converts downloaded adataset into pickle format file (Python read only).

3. Run **"data_preprocessing.py"** file to extract the data from pickle formatted file for preprocessing. This will generate a file called **'dataset'**.

4. Once either of this files get generated, run **'revised_data_preprocessing.py'** This will rearange the dataset by merging are data points from all classes and SNR values together. (This step incorporates SNR values, not a strict requirementfor training).

5. Running **'revised_data_preprocessing.py'**, You will then have two files generated **'new_model_SNR_test_samples'** which includes all the test data for each SNR value (This will later be used to evaluate the performance of the trained model for each SNR value), and **'combined_SNR_data'** which (containes the training set).   

6. Now using these files, run **'revised_training.py'*

7. Once the model is trained, it will save accuracy, loss, best model and confusion matrices for each SNR value.

8. Once you have the results, you can run **"load_and_plot_results.py"** to generate the plots and confusion matrix. 


## Guides to run Resnet method:

1. Dataset perparation. Our main reference dataset is RADIOML 2016.10A dataset, which can be downloaded from https://www.deepsig.ai/datasets. (We also need to convert our signals into comaprable formats, which is still under progress).

2. run **"extract_tarfile.py"** once you have dataset ready as a tar file. This step converts downloaded adataset into pickle format file (Python read only).

3. Run **"data_preprocessing.py"** file to extract the data from pickle formatted file for preprocessing. This will generate a file called **'dataset'**.

4. Once either of this file gets generated, run **'revised_data_preprocessing.py'** if you generated smaller dataset or run **'revised_data_preprocessing_B.py'** if you generated bigger dataset. 

5. You will then have two files generated **'new_model_SNR_test_samples'** and **'combined_SNR_data'** if you ran **'revised_data_preprocessing.py'** or you will have **'new_model_SNR_test-B'** and **'combined_SNR_data-B'** if you ran **'revised_data_preprocessing_B.py'**. 

6. Now using these files, run **'revised_training.py'** or **'revised_training-B.py'** depending on which dataset you want to use for training. 

7. Once the model is trained, it will save accuracy, loss, best model and confusion matrices for each SNR value.

8. Once you have the results, you can use **"Plots.ipynb"** to generate the plots and confusion matrix. 


## Guides to run CLDNN method:
1. Dataset perparation. Our main reference dataset is RADIOML 2016.10A dataset, which can be downloaded from https://www.deepsig.ai/datasets. (We also need to convert our signals into comaprable formats, which is still under progress).

2. run **"extract_tarfile.py"** once you have dataset ready as a tar file. This step converts downloaded adataset into pickle format file (Python read only).

3. Run **"data_preprocessing.py"** file to extract the data from pickle formatted file for preprocessing. This will generate a file called **'dataset'**.

4. Once either of this file gets generated, run **'revised_data_preprocessing.py'** if you generated smaller dataset or run **'revised_big_data_preprocessing.py'** if you generated bigger dataset. 

5. You will then have two files generated **'new_model_SNR_test_samples'** and **'combined_SNR_data'** if you ran **'revised_data_preprocessing.py'** or you will have **'new_model_SNR_test_samples_bigdata'** and **'combined_SNR_data_bigdata'** if you ran **'revised_big_data_preprocessing.py'**. 

6. Now using these files, run **'revised_training.py'** or **'revised_bigdata_training.py'** depending on which dataset you want to use for training. 

7. Once the model is trained, it will save accuracy, loss, best model and confusion matrices for each SNR value.

8. Once you have the results, you can run **"load_and_plot_results.py"** to generate the plots and confusion matrix. 

## Reference:

* Most of code in folder(CLDNN Model,Resnet,Robust_CNN Model,dataset_generator) is from DeepSig Company (https://www.deepsig.ai/?hsLang=en), what I did is to match the environment and tune the code to be runable in a new environment. 
