# Record_ordinary_anomalies

一 时间2022.04.19

1.问题：客户使用了半个月的机器(库存机器)，最近客户反馈系统各种弹框报错。
 
2.现象详情：1.机器寄回来后，发现开机后系统各种应用随机报错弹框 2.打开应用也会出现报错 3.等多一段时间随机出现黑屏或者重启 4.也会出现modem crash
  
3.通过抓取日志出现各种异常，直接掉电 无法分析

4.刷其他正常版本以及其他客户版本 现象还存在

5.解决办法：最终分析memory硬件问题。

6. 结果: 更换memory软件运行正常
  

二、apk验证签名


两种要求
1)只能安装与某个apk相同的签名apk  获取指定的apk的签名信息，然后获取要安装的apk签名信息，安装是匹对(framework->pms)

2)银行签名验证
  首先进行机构验签，在进行原生验签
  将META-INF 目下的SGN（建行 农行）或者CENTERM_CERT.CSN(_农信)开吧出来，将其从apk对应目录删除，还原原始apk - 不删除该签名文件安装apk 系统报V2签名异常
  解压的签名文件 并获取其中的收单机构签名信息主体、收单机构签名数据、收单工 作公钥证书、签名文件头；
使用终端保存的收单根公钥证书验证收单工作公钥证书的合法性；验证通过后，使用收单机构工作公钥证书验证原始 APK 文件的签名数据的合法性；
全部验签通过后，才可以进行 Android 原生验签。


三、10.1.2版本农信银行app UI界面显示不全。长城显示正常。MTK未给出方案。待修改....
