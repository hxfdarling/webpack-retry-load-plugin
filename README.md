# webpack-retry-load-plugin

如果你的站点使用的 CDN，该插件会绑定自动从你配置的其它域名 (例如主域) 重新下载哪些失败的资源。
插件必须配合 html-webpack-plugin 和 mini-css-extract-plugin。

支持同步 JS/CSS 自动重试，也支持异步 JS/CSS 自动重试(通过 webpack import 的 chunk)

并且你可以配置监控，支持上报成功和失败的量。

## Usage

install

```shell
npm i -D webpack-retry-load-plugin
```

webpack config

```js
const RetryPlugin = require('webpack-retry-load-plugin');
{
  output:{
    publicPath:"//cdn.com/pc/",// you cdn path
  },
  plugins: [
    new RetryPlugin({
      retryPublicPath: '//example.com/pc/',// you doamin path
    }),
  ]
}
```
