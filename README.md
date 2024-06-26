# 神庙地铁逃亡跑酷 技术文档 ~~(食用指南)~~

## **PART ONE** 开发环境 
### **操作系统**   
- window11  

### **c语言环境**
- vscode进行编译
- gcc 12.3.0 (MinGW-W64 x86_64-ucrt-posix-seh, built by Brecht Sanders)

### **编译选项**
- 默认

### **第三方库**
- 无
---
## **PART TWO** 游戏内容

### 1. **游戏基础操作**
#### 游戏内操作
- 跳跃(jumping) **W**  
- 下蹲(crouching) **S**
- 左移(left move)  **A**
- 右移(right move) **D**
- 左转(turn left) **Q**
- 右转(turn right) **E**
- 开火(fire) **F**
- 暂停(stop) **SPACE**

#### 其他操作
- 再来一把 **R**
- 退出 **E** or 右上角❌
- 设置界面 **T**

### 2. **游戏内图标**
- **\*** 玩家
- **U** 跳跃障碍
- **D** 下蹲障碍
- **X** 不可通行障碍
- **$** 金币(吃了加5得分)
- **L** 垃圾桶(开拓者特性,代替金币)
- **S** 护盾(免除下一次伤害)
- **F** 火球充能(增加一次火球发射次数,上限为3)
- **o** 发射出的火球
- **M** 磁铁(持续一段时间使金币(垃圾桶)爆率上升并吸引同行金币)
- **-** 丁字路口障碍物(不能被护盾抵挡且不能被火球消灭)

### 3. **游戏机制**
- 通过灵活走位躲避障碍(道路确保一定可通行),获取高分,解锁不同结局.~~也可以使用官方外挂(火球消灭一切)~~

- 提供三种游戏难度(Easy,Medium,Hard). 难度越高,移动速度越快,障碍增多,道具获取出率越低,初始火球数减少.~~总有适合你的那一款~~

- 提供两种角色:开拓者与托帕,角色拥有专属特性.  
  银河棒球侠(开拓者):特殊道具垃圾桶代替金币,除加5得分外,有概率格外加分或获得道具  
  托帕&账账:强化火球效果,火球消灭障碍时扩散至同一行,且被消灭障碍掉落金币

- 随着得分上升,移动速度不断加快(存在上限,上限与游戏难度相关).每得到100分,就会出现丁字路口,玩家拥有两条支路的两格视野,可在处于路口时敲击Q或者E来选择一条路径,若撞到丁字路口障碍物,则游戏结束.

- 游戏内共有三种道具:护盾,火球,磁铁.护盾与磁铁的效果均不可叠加,游戏总会优先刷出未拥有的道具  
火球机制:火球存储上限为三发,可消灭前方最近一格的非丁字路口障碍物,初始携带个数与难度相关(Easy为3发,Medium为1发,Hard无).
