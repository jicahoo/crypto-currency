# crypto-currency
Money in new era
# 比特币

# 搞懂比特币所需要的基础知识
* 数据结构
* P2P协议
* 加密算法。简单搜索过，貌似你SSL玩的好，应该很容易理解比特币里面的加密方法。

## 加密算法与比特币
* https://en.bitcoin.it/wiki/How_bitcoin_works 的 Cryptography 一节。
  * 提到了非对称加密算法：ECDSA
  * 提到了Hashcash函数。本来用于了垃圾邮件治理和Dos攻击。
  * In bitcoin, integrity, block-chaining, and the hashcash cost-function all use SHA256 as the underlying cryptographic hash function
## 数字签名

#### 基于非对称加密的数字签名技术:
* 靠虑A发送text给B
  * A发送： [text, encrypt\_with\_private\_key(digest(text))]   => [text, secret\_info]
  * B接收到 [text, secret\_info], 要确定下面的等式成立： digest(text) == decrypt\_with\_public\_key(secret\_info). 如果这个等式成立，text就是A发送的，而且没被篡改。
  * 前提是A要给B提供两个信息：我用的是什么摘要算法，我的公钥。


## 实际操作
* 第一步，下载Bitcoin client.

# 比特币的相关参考资料。
* https://yeasy.gitbooks.io/blockchain_guide/content/crypto/algorithm.html
