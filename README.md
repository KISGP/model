> 该仓库模型文件来源位置：
>
> Live2d 模型：
>
> - [https://github.com/Eikanya/Live2d-model](https://github.com/Eikanya/Live2d-model)
>
> spine 模型：
>
> - [https://github.com/fatboytao/NikkeSpine](https://github.com/fatboytao/NikkeSpine)
> - [https://github.com/isHarryh/Ark-Models](https://github.com/isHarryh/Ark-Models)
> - [https://github.com/Eikanya/spine-models/tree/master](https://github.com/Eikanya/spine-models/tree/master)

# 文件介绍

- ### [ModelListUpdateTime_Live2d.json](https://github.com/kisssssssss/model/blob/main/ModelListUpdateTime_Live2d.json)：Live2d 模型更新时间

- ### [ModelTranslation.json](https://github.com/kisssssssss/model/blob/main/ModelTranslation.json)：Live2d 文件夹下每个文件夹对应的游戏名

- ### [ModelList_Live2d.json](https://github.com/kisssssssss/model/blob/main/ModelList_Live2d.json)：live2d 模型具体信息和配置，如在网页的位置及缩放比例等

---

# 使用

主要搭配 [OhMyLive2D](https://oml2d.com/) 进行使用

```javascript
import { loadOml2d } from 'oh-my-live2d';

// 获取模型列表
const ModelList = await (await fetch('https://cdn.jsdelivr.net/gh/kisssssssss/model/ModelList_Live2d.json')).json();

// 根据模型列表生成配置
let models = [];
for (const key in ModelList) {
  models.push(...list[key].map(item => {
    // 获取模型文件路径
    let path = 'https://cdn.jsdelivr.net/gh/kisssssssss/model/live2d';
    // 由于模型文件都是网上搜罗来的，文件命名格式不统一，因此通过这种方式得出json文件路径
    switch (key) {
      case 'Azur':
      case 'Sin':
        path += `/${key}/${item.name}/${item.name}.model3.json`;
        break;
      case 'BengHuai2':
      case 'VenusScramble':
        path += `/${key}/${item.name}/model.json`;
        break;
      case 'GirlsFrontline':
        path += `/${key}/${item.name}/${item.name.split('@')[1]}.model3.json`;
        break;
    }

    // OhMyLive2D 模型配置
    return {
      name: item.name,
      position: item.position.map(e => Number(e)),
      scale: Number(item.scale),
      stageStyle: item.stageStyle,
      path
    };
  }));
}

// 加载 live2d
loadOml2d({models})
```

# 模型要求

1. 能跟随鼠标转动视角 > 有好看的待机动作
2. 不能有过大的背景

