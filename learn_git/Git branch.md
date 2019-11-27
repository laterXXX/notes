# Git branch

----

## Create branch

![image-20191127005553427](C:\Users\82710\AppData\Roaming\Typora\typora-user-images\image-20191127005553427.png)

- git branch branch_name  or  git checkout -b branch_name
- git log --decorate. This command lists all references about the version.
- ![image-20191127010940716](C:\Users\82710\AppData\Roaming\Typora\typora-user-images\image-20191127010940716.png)
- ![image-20191127011025236](C:\Users\82710\AppData\Roaming\Typora\typora-user-images\image-20191127011025236.png)

## Switch branch

- git checkout branch_name

- ![image-20191127011218828](C:\Users\82710\AppData\Roaming\Typora\typora-user-images\image-20191127011218828.png)

- git log --decorate --oneline. This command lists all versions line by line.

- ![image-20191127011432954](C:\Users\82710\AppData\Roaming\Typora\typora-user-images\image-20191127011432954.png)

- if you checkout branch, means reset HEAD~.

  ![image-20191127012156900](F:\paper\image-20191127012156900.png)

- Multi-person collaborative development

  <img src="F:\paper\image-20191127012731445.png" alt="image-20191127012731445" style="zoom:70%;" />

- Graphically display all branches.

  git log --decorate --oneline --all

  <img src="F:\paper\image-20191127013116451.png" alt="image-20191127013116451" style="zoom:80%;" />



## Merge branch

- The situation in the real world when we use git to develop the program

  <img src="F:\paper\image-20191127014504082.png" alt="image-20191127014504082" style="zoom:60%;" />

- first you need to checkout to master, then git merge branch_name

  

## Delete branch

- git branch -d branch_name