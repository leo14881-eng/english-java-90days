# CURRENT_QUEUE.md — Runtime Export (Non-Authoritative)

本文件是自动生成的运行时导出（Runtime Export），**不是**课程的维护文件，
不属于 ENGLISH_JAVA_90DAYS_SOT.md 的一部分。每次生成时整体覆盖重写，
不追加历史，不被本课程自身的 AI 读取或依赖。仅供外部工具/独立对话使用。

唯一权威学习记录文件仍然是 `ENGLISH_JAVA_90DAYS_SOT.md`（第 13 节
Active Review Window）。本文件与其内容不一致时，以 SOT 为准。

**Regeneration cadence**：每当 ENGLISH_JAVA_90DAYS_SOT.md 在某次执行中被
修改，同一次执行必须以完全重新生成并整体覆盖本文件作为最后一步（不追加、
不保留旧内容）。此约定记录在维护者的会话记忆中，不属于 SOT 第一部分，
不受 Architecture Freeze 约束。

Generated: 2026-07-09（基于 SOT V11.17，Session 7 完成后状态，Food Topic
全部 5 组 Standard Answer 已补全）

---

## 1. English Active Review Window

- Topic: Self Introduction
- Topic: English Learning
- Topic: Daily Routine
- Topic: Family
- Topic: Food

（当前已学 Topic 数为 5，≤ 5，全部纳入窗口）

---

## 2. English Active Question Bank

### Topic: Self Introduction
1. Q: Hello! — A: Hello!
2. Q: What's your name? — A: My name is Kevin.
3. Q: Where are you from? — A: I'm from Wuhan, China.
4. Q: Where do you live now? — A: I live in Ho Chi Minh City, Vietnam.
5. Q: What do you do? — A: I'm a Java programmer.

### Topic: English Learning
1. Q: Why are you learning English? — A: I'm learning English because I want to work for an international company.
2. Q: Do you like learning English? — A: （标准答案未逐字记录，练习时以学员当场表达为准）
3. Q: How do you learn English? — A: I learn English by speaking with ChatGPT every day.
4. Q: How long do you study English every day? — A: I study English for about six hours every day.
5. Q: What is your English goal? — A: My goal is to speak English fluently.

### Topic: Daily Routine
1. Q: What time do you usually get up? — A: I usually get up at seven o'clock.
2. Q: What time do you usually go to bed? — A: I usually go to bed at eleven o'clock.
3. Q: What do you usually do after work? — A: I usually study English after work.
4. Q: What do you usually do before you go to bed? — A: I usually read a book before I go to bed.
5. Q: What do you usually do on weekends? — A: I usually study English on weekends.

### Topic: Family
1. Q: Do you have a family? — A: Yes, I do. I have a happy family.
2. Q: How many people are there in your family? — A: There are three people in my family.
3. Q: Who do you live with? — A: I live with my wife.
4. Q: What does your wife do? — A: She is a teacher.
5. Q: Do you often spend time with your family? — A: Yes, I do. I often spend time with my family.

### Topic: Food
1. Q: What is your favorite food? — A: My favorite food is hot pot.
2. Q: What food do you eat most often? — A: I eat rice most often.
3. Q: Can you cook? — A: Yes, I can. I can cook simple meals.
4. Q: What do you usually drink? — A: I usually drink water.
5. Q: Do you like spicy food? — A: I like spicy food very much.

---

## 3. Java Active Review Window

- Interview Topic: Java Basics（已完成，永久保留在 Random Review 池，见
  Scenario Interview Mode）
  - Interview Question: What is Java?
  - Interview Question: Why do you use Java?
- Interview Topic: Production Incident Scenarios
  - Scenario 1: 线上接口 RT 从 50ms 飙升到 3 秒，作为值班负责人你会如何处理？
  - Scenario 2: 线上 CPU 突然达到 100%，你会如何处理？

（当前已学 Question/Scenario 数为 4，≤ 5，全部纳入窗口）

---

## 4. Java Canonical Answers

