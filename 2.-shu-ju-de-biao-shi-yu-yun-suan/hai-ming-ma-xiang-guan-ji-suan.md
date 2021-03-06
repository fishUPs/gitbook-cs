# 海明码相关计算

汉明码是一种具有纠错功能的校验码.本文简单地介绍汉明码的计算方法.汉明码的目的是能够纠正一位误码.假设信息码共有 n 位,汉明码共有 r 位,那么总共的码长为 n + r 位.为能检测出 n + r 位编码中其中一位的错误,汉明码必须能够表示至少 n + r + 1 种状态,其中 n + r 种表示 n + r 位编码中有一位错误,另外还需要一种来表示整个编码正确无误.则汉明码的长度需要满足下列关系：2 r >= n + r + 1



![](https://s3.bmp.ovh/imgs/2022/04/05/75dbbc06c61f3631.png)

校验位的确定

k个校验位是通过对m+k位复合码字进行奇偶校验而确定的。

其中：P1位负责校验海明码的第1、3、5、7、…（P1、D1、D2、D4、…）位，（包括P1自己）

P2负责校验海明码的第2、3、6、7、…（P2、D1、D3、D4、…）位，（包括P2自己）

P3负责校验海明码的第4、5、6、7、…（P3、D2、D3、D4、…）位，（包括P3自己）

3、5、7、9、11的二进制编码的第一位为1，所以3、5、7、9、11号位参加第一位校验位，

类似：3、6、7、10、11号位参加2号位校验，5、6、7号位参加4号位校验，9、10、11号位参加8号位校验

![](https://s3.bmp.ovh/imgs/2022/04/05/b63db94198772535.jpg)



汉明码的纠错方式实际上是对传送后的汉明码形成新的检测位P 根据P的状态 直接找出错误

因此可得到三个校验方程及确定校验位的三个公式：（根据规则进行校验 如果是配偶原则P=0 配奇原则P=1）

P1=B1⊕B3⊕B5⊕B7

P2=B2⊕B3⊕B6⊕B7

P3=B4⊕B5⊕B6⊕B7

例 唐 计原的一道例题



![](https://s3.bmp.ovh/imgs/2022/04/05/e0c8709ff13557d1.png)

注：汉明码常用来纠错一位的场合，若欲实现纠错2位，可以再增加一位就错位
