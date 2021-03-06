<!-- YAML
added: v0.5.5
changes:
  - version: v10.0.0
    pr-url: https://github.com/nodejs/node/pull/18395
    description: Removed `noAssert` and no implicit coercion of the offset
                 to `uint32` anymore.
-->

* `value` {integer} 要写入 `buf` 的数值。
* `offset` {integer} 开始写入之前要跳过的字节数。必须满足：`0 <= offset <= buf.length - 4`。**默认值:** `0`。
* 返回: {integer} `offset` 加上已写入的字节数。

用指定的[字节序][endianness]（`writeInt32BE()` 写入为大端序，`writeInt32LE()` 写入为小端序）将 `value` 写入到 `buf` 中指定的 `offset` 位置。
`value` 必须是有符号的 32 位整数。
当 `value` 不是有符号的 32 位整数，行为是未定义的。

`value` 会被解析并写入为二进制补码的有符号整数。

```js
const buf = Buffer.allocUnsafe(8);

buf.writeInt32BE(0x01020304, 0);
buf.writeInt32LE(0x05060708, 4);

console.log(buf);
// 打印: <Buffer 01 02 03 04 08 07 06 05>
```

