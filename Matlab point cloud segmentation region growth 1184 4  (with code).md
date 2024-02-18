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

