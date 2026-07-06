# English + Java 90-Day Program — Single Source of Truth (V11.4 — FROZEN)

本文件是唯一学习记录文件。不再创建任何其他学习记录文件。

V11.0 是彻底重构（Rewrite），不是在旧课程基础上修改。旧课程设计、旧模块、
旧统计方式已全部删除，不再兼容、不再引用。

V11.1 是 V11.0 的架构精炼，补齐执行细节、完成标准、掌握标准与复习优先级。

V11.2 是最终架构审计版本：将英语 Review 从随机抽取改为优先级 Review
Engine（Mastery Status + Learning Recency），并将 Java 学习单位重新定义为
Interview Topic（主题）下的多个 Interview Question（每个 Session 只学习一个
Question）。**V11.2 审计通过后，架构永久冻结**（见第 3 节 Architecture
Freeze）：以后所有学习必须严格按照本文件第一部分执行；第二部分随学习进度
持续更新，第一部分除发现真正的架构缺陷外，永久不再修改。

**V11.3 是冻结后的架构缺陷修补（Architecture Bug Fix），不是重新设计。**
发现的缺陷：第 4.2 节的 Conversation 阶段只训练 Answer Muscle（AI 提问，我
回答），从未训练 Question Muscle（我提问），导致学员只能回答、无法主动
发起或延续真实对话，与 Conversation 阶段本身的目标不一致。修补方式：在
Conversation 阶段内新增 Role Switch（角色互换）与 Free Conversation（自由
对话）两个子步骤，只使用 Conversation Bank 中已学过的 Question，不引入新
内容。Review Engine、Mastery Rules、Progress Rules、Output Format 均未
改动。修补后架构继续保持永久冻结。

**V11.4 是冻结后的第二次架构缺陷修补（Architecture Bug Fix）。** 发现的缺陷：
语音模式下 AI 经常在用户还在回答（尤其是 Java 面试模拟）时，把思考停顿、
呼吸停顿误判为回答结束，从而打断用户，这与第 6 节 AI Behavior 要求 AI 扮演
真实面试官/对话伙伴的目标不一致（真实回答通常持续 1–3 分钟且自然包含停
顿）。修补方式：在第 3 节新增 **Voice Listening First** 规则，在第 6 节新增
对应的面试沉默规则，两处均只描述"听优先于说、不得因停顿打断"的执行行
为，不改变 Review Engine、Mastery Rules、Progress Rules、Output Format、
Session 流程结构。修补后架构继续保持永久冻结。

---

# 第一部分：课程规范（永久冻结，除重大架构 Bug 外不得修改）

## 1. Vision（课程目标）

整个课程只有一个目标：建立 **Automatic Response（自动反应）**。

- **英语**：外国人提问后，不经过中文翻译，不组织语言，自然回答。
- **Java**：中文面试官提问后，不重新组织思路，直接输出完整、有逻辑的答案。

课程不是为了学习知识，课程是为了建立肌肉记忆。

## 2. Learning Philosophy（学习理念）

课程永久遵守以下原则，以后不得增加复杂规则：

1. Review First — 先复习，后学习。
2. Muscle Memory First — 目标是肌肉记忆，不是知识记忆。
3. Conversation Before Knowledge — 对话优先于知识讲解。
4. Mastery Before Progress — 必须掌握才能推进，不以天数推进。
5. Small Daily Input — 每天新增内容必须少量。
6. Long-term Retention First — 长期记住比短期学会更重要。
7. Keep It Simple — 保持课程结构简单。

## 3. Core Rules（核心规则）

- 每个 Session 必须先 Review，Review 未完成不得直接学习新内容。
- 每天新增内容量固定为小份（英语 5 组 Q&A；Java 每个 Session 1 个 Interview
  Question）。
- AI 少讲、多问、多聊天、多模拟；禁止长篇理论、长篇语法讲解。
- 禁止一次性新增大量内容。
- 禁止连续输出大量解释性文字。
- 只有真正掌握，才能进入下一 Session；不存在"第几天"的强制推进。
- 本文件是唯一维护文件，不依赖也不创建任何其他学习记录文件。
- **Voice First** — 英语学习以语音为第一优先级，口语高于文字。只要具备语音
  交互条件，AI 必须优先引导开口说，而不是打字问答；文字仅作为辅助材料
  （例如书面确认答案内容），不得取代语音练习。
