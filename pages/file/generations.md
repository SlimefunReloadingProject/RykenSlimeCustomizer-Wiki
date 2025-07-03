# 世界生成(generations.yml)

<mark style="color:red;">**注意：**</mark>带\*为必填

> 用于自定义自然生成于世界中的粘液科技方块。

**示例：**

```yaml
EXAMPLE_GENERATION:
  slimefun_id: "EXAMPLE_GENERATIONS" # 此物品必须是一个方块或头颅，且必须是已经注册的id
  areas:
    1:
      maxHeight: 64
      minHeight: 0
      most: 30
      amount: 2
      maxSize: 4
      minSize: 1
      replacement: stone
      environment: NORMAL
    2:
      maxHeight: 64
      minHeight: 0
      most: 30
      amount: 2
      maxSize: 4
      minSize: 1
      replacement: netherrock
      environment: NETHER
```

| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| \*`EXAMPLE_GENERATION` | 自然生成的ID。<br>该ID不能与任何其他物品的ID相同!注意：此ID并非是物品ID!! | **仅支持大写字母、数字、下划线!** |
| slimefun_id | 粘液科技方块物品的id，可以是其它附属的id，也可以是自己在items/geo/mob_drops等配置中自定义的物品(物品必须为方块或头颅) |
| areas | 可供方块生成的多个区域 |
| maxHeight | 最大生成高度，不可以小于minHeight |
| minHeight | 最小生成高度，不可以大于maxHeight |
| most | 此方块在哪一层生成的最多，且越靠近此层，生成的概率越大，数值需在[minHeight,maxHeight]间 |
| amount | 每个区块最大可生成的矿脉数量，最大为200。具体详见下文。| 注意：此值设置太大会导致服务器卡顿，建议此值控制在1~5之间 |
| maxSize | 矿脉的最大可连续生成粘液方块的数量，此值决定了矿脉肉眼看上去的最大规模 |
| minSize | 矿脉的最小可连续生成粘液方块的数量，最小为1，注意：若此值为0，则此粘液方块将无法在世界中生成 |
| replacement | 在自然世界中替代的原版方块，且不建议替换草方块，具体详见下文 |
| environment | 世界生成的维度。 | **仅包括：NORMAL/NETHER/THE_END/CUSTOM** |

### 有关自然生成的生成规则

矿脉中生成的粘液方块数量会在[minSize,maxSize]间随机取值，约接近于most定义的层数，取的值越大

amount实际为在一个区块中尝试生成矿脉的次数，每次尝试生成直至尝试生成失败或者到达设定的值(如果全部尝试生成成功了，那么这个区块中就会生成amount条矿脉)

矿脉数量指的是在视觉表现中，类似于矿石成坨或成条刷新的规模数量（再通俗点，拿原版的铁矿石来说，就是一个区块能生成几坨铁矿）

### 有关replacement

如果你想自定义类似矿石之类的方块想遵循rsc定义的生成条件，则可以将replacement:设置为stone，如果想遵循原版的矿石生成规律，则可以将replacement:设置为相应的原版矿石(前提是这种原版矿石能在你设定的[minHeight,maxHeight]间生成)

注意：不建议替换草方块，这将会使异域花园无法正常自然生成树木从而导致报错

注意：replacement:后填的id为原版的方块id，具体的方块id可以在我的世界wiki上查看，需要与物品id区别的是，部分方块状态id是不具备物品形式的，例如作物之类，马铃薯作物的方块状态id：POTATOES，而填马铃薯的id：POTATO是不生效的，因为马铃薯不是方块，更特殊点的诸如竹子与竹笋的关系，竹子既具有方块形式又具有物品形式，其物品id和方块id都为bamboo，而竹笋有方块形式但没有物品形式，其方块id为bamboo_sapling且没有对应的物品id
