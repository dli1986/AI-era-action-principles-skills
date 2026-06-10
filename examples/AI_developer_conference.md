# Action Card: 追踪 AI 大厂开发者大会与产品发布会

## 1. Real Need

不错过 OpenAI、Google、Meta、Anthropic、Microsoft、Nvidia 等主要 AI 公司的**开发者大会、模型发布、API 更新**，建立一套低噪音的持续追踪系统。

---

## 2. Expert Resources

### 各公司官方 Event / Developer 页面
- **为什么专家先看这里**：一手来源，含注册链接、日程、keynote 录像
- **在哪里操作**：直接收藏以下页面并订阅提醒
- **提取什么**：下一场活动日期 + 注册 / 直播链接
- **新手常见错漏**：等媒体报道再去看，已错过直播和早鸟注册

| 公司 | 年度核心大会 | 通常时间 | 官方页 |
|------|-------------|---------|--------|
| Google | Google I/O | 5月 | io.google |
| Microsoft | Microsoft Build | 5月 | build.microsoft.com |
| NVIDIA | GTC | 3月 | nvidia.com/gtc |
| Meta | LlamaCon / Connect | 4–10月 | ai.meta.com/events |
| AWS | re:Invent | 11–12月 | reinvent.awsevents.com |
| Apple | WWDC | 6月 | developer.apple.com/wwdc |
| OpenAI | DevDay（不固定） | 不定 | openai.com/events |
| Anthropic | 无固定大会，看官方博客 | 不定 | anthropic.com/news |

---

### X（Twitter）官方账号列表
- **为什么专家先看这里**：大会公告、model drop、API 变更通常首发于此，比新闻快数小时
- **在哪里操作**：创建一个 **X List**，把以下账号全加进去
- **提取什么**：`#GoogleIO` `#MSBuild` `#GTC` `#OpenAIDevDay` 等 hashtag 的首发推文
- **新手常见错漏**：只关注科技媒体转发，而不直接订阅官方账号，延迟且有信息过滤

核心账号：`@OpenAI` `@GoogleDeepMind` `@AnthropicAI` `@MetaAI` `@MSFTResearch` `@NvidiaAI` `@HuggingFace` `@AWSCloud` `@AppleDeveloper`

---

### AI 开发者 Newsletter（邮件订阅）
- **为什么专家先看这里**：每周精选，过滤噪音，有编辑判断
- **在哪里操作**：订阅后进邮件，建一个专属文件夹
- **提取什么**：upcoming events 列表 + 上周重要发布摘要
- **新手常见错漏**：订阅了但不看；订阅太多导致疲劳退订

推荐：
- **TLDR AI**（tldr.tech/ai）—— 日报，简洁
- **The Batch**（deeplearning.ai）—— Andrew Ng 主编，周报
- **Ben's Bites**（bensbites.com）—— 产品发布聚焦
- **AI Breakfast**（aibreakfast.beehiiv.com）

---

### GitHub Watch + Release 订阅
- **为什么专家先看这里**：模型权重、SDK 更新、API breaking change 先在 GitHub 出现
- **在哪里操作**：Watch → `Releases only` 以下仓库
- **提取什么**：Release notes 里的 breaking changes 和新功能
- **新手常见错漏**：只看文档，不 watch 仓库，错过 pre-release 和 RC

关键仓库：`openai/openai-python` `anthropics/anthropic-sdk-python` `huggingface/transformers` `meta-llama/llama-models` `google/generative-ai-python`

---

### AI 活动聚合站
- **为什么专家先看这里**：跨公司日历视图，避免遗漏小型但重要的发布会
- **在哪里操作**：定期浏览，导出 .ics 到日历
- **提取什么**：未来 60 天的会议列表
- **新手常见错漏**：这类站点更新不稳定，需交叉验证官方

参考：`lu.ma/ai`（社区活动聚合）、`aiconferences.org`

---

## 3. Correct Path（专家操作顺序）

```
1. 建立 X List（10 分钟，一次性）
2. 订阅 2–3 个 Newsletter（5 分钟）
3. GitHub Watch 核心仓库（10 分钟）
4. 收藏各公司 Event 页面，写入日历（年度大会时间相对固定）
5. 每周 10 分钟：扫 Newsletter + X List
6. 大会前一周：看官方日程，注册直播或录像提醒
```

---

## 4. Avoid

| 错误路径 | 为什么低效 |
|---------|-----------|
| 只看 36Kr / TechCrunch | 延迟 1–2 天，信息有翻译过滤 |
| 依赖微信公众号 | 更新慢，选题带编辑偏见 |
| 订阅 10+ Newsletter | 信息过载，全部不看 |
| 只看 Hacker News | 技术讨论强，但活动预告弱 |
| 等 YouTube 录像再看 | 错过 API 首发窗口和 early access |

---

## 5. Gateway Minimal Action

**目标**：用 30 分钟建立一个实际运转的追踪系统，产生可验证的输出。

**步骤**：
1. 在 X 上创建新列表，命名 `AI-Events`，加入上面 9 个官方账号
2. 订阅 **TLDR AI** + **Ben's Bites**（两分钟完成）
3. 在 GitHub Watch `openai/openai-python` 和 `anthropics/anthropic-sdk-python`（Releases only）
4. 打开 `io.google`、`build.microsoft.com`、`nvidia.com/gtc`，把下一场活动日期加入个人日历
5. 在日历里建一个重复提醒：**每周一早上 10 分钟扫 Newsletter + X List**

**Evidence（成功标志）**：
- X List 已建并有推文流
- 收件箱出现第一封 TLDR AI
- 日历里有至少 2 个 AI 大会日期
- GitHub 已 Watch 2 个仓库

---

## 6. Save This

将以下内容保存为个人笔记或 `ai-events-tracker.md`：

```markdown
## AI 大厂活动追踪资源

### X List: AI-Events
账号: @OpenAI @GoogleDeepMind @AnthropicAI @MetaAI @MSFTResearch @NvidiaAI @HuggingFace @AWSCloud @AppleDeveloper

### Newsletter 订阅
- TLDR AI: tldr.tech/ai
- Ben's Bites: bensbites.com

### 年度大会日历
- Google I/O: 每年5月
- MS Build: 每年5月  
- NVIDIA GTC: 每年3月
- Meta LlamaCon: 每年4月左右
- WWDC: 每年6月
- AWS re:Invent: 每年11-12月
- OpenAI DevDay: 不定期

### GitHub Watch 仓库
- openai/openai-python
- anthropics/anthropic-sdk-python
- huggingface/transformers
- meta-llama/llama-models
```

---

## 7. Optional Retro Hooks

执行上述 Gateway Action 后，回答：

- 哪个 Newsletter 信噪比最高？哪个可以退订？
- X List 里哪个账号发的有效信息最多？
- 有没有错过过去 30 天内某个重要发布？是从哪个渠道发现的？
- 现有系统每周需要多少时间维护？是否可持续？