# crypto-currency
Money in new era
# 比特币

# 搞懂比特币所需要的基础知识
* 数据结构
* P2P协议
* 加密算法。简单搜索过，貌似你SSL玩的好，应该很容易理解比特币里面的加密方法。

## 数字签名
基于非对称加密和摘要技术，能够确定某个文件就是由某个实体发送的。
* 靠虑A发送text给B
* A发送： [text, encrypt\_with\_private\_key(digest(text))]   => [text, secret\_info]
* B接收到 [text, secret\_info], 要确定下面的等式成立： digest(text) == decrypt\_with\_public\_key(secret\_info).


# 比特币的相关参考资料。
* https://yeasy.gitbooks.io/blockchain_guide/content/crypto/algorithm.html
