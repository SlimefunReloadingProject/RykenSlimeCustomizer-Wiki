# Researches (researches.yml)

<mark style="color:red;">**Note: Fields with * are required**</mark>

**Example:**

```yaml
rsc_example_research:
  id: 367450001
  name: "&aExample Research"
  levelCost: 10
  items:
    - RSC_EXAMPLE_ITEM
  currencyCost: 10 # Optional
```

| Fields                  | Description |
|-------------------------| ----------- |
| *`rsc_example_research` | The key for the research, each research key must be unique.<br>**Only lowercase letters, numbers, and underscores are supported!** |
| *id                     | The numerical ID for the research, maximum is 2147483647. |
| *name                   | The name of the research. |
| levelCost               | The experience level required to unlock the research. |
| *items                  | A list of items included in the research. Must be Slimefun item IDs. |
| currencyCost            | The in-game currency required to unlock the research, see notes for details. |

## Notes

Only one of levelCost or currencyCost can be present at a time. If both are present, levelCost will be ignored.

**When using currencyCost, please set `researches.use-money-unlock` to true in the Slimefun config file(config.ynl).**
