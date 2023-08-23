# Image_Processing
<p align="justify"> Image processing is a set of methods in which the quality of an image is increased or the desired features are extracted from the image. In fact, image processing is interpreted as a mapping from a space with m × n dimensions or m × n × 3 dimensions (depending on whether the image is color or not) to another space. The range of this mapping, if the processing output is still an image, is m × n, and if it is a feature, it can have different dimensions. In this field, the mappings (filters) are divided into two categories. In this project, we are going to learn more about spatial domain filters. </p>

<p align="justify"> In this group of processes, the value of each pixel in the processing output depends on the value of other pixels and the value of the pixel itself, from this point of view, this type of processing shows a local behavior. These local processes can be done linearly or non-linearly. A group of these linear filters work based on the convolution operation. </p>

<p align="justify"> You are familiar with the convolution operation in the time domain. This operation, which is introduced by the following formula, is equivalent to flipping one signal and sliding it over another signal. In the discrete time domain, this operation is easily generalized, and in fact, it is the basis of the performance of FIR filters and windowing. </p>

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/d37c2690-520a-4d10-b1ba-dc10785f74bb)

<p align="justify"> The multi-dimensional mode of this operation is also complete in the same way that a signal is inverted and is slid over another signal in the directions where the signal has a degree of freedom. In the case of images, the two-dimensional filter that should be slid over the images is called kernel. To learn more about this concept, you can go to the following website. </p>

https://www.youtube.com/watch?v=8rrHTtUzyZA&list=WL&index=18&t=45s

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/0c31127d-e156-4c29-b12b-ff82640773f0)

* First, load the "house.jpeg" image using the imread() command, and then apply the following kernels to it using the conv2() function.

**Note:** Due to the presence of negative weights in some kernels, the pixel value may become negative, which cannot be displayed. In this case, use the absolute value.

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/e5eeabe6-4380-4417-91cb-ea6f4ae976b8)

<p align="justify"> First, we import the image into the MATLAB environment. For each of the desired kernels, we form the corresponding matrix and convolute them with the matrix of the original image with the conv2 command. Please note that in order to display the output of kernels that have decimal values, it is necessary to convert them into integers so that they can be displayed. For this purpose, we use the uint8 command. In addition, for kernels that have negative dimensions, as mentioned, the value of the output pixels from the convolution may become negative. Since we do not have negative regions in the image matrix and it is not possible to display them, we use the abs command to display the output of these kernels. In the following, the output of each of the kernels is given and we give a brief explanation about the function of each. </p>

### Sharpen:
<p align="justify"> By filtering the image with this kernel, it can be seen that the edges of the shape are more clearly defined. In other words, we use this kernel to specify the edges of images, and in other words, the image is displayed in more detail after filtering with this kernel. By forming the corresponding kernel and convolutionalizing it with the image matrix, we will have the output as follows. As you can see, the details of the image are more clearly defined. </p>

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/fdc9fc96-d604-4a8e-9edb-8057391ba13e)

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/2125a45a-2c5d-4a35-bd24-2f221bf129a4)

### Blur:
<p align="justify"> This kernel is used to blur images in such a way that in this process, colors or pixels are transferred from one side of the edges of the image to the other, and this transfer is smooth and not sharp. And suddenly, it happens. It can be said that blurring is an example of applying a low-pass filter to an image. The following figure shows the output of this filtering. </p>

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/8d2f6043-0076-432e-94a4-a715f9654a7c)

### Outline:
<p align="justify"> With this filter, you can identify objects or people in images. Its function is similar to sharpen, and for this purpose, the edges of the image must be specified, with the difference that the rest of the image becomes black and dark, and only the edges that define the desired object or person are white. The output of this filter is shown in the figure below. As you can see, the edges or borders of the image of the house are bright white and the rest of the parts are dark and black, which helps us to better distinguish the components of the image. </p>

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/4fa6c8a3-66e9-4dc2-90d6-be181313e6af)

### Gauss:
<p align="justify"> As can be seen from the name of this filter, image processing and filtering in this mode is done in such a way that the Gaussian kernel is convoluted with the pixels of the image. The shape of the Gaussian kernel is the same as the Gaussian procedure that we learned about in the statistics lesson and is shown in the image below. </p>

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/c92cbd0f-3aa8-4e3d-bf49-21c729d279dd)

<p align="justify"> As it is clear from the matrix values ​​of this kernel, the middle area has a much larger value, so it can be said that a pixel of the image that is placed in this position and multiplied by the value of this area has a greater effect on the output pixel than the other pixels around. According to the obtained output, we can see that the original image is a bit blurry. </p>

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/2c8e15db-a1e2-4941-af84-05b7fc735e2e)

### Avg Moving:
<p align="justify"> It is clear from the name of this kernel that we use pixel averaging to filter the image. In this way, we move this 3x3 matrix on the pixels of the image and the value of each pixel in the output is equal to the average of its neighboring pixels. Since this matrix is ​​moved in all parts of the image and averaging is done, that is why it is called average moving. The roots of this matrix are all 0.1111, which is equal to 1/9, which is the weight of each data (the number of data that the matrix of this kernel covers is 9, that's why the averaging weight for each data is 1/9). The output of this filter is as follows: We can see that the image is very smoothly blurred. </p>

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/4549635a-4650-4054-8269-88840fbc83a7)

### Line H:
<p align="justify"> This filter is used to specify the horizontal lines inside the images. The name of this filter is also Line H, which H comes from the beginning of the word Horizontal, which Line H refers to the same horizontal lines. In the output image of this filter, we can also see that all the parts of the image are dark and black, and the horizontal lines inside the image are white and can be seen. </p>

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/04cc93c0-096e-45b8-bf2d-830441001ea9)

