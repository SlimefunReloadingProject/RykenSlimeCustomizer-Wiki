# Addon Structure

## Addon Structure

RSC uses a modular structure, without the annoying merge machine in SC.

Structure tree of the example addon:

```tree
addons
    └─example
        |  armors.yml
        │  capacitors.yml
        │  foods.yml
        │  generators.yml
        │  geo_resources.yml
        │  groups.yml
        │  info.yml
        │  items.yml
        │  machines.yml
        │  mat_generators.yml
        │  mb_machines.yml
        │  menus.yml
        │  mob_drops.yml
        │  recipe_machines.yml
        │  recipe_types.yml
        │  researches.yml
        │  simple_machines.yml
        │  solar_generators.yml
        │  supers.yml
        │  template_machines.yml
        │
        ├─saveditems
        │   │  example_saveditem1.yml
        │   │  example_saveditem2.yml
        │   └─ example_saveditem3.yml
        │
        └─scripts
            ├─ logs
            │ example_capacitor_energy.js
            │ example_chargeable_item.js
            │ example_connector_energy.js
            │ example_consumer_energy.js
            │ example_food.js
            │ example_generator_energy.js
            │ example_machine.js
            │ example_machine_energy.js
            │ example_menu.js
            └─example_script_item.js
```

| Folder name | Description                                                                                              |
|-------------|----------------------------------------------------------------------------------------------------------|
| addons      | Used to store addons                                                                                     |
| example     | Used to store addon files(Can be changed to other names, such as SFExpansion, **do not include spaces**) |
| scripts     | Used to store addon's script files                                                                       |
| saveditems  | Used to store addon's saved items                                                                        |
