
📱 手机端 AutoX 内置编辑器（无独立插件商店）
 
AutoX 手机端没有单独的插件商店，增强靠这两种方式：


https://github.com/aiselp/AutoX/releases

 
1. 内置增强脚本
​
- 下载：https://github.com/kkevsekk1/AutoX/tree/master/sample
​
- 导入：AutoX → 脚本 → 右上角  +  → 导入文件
​
2. 模板/工具包（含编辑器增强）
​
- template.apk（打包用）：https://github.com/kkevsekk1/AutoX/releases
​
- 示例项目：https://github.com/kkevsekk1/AutoX/tree/master/sample





📱 手机端 AutoX 内置编辑器（无独立插件商店）
 
AutoX 手机端没有单独的插件商店，增强靠这两种方式：
 
1. 内置增强脚本
​
- 下载：https://github.com/kkevsekk1/AutoX/tree/master/sample
​
- 导入：AutoX → 脚本 → 右上角  +  → 导入文件
​
2. 模板/工具包（含编辑器增强）
​
- template.apk（打包用）：https://github.com/kkevsekk1/AutoX/releases
​
- 示例项目：https://github.com/kkevsekk1/AutoX/tree/master/sample在 AutoX.js 里，template 一般就指这两个东西，我给你说最直白、最实用的：
 
1. 打包 APK 时的 template（模板）
 
你在 AutoX 里 打包为应用 时，会用到一个叫 template.apk 或 模板apk 的文件。
 
- 它是 AutoX 官方提供的空壳APK
​
- 你的脚本会被“塞”进这个模板里
​
- 最后生成一个可以独立安装的APP
 
位置通常在：
 
 
 
里面一般有：
 
- template.apk
​
- 一些配置文件
 
2. 脚本里的 template 字符串模板
 
比如 ES6 写法：
 
 
 
这里  `...`  包裹的就叫模板字符串，也有人叫 template。
 
 
 
你现在最可能需要的
 
如果你是在 打包APK时提示缺少 template：
 
1. 去 AutoX 设置里
​
2. 找到 应用模板 / template.apk
​
3. 点击 下载模板
 
我可以直接给你：
 
- 能用的 template.apk 下载地址
​
- 或者一键自动下载模板+打包APK的脚本
 
你要哪个？


AutoX.js 打包用的 template.apk 官方下载地址（直接可点）：
 
一、官方 GitHub 最新版（推荐）
 
https://github.com/kkevsekk1/AutoX/releases
 
进入后，在 Assets 里找到：
 
- template.apk（通用模板）
​
- 或 template-v7.apk（新版模板）
 
二、国内加速下载（GitHub 慢时用）
 
https://kgithub.com/kkevsekk1/AutoX/releases
 
三、下载后放哪里（必须放对）
 
1. 下载 template.apk
​
2. 手机文件管理器，新建文件夹：
 /sdcard/AutoX/template/ 
​
3. 把 template.apk 放进去
​
4. 重启 AutoX.js，即可正常打包 APK
 
四、一键下载+放置脚本（可选）