### Line V:
<p align="justify"> Similar to the previous explanation, it can be said that V comes from the beginning of the word Vertical, which means vertical, so this filter is used to specify vertical lines inside the image. From the output of this filter, you can also see the specified vertical lines. </p>

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/7cb9a12c-5158-4a85-bcaa-be59b3178f77)

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/d423cecc-1567-4610-bb5e-284836afb21a)

### Identity:
<p align="justify"> As it is clear from the shape of the matrix of this kernel, we can see that all its fields are zero except for its central field. So it can be concluded that the convlution of this matrix with the matrix of the original image does not cause the pixels around the original pixel to affect the final output pixel and only the current pixel in the original image affects the pixel of the output image and from there The value of the kernel matrix's center is 1, so exactly the same pixel size as the original image is transferred to the output image. So we expect to see the same initial image in the output, which is also seen in the figure. </p>

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/ff62963b-e784-4d91-8c58-23475fae75e0)


* <p align="justify"> In many cases, the size of the image we have is not desired. If we need a small image, there is not much problem and downsampling can be used easily, but if we need to enlarge an image, we will have different choices for interpolation kernel. </p>

<p align="justify"> Load the image "kobe.jpeg" and then scale it using the command (imresize) with a ratio of 1/5. Now scale and restore the image again with the same command, this time with a ratio of 5 and method = nearest. In this case, the output is as follows: </p>

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/a263adc5-f0cb-4ba1-8f9e-3d4bc3ded865)

Now we scale the new image with the same command and this time with a factor of 5. In this case, we have the following output:

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/7ad6cd5f-7973-4a70-9908-d3496c02a5d1)

<p align="justify"> The reason for the difference between the original and restored image is that when we reduce the image by a factor of 0.2, we actually reduce the number of samples or pixels. So it can be concluded that a large number of them will be eliminated in this shrinking. As a result, we can see that by removing information from the image, the reduced image can be seen with a lower quality. Now, if we want to enlarge the image whose information has been lost, pixels or samples need to be added to the reduced image. From the point where we use the nearest option in the case of the said project, we can understand that to enlarge the image, what Imresize() command does is that it uses the pixels around the current sample to increase the samples and enlarges the image, that's why we see that in this process of removing information and adding new information to resize the image, the original image becomes a little blurry and cannot be reached. </p>

<p align="justify"> Now, using two Gaussian kernels and moving average, we want to improve the image quality. With the conv2 command and using the mentioned kernels, we will have the following images. </p>

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/3cce78de-2488-4a44-b098-9ce4ff15c9ef)

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/0e8a02a3-9ea9-4248-ab7f-8b38213cb195)

<p align="justify"> According to the images above and comparing them with the unenhanced image, it can be concluded that using kernels is useful to improve the image and the quality of the image can be improved to a small extent. The difference that is evident in the two methods is that the use of the Avg Moving kernel can provide more improvement than the Gaussian kernel. </p>

* <p align="justify"> In the following, we are going to write a program that will determine the edges of a paper from the image using the method we have learned so far. The function of this program is the same as the Cam Scanner program, which finds the edges of the paper and marks it with a colored rectangle in the image. You can use H line kernel to find horizontal edges and V line kernel to identify vertical edges. You can also use the rectangle() function to draw a rectangle. Write the described program and measure the accuracy of its performance by applying it to the image "page.png". </p>

**Tip:** It is suggested that after uploading the image, you convert it to gray scale, as different colors will not help much in finding the edges.


First, we find the horizontal and vertical edges of the image using two kernels, Line H and Line V. These edges are marked in the figure below:

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/76b2f877-5a3c-4953-9130-d1ab589ae02d)

#### Algorithm:
<p align="justify"> The way to find the edges is that we first find the 4 corner points. To find the value of the line of dots, we first transpose the output of the image convolution with the Line H kernel and then apply the sum function to its values. With this, the values ​​of each row of the image above are added together and stored in the horizontal matrix in the written code. (Be careful, because we want to get the row value of the points and the sum function performs the sum on the columns, that's why we have transposed the desired matrix.) In the next step, we sort the sum of the obtained rows, which We have used the sort command. (Please note that we have removed the initial and final values ​​because according to the image above, the sum of the absolute value of their values ​​will be very large and will not give us the original output). After sorting the values, we should consider the two larger values, the last two indices, because the edges of the paper are displayed with white pixels, so their sum is greater than the sum of the other rows, and since two rows are for two edges We need horizontal, that's why we consider its last two values ​​in the sorted matrix. In the last step, we obtain the indices in which the matrix containing the sum of the rows is equal to the value of the last two elements in the sorted matrix as the two rows in which the horizontal edges are located. </p>

<p align="justify"> To calculate the column value of the corner points (or vertical edges), we implement the same thing as we did for the rows, with the difference that there is no need to transpose the matrix. </p>

<p align="justify"> Now that we have obtained the values, by using the rectangle function, we give the row and column values ​​of the upper left corner point in addition to the length and width of the paper (which is the difference between the rows of the edges and their columns) to this function, and the best rectangle that the edge We plotted the marks of the paper. The code of said algorithm is written as follows. </p>

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/28d67050-801f-458f-934d-d66173487875)

The detected edges are displayed in the image below:

![image](https://github.com/SogolGoodarzi/Image_Processing/assets/125180530/97a64e50-6cef-4e86-975d-ef0695b5ceeb)
