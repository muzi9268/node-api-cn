<!-- YAML
added: v0.1.29
changes:
  - version: v14.0.0
    pr-url: https://github.com/nodejs/node/pull/31030
    description: 参数 `data` 不再强制转换不支持的输入为字符串。
  - version: v10.10.0
    pr-url: https://github.com/nodejs/node/pull/22150
    description: 参数 `data` 可以是任何的 `TypedArray` 或 `DataView`。
  - version: v7.4.0
    pr-url: https://github.com/nodejs/node/pull/10382
    description: 参数 `data` 可以是 `Uint8Array`。
  - version: v5.0.0
    pr-url: https://github.com/nodejs/node/pull/3163
    description: 参数 `file` 可以是文件描述符。
-->

* `file` {string|Buffer|URL|integer} 文件名或文件描述符。
* `data` {string|Buffer|TypedArray|DataView}
* `options` {Object|string}
  * `encoding` {string|null} **默认值:** `'utf8'`。
  * `mode` {integer} **默认值:** `0o666`。
  * `flag` {string} 参见[文件系统 `flag` 的支持][support of file system `flags`]。
    **默认值:** `'w'`。

返回 `undefined`。

详见此 API 的异步版本的文档：[`fs.writeFile()`]。

