#  I. Introduction 

>  The principle is very simple and is mainly divided into three steps: 1. First, according to the center and axis of the cylinder, the point cloud is projected in a plane (axial). 2. Perform a circular search for the projected point cloud. 3. Extract the points in the cylindrical area of the point cloud. 

#  Implementation code 

>  CylinderSearch.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574042967
 ```  
#  III. Achieving results 

![avatar]( b9477164a53b440295f60c6ab8ed5e83.png) 

 ![avatar]( 86ae18a12a534bc99a1c431ad5fcc2c1.png) 

#  reference 

>  [1] CloudCompare & PCL Point Cloud Cylinder Neighborhood Search 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Matlab provides us with a method of denoising, which is similar to the principle of SOR filtering (or according to the "_" of SOR filtering). 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574054229
 ```  
#  III. Achieving results 

![avatar]( 635b90573a05481f94a2820760b4b55e.png) 

#  reference 

>  [1] Matlab Help Documentation 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Matlab provides a variety of sampling methods, including random sampling, voxel sampling, and non-uniform sampling, the most commonly used of which should be voxel sampling. As for the specific principles of these kinds of sampling, it has been introduced in the previous blog, and I will not go into details here. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574057278
 ```  
#  III. Achieving results 

![avatar]( ad3a6523cf6a4cddb2e54ced499ef515.png) 

 ![avatar]( 90b1830d06594b4a8d5e12b91096124a.png) 

 ![avatar]( 686ec507d0ac435d92d1124c68c9a698.png) 

#  reference 

>  [1] Matlab Help Documentation 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Gaussian curvature definition: The product of two principal curvatures is Gaussian curvature, also known as total curvature, reflecting the total degree of bending at a certain point. 

#  Implementation code 

>  GaussianCurvature.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574025944
 ```  
#  III. Achieving results 

![avatar]( d1f1b40dedcd4cefb3a5313049be79a5.png) 

#  reference 

>  [1] Matlab point cloud principal curvature calculation 



--------------------------------------------------------------------------------

>  There are only two tragedies in life: one is not getting what you want, and the other is getting what you want. ---- Wilde 

#  I. Introduction 

>  The idea of this algorithm is very simple. It is to fit a more suitable plane by removing some outliers. The specific process is as follows: 

1. First, use the least squares method to fit the initial value of a plane coefficient. 2. Calculate the distance from all valid points to the fitting plane 

           d 

           i 

         d_i 

     Di and calculate the standard deviation of these distances 

          s 

         \sigma 

     Sigma. 3. Assuming that the distribution of the data conforms to the normal distribution, here we consider that when 

           d 

           i 

>  

          3 

          ∗ 

          s 

         d_i>3*\sigma 

     Di > 3 * sigma, this point is an outlier, which is eliminated here. 4. Then use the remaining points to recalculate the plane coefficients. 5. Repeat steps 1-4 until the distance of all points is less than the threshold we specify, then the algorithm stops. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574076973
 ```  
#  III. Achieving results 

![avatar]( c3baac093b624db6ae68007fd307c14b.png) 

 Note: The blue points are the points used to fit the plane. 

#  reference 

>  [1]https://max.book118.com/html/2015/0918/25703686.shtm 



--------------------------------------------------------------------------------

#  I. Introduction 

>  This method is also very interesting, and its approximate process is as follows: filter each dimension in the point cloud separately ( 

          x 

          , 

          y 

          , 

          z 

         x,y,z 

     X, y, z), replacing the local area value with the median value of each dimension in the local neighborhood. This idea has strong applicability, and often high-dimensional or lower-dimensional data can be filtered using this method. 

#  II. Relevant parameters 

>  The PCMedian function in Matlab will be used here. 

Dimensions: Specifies the point cloud dimension of interest, specified as an integer vector in the range [1 3]. 1, 2, 3 correspond to the x, y, and z axes respectively. Must be specified in ascending order. 

FilterSize: This parameter is mainly for ordered point clouds, the size of the median filter for an organized point cloud, specified as an odd number in the range [3, N]. N is the smallest channel dimension in the point cloud. 

Radius: This parameter is mainly for disordered point clouds. The neighborhood radius of the disordered point cloud is specified as a positive value. The calculation time increases when there are many points within the specified radius. Therefore, for dense point clouds, a larger radius value results in a higher calculation time. 

#  III. Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 20240203095740998
 ```  
