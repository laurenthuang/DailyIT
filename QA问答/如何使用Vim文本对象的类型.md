# Q: Vim文本对象的类型有哪些？

---
tags:
  - vim
  - text-object
---
## 按文本对象执行命令

在Vim中，相比针对单个字符进行操作，对于单词、句子和段落等更大范围的文本对象（**text-objects** ）执行命令则更有效率。Vim的命令结构示例如下：

`[number]<command>[text object or motion]`

其中：**number**是指命令作用在几个文本对象之上。比如3个单词；**command**是指执行的具体命令。比如删除或复制；**text object or motion**是指具体的文本对象。比如单词、句子或段落。

### 文本对象的类型

- `iw` …inner word
- `aw` …a word
- `iW` …inner WORD
- `aW` …a WORD
- `is` …inner sentence
- `as` …a sentence
- `ip` …inner paragraph
- `ap` …a paragraph
- `it` …inner tag
- `at` …a tag
- `i(` or `i)` …inner block …everything between ( and ) excluding the parentheses
- `a(` or `a)` …a block …everything between ( and ) including the parenthesis
- `i<` or `i>` …inner block …everything between < and > excluding the brackets
- `a<` or `a>` …a block …everything between < and > including the brackets
- `i{` or `i}` …inner block …everything between { and } excluding the brackets
- `a{` or `a}` …a block …everything between { and } including the brackets
- `i[` or `i]` …inner block …everything between \[ and \] excluding the square brackets
- `a[` or `a]` …a block …everything between \[ and \] including the square brackets
- `i"` …inner block
- `a"` …a block
- ``i` `` …inner block
- ``a` `` …a block
