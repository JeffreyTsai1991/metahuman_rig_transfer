# Metahuman Rig 传输脚本
一系列 python 脚本，用于将 metahuman 装备修改为适用于 Maya 的新装备。

## 先决条件：
(用 Py 2.7 编写）
1. 要装配骨骼的新头部必须与原始泛人类头部共享相同的 UV 和拓扑结构。 像 R3DS Wrap 这样的程序会对此有所帮助。
2. 你从 Metahuman 下载的文件的 embeddedNodeRL4 节点将以 DNA_RL 文件命名，类似于 Kristopher_rl 或 rl4Embedded_Kristofer_rl，如果 metahuman 的名字是 Kristopher。 **将其更改为 rigLogicNode**
3. ![图片](https://user-images.githubusercontent.com/88772846/132264485-74e9d98e-38d9-4227-ab56-1ca9fc5effd5.png)
4. ![图片](https://user-images.githubusercontent.com/88772846/132264420-1128a2eb-d1f0-4ec2-bbdc-ea97e150c197.png)

###良好习惯
建议在尝试此操作之前保存一份 Maya 文件的副本， 因为它会在 rig logic 网络中创建新节点并且不可撤销。


## 指示：
1. 将所有文件保存在某个文件夹中，最好是您的 maya 项目的脚本文件夹。
2. 在maya中打开**Combined_MH.py**脚本。 你不必碰其他脚本。
3. 将上述文件夹的位置复制并粘贴到脚本中。 无需更改正斜杠或其他任何内容。
![图片](https://user-images.githubusercontent.com/88772846/132264121-a525cc5c-e89f-4a88-be70-74efe3d18be1.png)
3. 如图所示，复制并粘贴新形成的头部的名称。 将“NewHead”替换为该网格的名称。
4. 执行文件，等待提示**Proceed now**
5. 现在骨骼应该与新网格的表面对齐。 是时候装配新头部并转移骨骼重量了。
6. 选择 **DHIhead:spine_04**，然后在大纲中依次选择 **New mesh**。 去Skin >> bind skin (options) 并确保你有这样的设置
7. ![图片](https://user-images.githubusercontent.com/88772846/132264992-14f758d7-3061-4cb3-ae5c-24eb1464d548.png)
8. 现在是复制蒙皮权重的时候了。 按顺序在大纲中选择**original metahuman head（原始Metahuamn头部）**和**new head（新头部）**，然后转到 skin >> copy skin weights 并确保设置如下所示。
9. ![图片](https://user-images.githubusercontent.com/88772846/132265047-68307310-67fa-44ef-9059-cfc6b9e2ae58.png)
10. 你现在已经完成了，开始玩你绑定的头。

## 可选：
如果关节太大，您看不到它们是如何对齐的，您可以从大纲中选择 DHI:spin_04，然后运行 **select joint children.py** 脚本以选择层次结构中的所有关节。 您现在可以转到通道框并将骨骼的半径更改为 0.2 而不是原来的 1。

# 许可：
不得用于商业用途，即使经过修改。 不需要注明出处，但值得赞赏。