#  IV. Achieving results 

![avatar]( c90b85694eb148ceaa71a65caa963bd0.png) 

#  reference 

>  [1] Matlab Help Documentation 



--------------------------------------------------------------------------------

#  I. Introduction 

>  This function is relatively simple. According to the specified directory, all the point cloud files in the directory are merged into one file for output. The function is very simple, mainly to familiarize yourself with the code. 

#  Implementation code 

##  2.1 Standard method 

>  Use the function pcmerge provided in Matlab. 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574099787
 ```  
##  2.1 Array method 

>  Although the above method can merge point clouds, it will downsample. Sometimes we don't want to downsample, so we can use the following method without using the pcmerge function. 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574099787
 ```  
#  III. Achieving results 

![avatar]( e53a3d5f8a04472f8011069c42c8b8b4.png) 

 ![avatar]( d2da6e14303543829c3fbf930c531b28.png) 

 ![avatar]( 71b0134d435843fabd7c542324f29d80.png) 

 ![avatar]( 98d2e2b541e64939aab6fa84e43e0ccd.png) 

#  IV. References 

>  [1] Matlab Help Documentation 



--------------------------------------------------------------------------------

#  I. Introduction 

>  The method specifies the position of the camera, first obtain the vector of each point pointing to the position, and then calculate the angle between the point and its normal vector based on these vectors. If the angle is less than 90 degrees, the normal vector remains unchanged. Otherwise, flip. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574089977
 ```  
#  III. Achieving results 

![avatar]( 61f0f7a6d9ff424da81d2197c53d59b4.png) 

 ![avatar]( f9291a18c1024b6abf7391e4690dd578.png) 

#  reference 

>  [1] Open3D point cloud normal vector redirection (based on camera position) 



--------------------------------------------------------------------------------

#  I. Introduction 

>  There are various geometric features in the point cloud. Here, based on the neighborhood covariance of each point, the basic geometric features of the point are obtained (as shown in the figure below). Although this approach cannot extract the various parts of the out-point cloud well, it can be used as a means of data preprocessing. 

![avatar]( 432727c071324a6b8f2b8a8721971dbc.png) 

#  Implementation code 

##  2.1 Based on k adjacent points 

>  PlaneStrength.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574050012
 ```  
![avatar]( b71133f326e5429b9a7af2311acdedfc.png) 

 ![avatar]( 39f3c9868e854b11a42c05f104369818.png) 

##  2.2 Based on proximity radius 

>  PlaneStrengthV2.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574050012
 ```  
![avatar]( abf2220306dc4537b3f3a1b0054a9996.png) 

#  reference 

>  [1]Precise 3D extraction of building roofs by fusion ofUAV-based thermal and visible images 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Definition of principal curvature: There are infinite orthogonal curvatures at a point on the surface. There is a curve such that the curvature of the curve is maximal. This curvature is maximal Kmax, and the curvature perpendicular to the surface of maximal curvature is minimal Kmin. These two curvature properties are dominant curvatures. They represent the extremes of normal curvature. Here refer to the practice in PCL to calculate the principal curvature value of each point in the out-point cloud based on the normal vector of the point cloud. 

#  Implementation code 

>  MainCurve.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574061004
 ```  
#  III. Implementation code 

![avatar]( 2173ca717778465886ee5efc42ba73b8.png) 

 ![avatar]( 74a47e4dc1dd4b1bbdc2594906e88179.png) 

#  reference 

>  [1] PCL source code 



--------------------------------------------------------------------------------

#  I. Introduction 

