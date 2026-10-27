# jqrewrite

**把 JSON 查询语句按等价类归组并指出冗余写法。**

`jqrewrite` —— 识别功能等价的查询写法，归组并标出可简化的表达式

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`jqrewrite.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install jqg2code-jqrewrite
```

装完直接用命令名调用：

```bash
jqrewrite --help
```

也可以不用安装，直接把 `jqrewrite.py` 拷走用——它只依赖标准库。

## 为什么需要它

分组要基于语义等价而不是文本相似

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 JSON 查询语句改写 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python jqrewrite.py --file input.txt
python jqrewrite.py --text "示例内容"
python jqrewrite.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 分组靠标签与关键词相似度，分错组时不保证可解释。
- 不评估分组质量。

## 跑测试

```bash
python test_jqrewrite.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/jqg2code/jqrewrite>

---

## 关于作者

jqg2code 做JSON 查询语句改写相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://jqg2code.github.io>
- 仓库：<https://github.com/jqg2code/jqrewrite>

## 许可

MIT，见 [LICENSE](LICENSE)。
