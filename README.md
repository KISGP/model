# Live2d model
**该仓库模型文件均来源于网络。**

由于是在网上搜罗的模型，或多或少会存在一些问题如：model.json文件没有格式化、没有在配置文件添加默认动作、模型文件夹结构混乱，模型大小不一等。因此该仓库主要对这些问题进行相关处理，以便该模型能够直接通过 [OhMyLive2D](https://oml2d.com/) 在网页中进行使用。

具体处理内容：
1. 删除无意义的模型背景仅保留角色![PixPin_2024-05-17_13-16-32](https://github.com/kisssssssss/model/assets/88269600/f96b63e1-4d54-4d59-a106-6e450bd55be4)
2. 压缩所有json文件，尽量减少模型文件大小
3. 根据模型大小配置模型的缩放比例以及偏移位置（改配置仅适用于的OhMyLive2D配置）

> Live2d 模型来源：
>
> - [https://github.com/Eikanya/Live2d-model](https://github.com/Eikanya/Live2d-model)
> - ...

> spine 模型来源（暂时不打算添加，等后面处理完 Live2d 模型再考虑）：
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
  - ...
---

# 快速预览

该仓库的所有模型已经部署在我的网站中 [https://kisssssssss.space/setting/live2d](https://kisssssssss.space/setting/live2d) （由于是在 Vercel 部署的，国内访问会比较慢甚至可能无法访问）

# 使用

## 通过 [OhMyLive2D](https://oml2d.com/) 使用

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
如果你仅需要特定的模型，可以选择下载 [ModelList_Live2d.json](https://github.com/kisssssssss/model/blob/main/ModelList_Live2d.json) ，并从中选取你所需要的模型配置。

## 直接使用

通过请求 [ModelList_Live2d.json](https://cdn.jsdelivr.net/gh/kisssssssss/model/ModelList_Live2d.json) 获取模型信息并从中获取模型路径，再结合自身情况自行使用。

# 下载

该仓库大小是 1.45G (2024.5.9)，因此不建议全部下载。如确实需要某个模型文件，可以使用浏览器插件 [GitZip For Github (Google)](https://chromewebstore.google.com/detail/gitzip-for-github/ffabmkklhbepgcgfonabamgnfafbdlkn) [GitZip For Github (Edge)](https://microsoftedge.microsoft.com/addons/detail/gitzip-for-github/nlgkiabjnbdndgblhcaobimbpifcdkjj) 选择你所需要的模型文件进行下载。


