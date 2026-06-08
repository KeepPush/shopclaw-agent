# ShopClaw — 她的购物闺蜜

B站/小红书/抖音三平台智能比价Agent。用全网真实数据帮她花最少的钱买到最对的东西。

## 架构

```
w-default/
├── SOUL.md      # 六阶段购物协议+启动自检+已验证工具矩阵
├── USER.md      # 多用户画像（首次微信自动评估）
└── memory/
    ├── FACT.md  # 大促日历+品牌知识库+比价缓存
    └── JOURNAL.jsonl
```

## 依赖MCP

| MCP | 用途 |
|-----|------|
| china-mcp | B站视频详情/热榜 |
| xiaohongshu-mcp | 小红书搜索/笔记详情(Docker) |
| douyin-mcp | 抖音关键词搜索 |
| taobao-shop-price | 跨平台比价 |
| exa | 全网搜索 |
| agent-memory | 记忆存储 |
| MemAgent KG | 产品知识图谱 |

## 工作流

```
她说"想买XX" → 认出她 → 温柔追问 → 四路并行搜索 → 
KG存储 → 对比推荐 → 比价链接
```

## 安装

1. CherryStudio新建Agent → 粘贴系统提示词
2. 放入SOUL.md/USER.md/memory/FACT.md
3. 确保上述MCP全部连接
4. xiaohongshu-mcp需Docker: `docker run -d --name xhs-mcp -p 18060:18060 xpzouying/xiaohongshu-mcp`
