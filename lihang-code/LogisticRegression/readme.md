## Logistic Regression

逻辑回归(logistic regression)，一种典型的分类方法.

Logistic distribution 的分布函数是一条 S 形曲线，即 sigmoid 函数 :

$$g(x) = {1\over 1+e^{-x}}$$

对于二分类问题，可以看作是伯努利试验，即 :

$$P(y=1|x) = p ; P(y=0|x) = 1-p$$

$$P(x|\theta)=\theta^x(1-\theta)^{1-x}$$

对应的似然函数为 :

$$L(x)=\Pi P(y|x) = \Pi x^y (1-x)^{1-y} = \Pi g(x)^y (1-g(x))^{1-y}$$

则对数似然函数为 :

$$L(\theta) = \Pi \log g(x)^y (1-g(x))^{1-y}$$

$$=\sum \log g(x)^y + \log (1-g(x))^{1-y}$$

$$=\sum y\log g(x) + (1-y)\log (1-g(x))$$

$$=\sum y\log g(\theta^Tx) + (1-y)\log (1-g(\theta^Tx))$$

这时我们只需要最大化似然函数，就可以得到最优的参数估计，这里对其取负后除$n$作为最终的损失函数 :

$$J(\theta) = -{1\over n}L(\theta)=-{1\over n}\sum_{i=1}^n y\log g(\theta^Tx) + (1-y)\log (1-g(\theta^Tx))$$
