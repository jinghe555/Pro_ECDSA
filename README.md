# 项目名称
ECDSA签名算法
# 项目简介
椭圆曲线数字签名算法（ECDSA）是使用椭圆曲线密码（ECC）对数字签名算法（DSA）的模拟，其安全性基于椭圆曲线离散对数问题。椭圆曲线离散对数问题远远难于离散对数问题，因此椭圆曲线密码系统的单位比特强度要远高于传统的离散对数系统。在使用较短的密钥的情况下，ECC便可达到于DL系统相同安全级别，拥有计算参数小、密钥短、运算速度快等优势。
# 完成人
何静
# 项目流程
## 基本参数设置
确定a,b等椭圆曲线公式参数，以及基点G
## 公私钥部分
![image](https://user-images.githubusercontent.com/104714591/181490967-ac0e4d76-7d70-4602-a18e-13fb94641d8f.png)

## 签名部分
![image](https://user-images.githubusercontent.com/104714591/181491096-27706096-a2a4-465c-aa0a-b4d261a46a8d.png)

## 验签部分
![image](https://user-images.githubusercontent.com/104714591/181491140-64b9e415-a770-4c46-bd1b-4b7837f221e2.png)

# 部分代码说明
## QA=kp(int(dA,16),G,64)
计算得到公钥QA
## def kp(k,point,length)
椭圆曲线的点乘计算
## def sign(E,dA,K,length,hexstr=0)
生成签名，E:消息的hash值，dA:签名者的私钥，K：随机数
## def verify(sign,E,PA,length)
验证签名,sign：签名R||S,E:消息的hash值，PA：公钥
# 运行过程截图
![image](https://user-images.githubusercontent.com/104714591/181490089-c5fd3928-4e63-4de1-a3a5-b0d882dc4257.png)
输出签名结果，结果代入进行验证——验证通过
# 引用参考
[1]https://andrea.corbellini.name/2015/05/30/elliptic-curve-cryptography-ecdh-and-ecdsa/
[2]https://blog.csdn.net/s_lisheng/article/details/79871341
[3]https://blog.csdn.net/zjj67868236_2/article/details/88884216?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_title~default-1-88884216-blog-105528411.pc_relevant_vip_default&spm=1001.2101.3001.4242.1&utm_relevant_index=4
[4]https://blog.csdn.net/qq_41546054/article/details/120667547?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-2-120667547-blog-88884216.pc_relevant_vip_default&spm=1001.2101.3001.4242.2&utm_relevant_index=5
[5]https://zhuanlan.zhihu.com/p/42629724
[6]https://www.codetd.com/article/11399883
[7]https://www.zhihu.com/question/267039333
[8]https://blog.csdn.net/aaron67/article/details/109006982
