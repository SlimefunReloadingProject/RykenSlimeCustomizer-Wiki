# 生物掉落物(mob_drops.yml)

```yaml
RSC_EXAMPLE_MOB_DROP:
  item_group: rsc_example_sub_group
  entity: IRON_GOLEM
  chance: 60
  item:
    name: "&a示例生物掉落物品"
    material: IRON_INGOT
```


| 内容 | 描述 | 有效输入 |
| --- | ----------- | ----------------- |
| `RSC_EXAMPLE_MOB_DROP` | 生物掉落物的ID。<br>该ID不能与任何其他物品的ID相同! | **仅支持大写字母、数字、下划线!** |
| item_group | 物品所在[物品组（分类）](file/groups.md)的ID。 |
| entity | 掉落该物品所需击杀的[实体类型](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/EntityType.html)。 |
| chance | 物品的掉落概率（百分比），数值范围：1 - 100  |
| item.# | [通用物品格式](format/universal-item-format.md)| 可选择性添加modelId、lore、glow等。 |

