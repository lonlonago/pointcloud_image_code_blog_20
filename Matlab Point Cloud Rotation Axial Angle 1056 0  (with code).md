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

