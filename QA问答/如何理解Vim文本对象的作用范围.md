# Q: Vim文本对象的作用范围是什么？

---
tags:
  - vim
  - text-object
  - scope
---
### 文本对象的作用范围

`iw`表示**inner word**。如果键入`viw`命令，那么首先`v`将进入选择模式，然后`iw`将选中当前单词。

`aw`表示**a word**，它不但会选中当前单词，还会包含当前单词之后的空格。

以下实例中的 \[ \] 表示作用范围：

|              |                                                                                                         |
| ------------ | ------------------------------------------------------------------------------------------------------- |
| `iw`         | This is a [test] sentence.                                                                              |
| `aw`         | This is a [test ]sentence.                                                                              |
| `iW`         | This is a […test…] sentence.                                                                            |
| `aW`         | This is a […test… ]sentence.                                                                            |
| `is`         | …sentence. [This is a sentence.] This…                                                                  |
| `as`         | …sentence. [This is a sentence. ]This…                                                                  |
| `ip`         | End of previous paragraph.  <br>  <br>[This is a paragraph. It has two sentences.]  <br>  <br>The next. |
| `ap`         | End of previous paragraph.  <br>  <br>[This is a paragraph. It has two sentences.  <br>  <br>]The next. |
| `i(` or `i)` | 1 * ([2 + 3])                                                                                           |
| `a(` or `a)` | 1 * [(2 + 3)]                                                                                           |
| `i<` or `i>` | The <[tag]>                                                                                             |
| `a<` or `a>` | The \[\<tag\>\]                                                                                         |
| `i{` or `i}` | some {[ code block ]}                                                                                   |
| `a{` or `a}` | some [{ code block }]                                                                                   |
| `i[` or `i]` | some \[\[ code block \]\]                                                                               |
| `a[` or `a]` | some \[\[ code block \]\]                                                                               |
| `i"`         | The "[best]"                                                                                            |
| `a"`         | The[ “best”]                                                                                            |
| `` i` ``     | The `[best]`                                                                                            |
| `` a` ``     | The[ `best`]                                                                                            |
