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

