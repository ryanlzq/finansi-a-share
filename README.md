# A股技能入口

**A股技能入口**：当你说“帮我看看这只股票”“最近该怎么操作”“给我做个分析”但没说清要用哪个工具时，这个入口先判断意图，再分派给取数、回测、网格、验证、组合或复盘技能。

它只做分派和追问，不直接给结论。

## 安装

```bash
git clone https://github.com/ryanlzq/finansi-a-share.git
```

放到 Agent 的 skills 目录：

```text
Claude Code   ~/.claude/skills/finansi-a-share/
Codex         ~/.codex/skills/finansi-a-share/
Cursor        ~/.cursor/skills/finansi-a-share/
通用           ~/.agents/skills/finansi-a-share/
```

不需要额外依赖。

## 分派表

| 用户想做什么 | 交给 |
|---|---|
| 拉行情、查 ST/停牌、查涨跌停价、检查数据 | A股行情数据 |
| 均线、RSI、布林带、突破、参数回测 | A股回测 |
| 网格、档位、低买高卖、震荡套利 | A股网格 |
| 样本外、滚动验证、过拟合判断 | A股样本外验证 |
| 组合、相关性、权重、风险平价 | A股组合 |
| 交割单、胜率、盈亏比、行为复盘 | A股交易复盘 |

## 使用方式

```text
帮我看看宁德时代最近怎么样。
```

入口会先判断：是需要近期行情和风险，还是需要策略回测；缺代码、区间或策略时先追问，再分派。

## 设计原则

- 不替用户做投资决策
- 不在入口层编造收益或结论
- 信息不足时先追问
- 只做路由，不重复实现下游技能

## License

MIT. See [LICENSE](LICENSE).
