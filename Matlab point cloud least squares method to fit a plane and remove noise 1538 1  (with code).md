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

