# chongding-helper
冲顶大会答题辅助脚本，参考自 [TopSup](https://github.com/Skyexu/TopSup)

仅限于 Android 平台

## 使用方式

- 安装脚本依赖
```
$ git clone --depth=1 https://github.com/ahonn/chongding-helper.git
$ cd chongding-helper 
$ yarn install # or npm install
```

- 添加配置文件
```
$ touch config.yml
```

内容如下：
```
question:
  x: 45 # 截图中问题区域左上角 x 坐标
  y: 240 # 截图中问题区域左上角 y 坐标
  width: 620 # 截图中问题区域宽度
  height: 140 # 截图中问题区域高度

ocr:
  app_id: "API ID"
  app_key: "API KEY"
  secret_key: "SECRET KEY"
```

**问题区域具体坐标与宽高可通过开启 `开发者选项` -> `显示点按操作反馈` 与 `指针位置`, 并手动测量获得。**

**API ID 与 API KEY 等，需要通过创建[百度 OCR](https://cloud.baidu.com/product/ocr/general) 应用获得**

- 连接 Android 设备
通过 USB 连接 Android 设备，需要开启 USB 调试

运行 `adb devices` 查看连接设备
```
$ adb devices

# List of devices attached
# 930968b57d93    device
```

- 运行脚本
```
$ node ./index.js
```

脚本运行后按任意键获取 Android 设备截图，通过百度 OCR 获取问题描述，并自动打开浏览器搜索问题（百度知道搜索）
