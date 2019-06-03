# mechine-Learning
关于机器学习的笔记 

# 1.1决策树是什么
**信息熵**：$Ent(D) = -\sum_{k=1}^{|\gamma|}p_k\log_2p_k$ ，
$Ent(D)$的值越小，则$D$的纯度越高。

**信息增益**：
$$Gain(D,a) = Ent(D) - \sum_{v=1}^{V}\frac{|D^v|}{|D|}Ent(D^v)$$
信息增益越大， 意味这使用属性$a$来进行划分所获得的“纯度提升”越大。

选择属性时，考虑的是信息增益最大者， 即$a_* = \underset{a\in\mathrm{A}}{\arg\min}\ Gain(D,a)$

**增益率**：实际上，信息增益准则对可能取值数目较多的属性有所偏好，为减少这种偏好可能带来的不利影响，引入了“增益率”的定义
$$Gain\underline{\hspace{0.5em}}ratio(D,a) = \frac{Gain(D,a)}{IV(a)}$$
其中$$IV(a) = -\sum_{v=1}^{V}\frac{|D^v|}{|D|}\log_2\frac{|D^v|}{|D|}$$
选择属性时，先从候选划分属性中找出信息增益高于平均水平的属性，再从其中选择增益率最高的。

**基尼指数**：CART决策树使用“基尼指数”来选择划分属性。数据集$D$的纯度可由基尼值来度量：
$$Gini(D) = \sum_{k=1}^{|\gamma|}\sum_{k'\neq k}p_kp_{k'}$$


