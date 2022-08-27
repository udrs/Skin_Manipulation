要实现Skin Manipulation，最关键的一点是Recoloring。

但如果直接进行重新着色，周围的环境、衣服可能会随着肤色一起改变。

![image-20220724181337726](C:\Users\wenyihan\AppData\Roaming\Typora\typora-user-images\image-20220724181337726.png)

为此，我们需要通过多算法组合解决这一问题，具体流程如下

1. 首先要通过Skin semantic algorithm精确提取皮肤所在区域（可参考code中的1_Semantic部分）

![image-20220724181200690](C:\Users\wenyihan\AppData\Roaming\Typora\typora-user-images\image-20220724181200690.png)

2.使用Recoloring算法对提取出的皮肤部分进行重新着色（可参考2_Palette-based-photo-recoloring部分）

![image-20220724182020177](C:\Users\wenyihan\AppData\Roaming\Typora\typora-user-images\image-20220724182020177.png)

![image-20220724182045102](C:\Users\wenyihan\AppData\Roaming\Typora\typora-user-images\image-20220724182045102.png)

3.使用opencv中的掩码操作将原图和Skin_Recoloring image进行合并，最终得到如下效果（参考3_mask部分）

![image-20220724182247871](C:\Users\wenyihan\AppData\Roaming\Typora\typora-user-images\image-20220724182247871.png)