>  The principle here refers to the process of cylindrical projection in PCL, which is divided into two steps: (1) First solve the out-point 

          p 

         p 

     P coordinates on the axis 

          p 

          p 

         pp 

     Pp. (2) based on 

          p 

          p 

         pp 

     PP to 

          p 

         p 

     The direction of p can solve the projection coordinates on the cylindrical surface 

          p 

          r 

          o 

          j 

         proj 

     proj. 

>  For ease of understanding, you can take a closer look at the following image, as shown in the following figure: 

![avatar]( d76b25a0a7944071bb9e30c0c55592c0.png) 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574041647
 ```  
#  III. Achieving results 

![avatar]( fa955cd426f141dcaa079cde18e8a785.png) 

 ![avatar]( 691d47271b7a4d65bab8ccc61ea4f20d.png) 

#  reference 

>  [1] Open3D point cloud projection to a specified cylinder (Python version) 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Here, the point-to-point formula is used to represent a straight line, and the projection process from the point cloud to the straight line is completed. 

#  Implementation code 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574088088
 ```  
#  III. Achieving results 

![avatar]( c9bde1fc5cb84b6a906af739e9554a66.png) 

#  reference 

>  [1] Open3D point cloud least squares method for fitting straight lines in space 



--------------------------------------------------------------------------------

#  I. Introduction 

>  The principle can be found in this blog in detail: the projection coordinates of a point on a plane, which will not be detailed here. 

#  Implementation code 

>  PointCloudProjPlane.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574079428
 ```  
#  III. Achieving results 

![avatar]( bb56636cfd214b11afd7d09fdeaa2ba1.png) 

 ![avatar]( 514b0c3b388849699302955a73068324.png) 

#  reference 

>  [1] Projected coordinates of a point on a plane 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Matlab mainly uses pcread and pcwrite functions to read and write pcd data. Just take this opportunity to study the point cloud type objects provided by Matlab for us. 

#  Implementation code 

##  2.1 Reading the point cloud 

>  main.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574080099
 ```  
We can see from the help documentation that the properties of the "pc" object (pointCloud) are mainly as follows: 

>  Location: The location information of the points in the point cloud. Color: The color of each point in the point cloud. Normal: The normal vector of each point in the point cloud. Intensity: The intensity information of each point in the point cloud. Count: Number of points. XLimits, YLimits, ZLimits: Range of x, y, z respectively. 

##  2.2 point cloud simple color 

After understanding these properties, it is easy to perform some operations on the point cloud, such as coloring. 

>  main.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574080099
 ```  
![avatar]( 652ff361673246f2932baf9bd343597a.png) 

##  2.3 Point cloud normal vector 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574080099
 ```  
![avatar]( a6e4c33b9dad401aa9d4fdcdc34bcda3.png) 

 Strength information is also a similar operation, which will not be demonstrated here. You can consult the help documentation of Matlab. 

##  2.4 Converting ordinary arrays to point cloud objects 

In fact, it is very simple. It is just a type conversion. Let's take a look at the help documentation for this type: 

![avatar]( 3cbe1175b5c04922a0402a415222018f.png) 

 We only need to do this to convert a normal array to a pointCloud object: 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574080099
 ```  
##  2.5 Point cloud data preservation 

After obtaining the pointCloud object using the above method, you can use the following function to save the point cloud data. 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574080099
 ```  
For more information, please refer to the help documentation for the pcwrite function (select the function and press F1). 

![avatar]( 05d04aa83f1b432b9ca646e61d009a17.png) 

#  III. References 

>  [1] Matlab Help Documentation 



--------------------------------------------------------------------------------

#  I. Introduction 

Note: Only rotation matrices are discussed here, not quaternion-related rotation operations 

>  Any point cloud rotation can be described using three rotation angles around the x-axis, y-axis, and z-axis (specifically the rigid transformation here), so we can achieve the desired point cloud rotation operation through these three angles. 

#  Implementation code 

