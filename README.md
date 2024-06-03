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

> 如果对该仓库有疑问或者不知道如何使用，可以提出issue
# Model
**该仓库模型文件均来源于网络。**

由于是在网上搜罗的模型，或多或少会存在一些问题如：model.json文件没有格式化、没有在配置文件添加默认动作、模型文件夹结构混乱，模型大小不一等。因此该仓库主要对这些问题进行相关处理，以便该模型能够直接通过 [OhMyLive2D](https://oml2d.com/) 在网页中进行使用。

具体处理内容：
1. 删除无意义的模型背景仅保留角色特别是碧蓝航线的模型
   
   >特别是碧蓝航线的模型，基本上都有背景。
   >
   >由于删除背景我是通过 PS 边比较边删除的方法实现的，有些背景不能很好的清理干净，因此播放动作时可能会有某些东西突然飞入或者出现。

   ![PixPin_2024-05-17_13-16-32](https://github.com/kisssssssss/model/assets/88269600/f96b63e1-4d54-4d59-a106-6e450bd55be4)
2. 压缩所有json文件，尽量减少模型文件大小
    ![image](https://github.com/kisssssssss/model/assets/88269600/633e4e2b-ca14-4d99-b155-d697911907cb)

3. 根据模型大小配置模型的缩放比例以及偏移位置（改配置仅适用于的OhMyLive2D配置）

# 文件介绍

- [ModelTranslation.json](https://github.com/kisssssssss/model/blob/main/ModelTranslation.json)：Live2d 文件夹下每个文件夹对应的游戏名。
- [live2d.All.json](https://github.com/kisssssssss/model/blob/main/live2d.All.json)：live2d 模型具体信息和配置，如在网页的位置及缩放比例等。（所有模型）
  - [live2d.Azur.json](https://github.com/kisssssssss/model/blob/main/live2d.Azur.json)：碧蓝航线 模型列表
  - [live2d.BengHuai2.json](https://github.com/kisssssssss/model/blob/main/live2d.BengHuai2.json)：崩坏学园2 模型列表
  - ...

# 快速预览

该仓库的所有模型已经部署在我的网站中 [https://kisssssssss.space/setting/live2d](https://kisssssssss.space/setting/live2d) （由于是在 Vercel 部署的，国内访问会比较慢甚至可能无法访问）

# 使用

> 为了国内可以访问，使用 [Cloudflare Workers](https://workers.cloudflare.com) 和 [hunshcn/gh-proxy](https://github.com/hunshcn/gh-proxy) 进行代理，代理地址 [https://model.kisssssssss.space/](https://model.kisssssssss.space/)
> 
> 由于是免费版的，24 小时内只有 100,000 请求数量，因此如果无法访问可能是请求已经到限量了。
>
> 关于如何部署代理可以查看 [使用Cloudflare Workers优化Github文件国内访问](https://kisssssssss.space/docs/%E6%9C%8D%E5%8A%A1%E5%99%A8/%E4%BD%BF%E7%94%A8Cloudflare%20Workers%E4%BC%98%E5%8C%96Github%E6%96%87%E4%BB%B6%E5%9B%BD%E5%86%85%E8%AE%BF%E9%97%AE)
## 通过 [OhMyLive2D](https://oml2d.com/) 使用

```javascript
import { loadOml2d } from 'oh-my-live2d';

// 获取模型列表对象
let models = await (await fetch('https://model.kisssssssss.space/https://raw.githubusercontent.com/kisssssssss/model/main/live2d.All.json')).json();

// 将模型列表对象转成数组
models = Object.keys(models).map((key) => models[key].map((item) => item.configuration)).flat(1);

// 加载 live2d
loadOml2d({models})
```

如果你不需要全部模型，可以选择性导入提供的模型  json 文件。例如：

```javascript
// 只获取碧蓝航线模型
let models = await (await fetch('https://model.kisssssssss.space/https://raw.githubusercontent.com/kisssssssss/model/main/live2d.Azur.json')).json();

// 只获取崩坏学园2模型
let models = await (await fetch('https://model.kisssssssss.space/https://raw.githubusercontent.com/kisssssssss/model/main/live2d.BengHuai2.json')).json();

// 只获取少女前线模型
let models = await (await fetch('https://model.kisssssssss.space/https://raw.githubusercontent.com/kisssssssss/model/main/live2d.GirlsFrontline.json')).json();

// 其它模型请求同理
// https://model.kisssssssss.space/https://raw.githubusercontent.com/kisssssssss/model/main/ + 模型 json 文件
```
## 直接使用

查看 [live2d.All.json](https://github.com/kisssssssss/model/blob/main/live2d.All.json) 具体内容，从中选取你所需要的模型信息。

# 下载

该仓库大小是 ~~1.45G (2024.5.9)~~ 2.03G (2024.6.14)，因此不建议全部下载。如确实需要某个模型文件，可以使用浏览器插件 [GitZip For Github (Google)](https://chromewebstore.google.com/detail/gitzip-for-github/ffabmkklhbepgcgfonabamgnfafbdlkn) [GitZip For Github (Edge)](https://microsoftedge.microsoft.com/addons/detail/gitzip-for-github/nlgkiabjnbdndgblhcaobimbpifcdkjj) 选择你所需要的模型文件进行下载。


