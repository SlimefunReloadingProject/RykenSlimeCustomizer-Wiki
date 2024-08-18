# Content loading/registration options (In any content files)

<mark style="color:red;">**Note: Fields with * are required**</mark>

You can add these options for items, machines, etc. added to the addon

**Example (do not copy):**

```yaml
OBJECT_FOR_REGISTER_2:
  id_alias: OBJECT_FOR_REGISTER_1
  lateInit: false
  register:
  warn: false
  conditions:
    - "hasplugin DyeBench"
    - "!hasplugin DynaTech"
    - "version >= 1.18.1"
  unfinished: false
```

| Field | Description |
| -------- | -------- |
| `OBJECT_FOR_REGISTER_2` | ID for content registration. Each registered ID cannot be the same. <br>**Only letters, numbers, and underscores are supported!**<br>The new classification system no longer forces lowercase letters, but when referencing classifications from items, please pay attention to the case of the classification ID. |
| id_alias | See **About id_alias** for details. |
| lateInit | Determine whether to wait for **all** non-delayed loaded content of the current addon to be loaded and registered** before loading and registering** (**check first**)<br>Note: Research is **loaded last** anyway |
| register.warn | Issue a warning when content registration conditions are not met. |
| register.conditions | See **About conditions** for details. |
| register.unfinished | Set whether the current content is unfinished. If the content is not completed, the loading will be skipped directly. |

## About id_alias

**Use the id after this parameter as the registration id** (can be used for multi-version compatibility for your addons)
<br>That is, the registration id is changed to `OBJECT_FOR_REGISTER_1` instead of `OBJECT_FOR_REGISTER_2`
<br>**Note**: `OBJECT_FOR_REGISTER_1` must be **registration failed or does not exist**

## About conditions

Set the conditions required for content registration.

| Condition name | Explanation                                                                     | Example             |
|----------------|---------------------------------------------------------------------------------|---------------------|
| hasplugin      | Requires a certain plug-in                                                      | hasplugin DyeBench  |
| !hasplugin     | Conflict/incompatible with a certain plug-in                                    | !hasplugin DynaTech |
| version        | Check whether the MC version meets the requirements (use >=, <=, >, < to judge) | version >= 1.18.1   |