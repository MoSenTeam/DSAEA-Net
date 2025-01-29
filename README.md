# DSAEA-Net：Enhanced Medical Image Segmentation via Dynamic and Static Attention Aggregation
# Datasets
* The ISIC-2018 Challenge Dataset: The dataset comprises 2,594 images in the training set and 1,000 images in the test set, intended for three distinct tasks related to skin cancer detection. This dataset can be accessed through this link https://paperswithcode.com/dataset/isic-2018-task-1 Download.

* Thyroid Nodule Region Segmentation Dataset (TN3K): This dataset is dedicated to thyroid nodule ultrasound image segmentation. The images are sourced from 2,421 patients, with each image containing at least one thyroid nodule region. The dataset excludes lymphatic images or those with extensive color areas. This dataset can be accessed through this link https://github.com/haifangong/TRFE-Net-for-thyroid-nodule-segmentation Download.

# Introduction
* If you want to use our code, you must make the following preparations under the PyTorch framework: see requirements. txt for details
* If you want to use mixed precision training, please install Apex. If you do not want to install Apex, you can comment out the line and set it to False.

# Train
```
cd ./DSAEA-Net
python train.py
```

* work_dir: Specifies the working directory for the training process. Default value is .workdir
* image_size: Default value is 256.
* mask_num: Specify the number of masks corresponding to one image, with a default value of 5.
* data_path: Dataset directory, for example: .data_demo
* iter_point: Mask decoder iterative runs.
* multimask: Determines whether to output multiple masks. Default value is True.
* encoder_adapter: Whether to fine-tune the Adapter layer, set to False only for fine-tuning the decoder.
* use_amp: Set whether to use mixed-precision training.

# Test
```
cd ./DSAEA-Net
python test.py
```

* work_dir: Specifies the working directory for the testing process. Default value is .workdir
* batch_size: 1.
* image_size: Default value is 256.
* boxes_prompt: Use Bbox prompt to get segmentation results.
* point_num: Specifies the number of points. Default value is 1.
* iter_point: Specifies the number of iterations for point prompts.
* save_pred: Whether to save the prediction results.
* prompt_path: Is there a fixed Prompt file? If not, the value is None, and it will be automatically generated in the latest prediction.

# Reference
* C. Jiang, Q. Yuan, Y. Wang, H. Li, and G. Qiu, " Enhanced Medical Image Segmentation via Dynamic and Static Attention Aggregation," The Visual Computer
* J. Cheng et al., "The SAM-Med2D," Arxiv, preprint 2023 2023.https://doi.org/arXiv:2308.16184.




