# 研究

示例：

```yaml
example_research:
  id: 1
  name: "&a示例研究"
  levelCost: 10
  items:
    - EXAMPLE_ITEM
  currencyCost: 10 #非必填  
```

## levelCost

设置花费的经验等级。

## items

设置研究后解锁哪些物品。

## currencyCost

设置花费的金钱。

# 注意

levelCost和currencyCost仅能同时存在一个。如果两个同时存在，会忽略levelCost。

**使用currencyCost时请设置粘液本体配置里的`researches.use-money-unlock`为true**
