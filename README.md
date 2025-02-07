# Deep Learning project for automatic defect detection of Manufactured Solar Cells

**Project Description:**
>  There was dynamic development of various Deep Learning applications in the recent years. One of those is inspection of manufactured goods in search for defects and therefore defected products. This application is rather broad, as designing appropriate solutions one can encounter various challenges and therefore different approaches can be the most optimal in different cases. The description of Photovoltaic Cells inspection case and discussion on possible solutions with it’s advantages and disadvantages is covered in the next chapters. 
>
> The purpose of this study is therefore to identify challenges that are present in the chosen case, discuss possible solutions and choose most promising ones and thereafter make an implementation of this solution/s in this real world scenario. 
>
> What is intended in this project is to find a method through Deep Learning that facilitates the inspection of solar cells in their production process. For this, photographs of different cells will be analysed, they will be classified as "good" or "bad" depending on whether they have defects or not, and the defects of the bad cells and their magnitude will be identified. As for the Deep Learning model to be used, there will be a database with photographs of "good" and "bad" cells that will be used to carry out the training.

## Example of defected FV-Cell image with ROI (mask):
![bmp](/assets/1130.bmp "A sample defected FV-Cell")
![ROI](/assets/ROI_ex.JPG "Sample ROI image of a FV-Cell")

## **Deep Learning methods and approaches tested in the project:**
- Autoencoder approach
  > An Unsupervised Autoencoder will be used to detect these defects. It will be trained only with images of good cells. The aim is to train the model so that it can reconstruct the good images as similar as possible to the previous images and, in turn, be unable to correctly reconstruct the images that contain some type of defect. That is, compare the original images with the images reconstructed by the autoencoder and see how the images that contain good cells are practically the same, while there will be differences with the images with bad cells. \
  > **Results:** As the database of good cells contained only 200 images the training process of the model was not satisfactory hance method results were poor.
- Image segmentation
  > It will begin by segmenting the photographs into reduced images of 64x64 pixels to analyze each cell as if they were more than one and thus, by means of a cumulative, detect the pixels of the original images that contain some defect. \
  > **Results:** The model trained with good examples created this way and saved in the folder “segmentation/train/good” should train way better, as the number of training examples is more than 10 times higher.
- U-NET Architecture
  > U-Net is a semantic segmentation technique originally proposed for medical imaging segmentation. It’s one of the earlier deep learning segmentation models, and the U-Net architecture is also used in many GAN variants such as the Pix2Pix generator. \
  > **Results:** Comparison of images beeing results of different pretrained U-NETs

## Requirements:

Installed:
 > tensorflow, \
 > keras, \
 > matplotlib, \
 > scikit-image, \
 > numpy, \
 > opencv-python

## How to use the resources:

1. Downlad DataSet from the [Drive](https://drive.google.com/file/d/1KHIzLBT4mDT78LYAmoBT76wBO5z4e8a2/view?usp=sharing)
2. Create a project folder with all *\*.ipynb* files, inside it make a new directory **FV-Cells** and unzip the DataSet into it.
- DataSet used during the project should end up in the folders **/FV-Cells/Policristal/Full_Defected/** and **/FV-Cells/Policristal/Full_Defected/**,
3. Run *Auto_Encoder.ipynb* and *Image_segmentation.ipynb* notebooks to observe in detail the steps taken with those respective approaches and watch illustrated samples,
4. Run Notebook *Final_project.ipynb* to see utilization of all three approaches

For the full documentation and report visit [link](https://drive.google.com/file/d/18QVaWcz89qqX2FUrP4Oz0Faoa4F8xLXv/view?usp=sharing)

### Credits:

[Mondragon Unibertsitatea](https://www.mondragon.edu/en/home) - for the opportunity,
[prof. Luka](https://www.linkedin.com/in/luka-eciolaza-9a015a13/) - for the topic, dataset and guidance
