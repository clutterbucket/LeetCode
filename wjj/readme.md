
|Leetcode链表专题|题目|题解|
|-------|----|----|
||19.删除第N个结点|快慢指针，快指针先走n步，然后慢指针开始走，当快指针到达最后一个结点时，慢指针刚好到达倒数第n+1个节点，头结点可能被删除，所以需要创立哑结点|
||237.删除链表中给定结点|将下一个节点复制到当前节点，然后删除下一个节点|
||83.从排序链表中删除节点，只保留一个|判断当前节点是否与下一个节点相同，若相同删除下一个节点，不相同则将当前节点下移|
||61.旋转链表|第一步快慢指针，找到倒数第k+1个结点；第二步将尾结点指向头结点，更新头结点为倒数第k个结点，然后将倒数第k+1个结点->next=nullptr;第三步将新头结点head返回|
||24.交换所有相邻结点|因为头结点可能会改变所以创立了哑结点；循环起始条件为所要交换的前一个结点p,要交换的第一个结点a,要交换的第二个结点b；第二步p->next=b，a->next=b->next,b->next=a,p=a;第三步返回哑结点的->next|
||206.反转链表|从第二个结点开始，记录当前结点下一个结点，修改当前节点next为前一个节点，更新前一个节点为当前节点，更新当前节点为下一个节点；循环结束后，修改头结点->next=nullptr,避免形成环。|
||92.反转链表II|添加哑结点，然后分别走m-1与n步，得到要反转链表的前一个节点与最后一个结点，对其中链表进行反转，反转完成后，将前一个链表的next改为反转后链表部分的头，将原反转部分的头指向之前反转部分的下一个结点|
||110.求单链表的交点|解法1：先遍历得到两链表长度，然后长链表先走，然后两链表同时走，相同时即为交点。解法2：两链表同时走，走过相同路程则一定同时到达交点处(a(A链表不相交部分长度)+b(B链表不相交部分长度)+c(链表相交部分长度))。则从当前链表头开始走，若为nullptr,则赋为另一个链表头，当两指针相同时，return|
||142.链表入环点|快慢指针，快指针一次两步，慢指针一次一步，两指针相等后，快指针回到head,然后两指针一次一步，再次相等时，即为入环点。|
||148.链表排序| |
||25.k个一组翻转链表| |
||21.合并两个有序链表| |

|Leetcode树专题|题目|题解|
|--|--|--|
|M|98.有效的搜索二叉树|解法一，中序遍历，判断是否为递增序列。解法二，给定每一个结点的范围，判断其是否满足范围|
|M|94.二叉树的中序遍历|利用栈，从根节点开始，左子树依此进栈，然后弹出栈顶原始，压入到输出栈，并从栈顶元素的右子树继续进栈|
|E|101.镜像二叉树|判断是否为镜像二叉树，空树也为镜像二叉树(left->val==right->val)&&dfs(left->left,right->right)&&dfs(left->right,right->left)|
|E|27.二叉树的镜像|遍历二叉树，对每一个结点交换其左右树|
|M|105.构造二叉树|通过hash来记录先序结点值在中序vector中的位置，以此判断出左子树与右子树区间，以此递归，生成左右子树|
|M|102.层序遍历|层序遍历，利用queue,通过queue.size()得到每一层的节点个数|
|M|236.二叉树的公共祖先|遇到空则返回空，遇到q则返回q，遇到p则返回p。分别判断左右子树返回值，如果左为空则右边为祖先，若右为空则左边为祖先，若左右都不为空，则两节点分别在左右两边，即根节点为祖先。|
|E|543.二叉树的直径|相当于求左右子树高度和最大值|
|H|124.求权值最大路径|与上题类似，定义一个全局变量用于存储当前路径最大值，分别dfs左右子树得到左右子树最大值，以此更新路径长度，dfs返回当前左右路径中最大值，注意可能有负数，需要和0做比较。|
|M|173.二叉树搜索迭代器|中序遍历即可。|
|H|297.序列化二叉树|类似先序遍历，序列化，将字符串传引用；反序列化，将字符串当前位置记录。|
