# MachineLearning_Yixiu

## Guides to run DL method for training (Robust_CNN_Model):

1. Dataset perparation. Our main reference dataset is RADIOML 2016.10A dataset, which can be downloaded from https://www.deepsig.ai/datasets. (We also need to convert our signals into comaprable formats, which is still under progress).

2. run **"extract_tarfile.py"** once you have dataset ready as a tar file. This step converts downloaded adataset into pickle format file (Python read only).

3. Run **"data_preprocessing.py"** file to extract the data from pickle formatted file for preprocessing. This will generate a file called **'dataset'**.

4. Once either of this files get generated, run **'revised_data_preprocessing.py'** This will rearange the dataset by merging are data points from all classes and SNR values together. (This step incorporates SNR values, not a strict requirementfor training).

5. Running **'revised_data_preprocessing.py'**, You will then have two files generated **'new_model_SNR_test_samples'** which includes all the test data for each SNR value (This will later be used to evaluate the performance of the trained model for each SNR value), and **'combined_SNR_data'** which (containes the training set).   

6. Now using these files, run **'revised_training.py'*

7. Once the model is trained, it will save accuracy, loss, best model and confusion matrices for each SNR value.

8. Once you have the results, you can run **"load_and_plot_results.py"** to generate the plots and confusion matrix. 








* Most of code in folder() is from DeepSig Company, what I did is to match the environment and tune the code to be runable in a new environment.
