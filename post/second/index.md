# DDPG算法


# DDPG算法

DDPG算法一共包含了四个网络，分别是：Actor当前网络，Actor目标网络，Critic当前网络，Critic目标网络，2个Actor网络的结构相同，2个Critic网络的结构相同，这四个网络的功能如下：

- Actor当前网络：负责策略网络参数 $\theta$ 的迭代更新，负责根据当前状态 S 选择当前动作 A，用于和环境交互生成 S' 和 R。
- Actor目标网络：负责根据经验回放池中采样的下一状态 S' 选择最优下一动作 A'，网络参数 $\theta'$ 定期从 $\theta$ 中复制。
- Critic当前网络：负责价值网络参数 $w$ 的迭代更新，负责计算当前Q值 Q(S,A,w).
- Critic目标网络：负责计算目标Q值 $y_i=R+\gamma Q'(S',A',w')$ 中的 $Q'(S',A',w')$ 部分，网络参数 $w'$ 定期从  $w$ 复制。

![image-20230614232755640](https://llc-typora.oss-cn-hangzhou.aliyuncs.com/typora/image-20230614232755640.png)
