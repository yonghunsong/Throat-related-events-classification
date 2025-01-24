# Throat-related events classification


This project includes classification model used in “Multimodal deep ensemble classification system with wearable vibration sensor for detecting throat-related events” reported in npj Digital Medicine.

Please refer to the paper for more details.
Song, Y., Yun, I., Giovanoli, S. et al. Multimodal deep ensemble classification system with wearable vibration sensor for detecting throat-related events. npj Digit. Med. 8, 14 (2025). [https://doi.org/10.1038/s41746-024-01417-w]


Recording Data
----------

* Throat-related events: coughing, spekaing, swallowing, and throat clearing
* Subjects: 16 Korean (M: 11, F: 5), 2 American (M: 1, F: 1), 5 France (M: 2, F: 3), 6 German (M: 5, F: 1), 3 Spanish (M: 1, F: 2)
* Using soft skin-attachable throat vibration sensor (STVS)
* At Pohang University of Science and Technology (POSTECH) in South Korea and cereneo Foundation in Switzerland.
* Data is shared via zenodo. ([https://doi.org/10.5281/zenodo.12630148]).


Preprocessing
----------

* Normalization
* Processing with modified 1-D Kalman filter ([<https://ieeexplore.ieee.org/abstract/document/9954780>])
* Augmentation (flipping, moving, scaling, and noise injection)
* Segmentation
* Data transformation: waveform, fundamental frequency (F0), spectrogram, and mel spectrogram


Dataset
----------

* Training (12 subejcts): 1,984 coughing, 2,107 speaking, 2,028 swallowing, and 2,089 throat clearing
* Test (20 subejcts): 150 coughing, 333 speaking, 161 swallowing, and 148 throat clearing


Model
----------

* Deep Neural Networks: WaveNet, ResNet50, and EfficientNet-b0 
* Stacking Ensemble Methods: gradient boosting machine (GBM), random forest (RF), extreme gradient boosting (XGBoost), LightGBM, extra trees, adaptive boosting (AdaBoost), and support vector machine (SVM) 


![image](figures/model.png)


Python file
----------

* Data processing and utils: augmentation.npy, data_preprocessor.npy, data_utils.npy, and image_processing.npy

* neural_network_models.npy: single model
* Trainaing neural networks: Training_WaveNet.npy, Training_ResNet50.npy, Training_EfficientNet.npy
* neural_network_models_test.npy: for test

* ensemble.npy: single ensemble model
* ensemble_models.npy: Training the ensemble model
* ensemble_models_test.npy: for test

