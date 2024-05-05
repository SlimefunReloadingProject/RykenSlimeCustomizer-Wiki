# 研究(researches.yml)

示例：

```yaml
rsc_example_research:
  id: 367450001
  name: "&a示例研究"
  levelCost: 10
  items:
    - RSC_EXAMPLE_ITEM
  currencyCost: 10 #非必填  
```

| 内容 | 描述 |
| -------- | -------- |
| `example_research` | 研究的key，每个研究的key不能相同。<br>**仅支持小写字母、数字、下划线!** |
| id | 研究的数字ID，最大为 2147483647。 |
| name | 研究的名称。 |
| levelCost | 解锁研究所需要的经验等级。 |
| items | 研究所包含的物品列表。必须为粘液科技物品ID。 |
| currencyCost | 解锁研究所需要的游戏币，详见注意事项。 |


# 注意事项

levelCost和currencyCost仅能同时存在一个。如果两个同时存在，则会忽略levelCost。

**使用currencyCost时请设置粘液本体配置里的`researches.use-money-unlock`为true**
