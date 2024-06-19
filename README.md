# Neural_Style_transfer

Implementation of Neural Style Transfer from the paper '<a href = "https://arxiv.org/pdf/1508.06576">A Neural Algorithm of Artistic Style</a>' using keras and tensorflow with a few changes, like the addition of variation loss.

Using Neural style Transfer, we can generate an image with the help of two images namely a base image and a style image, the content for the generated image comes from the base image while the artistic style of the image comes from the style image. This has helped us to view any image in the artistic form of famous artists. This combination from both the images is achieved by using loss with different components. 

The core mechanism of neural style transfer revolves around the extraction and manipulation of feature representations using pre-trained CNN networks, like in this implementation VGG19 model is used for the extraction of the features representations.

We initilaize a output image, (in this project we are using a copy of the base image for the output image, but a noisy image can also be used) and then we try to calculate the similarity between this image and the base and style images respectively. Since, we want to have the content of the base image in the output image, therefore a content loss is introduced, and also to have the style of the style image a style loss is also introduced. In addition to these two losses, a third loss is also introduced, which is the total variation loss and it helps in ensuring spatial continuity and smoothness in the generated image to avoid noisy and overly pixelated results. The total loss is calculated by weighted addition of these losses.

Once the loss is calculated,then this loss can be minimized using backpropagation which in turn will optimize our randomly generated image into a meaningful piece of art.

# Installation guide:

- Just install the libraries in the requirements.txt manually or run the following script after cloning the repository: - 
```
git clone https://github.com/abhishekbaghel11/Neural_style_transfer
cd Neural_style_transfer
pip install -r requirements.txt
```

- **NOTE** : If you are working on your local machine and if you want to utilize your GPU, make sure your GPU is connected with tensorflow (for which you may require libraries like CUDA toolkit, cudnn) and if you are working on google colab, then in order to use the GPU, make sure that the runtime is set to GPU. If you do not want to run the code the GPU, then you can simply run the code also.  

# Running the files

- Just open the Neural_style_transfer.ipynb file and follow the instructions mentioned in the file, you can also modify the values of the parameters and see the changes in your results.

# Dependencies:

- keras
- tensorflow
- numpy
- matplotlib
- pillow
- os

# Results:

- These results are generated by keeping the weights of the losses as style_wt = 1e6, content_wt = 1 and the total_variation_wt = 1e2 and the number of iterations as 2000.

![Img1](https://drive.google.com/uc?export=view&id=1SruYa_6HhZS6Te3f5RN8woN2fGYlmBxK)
![Img1](https://drive.google.com/uc?export=view&id=1Oby-F8JtqfdSnLhNZRjkgZCf4Rb4UCIm)
![Img2](https://drive.google.com/uc?export=view&id=1pcr6X2ghJSh4eJyIF4DInmuij5USgebK)
![Img1](https://drive.google.com/uc?export=view&id=1bf3znwQ_MNRvFVq73tpcw1bm-kUYwtTy)
