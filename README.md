# SVD Image Classification

## Problem Set

![Lena](https://user-images.githubusercontent.com/45877677/75563206-06c02180-5a5b-11ea-96ca-6cbc3bcee80f.png) 
> Figure : Lena.


#### The digital images are represented with matrices. Each entry of the matrix is a number that shows the level of brightness (intensity) of the corresponding region in the image. The above figure Lena is represented with a matrix of size 512 by 512, i.e., 512 × 512 = 262144 real numbers. Each of these numbers stores about 1 byte in the computer, so this image will require considerable space in the machine. However, it is possible to reduce the storage required for images by decomposing them into smaller blocks. For instance, we can reproduce a matrix in size [512,512] by the production of two matrices in size [512,1] and [1,512]. Hence, instead of keeping 512×512 numbers, it would be enough to keep only 512×2. Unfortunately, it is not possible to have direct decomposition for most of the natural images. Yet, we can approximate them with reasonable errors. In this project, you are supposed to compress the given image Lena with a minimum error and a reasonable strategy.

#### The images can be compressed in many different techniques. Here, you are going to use Singular Value Decomposition (SVD) for image compression. SVD decom- poses any matrix A with size [m,n] as A = USVt where S is a diagonal matrix (with size [m,n]), U and V are orthogonal matrices (with size [m,m] and [n,n] respectively). SVD gives a decomposition of matrix A with a similar application of diagonalization. Diagonal matrix S stores the square roots of eigenvalues of AtA in reducing order (please note that eigenvalues store the energy/information and larger eigenvalues store larger information. So the larger eigenvalues and cor- responding eigenvectors are more informative than others.). Columns of V are the eigenvectors of AtA. The order of these eigenvectors are same with the correspond- ing eigenvalues. Hence, first column of V is the eigenvector of AtA correspond to largest eigenvalue of AtA, etc.

#### Remember from Linear Algebra that d linearly independent eigenvectors span d- dimensional vector space. Since columns of V store n orthogonal (hence linearly independent) eigenvectors, columns of V form a basis for any n-dimensional space. In particular, they form a basis for the row space of A (it makes sense when we consider that AtA store similarity information of columns of A). More importantly this basis is in a special form: basis elements are ordered according to how infor- mative they are about the matrix A. Thus, when we use only first k columns of V, and corresponding columns/rows of matrices S and D, and remove the remaining columns/rows we get an approximation to matrix A. Lets call this approximation as ”k-rank approximation of A” (please note that k-rank approximation of A is supposed to be a matrix in the same size of A).

#### Follow the following steps and answer the questions clearly. Please include all the figures and plots you generated in your report.

- **(a) Load the attached grayscale image Lena.tif. To use MATLAB functions with- out an error I recommend you convert the image Lena to double.**
- **(b) How many entries do you need to store if compression is not applied to the given image (what is the total number of pixels in the image)?**
- **(c) Find U,S,V matrices as a result of SVD. What are the size of each of these matrices?**
- **(d) Calculate 3, 10, 20, 30, 50, 60 ,70, 80, 100-rank approximations through SVD. For each case calculate the approximation error as the mean-squared error (an error will be a scalar.), and also calculate the total number of entries the machine needs to store. Plot the errors at the end as a line graph.**
- **(e) Plot the figures for each of the approximations you generated in the previous step. In the title of the figures state the rank of the approximation, calculated mean-squared error and how many entries need to be stored. Include these figures in your report.**
- **(f) Visually which approximations are good enough in your opinion? So by considering the number of entries how much can you compress the image without large error.**
- **(g) Would that make sense to compress image by using 250-rank approximation by SVD? Explain your answer.**