>  rotate.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574063470
 ```  
#  III. Achieving results 

![avatar]( 7115d2c6b6404e63b578de6ef445dc61.png) 

#  reference 

>  [1] Matlab Help Documentation 



--------------------------------------------------------------------------------

#  I. Introduction 

>  There are many ways to represent rotation in three-dimensional space, and the axis angle is a very classic way of expressing it. Although the Euler angle method of representing rotation is very common, the Euler angle has the problem of universal locking, so the axis angle rotation is more suitable for rotation use. The principle is also very clear, as follows: 

>  First, let's assume that an axis passes through the origin 

          u 

          = 

          ( 

          x 

          , 

          y 

          , 

          z 

           ) 

           T 

         u=(x,y,z)^T 

     U = (x, y, z) T, a vector 

          v 

         v 

     V Rotate a certain angle along this axis 

          i 

         \theta 

     Theta, transform to 

           v 

           ′ 

         v' 

     v′： 

![avatar]( 1eaa8604ea49421194846777d039b784.png) 

 Among them, the above 

          u 

         u 

     U only represents the direction, and its modulus is meaningless. To define a direction in three-dimensional space, only two quantities are needed, that is, the angle between any two coordinate axes. The longitude and latitude of the earth are the simplest example. Since 

          u 

         u 

     The die length of u is meaningless, so it is agreed here that 

          u 

         u 

     U is the unit vector, which facilitates the following calculations. 

>  Ok, after a general understanding of the representation of axial angular rotation, how should we implement rotation from one vector to another? Here we need to 

          v 

         v 

     V is decomposed, which is also our usual method when dealing with vectors. Here we can 

          v 

         v 

     V decomposed parallel to the axis of rotation 

          u 

         u 

     U and perpendicular to 

          u 

         u 

     The two components of u, 

           v 

            ∣ 

            ∣ 

         v_{||} 

     V 🥰 🥰 and 

           v 

           ⊥ 

         v_{⊥} 

     V, i.e. 

>  Yeah. 

           v 

           ′ 

         v' 

     V ′ Also perform the above processing: 

![avatar]( 13f1909028cb47ce817b66d005818c58.png) 

 It is easy to find that it is actually parallel to the direction 

           v 

            ∣ 

            ∣ 

         v_{||} 

     There is no need to rotate because it is related to the rotation axis 

          u 

         u 

     U coincides, we only need to rotate the components in the vertical direction, as shown in the figure below. 

![avatar]( 6933a923099946e4b69abf2788e282cd.png) 

>  Here we construct a relationship with 

          v 

         v 

     V perpendicular component 

          w 

         w 

     w（ 

          w 

          = 

          u 

          × 

           v 

           ⊥ 

         w=u×v_{⊥} 

     W = u × v), if the 

          v 

          , 

          w 

         v,w 

     V, w as the coordinate axes of the two-dimensional plane, we can 

           v 

           ⊥ 

           ′ 

         v_{⊥}' 

     V 🥰 ′ decomposes into 

           v 

           v 

           ′ 

          , 

           v 

           w 

           ′ 

         v_{v}' ,v_{w}' 

     Vv ′, vw ′, here can be easily derived: 

At this point, we can naturally arrive at the following results: 

Of which: 

>  Finally, we can obtain a well-known formula, the Rodrigues rotation formula: 

>  Expand it to get: 

![avatar]( 360855ae9a424c11a8577722e184afc7.png) 

#  Implementation code 

>  Here is a demonstration of rotating one vector in the direction of another: 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574081755
 ```  
#  III. Achieving results 

![avatar]( 673c020662974ea0a3dc9f0a2e020734.png) 

 ![avatar]( 5b4baf0eb1004b2a9028ebee16af1569.png) 

#  reference 

>  [1]https://github.com/Krasjet/quaternion [2]https://zh.wikipedia.org/wiki 



--------------------------------------------------------------------------------

#  I. Introduction 

>  One expression that cannot be avoided in three-dimensional rotation is the quaternion. A big problem with Euler's angle in three-dimensional space is its existence of a universal lock, that is, when the pitch angle is ± 90 °, the first rotation and the third rotation will use the same axis, causing the system to lose a degree of freedom (from 3 rotations to 2 rotations, as shown in the figure below). This is called the singularity problem, and it also exists in other forms of Euler's angle. In theory, it can be proved that as long as you want to use 3 real numbers to express three-dimensional rotation, you will inevitably encounter the singularity problem. 

