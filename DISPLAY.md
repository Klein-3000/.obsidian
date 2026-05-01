# 一、整体认知
```shell
.obsidian
    ├── [app.json]{存储核心行为设置（如自动更新链接、PDF 导出、Vim 模式等）}
    ├── [appearance.json]{记录,使用的字体}
    ├── [community-plugins.json]{记录启用的社区插件}
    ├── [core-plugins.json]{记录启用的核心插件}
    ├── [hotkeys.json]{配置快捷键}
    ├── page-preview.json
    ├── [plugins/]{存放安装的插件的本体}
    ├── [snippets/]{存放各种css文件} 
    ├── [templates.json]{指定存放模版的目录}
    ├── themes/
    └── [workspace.json]{记录: 1.打开过的标签页; 2.窗口的位置,大小等}
 
```
> [!attention] 注意
> 同步配置时,不要同步"workspace.json"文件


| 类别           | 包含文件                                                      | 作用          |
| ------------ | --------------------------------------------------------- | ----------- |
| 🔧 **插件管理**  | `plugins/`, `community-plugins.json`, `core-plugins.json` | 控制功能扩展      |
| 🎨 **外观主题**  | `themes/`, `snippets/`, `appearance.json`                 | 控制视觉风格      |
| 🖼️ **界面布局** | `workspace.json`                                          | 控制窗口结构与打开状态 |
| ⌨️ **操作习惯**  | `hotkeys.json`                                            | 保存你的快捷键偏好   |
| 📊 **高级功能**  | `graph.json`, `templates.json`                            | 图谱与模板设置     |

---
# 二、hotkeys

| 热键（hotkeys） | 作用                  |
| ----------- | ------------------- |
| alt+t       | Table(表格)           |
| alt+h       | heightlight(高亮)     |
| alt+s       | separator(分隔线)      |
| alt+i       | insert template(模版) |
| alt+1~6     | 各级标题                |
| alt+,       | 打开设置                |
| alt+q       | 展开（或折叠）**左**侧边栏     |
| alt+e       | 展开（或折叠）**右**侧边栏     |

---

# 三、plugins
## contribution-graph(热力图)
依赖 dataview
## dataview

## dms-widget-sidebar(有侧边栏小组件)

## hover-reveal(悬浮显示)
### 使用
\[普通文本]\{悬浮文本}
### 实际效果
[普通文本]{悬浮文本}
> [!attention] 注意
> 支持在代码块中使用,
> ```
>    # 建议空两行，以便显示完整悬浮文本
>        tar [-zxf]{调用gzip,解压参数'f'后面的归档文件} <file.archive>
> ```
## i18n
汉化插件的插件
```powershell
# 
plugins/<plugin>
└─lang
	├─ state.json
	└─ zh-ch.json
```
> [!attention] 注意
> i18n 会**修改**被汉化的插件, 记得备份插件

## live-wallpaper
设置 obsidian 背景图,支持图片、视屏、GIF(支持本地资源)。
```powershell
plugins/live-wallpaper
└─wallpapers
    ├─active
    │  └─normal  <-- 存放当前使用背景资源(有且仅有当前背景资源)
    └─history    <-- 存放历史背景资源
```
## obsidian-git

## obsidian-style-setting


---
# 四、snippets
## Akifyss_Obsidian-border(theme).css
==外观主题==
辅助文件 Borderless.json
辅助插件 style-setting : 启用后自动**隐藏**侧边栏

其他功能
1. **悬浮**在标题上,**显示**为几级标题
2. 支持**图片放大**功能
3. 左侧边栏带有 "目录" 和 " 文件" 的**图标**
## Color Header.css
彩虹==标题==
编辑视图 + 阅读视图==统一==标题颜色 
> [!summary] 展示
> # 一级
> ## 二级
> ### 三级
> #### 四级
> ##### 五级
> ##### 六级


## Colored Siedbar Items.css
彩虹==目录==
根据前缀识别，判断显示什么颜色
默认配置13个前缀 ，推荐 "99-prefix" 用作 template(模版) 目录
### 颜色展示
1. <span style="color:d5abdd">00-prefix</span>
2. <span style="color:ffaad2">01-prefix</span>
3. <span style="color:ffafb7">02-prefix</span>
4. <span style="color:ffbf94">03-prefix</span>
5. <span style="color:ffda77">04-prefix</span>
6. <span style="color:f9f871">05-prefix</span>
7. <span style="color:e99a43">06-prefix</span>
8. <span style="color:c1fcf5">07-prefix</span>
9. <span style="color:b3ffe7">08-prefix</span>
10. <span style="color:b2ffd0">09-prefix</span>
11. <span style="color:c0ffb2">10-prefix</span>
12. <span style="color:d9ff91">11-prefix</span>
13. <span style="color:515768">99-prefix</span>
> [!attention] 注意
> 子目录无需前缀, 即可继承父目录的颜色
> 添加(修改)前缀, 子目录都只会继承父目录的颜色

## colorful clock.css
彩虹==时钟==
装饰性使用, 用户搭配主页
辅助插件 dataview
在".md" 文件中使用 `snippets/colorful clock dataviewjs.txt` 中的代码显示==时钟== 。(代码类型==dataviewjs==)

## Notation Colour blocks.css
github 仓库: [notion-colour-block](https://github.com/deathau/obsidian-snippets/blob/main/notation-colour-blocks.css)
类似于 Notion 的 颜色块 -- 字体颜色(note-\<color>) 或 背景颜色 (note-\<color>-background)
### 内置的颜色(\<color>的可选值)
1. 棕色 brown
2. 橙色 orange
3. 黄色 yellow
4. 绿色 green
5. 蓝色 blue
6. 紫色 purple
7. 粉红色 pink
8. 红色 red

### 实际效果
```note-yellow
黄色字体
```

```note-yellow-background
黄色背景
```
> [!attention] 注意
> 预览模式下,才有效果

## realistic Hightlight.css
github 仓库 : [realistic Hightlight]([https://github.com/deathau/obsidian-snippets/blob/main/realistic-highlight.css](https://github.com/deathau/obsidian-snippets/blob/main/realistic-highlight.css))
仿真高亮(马赛克笔)
### 实际效果
1. ==默认==
2. <mark class="green">Green</mark> 
3. <mark class="blue">blue</mark>
4. <mark class="pink">pink</mark>
5. <mark class="purple">purple</mark>
6. <mark class="coral">coral</mark>

## MCL Multi Column.css
### 使用
```markdown
# 标识符
## 双箭头(">>")表示一个列
> [!multi-column]
>> [!left] 左边的列
>>
>>
>  <---- 只用一个">" 表示下面为另一列
>> [!right] 右边的列
>>
>>
```
### 展示
> [!multi-column]
>
>> [!Ideas]
>>  *Explore your mind*
>> - [[Insert link here]]
>
>> [!Books]
>> *Review your books*
>> - [[Insert link here]]
>> 
>
>> [!Projects]
>> *See your projects* 
>> - [[Insert link here]]
>>
>
>> [!todo]+
>> *See your tasks*
>> - [[Insert link here]]

> [!attention] 注意
> 最多展示三列
> 无法自定义列数

> [!multi-column]
>
>> [!roseframe] 凯尔特
>> 1
>> 2
>> 3
>
>> [!roseframe] 玫瑰
>> 1
>> 2
>> 3
## Celtic callout border.css
### 使用
```markdown
# rose frame : 玫瑰框架
> [!roseframe]
> content
> ...
```
### 展示

> [!roseframe]
> 凯尔特

