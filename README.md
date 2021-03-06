# 币改治理上链阶段一工作方案

## 背景

链上治理是币改工作的一项重要组成部分，决定了币改是否能够向社区化治理演进、公平公开的服务于各类通证化改造项目。但实现链上治理将是一项长期、复杂的工作，而当前币改已接到大量的项目申请，而包括项目的申请、项目信息、评价结果以及币改所发出的一系列公告、决议，迫切的需要采用一套公开、透明以及可追朔的方法对相关文件进行管理，并为各项目币改的过程管理提供支撑。因此，为在短期内初步实现这一目标，决定采用github作为币改工作治理文档提交、发布、存证的管理工具。

## Github目录结构

**根目录**：用于存放币改github的管理规范说明文档。  
**一级目录**：币改公告、项目评审、评审结果存档、治理文档

### 币改公告目录  

本目录用于存放币改工作治理相关的公告、规程、定义解释以及其它相关的合规性声明文件。

### 项目评审目录  

本目录用存放具体币改项目的申请材料、项目说明与应答文件以及评审过程性材料。该目录下设二级子目录，对应具体申请项目，所有该项目的相关资料均应存放在该子目录下。

### 评审结果存档

本目录用于存放通过币改评审项目的最终评审报告，便于各方快速检索、查看。

### 治理文档

本目录用于存放币改工作
的治理文档，包括但不限于币改工作原则、币改治理架构、币改激励规则、项目申请与评审流程等。

## 使用管理规范

### 适用范围

本规则针对所有币改流程参与者，包括提案人，评审人，管理员等。其中，暂定币改秘书处为全局管理员，币改治理工作小组为治理文件目录管理员。各项目方为提案人，在通过线下各推荐人或行业分群筛选后，由管理员分配项目资料提交等权限。评审人（或称为仲裁员）从现有币改筹备委员会中随机抽取21名委员担任，分配对应项目目录下的评审意见结果的提交与修订权限。

### 提交内容版权声明

所有提交的文本、图片等材料不应包含受保护的第三方材料（商标、版权、商业机密、其他私有内容），所有的侵权责任由提交人承担。  
所有提交的材料如无特别说明，视为遵循CC BY协议，所有对此处材料的利用需遵循指明的授权协议。

### Git基本规则

所有提交（``git commit``）的内容，必须注明备注信息。  
请在git客户端中配置自己的用户名和电子邮件地址。

```bash
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

请使用Markdown格式(*.md)或者普通文本文件格式(*.txt)提交文本内容，以便使用Git的差异显示工具。

### 使用流程

币改申请流程包含如下六个步骤，依次为申请提案，初审，补充材料，评审结果公示，评审结果确定。其中，在公示阶段用户可以提出申诉。  

#### 申请提案

申请人在Github站点使用New Issue按钮，选择Application模板进行申请，需填充如下必备内容  

1. 主题
2. 申请人
3. 申请人电子邮件
4. 项目背景与基本概况简述

#### 初审阶段

管理员将对**符合基本规则**的提案分配提案编号BGP001（BG proposal），创建对应名称分支，创建提案目录，生成默认文档目录结构，并在文档目录中填写申请人基本信息，设立项目(Project)看板。  
**不符合要求**的申请将被直接关闭。

#### 补充材料

申请人需Fork全项目，在自己的合理分支中进行文档编写组织工作，并commit至Github，确定完成后，进行Pull Request，其中标题应标识BGP编号，内容应描述清晰准确。  
管理员在判断格式合规后，将接受请求，并指定审阅人，并移动看板状态。

```bash
git clone https://github.com/YOURNAME/YOURFORK
git checkout BGP005
  
修改材料
  
git commit -m '说明'
git push origin
```

请注意，如果你曾经Fork过全项目并发现fork落后于主项目，需要取回项目最新状态进行合并后再进行分支切换。  

```bash
git remote add tr https://github.com/TokenReforming/GovernanceOnChain.git
git fetch tr
git checkout -b BGP005 tr/BGP005
  
修改材料
  
git commit -m '说明'
git push origin
```

#### 申诉

申请人在Github站点使用New Issue按钮，选择Appeal模板进行申诉，需填充如下必备内容，其中申诉材料需参考补充材料部分进行修正或者补全

1. 提案编号，BGP001
2. 提交的申诉材料Pull request编号
3. XXX  

#### 评审结果确定

管理员将结果分支合并进入Master分支，关闭评审分支，为当前状态添加标签，将对应材料归类存档。

```bash
git tag -a BGP005 -m 'BGP005 pass'
```

## 补充说明

本工作方案将根据实际执行情况进行调整。