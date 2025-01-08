# FL_ExP
## 简介
联邦学习相关的实验框架，内置一些基础版本的实现，可以自定义扩充内容。
包括以下功能：
- 拜占庭鲁棒性实验（可以自定义攻击和防御算法）
- 自定义联邦学习框架实验
- non-i.i.d 环境设置
- 差分隐私支持

目前内置实现了 LF attack、sine attack，防御实现了 krum 以及 fltrust。

## 元定义解释
设置在包 `meta_define` 下，通过继承其中的抽象类来实现自定义内容。

- `attack.py`：
  - `Attack`：实现自定义拜占庭攻击。
  - `Strategic`：实现自定义防御策略。
- `fl.py`：
  - `TaskType`：实现自定义任务类型，目前已实现分类任务和回归任务，以及对应加入DP的版本。
  - `ClientTrain`：实现自定义客户端训练，目前已实现普通客户端和敌手客户端（将自动调用攻击算法）。
  - `Framework`：实现自定义联邦学习框架，目前已实现FedAvg。
- `setting.py`：实现自定义配置文件读取。