![avatar]( 1b47b19d50924d109471ff16f621b7f6.png) 

##  1.1 Basic knowledge 

>  In order to solve this problem, we need to use the concept of quaternions. Essentially, quaternions still belong to the category of complex numbers, the only difference is that quaternions have three imaginary parts, while complex numbers have only one, so all quaternions can be expressed as: 

Of which: 

![avatar]( 82ee436fede64a2e84a26260e90e43fe.png) 

>  In analogy with complex numbers, quaternions are actually pairs based on { 

          1 

          , 

          i 

          , 

          j 

          , 

          k 

         1,i,j,k 

     A linear combination of 1, i, j, k}, so it can also be written as a vector: 

If the real part is separated from the imaginary part, it can be written as: 

>  The process is very simple. You can learn about it casually on the Internet. Let's focus on the multiplication of quaternions. The multiplication between quaternions is special. It does not obey the commutative law, but obeys the associative law and distributive law. This is similar to the calculation of matrices. It also has the difference between left multiplication and right multiplication. So, if there are two quaternions 

           q 

           1 

          = 

          a 

          + 

          b 

          i 

          + 

          c 

          j 

          + 

          d 

          k 

          and 

           q 

           2 

          = 

          e 

          + 

          f 

          i 

          + 

          g 

          j 

          + 

          h 

          k 

         q_1=a+bi+cj+dk和q_2=e+fi+gj+hk 

     Q1 = a + bi + cj + dk and q2 = e + fi + gj + hk, the product of which can be written as: 

![avatar]( c325983b4dc8484da994b0e66a8ad526.png) 

 To simplify it, we can get: 

We can also conclude that: 

>  Observe the above equation, here let 

          v 

          = 

          [ 

          b 

          , 

          c 

          , 

          d 

          ] 

          , 

          u 

          = 

          [ 

          f 

          , 

          g 

          , 

          h 

          ] 

         v=[b,c,d],u=[f,g,h] 

     V = [b, c, d], u = [f, g, h], we can also use 

          u 

          , 

          v 

         u,v 

     U, v simplify it: 

It can be obtained that: 

This result is also known as the Gražmann product. 

>  In addition, it is also necessary to understand the pure quaternion and its inverse, the former can be expressed as 

            v 

            ′ 

           = 

           [ 

           0 

           , 

           v 

           ] 

          v'=[0,v] 

      V ′ = [0, v], that is, the real part is 0 and only the imaginary part is left. If two pure quaternions 

           v 

            

          = 

          [ 

          0 

          , 

          v 

          ] 

          , 

           u 

            

          = 

          [ 

          0 

          , 

          u 

          ] 

         \ thing {v} = [0, v],\ thing {u} = [0, u] 

     v

=[0,v],u

= [0, u] multiplied to get: 

>  As for its inverse, we can compare it to a matrix, namely 

           q 

            − 

            1 

          q 

          = 

          q 

           q 

            − 

            1 

          = 

          1 

          ( 

          q 

          ! 

          = 

          0 

          ) 

         q^{-1}q=qq^{-1}=1(q!=0) 

     Q − 1q = qq − 1 = 1 (q! = 0), if you directly solve for a 

          q 

         q 

     The inverse of q is not easy, but we can use its conjugate 

           q 

           ∗ 

          = 

          a 

          − 

          b 

          i 

          − 

          c 

          j 

          − 

          d 

          k 

         q^*=a-bi-cj-dk 

     To solve the problem, the conjugate quaternion has a very useful property: 

As you can see, the final result is a real number. 

>  After that, it can be easily concluded that: 

It can be easily found that the inversion of the quaternion is much simpler than the inversion of the matrix, which can speed up the computational efficiency of rotation in the computer. 

##  1.2 Quaternion rotation 

>  Here we are still learning the previous axial angle form (Matlab point cloud rotation axial angle form), and the vector 

          v 

         v 

     V memory splitting, i.e. 

          v 

          = 

           v 

            ∣ 

            ∣ 

          + 

           v 

           ⊥ 

         v = v_{||} + v_{⊥} 

     V = v < unk > < unk > + v < unk >, here we can define these vectors as pure quaternions: 

