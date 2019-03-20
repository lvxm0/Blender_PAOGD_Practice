#  PAOGD_HW1

## 弹出小球——简单建模、插值动画

---

### 目标实现

在 Blender 2.8 beta中，实现一个盒子中的小球被盒子底部弹起，落到地面反弹（有形变），并最终平稳落下的过程。

---

### 实现关键

- **缩放、位移和旋转**：新建`shift+A`正方体经纬球，位移到合适地方；在`Z`轴缩放`S+Z`；旋转箱子一个角度`R`。
- **环切和挤出**：箱子的构造一开始用到了环切，`control+R`进行切分，一个扁长方体切分成了9部分；挤出`control+E`除了中心块的8部分构造箱子。![](https://ws3.sinaimg.cn/large/006tKfTcgy1g18lzyg23uj31bc0u00yp.jpg)
- **箱子形态键**：物体模式下加入两个形态键`Basis` 和`Finish`，编辑模式下对`Finish`进行形变操作（此处把箱子中心部分挤出），设置`value`，然后右键设置关键帧。![](https://ws2.sinaimg.cn/large/006tKfTcgy1g18m49j39cj31e10u0h32.jpg)![](https://ws2.sinaimg.cn/large/006tKfTcgy1g18m645hu4j31d80u0dym.jpg)
- **关键帧**：位移起末点设置位移关键帧。
- **曲线编辑器**：用来控制小球运动的速度和加速度。![](https://ws4.sinaimg.cn/large/006tKfTcgy1g18mafc6lwj31d80u0h6s.jpg)![](https://ws4.sinaimg.cn/large/006tKfTcgy1g18mcwa9pvj31d80u0tts.jpg)
- **小球形态键**：采用同样的方式，用形态键关键帧的方法为小球制造弹起效果。![](https://ws3.sinaimg.cn/large/006tKfTcgy1g18mjg9zwxj31d80u07pa.jpg)![](https://ws3.sinaimg.cn/large/006tKfTcgy1g18mlnksc3j31d80u01dr.jpg)![](https://ws3.sinaimg.cn/large/006tKfTcgy1g18mol5aqsj31d80u04jf.jpg)
- **材质纹理**：为箱子和球创建材质，并对材质增加纹理。![](https://ws1.sinaimg.cn/large/006tKfTcgy1g18mu5cev0j31d80u0e0k.jpg)![](https://ws3.sinaimg.cn/large/006tKfTcgy1g18mvluxzij31d80u0nck.jpg)
- **灯光**：试了所有灯光，发现聚光灯最漂亮。![](https://ws1.sinaimg.cn/large/006tKfTcgy1g18mx2x3iyj31d80u0qhe.jpg)



---

### 实现结果

1. 聚光灯下，一个星空小球在空心磨砂纸盒中。

- *为了让小球弹出箱子，箱子需要和地面有个夹角（箱子倾斜）。*

![](https://ws4.sinaimg.cn/large/006tKfTcgy1g18l2nowwqj31d50u0jug.jpg)

2. 星空小球随空心磨砂纸盒底板上升而弹出。

- *箱底上升的过程显然有滑动。小球在顶面有顺着坡的滑动。*

![](https://ws2.sinaimg.cn/large/006tKfTcgy1g18l3nryq8j31d70u0whg.jpg)

3. 星空球经历自由落体运动。

- *这里遵循牛顿第一第二定律，并且至高点有减速。*

![](https://ws3.sinaimg.cn/large/006tKfTcgy1g18l6dshyfj31d30u0tbs.jpg)

4. 星空球落地产生形变（被压扁）。

- *小球比较软，所以落地有形变。*

![](https://ws1.sinaimg.cn/large/006tKfTcgy1g18l7q57y7j31cs0u0dj4.jpg)

5. 星空球再次被弹起，只不过没有那么高了。

- *弹性碰撞导致能量损失，弹射高度变矮。*

![](https://ws3.sinaimg.cn/large/006tKfTcgy1g18l8jmm0pj31cy0u041q.jpg)

6. 星空球再次落下。

- *因为不那么高，小球几乎不形变了。*

![](https://ws4.sinaimg.cn/large/006tKfTcgy1g18l9mzmh7j31dd0u041l.jpg)

7. 再次稍稍弹动，旋转着落地（经纬球角度变化）。

- *为了让弹动更加真实，小球还是会象征性的上升一点点。*
- *因为横向动能由摩擦损失（两次碰撞），弹动摩擦导致小球旋转，所以最后小球一定是转着停下的。*

![](https://ws4.sinaimg.cn/large/006tKfTcgy1g18ljp9cghj31dd0u0tbv.jpg)

---

### 实验心得

- 3-D 建模很考验方向感。
- Blender快捷键之众多。
- 形态帧快捷键之重要性（特殊性）。
- 调整曲线编辑器和动画摄影表也可能会改变关键帧。
- 透视物体和视图插件对精确作图的好处。

---

### 参考资料

- [零基础学Blender](https://www.bilibili.com/video/av24292767/?p=21)
- [Blender 添加纹理教程](https://jingyan.baidu.com/article/6766299798fc9554d41b8475.html)
- [Blender形变动画制作](https://jingyan.baidu.com/article/b2c186c82a5652c46ef6ff02.html)

---