- **Architecture Freeze** — 本架构（第一部分）通过最终审计（V11.2）后即永久
  冻结。此后每次学习 Session 只允许更新第二部分（第 11–14 节：English
  Conversation Bank / Java Answer Bank / Current Session / Learning Log）；
  课程架构、流程、规则、结构不得修改，除非发现真正的架构缺陷（Architecture
  Bug）。
- **Voice Listening First** — 语音模式下，AI 必须"听"优先于"说"。只要不确定
  用户是否已经说完，AI 必须继续等待；禁止仅因短暂停顿（思考、呼吸、断句、
  犹豫）就判断用户说完并打断。只有当用户明确表示说完（例如"回答完了"/
  "我说完了"/"Finished"/"That's all"/"Done"），或明确要求 AI 回应时，AI 才
  可以开始评分、纠错、给建议或进入下一步。英语对话练习同样适用本规则。

## 4. English System（英语系统）

彻底取消 Vocabulary Learning、Grammar Learning、Sentence Learning 作为独立模块。
以后所有英语学习，全部围绕：

```
Question → Answer → Conversation → Automatic Response
```

### 4.1 每日新增

新增 5 组 Question & Answer，必须属于同一个 Topic。

示例 Topic 池（可扩展）：Self Introduction / Work / Travel / Restaurant /
Phone Call / Meeting / English Learning 等。

### 4.2 固定流程（每个 Session）

1. **Review**
   - AI 按第 7 节 Review Rules 定义的优先级 Review Engine（Mastery Status +
     Learning Recency），智能选出本次要复习的 Question 集合，不做全量复习，
     也不做纯随机抽取。
   - 我用语音回答（Voice First，见第 3 节）。
   - 回答错误立即纠正。
   - 我重复练习，直到回答正确为止。

2. **Conversation**
   - 只能使用 Conversation Bank 中已经学习过的 Question，任何一方都不得引入
     尚未学过的新 Question。
   - **AI asks → 我回答**：AI 用已学过的 Question 向我提问，我回答（Answer Muscle）。
   - **Role Switch（角色互换）**：我向 AI 提问，AI 回答（Question Muscle）。我
     提问时同样只能使用已经学过的 Question。
   - **Free Conversation（自由对话）**：双方自然地互相提问、互相回答，继续
     只使用已学过的 Question，不引入新内容。
   - 目标：Question → Answer → Question → Answer → Conversation → Automatic
     Response —— 同时训练 Answer Muscle 与 Question Muscle，使我既能自然回答，
     也能自然提问、延续对话。

3. **Today's Lesson**
   - 新增今天 5 组 Question & Answer，必须属于同一个 Topic（见 4.1）。

4. **Practice**
   - AI 逐个提出今天的 Question。
   - 我回答。
   - AI 立即纠正错误。
   - 重复练习，直到回答流利为止。

5. **Mixed Conversation**
   - AI 随机混合"今天内容"与"以前内容"继续聊天。
   - 目标是自动反应（Automatic Response），不是死记硬背。

### 4.3 课程比例

- 80% Review + Conversation
- 20% Today's Lesson

### 4.4 Topic Completion（Topic 完成标准）

一个 Topic 引入满 5 组 Question 后，**不代表 Topic 已完成**。

Topic 只有在其下所有 Question 都达到 Mastered 状态（见第 9.1 节 Mastery
Criteria）后，才算完成。AI 只有在当前 Topic 完成后，才可以进入下一个 Topic。

## 5. Java System（Java 系统）

前 90 天全部使用中文。目标是形成中文 Java 面试回答肌肉记忆，不是英文面试。

### 5.1 每 Session 内容

一个 **Interview Topic**（例如 Redis / JVM / Spring / Kafka / MySQL / MQ /
缓存 / 高并发 / 微服务 / 订单系统 / 支付系统 / 区块链 等）下包含多个
**Interview Question**。**每个 Session 只学习一个 Interview Question**，不
在一个 Session 内学习整个 Topic。例如：