Then you can get: 

>  The rotation of\ vec {v_ {< unk >}}: previously deduced that if a vector 

           v 

           ⊥ 

         v_{⊥} 

     V is orthogonal to the axis of rotation 

          u 

         u 

     U, then: 

We have previously deduced: 

           v 

            

           u 

            

          = 

          [ 

          0 

          − 

          v 

          ∗ 

          u 

          , 

          0 

          + 

          v 

          × 

          u 

          ] 

          = 

          [ 

          − 

          v 

          ∗ 

          u 

          , 

          v 

          × 

          u 

          ] 

         \ thing {v}\ thing {u} = [0-v * u, 0 + v × u] = [-v * u, v × u] 

     v

u

= [0 − v * u, 0 + v × u] = [− v * u, v × u], 

           u 

            

            v 

            ⊥ 

            

         \ thing {u}\ thing {v _ {}} 

     u

v⊥​

It can be concluded that: 

Here we can use the same pure quaternion for equivalent substitution, resulting in: 

>  Continue to simplify the above equation: 

order 

          q 

          = 

          c 

          o 

          s 

          i 

          + 

          s 

          i 

          n 

          i 

          u 

         q=cos\theta+sin\theta u 

     q = cosθ + sinθu, 真 घेत: 

>  So it's obvious here that if we can get a quaternion 

          q 

         q 

     Q then we can complete 

          v 

          e 

          c 

           v 

           ⊥ 

         thing {v _ {}} 

     VECV is coming 

             v 

             ⊥ 

             

           ′ 

         \ thing {v _ {}} ' 

     v⊥​

′ This rotation operation. 

>  It is natural to conclude that: 

Then we need to replace the 

            v 

             ∣ 

             ∣ 

            

          , 

            v 

            ⊥ 

            

         \ thing {v _ {| |}},\ thing {v _ {}} 

     v∣∣​

​,v⊥​

Here we introduce a new quaternion 

          p 

          = 

          [ 

          c 

          o 

          s 

          ( 

          i 

          / 

          2 

          ) 

          , 

          s 

          i 

          n 

          ( 

          i 

          / 

          2 

          ) 

          u 

          ] 

         p=[cos(\theta/2),sin(\theta/2)u] 

     p=[because (θ/2),sin (θ/2)u], 

>  Here are two more lemmas to achieve the final step (there are too many symbols, here is a direct map~~): 

![avatar]( b389d69212f547bfb960e04094e4286c.png) 

 ![avatar]( 33f21c2bf0ca4650a352c32ba8aa7bb2.png) 

 ![avatar]( 918df8f5492446cd87cc23e324624326.png) 

>  This is where we finally get the result we want. 

Among them, 

           v 

            

          = 

          [ 

          0 

          , 

          v 

          ] 

          , 

           p 

            

          = 

          [ 

          c 

          o 

          s 

          ( 

          i 

          / 

          2 

          ) 

          , 

          s 

          i 

          n 

          ( 

          i 

          / 

          2 

          ) 

           u 

            

          ] 

         \ thing {v} = [0, v],\ thing {p} = [cos (\ theta / 2), sin (\ theta / 2)\ thing {u}] 

     v

=[0,v],p

=[cos (θ/2),sin (θ/2)u

] 

>  Finally, it can be seen intuitively from the results that quaternions are very related to axial angles. We can use axial angles to construct quaternions intuitively. 

##  1.3 Matrix form 

>  In practical applications, due to the convenience of the matrix form, we still end up converting quaternions into a rotation matrix, and the process is simple. Remember that the left and right multiplications above are equivalent to the following two matrices: 

>  Therefore, the original formula can be expressed as: 

Namely: 

![avatar]( 7b18dd779a144f60a8edfc84f1a0d0c6.png) 

#  Implementation code 

>  Here's a demonstration of using quaternions to rotate one vector in the direction of another: 

