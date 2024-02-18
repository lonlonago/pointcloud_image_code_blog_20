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

