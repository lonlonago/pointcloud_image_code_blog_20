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

