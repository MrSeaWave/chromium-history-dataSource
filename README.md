# chromium-history-dataSource

chromium 的历史版本数据 json

Example:

- Version: 91.0.4462.4
- Position: 867092
- OS: Mac
- Link: https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Mac/867092/

## 文件描述

- `all-version.json`: 从 https://chromium.googlesource.com/chromium/src/+refs 获取的所有版本
- `version-position.json`: 从 `all-version.json` 和类似这种 https://omahaproxy.appspot.com/deps.json?version=87.0.4253.0 链接获取到 version 对应的 position
- `position/position-Mac.json`: position 按照 os 分类，[链接](<https://www.googleapis.com/storage/v1/b/chromium-browser-snapshots/o?delimiter=/&prefix=Mac/&fields=items(kind,mediaLink,metadata,name,size,updated),kind,prefixes,nextPageToken>)
- `ver-pos-os/version-position-Mac.json`: 根据`version-position.json`与`position/position-Mac.json`生成
- `ver-pos-os-link/version-position-link-Mac.json`: 和`ver-pos-os/version-position-Mac.json`类似，只是带有这种地址信息 https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Mac/867092/

## 缺少某些版本？

某些版本可能缺少，因为没有从 API 返回任何数据：

- 数据正常：https://omahaproxy.appspot.com/deps.json?version=87.0.4253.0
- 没有数据：https://omahaproxy.appspot.com/deps.json?version=33.0.1733.0