### Interview Question: What is Java?
Java 是一门面向对象、跨平台的编程语言。
它运行在 JVM 之上，能够实现"一次编写，到处运行"（Write Once, Run Anywhere）。
它具备自动垃圾回收、稳定性和安全性等特性。
它被广泛应用于电商、银行、金融、大数据等企业级应用开发场景。
在我的工作中，我主要使用 Java 开发高并发后端系统与微服务。
我主要使用的技术栈包括 Spring Boot、Redis、MySQL、Kafka、MQ 和 WebSocket。
（Mastery Status: Practicing — 已完成 2 次锁定后 Random Review）

### Interview Question: Why do you use Java?
1. 结论
Java 成熟、稳定，拥有完善的生态系统，非常适合企业级后端系统开发。

2. 技术优势
面向对象；跨平台；运行在 JVM 之上，实现"一次编写，到处运行"；自动垃圾回收；
生态成熟（Spring Boot、Spring Cloud）；在高并发系统与微服务架构中性能表现
出色。

3. 个人经验
长期从事 Java 后端开发，有搭建后端系统的经验，参与过高并发系统与微服务架构
项目。常用技术栈：Spring Boot、Spring Cloud、MySQL、Redis、Kafka、MQ、
WebSocket。

4. 总结
Java 成熟、稳定、生态完善，非常适合企业级后端系统开发，是构建微服务架构与
高并发系统的重要技术选型。
（Mastery Status: Practicing — 已完成 2 次锁定后 Random Review；注意：此答案
沿用旧的编号列表格式，为 V11.16 之前锁定的历史条目，不追溯改写，新规则
[Canonical Answer Style Rule] 仅对未来内容生效）

### Scenario 1: 线上接口 RT 从 50ms 飙升到 3 秒，作为值班负责人你会如何处理？

**Interviewer Intent**：考察线上故障处理能力、处理优先级、线上经验以及
Senior / Tech Lead 的决策思维。

**Canonical Thinking（内部思维框架，面试作答时不得直接说出）**：
Impact Assessment → Business Recovery → Root Cause Analysis →
Recovery Validation → RCA / Long-term Prevention

**Canonical Answer**：
如果线上接口 RT 突然从 50ms 飙升到 3 秒，我首先会确认问题影响范围，看是
单个接口、单个服务还是整个系统，同时确认哪些核心业务受到了影响。

确认影响范围以后，我会优先恢复业务。如果是新版本导致的问题，我会优先
回滚；如果系统压力过大，我会根据情况做限流、降级、熔断或者扩容，先让
业务恢复正常。

业务恢复以后，我会结合监控、日志和链路追踪继续定位原因，看问题是在
JVM、数据库、Redis、MQ，还是第三方接口，尽快找到真正的故障点。

最后，我会持续观察系统是否已经恢复正常，并组织团队做一次 RCA，把根因
分析清楚，同时完善监控和告警，避免同样的问题再次发生。
（Mastery Status: Practicing — 三轮流程刚完成，尚未经过后续 Session 的
Random Review）

### Scenario 2: 线上 CPU 突然达到 100%，你会如何处理？

**Interviewer Intent**：本题考察的不是 CPU 本身的知识，而是考察候选人是否
具备真实的生产故障处理经验、是否遵循正确的故障处理顺序、是否优先保证业务
恢复而不是先做根因分析、能否系统性定位根因、是否具备 RCA 与长期改进意识——
一句话概括：本题考察生产故障处理能力，而不是 CPU 知识本身。

**Canonical Thinking（内部思维框架，面试作答时不得直接说出）**：
Confirm impact → Recover business → Locate root cause → Verify recovery
→ RCA

**Canonical Answer**：
如果线上 CPU 突然达到100%，我会先看影响范围，确认是不是已经影响核心业务。

如果业务已经受影响，我会先恢复服务，比如扩容、限流、降级或者切流量，先
保证业务恢复正常。

然后我再定位原因，一般会结合监控、日志和链路追踪，重点看看是不是 GC、
线程、数据库、Redis、MQ，或者代码本身的问题。

