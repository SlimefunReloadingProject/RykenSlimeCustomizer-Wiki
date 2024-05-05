# 指令与权限

<table><thead><tr><th width="234">指令</th><th width="108">别名</th><th>作用</th></tr></thead><tbody><tr><td>rykenslimefuncustomizer</td><td>rsc</td><td>显示帮助</td></tr><tr><td>rsc help</td><td></td><td>显示帮助</td></tr><tr><td>rsc reload</td><td></td><td>重载插件及附属</td></tr><tr><td>rsc reloadPlugin</td><td></td><td>重载插件</td></tr><tr><td>rsc list</td><td></td><td>显示加载成功的附属</td></tr><tr><td>rsc enable &#x3C;addons里的文件夹名称></td><td></td><td>加载附属</td></tr><tr><td>rsc disable &#x3C;附属id></td><td></td><td>卸载某附属</td></tr><tr><td>rsc saveitem &#x3C;附属id> &#x3C;物品id></td><td></td><td>保存物品</td></tr><tr><td>rsc menupreview &#x3C;菜单ID></td><td></td><td>预览机器菜单（其他附属的也行）</td></tr></tbody></table<>

指令的权限是`rsc.command.子指令名`，默认仅op可执行。

给予`rsc.command`权限可以执行这里的所有指令（<mark style="color:red;">**不建议给予玩家此权限！**</mark>）。

<mark style="color:red;">**不建议给予玩家除list以外的权限！**</mark>