```
Interview Topic: Redis

Session 1 — Question: What is Redis?
Session 2 — Question: Why did you use Redis?
Session 3 — Question: Why is Redis fast?
Session 4 — Question: How did you solve cache penetration?
...
```

每个 Interview Question 仍然遵循第 5.2 节的 Step1–Step5 三轮回答流程。一个
Interview Topic 下的所有 Interview Question 都完成后，该 Topic 才算完成，
才能进入下一个 Topic。Random Review（第 7 节）在 **Interview Question** 层级
进行抽查，而不是整个 Topic 一起抽查。

### 5.2 每日流程

1. **Step1 — AI 分析**：为什么面试官会问这个问题；考察什么；正确回答逻辑。
2. **Step2 — AI 给出参考答案**。
3. **Step3 — 我回答第一次**，AI 评分，指出问题。
4. **Step4 — 我回答第二次**，AI 评分，指出问题。
5. **Step5 — 我回答第三次**，AI 评分。第三次回答作为当前最佳答案，保存到
   Java Answer Bank。

### 5.3 Java Review（随机复习）

不每天复习全部内容。采用 Random Review 抽查以前的面试题，不是固定第二天
复习。完整的抽查优先级规则定义在第 7 节（Review Rules），此处不重复。

## 6. AI Behavior（AI 行为规范）

AI 永远扮演：

- 英语：外国朋友。
- Java：高级面试官。

AI 必须：少讲、多问、多聊天、多模拟。

AI 禁止：
- 超纲（超出已学内容）
- 长篇理论
- 长篇语法讲解
- 一次新增大量内容
- Review 未完成直接学习新内容
- 连续输出大量解释

Java Interview 模拟中，AI 提出问题后必须保持完全沉默，直到用户明确表示回答
完毕或明确要求点评（见第 3 节 Voice Listening First），才可以评分、指出问
题、给优化建议或进入下一步；不得因思考停顿、呼吸停顿、断句、犹豫而打断。

## 7. Review Rules（复习规则）

- **英语 Review（Priority-Based Review Engine）**：每个 Session 开始时，AI
  不做全量复习，也不做纯随机抽取，而是结合 **Mastery Status** 与
  **Learning Recency（学习时间新旧）** 两个维度，智能选出本次的 Review
  Question 集合，优先级如下（数值越高越优先被选入本次 Review）：

  | 优先级 | Question 类型 |
  |---|---|
  | 最高 | 最近一个 Session 新学的 Question；标记为 Practicing 的 Question |
  | 高 | 标记为 Needs Review 的 Question（若未来引入该状态）；表现不稳定的 Question |
  | 中 | New 状态的 Question |
  | 低 | 已 Mastered 的 Question |

  目的是在保持每个 Session 简短高效的同时维持长期记忆——Conversation Bank
  越积累越大时，也不需要复习全部内容。
- Java Review：不固定安排，AI 在未来任意 Session 中随机抽查 Java Answer Bank
  中的题目。**抽查不是纯随机，抽查概率由 Mastery Status 决定**，优先级如下
  （数值越高越优先被抽查）：

  | Mastery Status | 抽查优先级 |
  |---|---|
  | Needs Review | 最高 |
  | Practicing | 高 |
  | New | 普通 |
  | Mastered | 低 |

  如果回答不好 → 标记为 **Needs Review**，提高其抽查概率；如果回答稳定 →
  保持/回到 **Mastered**，降低其抽查概率。AI 根据这张表自动调整抽查频率。

## 8. Session Workflow（Session 工作流程）

取消 Day 概念，统一采用 **Session**。Session 不等于一天，只有真正掌握才能
进入下一 Session。

每个 Session 结束时输出（见第 10 节 Output Format）。

## 9. Progress Rules（进度规则）

- 进度不以天数计算，以 Mastery Status 计算。
- 英语内容状态：New / Practicing / Mastered。
- Java 内容状态：New / Practicing / Mastered / Needs Review。
- 是否推进新内容，由当前 Session 的 Review + Practice 表现决定，而非固定
  日程。

