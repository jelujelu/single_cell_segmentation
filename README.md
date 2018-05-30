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

First, raw data should be input into deep_distance_estimator.ipynb. This output will result in a Euclidean distance transform
of the original data.

Second, the Euclidean distance transform data performs much faster and accurately when processed by our modified FCN.
Output of frcnn_apply.ipynb produces results in bounding box of each detected cell.

Finally, the Euclidean distance transform data and the detection data are input into watershed_boundingbox.ipynb.
The distance transform data serves as the objects and the detection data serves as the seeds for the watershed
segmentation.

This method simplifies what would be a complicated input for a watershed segmentation task and provides seeds automatically
without the need for manually tweaking of parameters.

