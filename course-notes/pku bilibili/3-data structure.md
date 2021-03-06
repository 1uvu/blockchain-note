### 区块链表

哈希指针（hash pointers），不光保存结构体的位置，还保存结构体的哈希值。

区块链就是一个一个区块组成的链表，与普通链表相比的不同为：使用哈希指针代替普通指针（Block chain is a linked list using hash pointers）

最前面的区块是系统自动产生的区块，叫做创世纪块（genesis block）

最后的区块是最近产生的区块（more recent block）

每一个区块都包括指向前一个的哈希指针，最后一个区块也有一个哈希指针指向，保存在系统里。

每一个区块保存的哈希，都是前面整个区块的内容+哈希指针合在一起计算得到的，这样的性质称为（tamper-evident-log）

因此，这样的数据结构使得，只需保存最后一个或几个区块的哈希，就可以检测前面所有的区块是否被篡改。

当需要本地没有保存的区块的哈希值时，可以向其他的结点索要，

### 二叉树

(Merkle tree)，使用哈希指针代替了普通的指针。且内部节点与叶节点的结构不同。

叶节点是数据块，内部节点保存了孩子结点的哈希指针，指针的方向自下向上。

根节点保存根哈希，因此这样的数据结构使得，只需保存根哈希，就可以检测整棵树的区块是否被篡改。

比特币中各个区块是通过哈希指针连接在一起的，而每个区块包含的交易是组织成 Merkle tree 形式的。

每个数据块保存的其实是交易（Transaction）

根哈希值，保存在区块首部（block header）的域中

区块首部中不保存交易内容，区块主体（block body）中保存·交易记录

Merkle tree 的作用有：

1. （Merkle proof）或者（proof of membership）或者（proof of inclusion）

   比特币中的节点分为两种：

   - 全节点（full node）或者（fully validating node）
   - 轻节点（light node）：只保存区块首部

   因此，在发生交易时，需要向轻结点证明交易是否正确写入了区块的 Merkle tree 中。

   但是向全节点请求的哈希值无法判断，然而由于哈希的抗碰撞性，实际中通过这个缺漏制作碰撞不可行。

   验证一个 Merkle proof 时间复杂度为 log(n)，n 为总共有 n 条交易记录。

2. 如果想要证明一条交易不在一个 Merkle tree 中，直接挨个对比很慢，n*log(n)

   所以可以将交易按照交易的哈希值排序，只需先计算要验证的交易的哈希，在根据其范围找到两个待定的交易，最后对比存不存在。

   此时使用的是（Sorted Merkle tree），比特币没有使用这个数据结构。

   只要数据结构是无环的都可以使用哈希指针。