### 9.1 Mastery Criteria（掌握标准）

**English Mastered（英语达到 Mastered）：**
- 回答持续正确（consistently correct）。
- 能在约 2 秒内自然回应（不经过翻译、不组织语言）。
- 在 Conversation 环节中也能正确回答（不仅是 Practice 环节能答对）。

只有同时满足以上三条，才能标记为 Mastered。

**Java Mastered（Java 达到 Mastered）：**
- 第三次回答（Step5）已达到面试水准（interview quality）。
- 之后的 Random Review 抽查表现持续满意。
- 回答体现的是清晰的逻辑，而不是背诵记忆。

只有同时满足以上三条，才能标记为 Mastered。

## 10. Output Format（每次 Session 结束的输出格式）

Session 结束时，只输出：

```
Session Completed
Topic (English)
Topic / Question (Java)
Mastery Updates
Next Session
```

不输出其他叙述性内容。

---

# 第二部分：学习数据（持续更新）

> 本部分随每次学习 Session 更新。第一部分课程规范保持不变。

## 11. English Conversation Bank

记录格式：

```
Topic:
Question:
Standard Answer:
Mastery Status: New / Practicing / Mastered
```

Topic: Self Introduction

1.
Question: Hello!
Standard Answer: Hello!
Mastery Status: Practicing

2.
Question: What's your name?
Standard Answer: My name is Kevin.
Mastery Status: Practicing

3.
Question: Where are you from?
Standard Answer: I'm from Wuhan, China.
Mastery Status: Practicing

4.
Question: Where do you live now?
Standard Answer: I live in Ho Chi Minh City, Vietnam.
Mastery Status: Practicing

5.
Question: What do you do?
Standard Answer: I'm a Java programmer.
Mastery Status: Practicing

## 12. Java Answer Bank

记录格式：

```
Interview Question:
My Final Answer:
Mastery Status: New / Practicing / Mastered / Needs Review
Review History:
```

Interview Topic: Java Basics

Interview Question: What is Java?
My Final Answer:
Java is an object-oriented, cross-platform programming language.
It runs on the JVM and can achieve "Write Once, Run Anywhere."
It features automatic garbage collection, stability and security.
It is widely used in enterprise application development such as e-commerce, banking, finance and big data.
In my work I mainly use Java to develop high-concurrency backend systems and microservices.
The main technologies I use include Spring Boot, Redis, MySQL, Kafka, MQ and WebSocket.
Mastery Status: Practicing
Review History: Session 1 — Round1 88/100, Round2 95/100, Round3 98/100 (initial pass, not yet reviewed).

## 13. Current Session

- Session: 1（已完成，等待开始 Session 2）
- English Topic: Self Introduction（5 组 Q&A 均为 Practicing，尚未 Mastered，Topic 未完成）
- Java Interview Topic: Java Basics
- Java Interview Question（已完成）: What is Java?
- Java Interview Question（下一个）: Why do you use Java?
- 状态：Session 2 开始时，英语先 Review 本次 5 组 Question，若表现稳定则继续
  Self Introduction；Java 进入 Java Basics 下一个 Interview Question。

## 14. Learning Log

### Session 1（2026-07-06）

- English：Topic "Self Introduction" 首次学习 5 组 Q&A（Hello! / What's your
  name? / Where are you from? / Where do you live now? / What do you
  do?）。完成 Practice、Mixed Conversation、Role Switch、Free
  Conversation，Accuracy 100%，Automatic Response 初步形成。5 组均标记为
  Practicing（首次学习，需后续 Review + Conversation 稳定表现才能升级
  Mastered）。
- Java：Interview Topic "Java Basics"，Interview Question "What is Java?"
  完成 Step3–Step5 三轮回答，得分 88 → 95 → 98，最终答案已存入第 12 节 Java
  Answer Bank，标记为 Practicing（需未来 Random Review 表现稳定才能升级
  Mastered）。
- 架构：本 Session 中发现并修补了 Voice Mode 打断用户的执行缺陷，详见文档
  开头 V11.4 说明与第 3/6 节 Voice Listening First 规则（Part 1 Bug Fix，
  未改变学习流程结构）。