找到根因以后，我会修复问题，然后持续观察系统运行情况，确认业务已经恢复
正常。

最后我会组织团队做一次 RCA，把根因分析清楚，同时完善监控、告警和预案，
避免同样的问题再次发生。
（Mastery Status: Practicing — 三轮流程刚完成，尚未经过后续 Session 的
Random Review）

---

## 5. Session Rules（供外部工具执行时参考的关键约束摘要）

- **Curriculum Boundary / Session Context Grounding**：AI 只能从上方
  Active Review Window 中的 Question/Interview Question/Scenario 提问或
  练习，禁止改写、扩写、临场编造相似或"顺理成章"的新问题；只有明确进入
  "学新内容"环节才允许引入新问题。
- **Continuous Flow**：完成一次简短反馈后立即自动提出下一题，不等待
  "继续"之类的确认；除非学员明确要求暂停/结束/讲解/提问。
- **Correct Fast-Path**：完全正确时只做简短确认（如 "Correct.
  100/100."）并立即下一题，禁止长篇夸奖。
- **Accurate Feedback**：存在任何语法/用词/表达/技术错误时，禁止说
  "Perfect"/"Great"等虚假肯定评价，必须按语法→用词→表达→技术→正确版本
  的顺序纠正。
- **No Assumption Feedback**：必须依据学员实际说出的内容评判，不得默默
  替换成期望答案后当作正确处理。
- **Voice Listening First**：学员说话过程中（含停顿、思考、语塞）不得
  打断，只有学员明确表示说完才可评价。
- **English Question Mode**：默认使用中文提示（Chinese Prompt Method），
  由学员自己说出英文 Question 与 Answer；该 Topic 完成 Immediate
  Reinforcement 后可切换为纯英文提问/回答，不再使用中文提示。
- **Java Language Rule**：Java Interview 全程使用中文，专有技术名词（JVM/
  Spring Boot/Redis 等）保留英文；Canonical Answer 逻辑结构永久锁定，不得
  重写，除非学员明确要求修订。
- **Canonical Answer Style Rule**（V11.16）：Canonical Answer 必须口语化、
  自然，禁止"First/Second/Third"式编号罗列，约一分钟，体现真实 Senior
  生产经验，"自然地思考，而不是自然地背诵"。
- **Canonical Thinking Rule**（V11.16）：每个 Java Question 分两层——
  Layer 1 Canonical Answer（实际说出）与 Layer 2 Canonical Thinking（内部
  思维框架）；Layer 2 永远不得在作答中直接说出或列举。
- **Scenario Interview Mode**（V11.16）：Java Basics 两个基础问题锁定后，
  此后所有新 Interview Question 默认使用场景型（Scenario）框架，每
  Session 仍只新增一个。
- **Course Improvement Validation（非正式规则，仅供参考）**：一种更口语化
  （约 60–90 秒）的 Canonical Answer 表达风格候选，以及一个新教学模板候选
  （Interviewer Intent → Thinking Process → Canonical Answer → Review），
  目前已在 RT Spike、CPU 两个场景验证，**仍为 Validation Only，尚未采纳
  进入 SOT**，需在 OOM / Database / Redis / MQ 等更多场景验证后才考虑
  正式改动课程，不得当作正式规则执行。

---

## 6. Next Session

- English：继续 Review Topic 5（Food）的 Random Review；表现稳定后可
  引入 Topic 6。Topic 1–4 按 Priority-Based Review Engine 继续轮换（已学
  Topic 数达到 5，下次新增 Topic 6 后将超过 5，需转为抽样机制，见 SOT 第
  7 节）。
- Java：按 Scenario Interview Mode 引入下一个新场景——"Production OOM
  (OutOfMemoryError)"；继续沿用当前教学流程 Interviewer Intent →
  Thinking Process → Canonical Answer → User Practice → Review（该流程
  仍为 Validation Only，非正式 SOT 规则，见第 5 节）。同时 Random Review
  池已包含 What is Java? / Why do you use Java? / Scenario 1 / Scenario 2
  四题。
