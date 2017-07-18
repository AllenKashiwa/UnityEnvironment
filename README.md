# 打造舒适的Unity开发环境

# 前言

我相信每个开发人员都在工作中慢慢配置了一套让自己最舒适的开发环境。不管是软件还是硬件，用起来得心应手，剑随意动一直是程序员们的追求。本文想仅从软件的角度介绍下我自己开发基于Unity的游戏时的工具及配置。希望初学者可以根据此文扫清环境搭建的困惑，资深开发者可以与我交流自己的见解。本文将持续维护并优先更新于我的[github](https://github.com/AllenKashiwa/UnityEnvironment)和[博客](http://baizihan.me/)。

# 系统篇

本文采用的是Windows 10。windows系统默认的一些设置不太适合程序员，我们来做一些设置。

- （点击Windows键，输入file，）打开文件资源管理器，点击文件菜单，点击**更改文件和搜索选项**：

![image](http://baizihan.me/assets/images/in-post/unity_environment/04.png)

- 进入查看选项卡，显示已知文件扩展名，显示隐藏文件夹并确定：

![image](http://baizihan.me/assets/images/in-post/unity_environment/05.png)


# Unity篇

Unity在windows和mac OS上都有发布自己稳定的版本，我个人是在Windows上做开发。建议你从官网下载安装最新的Unity版本，有移动平台部署需求的，需选取对应的Support项。

- 前往[官网](https://unity3d.com/cn/)下载最新版本的安装助手:

![image](http://baizihan.me/assets/images/in-post/unity_environment/01.png)

- 选择需要的组件并选择存放地址方便重装:

![image](http://baizihan.me/assets/images/in-post/unity_environment/02.png)

- 点击Edit下的Preferences进入设置界面，在General选项卡中去掉Audo Refresh的勾选，在需要刷新的时候按Ctrl+r刷新

![image](http://baizihan.me/assets/images/in-post/unity_environment/06.png)

# Visual Studio篇

IDE(Integrated Development Environment 集成开发环境)的选择上，我用着最新的Visual Studio2017 Community，也建议你安装此版本。2017版的安装需要选取适合Unity开发的组件，其他组件你可以根据自己的喜好选择。

- 前往[官网](https://www.visualstudio.com)下载安装助手:

![image](http://baizihan.me/assets/images/in-post/unity_environment/08.png)

- 打开安装助手选取需要的组件:

![image](http://baizihan.me/assets/images/in-post/unity_environment/07.png)

选取之后会自动添加**Visual Studio 2017 Tools for Unity**插件。

- 单击下一步等待安装完成即可。

如果在安装完成之后需要其他组件，可以找到vs_installer.exe添加和更新组件。我的在这个位置：C:\Program Files (x86)\Microsoft Visual Studio\Installer，你应该可以找到你自己的。

我们还可以为VS安装一些插件以进一步提升效率。这里列出我正在使用的插件供大家参考：

- VsVim（习惯了Vim，用什么编辑器都会装个vim的插件的）
- Resharper（提供了很好的代码提示和重构功能）
- Code Cleaner（强迫症患者的福音，让代码整洁的利器）

VS的配色方案可以在这个[studiostyl](https://studiostyl.es/)网站上找找适合自己的。

# Visual Studio Code篇

如果你有写脚本的需求，那VS Code绝对是一个不错的选择。强大的插件管理，丰富且持续更新的的插件库都十分令人满意。

- 前往[官网](https://code.visualstudio.com/)下载本体:

![image](http://baizihan.me/assets/images/in-post/unity_environment/09.png)

- 打开扩展添加插件：

![image](http://baizihan.me/assets/images/in-post/unity_environment/10.png)

在扩展选项卡中搜索对应的插件名称，在结果中点击安装即可

附上我的插件列表:

Vim（同Visual Studio篇）

LuaIde（提供Lua脚本的只能补全和语法分析）

Code Spellchecker（提供英文拼写检查）

vscode-icons（提供一套漂亮的图标）

插件安装完成，我们来完善一下配置。点击菜单 文件-> 首选项-> 设置，打开用户配置。在左侧窗口中找到对应的配置项，复制到右侧窗口中编辑：

![image](http://baizihan.me/assets/images/in-post/unity_environment/13.png)

点击图中所示的笔，会自动复制到右边窗口。

下面是我自己使用的配置：
```
// 将设置放入此文件中以覆盖默认设置
{
    "vim.useSystemClipboard": true,
    "workbench.iconTheme": "vscode-icons",
    "editor.minimap.enabled": true,
    "editor.fontFamily": "'YaHei Consolas Hybrid', Consolas, 'Courier New', monospace",
    "vim.disableAnnoyingNeovimMessage": true,
    "files.exclude": {
        "**/.git": true,
        "**/.svn": true,
        "**/.hg": true,
        "**/CVS": true,
        "**/.DS_Store": true,
        "**/*.meta": true,
        "**/*.unity": true,
        "**/*.unityproj": true,
        "**/*.mat": true,
        "**/*.fbx": true,
        "**/*.FBX": true,
        "**/*.tga": true,
        "**/*.cubemap": true,
        "**/*.prefab": true,
        "**/Library": true,
        "**/ProjectSettings": true,
        "**/Temp": true,
        "**/*.csproj": true,
        "**/*.sln": true,
        "**/*.userprefs": true
    },
    "editor.renderWhitespace": "all",
    "files.associations": {
        "*.txt":"lua"
    },
    "files.eol": "\n",
    "luaide.scriptRoots": ["D:\\WorkSpace\\Breeze\\Breeze\\Assets\\Scripts\\Slua\\Resources"]
}
```
这里所有的配置项在左边窗口都有对应的中文注释表明配置的效果，这里就不再赘述了。其中["YaHei Consolas Hybrid"字体](https://github.com/yakumioto/YaHei-Consolas-Hybrid-1.12)是一款雅黑与Consolas结合的字体。

配色方面，在扩展里面搜索theme可以找找自己喜欢的主题：

![image](http://baizihan.me/assets/images/in-post/unity_environment/11.png)


# Git篇

版本控制每天都离不开，配置好我们的版本控制工具十分必要。工作中和自己的娱乐项目都使用Git来做版本控制，这里简单说说配置。使用教程可以参考[官方文档](https://git-scm.com/docs)或搜索网上的教程，这里不做讨论。

- 前往[官网](https://git-scm.com/)下载安装Git:

![image](http://baizihan.me/assets/images/in-post/unity_environment/03.png)

- 打开git bash配置用户名密码:
```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

- 配置默认编辑器:
```
$ git config --global core.editor gvim
```

- 配置换行符不自动替换
```
$ git config --global core.autocrlf false
```

- 下载安装[kdiff3](http://kdiff3.sourceforge.net/)之后，将其配置为difftool和mergetool
```
$ git config --global diff.tool kdiff3
$ git config --global merge.tool kdiff3
```

另外推荐图形化工具[SourceTree](https://www.sourcetreeapp.com/)可以帮助我们使用Git.

# Everything篇

Everything绝对是你提高开发效率的利器。秒搜文件的感觉非常满足控制欲。想找log文件只需搜索及打开两个步骤。翻阅文档也不用慢慢点击子文件夹，方便快捷。

- 前往[官网](https://www.voidtools.com/)下载最新的Everything
- 点击Tools-> Options菜单，设置调出快捷键并开机自启动：

![image](http://baizihan.me/assets/images/in-post/unity_environment/12.png)

# 有道云笔记篇

在开发中遇到解决了或没解决的问题我都建议大家使用有云同步功能的笔记本记下来方便查阅。也可以将所思所想记录下来与人交流。有道云笔记基本满足我的需求，本文即是在有道云笔记的markdown编辑器中编写。

- 前往[官网](https://note.youdao.com/)下载安装最新的有道云笔记
- 用喜欢的姿势登录并打开

# 奇妙清单篇

公司里可能已经使用禅道或类似产品做项目管理，但总有一些零碎的小事需要记录。相比使用便签贴的到处都是(不管是实体的还是电子的)，我更喜欢列成清单，分门别类，逐个完成。

- 前往[官网](https://www.wunderlist.com/zh/)下载安装奇妙清单
- 用喜欢的姿势登录

所有的工具都是死的，同一款产品很难满足不同用户的不同需求，希望读者活学活用，配置出属于自己的舒心的开发环境。

# 支持
最后，如果你喜欢本文，欢迎进行关注，打赏，点赞。
用支付宝请我喝咖啡：

![image](http://baizihan.me/assets/images/alipay.png)

用微信请我吃辣条：

![image](http://baizihan.me/assets/images/wechat.png)