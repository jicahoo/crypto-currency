# crypto-currency
Money in new era
# 比特币

# 比特币的单位
* https://en.bitcoin.it/wiki/Units
* https://en.bitcoin.it/wiki/Satoshi_(unit)

# 有意思的比特币分析图表
* https://blockchain.info/charts

# 搞懂比特币所需要的基础知识
* 数据结构
* P2P协议
* 加密算法。简单搜索过，貌似你SSL玩的好，应该很容易理解比特币里面的加密方法。

## 基本概念
* 什么是公钥，私钥？ 什么关系？
    * 从私钥可以算出公钥，反之，不可以。
* 数字签名，哈希，checksum, 摘要，MAC(完整性和认证(谁发的)的双重功能)

## 科普
* http://lucky521.github.io/blog/design/2015/12/26/bitcoin.html

### Hash函数与加密算法的区别
* https://stackoverflow.com/questions/4948322/fundamental-difference-between-hashing-and-encryption-algorithms
    * Hash函数会丢信息，所以不可逆，因为丢信息，所以会碰撞，是多对一。 
    * 加密函数不会丢信息，所以可逆。是1对1.

## 加密算法与比特币
* https://en.bitcoin.it/wiki/How_bitcoin_works 的 Cryptography 一节。
  * 提到了非对称加密算法：ECDSA
  * 提到了Hashcash函数。本来用于了垃圾邮件治理和Dos攻击。
  * In bitcoin, integrity, block-chaining, and the hashcash cost-function all use SHA256 as the underlying cryptographic hash function
## 数字签名

## 比特币的Transaction
* https://www.ccn.com/bitcoin-transaction-really-works/
    * wallet 和 address 的区别

#### 基于非对称加密的数字签名技术:
* 靠虑A发送text给B
  * A发送： [text, encrypt\_with\_private\_key(digest(text))]   => [text, secret\_info]
  * B接收到 [text, secret\_info], 要确定下面的等式成立： digest(text) == decrypt\_with\_public\_key(secret\_info). 如果这个等式成立，text就是A发送的，而且没被篡改。
  * 前提是A要给B提供两个信息：我用的是什么摘要算法，我的公钥。

## 比特币的概念 
### 比特币交易是有成本的，甚至会有手续费。Bitcoin transcation fee. 而且有复杂的算法。
* http://bitcoinfees.com/
### 区块链
* https://bitcoin.org/en/developer-guide#block-chain
   ![graph](https://bitcoin.org/img/dev/en-blockchain-overview.svg "Logo Title Text 1")
* 区块链通过哈希环环相扣。当前区块头要存储前一区块头的哈希值。所以说，当前区块头的值是由所有祖先区块所决定的；而区块头的一部分信息是由所有该区块的交易信息决定的（通过Merkle树，一层一层地算哈希），那么，前一区块头的哈希值是和所有祖先的交易信息相关的。


## 实际操作
* 第一步，下载Bitcoin client.

# 比特币的相关参考资料。
* https://yeasy.gitbooks.io/blockchain_guide/content/crypto/algorithm.html
* https://www.coindesk.com/information/
* https://bitcoin.org/en/bitcoin-paper
