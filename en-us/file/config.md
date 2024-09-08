# Addon Configuration File

Addon authors can write configuration files to allow the server owner to reasonably allocate addon content.

## Creating a Default Configuration File
1. First, create a `default_config.yml` in the folder where the addon content is located, and then write some options.
2. Save the `default_config.yml` (**Note: The encoding should be UTF-8**).

## Notes
1. RSC will copy the `default_config.yml` from the addon and paste it into `RykenSlimeCustomizer/addon_configs/(addon id)/config.yml`.
2. Do not modify the `default_config.yml` in the addon, as that file is only used as a template, and the content that is actually read is in the configuration file in the `addon_configs` folder.
   (Updating the addon will overwrite the `default_config.yml`).
3. Do not delete the `default_config.yml`, otherwise, the addon may not work properly.

## Linkage with Scripts
For details, see [Scripts - Basic](../scripts-basic/basic.md#addon-configuration-file).

## As a Condition for Content Registration
For details, see [Content Registration/Loading Options](context-options.md#about-conditions).
