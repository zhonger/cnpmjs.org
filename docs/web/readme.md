# 上海大学开源社区NPM镜像


## `npm.shuosc.org`: 基于`cnpmjs.org`构建的上大npm加速镜像

- 当前的镜像 [registry.npm.shuosc.org](https://registry.npm.shuosc.org)是从 [registry.npmjs.com](https://registry.npmjs.com)进行部分同步的.
- [npm.shuosc.org](/) version: <span id="app-version"></span>
- [Node.js](https://nodejs.org) version: <span id="node-version"></span>
- 对于教育网内的`npm`开发者, 请访问 [上海大学开源社区NPM镜像](https://npm.shuosc.org). 非教育网用户请访问[淘宝镜像站点](https://npm.taobao.org)。

<div class="ant-table">
<table class="downloads">
  <tbody>
    <tr>
      <td class="count" id="total-packages"></td><td>个模块</td>
      <td class="count" id="total-versions"></td><td>个模块版本</td>
      <td class="count" id="total-deletes"></td><td>次删除</td>
    </tr>
    <tr>
      <td class="count"></td><td> 次本日下载</td>
      <td class="count"></td><td> 次本周下载</td>
      <td class="count"></td><td> 次本月下载</td>
    </tr>
    <tr>
      <td class="count"></td><td> 次昨日下载</td>
      <td class="count"></td><td> 次上周下载</td>
      <td class="count"></td><td> 次上月下载</td>
    </tr>
  </tbody>
</table>
</div>

<div class="sync" style="display:none;">
  <h3>同步状态</h3>
  <p id="sync-model"></p>
  <p>上次同步完成时间： <span id="last-sync-time"></span>. </p>
  <div class="ant-alert ant-alert-info syncing">
    <span class="anticon ant-alert-icon anticon-info-circle"></span>
    <span class="ant-alert-description">同步工具正在后台运行. </span>
  </div>
  <div class="ant-table">
  <table class="sync-status">
    <tbody>
      <tr>
        <td>共 <span id="need-sync"></span> 个模块需要同步</td>
        <td class="syncing"><span id="left-sync"></span> 个模块正在等待同步</td>
        <td>已完成<span id="percent-sync"></span>%</td>
      </tr>
      <tr>
        <td><span id="success-sync"></span> 个模块已完成同步</td>
        <td><span id="fail-sync"></span> 个模块同步失败</td>
        <td>最近同步成功的模块是: <span id="last-success-name"></span></td>
      </tr>
    </tbody>
  </table>
  </div>
</div>

<script src="/js/readme.js"></script>

## Badges

Default style is `flat-square`.

### Version

Badge URL: `https://cnpmjs.org/badge/v/cnpmjs.org.svg` ![cnpmjs.org-version-badge](//cnpmjs.org/badge/v/cnpmjs.org.svg)

* `<0.1.0 & >=0.0.0`: ![red-badge](https://img.shields.io/badge/cnpm-0.0.1-red.svg?style=flat-square)
* `<1.0.0 & >=0.1.0`: ![red-badge](https://img.shields.io/badge/cnpm-0.1.0-green.svg?style=flat-square)
* `>=1.0.0`: ![red-badge](https://img.shields.io/badge/cnpm-1.0.0-blue.svg?style=flat-square)

### Downloads

Badge URL: `https://cnpmjs.org/badge/d/cnpmjs.org.svg` ![cnpmjs.org-download-badge](//cnpmjs.org/badge/d/cnpmjs.org.svg)

## 使用说明

你可以使用我们定制的 [cnpm](https://github.com/cnpm/cnpm)(gzip压缩支持)命令行工具代替默认的`npm`:

```bash
$ npm install -g cnpm --registry=https://registry.npm.shuosc.org
```

或者你直接通过`npm`参数`alias`一个新命令:

```bash
alias cnpm="npm --registry=https://registry.npm.shuosc.org \
--cache=$HOME/.npm/.cache/cnpm \
--disturl=https://npm.taobao.org/mirrors/node \
--userconfig=$HOME/.cnpmrc"

#Or alias it in .bashrc or .zshrc
$ echo '\n#alias for cnpm\nalias cnpm="npm --registry=https://registry.npm.shuosc.org \
  --cache=$HOME/.npm/.cache/cnpm \
  --disturl=https://npm.taobao.org/mirrors/node \
  --userconfig=$HOME/.cnpmrc"' >> ~/.zshrc && source ~/.zshrc
```

### 安装模块

从 [registry.npm.shuosc.org](//registry.npm.shuosc.org)安装所有模块. 当安装的时候发现安装的模块还没有同步过来, 上大开源社区NPM会自动在后台进行同步，并且会让你从官方NPM([registry.npmjs.org](https://registry.npmjs.org))进行安装.下次你再安装这个模块的时候，就会直接从淘宝NPM安装了.

```bash
$ cnpm install [name]
```

### 同步模块

直接通过`sync`命令马上同步一个模块，只有 `cnpm` 命令行才有此功能.

```bash
$ cnpm sync connect
```

当然，你可以直接通过web方式来同步: [sync/connect](/sync/connect)

```bash
$ open http://registry.npm.shuosc.org/sync/connect
```

### 其他命令

支持`npm`除`publish`之外的所有命令，如:

```bash
$ cnpm info connect
```
