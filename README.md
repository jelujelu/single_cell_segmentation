<<<<<<< HEAD
The classification FCN is modified based on the code from  https://github.com/imlab-uiip/keras-segnet
The faster R-CNN is modified based on the code from  https://github.com/yhenon/keras-frcnn



=======
# single_cell_segmentation
The classification FCN is modified based on the code from  https://github.com/imlab-uiip/keras-segnet
The faster R-CNN is modified based on the code from  https://github.com/yhenon/keras-frcnn
>>>>>>> 0d8a1672a422e0db16da21e5ee593a8d8823f466


This single cell segmentation method is a multistep, sequential method.
Manually segmenting cells is a physically taxing and time consuming process.
By combining multiple methods, we attempted to create a fast and accurate pipeline for automatically segmenting cells.


The first step in this method is the Euclidean distance transform. In deep_distance_estimator.ipynb, raw data for training should be located at path_train_input and training labels should be located at path_train_gt. During training, comment out prediction. Once weight file has been created, you can then comment out training and load weight file with any raw data you wish to perform Euclidean distance transform on.


The next step is to train the cell detector. To train the model use train_frcnn.ipynb. Using the Euclidean distance transform data as opposed to raw data has yielded much more accurate results. Euclidean distance transofrm data should be located at "Images" and training labels should be located at "Annotations" (see wwk_parser.py). In order to then use the trained model, use frcnn_apply.ipynb and load weights and input Euclidean distance transform data for prediction. The output of this prediction will be saved at "/bndbox.txt".


Finally, using watershed_boundingbox.ipynb we input the Euclidean distance transform data as the subject of segmentation and the detector, bounding box data as the seeds. Distance transform images should be located at ori_img_path and bounding box data should be located at "bndbox.txt".