>  rotate.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574089562
 ```  
#  III. Achieving results 

![avatar]( 85132f8bd0554058a6ae7002d6cd2add.png) 

 ![avatar]( 1b5b409ceda7478e86a3c116c94a5b24.png) 

#  reference 

>  [1]https://github.com/Krasjet/quaternion [2]https://zh.wikipedia.org/wiki 



--------------------------------------------------------------------------------

#  I. Introduction 

>  The principle of calculating the roughness value is very simple, that is, first obtain the neighborhood point set of a point, then use the neighborhood point set to fit a plane, and finally calculate the standard deviation of the distance from the neighborhood point set to the plane. This standard deviation is the roughness of the point. For details, please refer to References [1]. 

#  Implementation code 

>  Roughness.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574081483
 ```  
#  III. Achieving results 

![avatar]( 9e94304939b34accb27c6913fcdd294e.png) 

 ![avatar]( 46ae1022b5e4487e918bd42395ae0179.png) 

#  References 

>  [1]A CORRESPONDENCE FRAMEWORK FOR ALS STRIP ADJUSTMENTS BASED ON VARIANTS OF THE ICP ALGORITHM 



--------------------------------------------------------------------------------

>  A kind personality is not as good as a beautiful appearance, but a kind personality is better than being ugly. ---- Wilde 

#  I. Introduction 

>  As the premise of many applications, point cloud segmentation is directly related to the effect of subsequent processing such as surface reconstruction and feature extraction using point cloud data. As a classic clustering segmentation algorithm, the region growth algorithm has a wide range of applications. The algorithm process is as follows: 

>  1. First, the curvature value of each point will be sorted from small to large. 2. Select the point with the smallest curvature value as the starting seed point, add it to the seed point set P, and start the whole growth process. Why choose the minimum curvature point? Mainly because in general, the position with the smaller curvature value is relatively flat, and growing from the flattest area can reduce the number of finally divided point clouds. 3. Traverse each seed point in the seed point set to find the seed point 

           P 

           i 

         P_i 

     Near point of Pi 

           N 

           j 

         N_j 

     Nj, test the angle of the normal vector between the seed point and the neighboring point, if this angle is less than the smoothing threshold we set, then the neighboring point 

           N 

           j 

         N_j 

     Nj is added to the class point set C; and if the curvature of the neighboring point is less than the curvature threshold we set, it is added to the seed pointset. until all neighboring points are 

           N 

           j 

         N_j 

     Nj and seed points 

           P 

           i 

         P_i 

     After the Pi comparison, the 

           P 

           i 

         P_i 

     Pi is removed from the seed point set and the process is repeated until the seed point set is empty. At this time, the point set C is the result of clustering the local area content according to the curvature. 4. Find the next seed point again and repeat the process in 1-3 until all points are traversed and the algorithm ends. 

#  Implementation code 

>  RG.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957409561
 ```  
>  RegionGrowingAlgo.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957409561
 ```  
#  III. Achieving results 

![avatar]( 50ac00fe184843e1b93ffe93b41ef97b.png) 

 ![avatar]( 156007d2fd1c4bf2a3476b005ab9751e.png) 

#  reference 

>  [1] PCL region growth source code 



--------------------------------------------------------------------------------

#  I. Introduction 

>  Here, based on the neighborhood covariance of each point, the points with the geometric features of the surface in the point cloud are obtained. The calculation method is as follows: 

![avatar]( 432727c071324a6b8f2b8a8721971dbc.png) 

#  Implementation code 

##  2.1 Based on k adjacent points 

>  SurfaceWar.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574051063
 ```  
![avatar]( b71133f326e5429b9a7af2311acdedfc.png) 

 ![avatar]( 0c932f0f635f4ebea697a830bc474d76.png) 

##  2.2 Based on proximity radius 

>  SurfaceVarV2.m 

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574051063
 ```  
![avatar]( a02b3fb53d94496d86da32341891e7ed.png) 

#  reference 

>  [1]Precise 3D extraction of building roofs by fusion ofUAV-based thermal and visible images 



--------------------------------------------------------------------------------

