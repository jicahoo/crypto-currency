# crypto-currency
Money in new era
# 比特币

# 比特币的单位
* https://en.bitcoin.it/wiki/Units
* https://en.bitcoin.it/wiki/Satoshi_(unit)

# 有人对比特币有误解
* “ 比特币的上限是两千一百万。这个两千一百万是一个方程的解的数量。矿工的挖矿行为是在计算这个方程的特解。” 我只能说，胡说八道。

# 有人不看好比特币？
* 一个运营私募基金的同事说，比特币不具有货币的本质属性。比特币数量有上限，所以，总数通缩的，通缩，大家就会不花比特币存取来；比特币不用于流通或交易了，就是没有货币的本质属性。而真正的钞票可以更多的发行，做到通胀，大家都想着赶紧花掉。

# 为什么比特币貌似有个2100万的上限？
* 本质是一个几何级数的收敛值.
* 这个级数是如何来的？
    * 新的比特币的来源：矿工发现一个Block, 给的奖励就是新的比特币。最开始的时候，发现一个Block奖励50个比特币。
    * 但是奖励的数额不是一层不变的。每隔210000个Block，奖励就要减半。Block的产生速率是`6Block/Hour`。所以，210000个块相当于4年:`4*365*24*6 = 210240`. 
    * 所以比特币的总量等于 `= 210000*50*1 + 210000*50*(1/2) + 210000*50*(1/4) + ...`, 这个数列的和就是几何级数，结果就是`210000*50*(1/(1-1/2)) = 21000000`. 结果就是两千一百万，单位是BTC。 可以算一算什么时候挖到一个Block，得到的奖励还不到一个聪?
   
* https://en.bitcoin.it/wiki/Controlled_supply
* 比特币发行的趋势图：https://en.bitcoin.it/wiki/File:Controlled_supply-supply_over_block_height.png (第6929999块被挖出来之后，比特币就达到了21000000个)。
* https://www.quora.com/Why-is-Bitcoins-cap-set-at-circa-21-million-coins-and-not-more-or-less-Is-this-amount-chosen-in-an-arbitrary-way-or-is-there-an-argument-behind-it

# 比特币的单位
* 理解单位是真正理解比特币的基础。你才能理解"3个比特币“中3个的内涵到底是什么。
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
