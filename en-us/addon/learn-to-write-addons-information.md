# Write addon information (info.yml)

<mark style="color:red;background:transparent">Note: Fields with * are required</mark>

**Example addon's info.yml:**

```yaml
id: example
name: "Example Addon"
depends: []
pluginDepends: []
scriptListener: "script-listener"
version: "1.0"
description: "RSC Example Addon"
authors: ["mmmjjkx"]
repo: "SlimefunReloadingProject/rsc-example"
```

| 内容 | 描述                                                                                                  |
| --- |-----------------------------------------------------------------------------------------------------|
| \*id | The id of the addon.                                                                                |
| \*name | The name of the addon.                                                                              |
| depends | The id of other custom dependencies edited with RykenSlimeCustomizer                                |
| pluginDepends | The name of the plugin to depend on, that is, the name defined in plugin.yml.                       |
| scriptListener | The name of the event-listening script, a `.js` file named accordingly should be placed in the "scripts" folder, See [Script Advanced-Listener](/en-us/scripts-advanced/listener.md) |
| \*version | The version of the addon.                                                                           |
| description | The description of the addon.                                                                       |
| \*authors | Authors of the addon.                                                                               |
| \*repo | The github repository corresponding to the add-on, which is a required field for addon updates.     |

## Make your dependencies automatically update

### RSC update steps for addons

1. Get the repository from **GitHub**, the address is the above `repo`

2. Find the latest release and compare

3. If the latest version is different from the current version, download the source code zip

4. Unzip the zip to `addons/'addon ID'`

### Notes

The Releases version set on GitHub must be the same as the above version!

Otherwise, it will cause **duplicate downloads**.