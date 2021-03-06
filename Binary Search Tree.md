# 引子

二分法的查找过程是，在一个有序的序列中，每次都会选择有效范围中间位置的元素作判断
即每次判断后，都可以排除近一半的元素，直到查找到目标元素或返回不存在
所以 n 个有序元素构成的序列，查找的时间复杂度为 O(log_2 n)
既然线性结构能够做到查询复杂度为 O(log_2 n) 级别，那二叉搜索树产生又有何必要呢？
毕竟二叉搜索树的查询复杂度只是介于 O(log_2 n)~O(n)  之间，并不存在查询优势

# 定义

二叉搜索树是一种节点值之间具有一定数量级次序的二叉树，对于树中每个节点：

若其左子树存在，则其左子树中每个节点的值都不大于该节点值
若其右子树存在，则其右子树中每个节点的值都不小于该节点值

# 查询复杂度

观察二叉搜索树结构可知，查询每个节点需要的比较次数为节点深度加一
如深度为 0，节点值为 “6” 的根节点，只需要一次比较即可；深度为 1，节点值为 “3” 的节点，只需要两次比较
即二叉树节点个数确定的情况下，整颗树的高度越低，节点的查询复杂度越低

# 构造复杂度

二叉搜索树的构造过程，也就是将节点不断插入到树中适当位置的过程。该操作过程，与查询节点元素的操作基本相同
单个节点的构造复杂度和查询复杂度相同，为 O(log_2 n)~O(n)

# 删除复杂度

O(log_2 n)~O(n)

# 总结

由此可知，二叉搜索树相对于线性结构，在构造复杂度和删除复杂度方面占优
在查询复杂度方面，二叉搜索树可能存在类似于斜树，每层上只有一个节点的情况，该情况下查询复杂度不占优势。

二叉搜索树的节点查询、构造和删除性能，与树的高度相关，如果二叉搜索树能够更“平衡”一些，避免了树结构向线性结构的倾斜，则能够显著降低时间复杂度
二叉搜索树的存储方面，相对于线性结构只需要保存元素值，树中节点需要额外的空间保存节点之间的父子关系，所以在存储消耗上要高于线性结构

