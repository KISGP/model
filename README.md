> 该仓库模型文件均来源于网络

> 该仓库模型文件来源位置：
>
> Live2d 模型：
>
> - [https://github.com/Eikanya/Live2d-model](https://github.com/Eikanya/Live2d-model)
> - ...
>
> spine 模型：
>
> - [https://github.com/fatboytao/NikkeSpine](https://github.com/fatboytao/NikkeSpine)
> - [https://github.com/isHarryh/Ark-Models](https://github.com/isHarryh/Ark-Models)
> - [https://github.com/Eikanya/spine-models/tree/master](https://github.com/Eikanya/spine-models/tree/master)
> - ...

# 文件介绍

- [ModelTranslation.json](https://github.com/kisssssssss/model/blob/main/ModelTranslation.json)：Live2d 文件夹下每个文件夹对应的游戏名。
- [ModelList_Live2d.json](https://github.com/kisssssssss/model/blob/main/ModelList_Live2d.json)：live2d 模型具体信息和配置，如在网页的位置及缩放比例等。（所有模型）
  - [ModelList_Live2d_Azur](https://github.com/kisssssssss/model/blob/main/ModelList_Live2d_Azur.json)：碧蓝航线 模型列表
  - [ModelList_Live2d_BengHuai2](https://github.com/kisssssssss/model/blob/main/ModelList_Live2d_BengHuai2.json)：崩坏学园2 模型列表
  - [ModelList_Live2d_GirlsFrontline](https://github.com/kisssssssss/model/blob/main/ModelList_Live2d_GirlsFrontline.json)：少女前线 模型列表
  - [ModelList_Live2d_shuangshengshijie](https://github.com/kisssssssss/model/blob/main/ModelList_Live2d_shuangshengshijie.json)：双生视界 少女咖啡枪 模型列表
  - [ModelList_Live2d_Sin](https://github.com/kisssssssss/model/blob/main/ModelList_Live2d_Sin.json)：sin 七大罪～魔王崇拜～模型列表
  - [ModelList_Live2d_StarRail](https://github.com/kisssssssss/model/blob/main/ModelList_Live2d_StarRail.json)：崩坏: 星穷铁道 模型列表
  - [ModelList_Live2d_VenusScramble](https://github.com/kisssssssss/model/blob/main/ModelList_Live2d_VenusScramble.json)：女神大乱战 模型列表

---

# 快速预览

该仓库的所有模型已经部署在我的网站中 [https://kisssssssss.space/setting/live2d](https://kisssssssss.space/setting/live2d) （由于是在 Vercel 部署的，国内访问会比较慢）

# 使用

主要在网页端搭配 [OhMyLive2D](https://oml2d.com/) 进行使用

```javascript
import { loadOml2d } from 'oh-my-live2d';

// 获取模型列表对象
let models = await (await fetch('https://cdn.jsdelivr.net/gh/kisssssssss/model/ModelList_Live2d.json')).json();

// 将模型列表对象转成数组
models = Object.keys(models).map((key) => models[key].map((item) => item.configuration)).flat(1);

// 加载 live2d
loadOml2d({models})
```

如果你不需要全部模型，可以选择性导入提供的模型  json 文件。例如：

```javascript
// 获取碧蓝航线模型
let models = await (await fetch('https://cdn.jsdelivr.net/gh/kisssssssss/model/ModelList_Live2d_Azur.json')).json();

// 获取崩坏学园2模型
let models = await (await fetch('https://cdn.jsdelivr.net/gh/kisssssssss/model/ModelList_Live2d_BengHuai2.json')).json();

// 获取少女前线模型
let models = await (await fetch('https://cdn.jsdelivr.net/gh/kisssssssss/model/ModelList_Live2d_GirlsFrontline.json')).json();

// ...
```

如果你仅需要特定的模型，可以下载选择下载 [ModelList_Live2d.json](https://github.com/kisssssssss/model/blob/main/ModelList_Live2d.json) ，并从中选取你所需要的模型配置。

# 下载

该仓库大小是 1.45G (2024.5.9)，因此不建议全部下载。如确实需要某个模型文件，可以使用浏览器插件 [GitZip For Github (Google)](https://chromewebstore.google.com/detail/gitzip-for-github/ffabmkklhbepgcgfonabamgnfafbdlkn) [GitZip For Github (Edge)](https://microsoftedge.microsoft.com/addons/detail/gitzip-for-github/nlgkiabjnbdndgblhcaobimbpifcdkjj) 选择你所需要的模型文件进行下载。

# 模型要求

1. 能跟随鼠标转动视角或者有好看的待机动作
2. 不能有过大的背景
