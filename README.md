# refusalmap

**把拒答按实际原因归类，区分能力不足与合规拒绝。**

`refusalmap` —— 分析拒答语句，区分是真做不了、是不该做、还是格式没对上

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`refusalmap.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install erinyfito-refusalmap
```

装完直接用命令名调用：

```bash
refusalmap --help
```

也可以不用安装，直接把 `refusalmap.py` 拷走用——它只依赖标准库。

## 为什么需要它

把「拒答」拆成可区分的原因类别，让拒答率这个指标变得有意义

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 拒答模式识别 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python refusalmap.py --file input.txt
python refusalmap.py --text "示例内容"
python refusalmap.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 分组靠标签与关键词相似度，分错组时不保证可解释。
- 不评估分组质量。

## 跑测试

```bash
python test_refusalmap.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/erinyfito/refusalmap>

---

## 关于作者

erinyfito 做拒答模式识别相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://erinyfito.github.io>
- 仓库：<https://github.com/erinyfito/refusalmap>

## 许可

MIT，见 [LICENSE](LICENSE)。
