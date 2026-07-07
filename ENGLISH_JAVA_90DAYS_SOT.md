# English + Java 90-Day Program — Single Source of Truth (V11.15 — FROZEN)

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

**V11.5 是冻结后的执行改进（Execution Improvement），不是架构重新设计。**
本次为 Java Interview 练习新增/细化以下执行规则，均为最小、可加性修改，
Step1–Step5 三轮流程结构、Review Engine、Mastery Rules、Progress Rules、
Output Format、Session 结构均未改变：(1) 第 3 节 Voice Listening First 的
"说完"判定短语列表补充"我回答完了"与"寻找措辞/语塞"场景；(2) 第 5 节新增
"训练目标"说明——目标是面试思维与临场表达（识别问题类型、组织结构、忘词
后恢复、保持自信），不是死记标准答案；(3) 第 5.2 节 Step1 新增"先判断
Question 类型、再选择对应回答框架"的框架表（定义型/原因型/对比型/场景型/
架构型），不再对所有问题套用同一模板；(4) 第 5.2 节 Step3–Step5 新增固定
顺序的 Review Checklist（总分→是否切题→逻辑→语法措辞→技术纠正→遗漏得分
点→更好表达→最终优化答案），并要求每轮反馈后立即纠正、同一错误不得在下
一轮重复出现。

**V11.6 是冻结后的英语 Review 执行改进（Execution Improvement）。** 新增/
细化以下执行规则，Step 数量与 Session/Topic/Mastery/Output 结构均未改变：
(1) 第 7 节新增 Coverage Rule（Hybrid）——已学 Topic ≤ 5 个时 Review 必须
覆盖每一个 Topic，超过 5 个后回到原有 Priority-Based Review Engine 抽样
机制（原抽样机制本身未改动，仅在 Topic 数较少的早期阶段叠加一条覆盖保
证）；(2) 第 4.2 节 Review 步骤新增：选中 Question 必须随机顺序提问（不
按 Topic 顺序）、可随机合并 2–4 个已学 Question 一起问、Review 阶段也采
用双向提问（我问/AI 答）、Review 期间只用英文提问、中文仅用于回答后纠
错、回答后按语法→用词→表达→发音→流利度顺序检查并立即纠正。未改动
Section 4.2 的 5 个步骤本身、Section 4.3 比例、Section 4.4 Topic 完成标
准、Section 2 Learning Philosophy、Progress Rules、Output Format。

**V11.7 是冻结后的执行改进（Accurate Error Feedback）。** 发现的执行问题：
AI 有时在回答仍存在语法/用词错误时说"Perfect"/"Great"等虚假肯定评价，
可能让错误固化为肌肉记忆。修补方式：第 6 节新增 Accurate Feedback Rule，
统一规定英语与 Java 反馈固定顺序（总体评分→正向鼓励→逐一指出语法错误→
逐一指出用词错误→逐一指出不自然表达→技术纠正[仅 Java]→正确版本→继续
练习），并明确"准确度优先于鼓励"。未修改 Session Workflow、Review
Engine、Mastery Rules、Progress Rules、Topic 结构、Java Step1–Step5
数量、Output Format——第 4.2 节与第 5.2 节的既有纠错步骤/Checklist 均
保留，仅新增对本规则的引用。

**V11.8 是冻结后的执行改进（No Assumption Feedback）。** 发现的执行问题：
AI 有时在心里把用户实际说的内容替换成期望的标准答案，再当作用户回答正确
处理（例如用户说"I live in Huizhou City, Hainan."被当作"I live in Ho Chi
Minh City, Vietnam."处理）。修补方式：第 6 节新增 No Assumption Feedback
Rule，要求 AI 必须依据用户实际说出的内容评判，若与期望答案不同，用固定
的"I heard / Expected answer / Correction / Please repeat"格式明确指出，
不得用鼓励话语掩盖差异；适用于 English Review/Practice/Mixed
Conversation/Role Switch 与 Java Interview practice。未修改 Session
Workflow、Review Engine、Mastery Rules、Progress Rules、Topic 结构、Java
Step1–Step5 数量、Output Format。

**V11.9 是冻结后的执行改进（早期阶段 Review 执行强化）。** 在 V11.6 已建立
的 ≤5 Topic Hybrid Coverage Rule 基础上进一步明确执行细节：(1) ≤5 Topic
阶段的 Review 必须覆盖每个 Topic 下的**全部** Question，而不是每个 Topic
只抽 1 个；(2) 明确该阶段的执行按 Stage 1–4 递进（逐个随机复习全部
Question → 随机合并 2–4 个 Question → Role Switch → Free
Conversation），均复用第 4.2 节已有的 Review/Conversation 机制，不改变
其步骤顺序或引入新机制；(3) 只有以上阶段表现稳定才可引入新 Topic——这
一点本就由第 3 节与第 4.4 节保证，此处仅交叉引用。>5 Topic 时的
Priority-Based Review Engine 抽样机制未改动。未修改 Review Engine、
Mastery Rules、Progress Rules、Session Workflow（5 步顺序不变）、Output
Format、Topic 结构。

**V11.10 是冻结后的执行改进（Immediate Reinforcement + English Template）。**
新增两项最小、可加性执行规则，Session Workflow、Review Engine、Mastery
Rules、Progress Rules、Topic 结构、Output Format 均未改变：(1) 第 3 节新增
Immediate Reinforcement 规则、第 4.2 节 Practice 步骤后新增对应执行细节——
今天新学的全部英语 Question 必须先完成 Individual Review / Random Review /
Combined Questions 同 Session 强化（复用第 4.2/第 7 节已有的随机顺序提问、
2–4 合并提问机制，不新增机制种类），达到"正确、流利、自然、无明显犹豫"
后，才可以开始该 Session 的 Java Interview 部分（第 5 节新增一句入口条件
交叉引用）；本强化明确不是 Mastery，不改变第 9.1 节 Mastery Criteria 或第
4.4 节 Topic Completion 的判定标准。(2) 第 4.1 节新增英语学习内容固定模板
（Question / Standard Answer 均含 English / 中文翻译 / IPA / 中文谐音标注，
新增词汇与例句同样按模板记录），第 11 节记录格式相应扩展以容纳该模板字段，
仅对未来新增内容生效，不回填已记录的历史条目。

**V11.11 是冻结后的执行改进（Chinese Prompt Review Mode + No-Interrupt 强化 +
Correct Fast-Path + Today's Final Review）。** 基于真实学习 Session 反馈，
新增/合并以下最小、可加性执行规则，Session Workflow、Review Engine
（Mastery Status + Recency 选题算法、Coverage Rule）、Mastery Rules、
Progress Rules、Topic 结构、Java 流程结构、Output Format 均未改变：
(1) 第 4.2 节 Step1 Review 新增 **Chinese Prompt Method** 作为默认触发方
式——AI 默认只给中文提示，由我自己先构造英文 Question 再自己给出英文
Answer，AI 在我尝试前不得提前给出英文 Question；此项只改变提问触发语
言，不改变第 7 节的选题算法与覆盖规则。(2) 第 3 节 Voice Listening First
补充"无例外"声明与场景枚举（English Speaking / Java Interview / Role
Play / Self Introduction / Question Practice），合并进已有规则而非新建
规则。(3) 第 6 节新增 Correct Fast-Path Rule，与既有 Accurate Feedback
Rule 互补——回答完全正确时只说"Correct. 100/100."并立即进入下一题，存
在任何错误时仍适用原 Accurate Feedback Rule 完整流程。(4) 第 4.2 节 Step4
的 V11.10 Immediate Reinforcement Rule 尾部新增 Today's Final Review 子
步骤——复用 (1) 的 Chinese Prompt Method，对今天新学的每个 Question 做
最后一次中文提示驱动的 Question+Answer 验证，作为进入 Java Interview 前
的最终检查，不改变 Mastery/Topic 判定标准。用户同时提出的"Question Bank
Growth"（新 Answer 必配对新 Question）经核对，已由第 4.1 节"新增 5 组
Question & Answer"的既有配对结构满足，未新增规则；"Question Priority"与
"Speaking Rhythm"两项内容分别与 (1)(3) 重复，合并说明，未重复建规则。

**V11.12 是冻结后的执行改进（Java Canonical Answer Rule + Senior / CTO
Thinking Rule）。** 用户在真实 Java 面试练习中发现：Java Answer Bank 虽然
在第 5.2 节 Step5 保存 Final Answer，但架构从未明确规定该答案在未来 Session
（尤其是 Random Review）中必须保持逻辑结构与要点不变，导致同一 Interview
Question 可能在不同 Session 得到不同的"标准答案"，与肌肉记忆目标冲突；同时
架构也从未明确规定 Canonical Answer 的内容深度必须永久达到 Senior /
Tech Lead / CTO 级别的工程与架构思维，而不是教科书式或初级罗列式回答。
经审计，两项提议均未新增/改变 Step1–Step5 的流程数量与顺序、未改变 Review
Engine（第 7 节）选题算法、未改变 Session Workflow（第 8 节）、未改变
Progress Rules 与 9.1 Mastery Criteria 的判定标准本身，只是为已存在但从未
明确规定的"答案内容应保持什么状态"补齐规则，判定为 Execution Improvement。
因用户本次请求明确要求不得修改第 5 节 Java learning workflow 本身，两条新
规则改为放入第 6 节 AI Behavior（该节已是 Accurate Feedback Rule / Correct
Fast-Path Rule / No Assumption Feedback Rule 等跨 English/Java 内容质量
规则的既定归属位置），并在第 12 节 Java Answer Bank 记录格式说明中补充一句
交叉引用，未改变第 12 节的字段结构本身。

**V11.13 是冻结后的执行改进（Java Interview Language Rule）。** 用户报告
Java Interview 有时被 AI 切换为英文模式，与第 5 节已有的"前 90 天全部使用
中文"原则冲突。审计确认：该原则本已存在于第 5 节，并非缺失，但从未列举其
覆盖范围（Interview Question 措辞 / Step1 AI 分析 / Step2 参考答案示范 /
Step3–Step5 学员回答 / AI 反馈 / 最终存入第 12 节的 Final Answer）、从未声明
"学员可明确要求英文面试练习"的例外情形，也从未说明专有技术名词（如 JVM /
Spring Boot）本身允许保留英文——这一空白已经在第 12 节的既有历史数据中
体现为真实违反（"What is Java?"与"Why do you use Java?"两条 Final Answer
均为纯英文）。判定为 Execution Improvement——只是把第 5 节已有原则的覆盖
范围与例外情形明确化，不新增学习机制，不改变第 5.1/5.2 节的 Step1–Step5
流程、顺序或数量。因用户本次请求同样明确要求不修改第 5 节（Java learning
workflow），本规则改为放入第 6 节 AI Behavior，与 V11.12 的 Java Canonical
Answer Rule / Senior CTO Thinking Rule 并列，同属"AI 生成 Java 内容时必须
遵守的永久规则"类别。本次请求另提出的 Java Canonical Answer Rule 与
Senior/CTO Thinking Rule 与 V11.12 已实现的规则内容重复，审计确认后不重复
新增，避免产生冲突或重复的规则文本。第 12 节两条历史 Final Answer 条目为
英文这一事实与新规则不符，但按 V11.10/V11.11 已确立的"新规则仅对未来内容
生效，不回填历史条目"惯例，本次未做改写，已在实施报告中向用户说明，是否
需要转换为中文由用户后续决定。

**V11.14 是冻结后的第三次架构缺陷修补（Architecture Bug Fix）。** 用户提出四项
"架构级问题"，逐条审计如下（三项已被现有规则满足，一项确认为真正的架构缺陷）：
(1) "Immediate Reinforcement 必须成为强制框架步骤"——已由第 3 节 Immediate
Reinforcement 规则（"必须先完成...才可以开始该 Session 的 Java Interview 部分"）
与第 4.2 节 Step4 明确规定为强制步骤，并非可选执行行为，判定为 ALREADY
SATISFIED，未重复新增规则。(3) "Java Question 不能在 Round3 后立即 Mastered，
必须先经过一次未来 Session 的 Random Review"——已由第 9.1 节 Java Mastered 三
个并列条件之一（"之后的 Random Review 抽查表现持续满意"）保证：单次 Step5
完成不存在"之后"的 Random Review 记录，因此逻辑上不可能满足该条件，判定为
ALREADY SATISFIED（本 Session 记录 "Why do you use Java?" 时已按此标准标记为
Practicing 而非 Mastered，与本条要求一致）。(4) "Topic 不能仅因 Practice 正确
就算完成，需 Practice+Immediate Reinforcement+Random Review+Combined
Questions+Final Review 全部通过才能进入 normal review"——审计发现第 4.4 节
Topic Completion 现有标准（要求 Topic 下全部 Question 达到第 9.1 节 Mastered，
即跨 Session 的持续稳定表现）已经严格于本条提议，采用本条提议反而会把完成
门槛降低为单 Session 达标，与已冻结的第 4.4/9.1 标准冲突，因此不采纳，判定
为 ALREADY SATISFIED（且以更严格的现有标准为准）。

(2) "English Question Mode Progression（Chinese Prompt → 纯英文 → Free
Conversation 需要明确阶段触发条件，而非依赖 AI 临场判断）"——审计确认为真正
架构缺陷：第 4.2 节 Step1 的 Chinese Prompt Method（V11.11 新增）被定义为
"默认"提问方式，AI 仅"随机穿插"直接英文提问，从未定义任何从依赖中文提示
过渡到不依赖中文提示的触发条件；但第 9.1 节 English Mastered 明确要求
"不经过翻译、不组织语言"，即最终状态必须完全脱离中文提示。这是 Review 阶段
实际机制（长期允许无条件依赖中文提示）与其应服务的 Mastery 目标（最终必须
脱离中文提示）之间的真实不一致，符合 V11.3/V11.4 建立的架构缺陷判定标准。
修补方式（最小、可加性）：在第 4.2 节 Step1 新增 English Question Mode
Progression，为 Chinese Prompt Method 补充明确的 Stage A → Stage B 触发条件
（触发点复用已有构件：第 3 节 Immediate Reinforcement + Today's Final Review
完成、Topic 进入第 7 节正常 Review 轮换），并将已有的 Role Switch / Free
Conversation 标注为 Stage C 终点，不新增机制、不新增 Session 步骤、不改变
Review Engine 选题算法（第 7 节）、不改变 9.1 节 Mastery Criteria 文本本身。

**V11.15 是冻结后的第四次架构缺陷修补（Architecture Bug Fix）。** 用户报告
Speaking 环节暴露六项"框架级缺陷"，逐条审计如下（两项确认为真正的架构缺陷、
两项已被现有规则满足、一项与另一项重复、一项超出 Bug Fix 范围）：

- **Bug 1（Current Session Context Rule）与 Bug 6（Strict Curriculum
  Boundary，二者为同一问题的重复表述，合并审计）**——现象：AI 提出了当天
  从未学过的问题（如 "What time do you usually go to work?"、"Why do you
  want to work for an international company?"）。审计确认：不超纲这一
  **结果**规则本就存在（第 6 节"AI 禁止：超纲（超出已学内容）"；第 4.2 节
  Step2 Conversation "只能使用 Conversation Bank 中已经学习过的
  Question"），但框架从未规定任何**保证该结果达成的前置机制**——即 AI 在
  提问前必须先加载当前 Session 的真实已学内容（第 11/12/13 节），而不是凭
  记忆或语感"顺理成章"地临场生成相似问题。这是"已声明的结果要求"与"从未
  存在、用于保证该结果的机制"之间的真实缺口，符合 V11.3/V11.4/V11.14 已
  建立的架构缺陷判定标准。修补方式（最小、可加性）：第 3 节新增 Session
  Context Grounding 规则，不改变第 6 节"超纲"禁止或第 4.2 节 Conversation
  Bank-only 限制本身，只补齐让这两条既有规则得以被执行的前置加载步骤。
- **Bug 2（Continuous Conversation Loop）**——现象：AI 在几乎每次回答后
  停下等待学员输入"继续"。审计确认：第 6 节已明确声明 AI 行为目标"少讲、
  多问、多聊天、多模拟"，但从未规定问题与问题之间的衔接机制，导致实际
  行为（等待确认才继续）与已声明目标（多问、连续聊天）产生真实冲突，
  同样符合 V11.4 的判定标准（第 6 节目标与实际机制不一致）。修补方式
  （最小、可加性）：第 6 节新增 Continuous Flow Rule，仅约束"两次提问
  之间"的衔接方式，不改变 Voice Listening First（仍必须等待学员说完当次
  回答，不得在学员说话过程中打断）、不改变 Session 步骤数量、Review
  Engine 选题算法或 Mastery/Progress 判定标准。
- **Bug 3（Low-Interruption / 简短反馈）**——审计确认 **ALREADY
  SATISFIED**：第 6 节 Correct Fast-Path Rule（V11.11）已明确规定回答完全
  正确时"只需简短确认——固定使用'Correct. 100/100.'...禁止额外的夸奖语句
  或长篇解释"，用户描述的"Excellent! / Very good! / Amazing!"式长篇夸奖
  正是该规则本已禁止的行为。这是既有规则的执行失败，不是规则缺失，未新增
  规则，避免产生重复/冲突文本。
- **Bug 4（Random Question Engine）**——审计确认 **ALREADY SATISFIED**：
  第 4.2 节 Step1（V11.6）已明确规定"选出的 Question 必须以随机顺序提问，
  不得按 Topic/Bank 原始顺序依次提问（例如 Topic2 → Topic1 → Topic3 →
  Topic1 …）"，第 7 节 Coverage Rule Stage 1 同样要求"随机顺序（不按 Topic
  顺序）"。用户描述的"Topic1 → Topic2 → Topic3 顺序提问"正是该规则本已
  禁止的行为，同属执行失败而非规则缺失，未新增规则。
- **Bug 5（Immersive Speaking Mode，固定 30/60/90 分钟新模式）**——审计
  判定为**超出 Bug Fix 范围**：用户原文本身即为"Add a **new** permanent
  Speaking Mode"，这是新增课程结构/模式，而不是修补某条已声明规则与其
  实际机制之间的不一致；其列出的子规则（不讲解、不长篇语法讲解、不每题
  等待、正确才简短确认、详细点评延后到结束后）已分别被第 3 节 Core
  Rules、第 6 节 AI 禁止清单、Correct Fast-Path Rule、以及本次新增的
  Continuous Flow Rule 覆盖，真正新增的部分只剩"固定时长（30/60/90 分钟）
  的独立模式"这一结构性新概念，这违反 Architecture Freeze 的 Bug-Fix-Only
  例外条件与第 2 节 Keep It Simple 原则，不能在本次 Bug Fix 中静默新增，
  已通过 AskUserQuestion 向用户确认处理方式，用户选择**不采纳**——不新增
  固定时长 Speaking Mode 结构，理由是实际想要的行为（连续提问、简短反馈、
  不在说话中途讲解、超纲边界）已由既有规则 + 本次 Bug1/2 修补完整覆盖。

本次修补未改变 Session Workflow（第 8 节）、Review Engine 选题算法（第 7
节）、Mastery Criteria（9.1 节）、Progress Rules（第 9 节）、Topic/Step
结构或 Output Format（第 10 节）。

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
- **Voice Listening First** — 语音模式下，AI 必须"听"优先于"说"，且优先级高
  于响应速度。只要不确定用户是否已经说完，AI 必须继续等待；禁止仅因短暂
  停顿（思考、呼吸、断句、犹豫、寻找措辞/语塞）就判断用户说完并打断。只有
  当用户明确表示说完（例如"回答完了"/"我说完了"/"我回答完了"/"Finished"/
  "That's all"/"Done"），或明确要求 AI 回应时，AI 才可以开始评分、纠错、给
  建议或进入下一步。英语对话练习同样适用本规则，Java 面试模拟见第 6 节。
  本规则没有例外，适用于 English Speaking / Java Interview / Role Play /
  Self Introduction / Question Practice 等一切语音练习场景；即使停顿持续
  数秒，AI 也不得打断。
- **Immediate Reinforcement（同 Session 即时强化，非 Mastery）** — 同一
  Session 内，今天新引入的英语 Question 必须先完成第 4.2 节 Practice 之后
  的 Immediate Reinforcement（Individual Review / Random Review / Combined
  Questions），达到"正确、流利、自然、无明显犹豫"后，才可以开始该 Session
  的 Java Interview 部分。本强化不是 Mastery——Mastery 判定仍以第 9.1 节
  Mastery Criteria 为准，Topic 完成标准仍以第 4.4 节为准，Progress Rules
  （第 9 节）不因本条改变。
- **Session Context Grounding（Session 启动前必须加载当前学习状态，防止
  超纲提问）** — 每个 Session 开始时，AI 必须先加载并明确当前状态：第 13
  节 Current Session（当前 English Topic 列表、Java Interview
  Topic/Question）、第 11 节 English Conversation Bank 中已学 Topic 与
  Question、第 12 节 Java Answer Bank 中已学 Interview Question。此后本
  Session 内任何步骤（Review / Conversation / Practice / Mixed
  Conversation / Java Interview）中 AI 提出的问题，必须逐字或语义等价于
  已加载的 Bank 内容，禁止改写、扩写、临场编造"相似"或"顺理成章"的新问题
  （例如已学"Why are you learning English?"不得改问成"Why do you want to
  work for an international company?"；已学 Daily Routine 的 get up/go to
  bed 不得改问"What time do you usually go to work?"）。只有第 4.2 节
  Step3 Today's Lesson 明确进入"新增今天 5 组 Question & Answer"环节时，
  才允许引入新问题。本规则是对既有"超纲"禁止（第 6 节）与 Conversation
  Bank-only 限制（第 4.2 节 Step2）的启动前置保证，不改变这两条规则本身，
  也不改变 Session 步骤数量或顺序。

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

**English Learning Template（固定模板，此后每次新增内容均按此格式呈现/记录，
仅对未来新增内容生效，不回填已记录的历史条目）：**

- Question：English / 中文翻译 / 国际音标（IPA）/ 中文谐音标注
- Standard Answer：English / 中文翻译 / 国际音标（IPA）/ 中文谐音标注
- 每个新增词汇：English / 中文含义 / 国际音标（IPA）/ 中文谐音标注
- 每个例句：English / 中文翻译

本模板用于提升发音准确度、理解与长期肌肉记忆，不改变每日新增数量（5 组
Q&A）、Topic 结构，也不改变第 3 节 Voice First 的优先级——书面模板仍只是
语音练习的辅助确认材料。

### 4.2 固定流程（每个 Session）

1. **Review**
   - AI 按第 7 节 Review Rules 定义的优先级 Review Engine（Mastery Status +
     Learning Recency），智能选出本次要复习的 Question 集合（覆盖范围规则
     见第 7 节）。
   - 选出的 Question 必须以**随机顺序**提问，不得按 Topic/Bank 原始顺序
     依次提问（例如 Topic2 → Topic1 → Topic3 → Topic1 …），避免我靠"顺序"
     而不是"自动反应"答题。
   - AI 有时可将 **2–4 个已学 Question 合并成一句话一起问**（例如 "What's
     your name, and where are you from?"），次数随机，不必每次只问一个。
   - Review 阶段同样采用**双向提问**：多数时候 AI 问、我答；也要随机出现
     我问、AI 答，训练听与说两个方向。
   - **Chinese Prompt Method（默认 Review 触发方式）**：AI 默认只给出**中文
     提示**（该 Question 的中文含义），不直接给出英文 Question；由我自己
     先构造英文 Question，再自己给出英文 Answer（Question → Answer 连续
     说出）。AI 在我尝试之前不得提前给出英文 Question，只有在我回答完毕
     后才可以用中文讲解纠错（呼应第 3 节 Voice First）。此模式同时训练
     Question Muscle 与 Answer Muscle。AI 仍可随机穿插原有的"直接用英文
     提问"方式变换节奏，Combined Questions 场景下也可一次给出 2–4 个中文
     提示，但 Chinese Prompt 为默认方式。
   - **English Question Mode Progression（Chinese Prompt Method 的阶段推进，
     不再依赖 AI 临场判断）**：
     - **Stage A（默认）**：适用于尚未完成第 3 节 Immediate Reinforcement +
       Today's Final Review 的 Question。使用上方 Chinese Prompt Method，
       AI 只给中文提示，我自己说出英文 Question 与 Answer。
     - **Stage B（触发条件：该 Question 所属 Topic 已完成 Immediate
       Reinforcement + Today's Final Review，进入第 7 节正常 Review 轮换）**：
       Review 阶段改为 AI 直接用英文提问、我直接用英文回答，不再提供中文
       提示，呼应第 9.1 节 English Mastered "不经过翻译"的要求。
     - **Stage C（进度终点标注，复用第 4.2 节第 2 步已有机制，不新增
       步骤）**：Role Switch / Free Conversation，全程英文，不引入中文提示
       或翻译。
   - 我用语音回答（Voice First，见第 3 节）。
   - 回答完毕后，若完全正确，AI 按第 6 节 Correct Fast-Path Rule 简短确认
     后立即进入下一题；若存在语法/用词/表达/发音问题，AI 按顺序检查：语法
     → 用词 → 表达是否自然 → 发音提示（如需要）→ 流利度，立即纠正错误，
     禁止把错误的英文变成肌肉记忆（呼应第 6 节 Accurate Feedback Rule）。
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
   - **Immediate Reinforcement Rule（同 Session 即时强化，非 Mastery，见第 3
     节）**：初次练习流利后，AI 必须继续对今天新学的全部 Question 做同
     Session 强化，包括：Individual Review（逐个重新提问今天新学的全部
     Question）、Random Review（随机顺序提问，不按今天引入顺序）、
     Combined Questions（随机将 2–4 个今天新学的 Question 合并成一句话一起
     问，复用本节 Review 步骤已有的合并机制）。强化持续到今天新学的全部
     Question 都能正确、流利、自然、无明显犹豫地回答为止，才可以进入
     **Today's Final Review**：AI 只给中文提示（复用本节 Step1 的 Chinese
     Prompt Method），我需对今天新学的每一个 Question 独立说出英文
     Question 与英文 Answer，全部通过后才可以进入第 5 步 Mixed Conversation
     以及该 Session 的 Java Interview 部分。达到本条标准仍标记为
     Practicing，不因此改变第 9.1 节 Mastery 判定或第 4.4 节 Topic 完成
     标准。

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

**Session 内启动条件**：本 Session 的 Java Interview 必须在第 3 节 Immediate
Reinforcement 完成后才能开始（今天新学的英语 Question 已通过 Individual
Review / Random Review / Combined Questions 强化，见第 4.2 节 Practice）。

**训练目标**：目标不是背诵标准答案，而是训练面试思维——识别面试官真正
在考察什么、快速组织回答结构、在忘记细节时也能继续说下去而不卡壳、自信
自然地表达而不是背稿。学员最大的弱点通常不是技术知识本身，而是忘词、
卡壳、丢失回答结构、紧张。因此训练应持续围绕：结构化表达、保持语流、
使用过渡句、忘记细节后的恢复、保持自信——面试流畅度与临场应变，与内容
准确度同等重要。

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
   AI 必须先判断该 Interview Question 属于哪种类型，选择对应回答框架，
   禁止对所有问题套用同一模板：

   | Question 类型 | 回答框架 |
   |---|---|
   | 定义型 | Definition → Core characteristics → Typical scenarios → Personal experience |
   | 原因型 | Main reasons → Technical advantages → Business value → Personal experience |
   | 对比型 | Differences → Advantages/disadvantages → Real project choice |
   | 场景型 | Problem → Analysis → Solution → Result |
   | 架构型 | Background → Design → Trade-offs → Experience |

2. **Step2 — AI 给出参考答案**（按 Step1 选定的框架给出）。
3. **Step3 — 我回答第一次**，AI 按下方 Review Checklist 固定顺序评分与反馈，
   并立即纠正错误；同一错误不允许在下一轮重复出现。
4. **Step4 — 我回答第二次**，AI 按同样的 Review Checklist 评分与反馈，
   同样立即纠正、不允许错误重复。
5. **Step5 — 我回答第三次**，AI 按同样的 Review Checklist 评分。第三次回答
   作为当前最佳答案，保存到 Java Answer Bank。

**Review Checklist（每轮反馈固定顺序，禁止只夸奖，必须找出所有问题后才能
进入下一题）：**
1. Overall score
2. 是否直接回答了面试问题
3. 逻辑是否清晰
4. 语法 / 措辞纠正（如涉及英文）
5. 技术内容纠正
6. 遗漏的关键得分点
7. 更好的面试表达方式
8. 最终优化后的答案

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

**Accurate Feedback Rule（英语与 Java 通用，禁止虚假肯定评价）**：只要回答
中存在任何语法、用词、表达不自然或技术错误，AI 禁止说"Perfect"/"Great"/
"完全正确"等与事实不符的肯定评价。反馈固定顺序为：总体评分 → 正向鼓励 →
逐一指出每个语法错误 → 逐一指出每个用词错误 → 逐一指出每个不自然表达 →
技术纠正（仅 Java）→ 给出正确版本 → 继续练习。鼓励与指出错误必须共存，
但准确度优先于鼓励——绝不能为了鼓励学员而把有错误的回答说成完全正确，
否则错误会变成肌肉记忆（呼应第 2 节 Muscle Memory First）。第 4.2 节
Review 的纠错步骤与第 5.2 节 Java Review Checklist 均遵循本规则。

**Correct Fast-Path Rule（回答完全正确时的最简反馈，与上方 Accurate
Feedback Rule 互补）**：当回答不存在任何语法、用词、表达或技术错误时，AI
只需简短确认——固定使用"Correct. 100/100."，然后立即进入下一题，禁止额
外的夸奖语句或长篇解释。仅在以下情况才展开说明：语法错误、发音问题、语
序错误，或我明确要求解释原因（例如问"为什么"）。目的是保持高语速、少打
断、最大化我的开口时间（呼应第 3 节"AI 少讲、多问"）。只要存在任何错误，
必须改用上方 Accurate Feedback Rule 的完整反馈顺序，本条快速通道不适用。

**No Assumption Feedback Rule（禁止臆测用户答案）**：AI 必须根据用户**实际
说出的内容**评判答案，禁止在心里默默把用户的回答替换成期望中的标准答案后
当作正确处理。若用户的回答与期望答案不同，AI 必须使用以下固定格式明确
说明，禁止用"Perfect"/"Great"等话语掩盖这一差异：

```
I heard: "（用户实际说的内容）"
Expected answer: "（期望/标准答案）"
Correction: （为什么不同或哪里错）
Please repeat: "（要求用户重复的正确版本）"
```

本规则优先级高于鼓励——不得为了保护学员信心而隐藏或忽略其与实际回答不
符的问题。适用范围：English Review、English Practice、Mixed
Conversation、Role Switch、Java Interview practice（Java 场景下 AI 必须
评判用户实际表达的技术内容，不得假设用户想表达的是正确概念）。

**Java Canonical Answer Rule（Java 标准答案永久锁定规则）**：每个 Interview
Question 有且只有一个 Canonical Answer——即第 5.2 节 Step5 完成后保存到第 12
节 Java Answer Bank 的 "My Final Answer"。一旦该答案完成保存（视为学员已
确认），此后任何 Session（包括 Random Review）都不得重写、重新组织、替换
该答案，或为同一 Interview Question 生成另一套不同的逻辑答案。之后的练习
只允许在不改变逻辑结构与要点的前提下，提升表达流利度、反应速度、发音与
自信程度；不得改变逻辑结构与关键要点，除非学员明确要求修订。若学员明确
要求修订，AI 才可更新第 12 节该 Question 的 "My Final Answer"，并在 Review
History 中记录修订原因。Random Review（第 5.3/7 节）评分与纠错必须以第 12
节已保存的 Final Answer 作为固定参照标准，不得凭空生成新的"标准答案"。本
规则不改变第 5.2 节 Step1–Step5 的流程、顺序或数量，也不改变第 9.1 节
Mastery Criteria 中"回答体现的是清晰的逻辑，而不是背诵记忆"的判定标准——
逻辑结构固定不等于逐字背诵，学员仍需能够灵活、自然地用自己的语言表达同一
套固定逻辑与要点，而不是机械复述固定文本。

**Senior / CTO Thinking Rule（面试思维层级永久规则）**：每个 Java Canonical
Answer（第 5.2 节 Step2 参考答案与最终存入第 12 节的 Final Answer）必须永久
体现 Senior Backend Engineer / Technical Lead / CTO 级别的思考方式，禁止是
教科书式定义、初级工程师式罗列功能、或通用 AI 模板化回答。回答必须持续
体现：工程思维、架构思维、生产环境经验、权衡取舍（trade-off）分析、业务
价值、真实场景下的决策依据。本规则适用于 AI 在第 5.2 节 Step1/Step2 生成
参考答案时，也适用于第 12 节 Final Answer 最终定稿时；不改变 Step1–Step5
的流程、顺序、数量，也不改变第 9.1 节 Mastery Criteria 的判定标准本身——
只约束"面试水准"这一判定标准背后应达到的内容深度。

**Java Interview Language Rule（Java 面试语言永久规则）**：Java Interview
模块——包括 Interview Question 措辞、第 5.2 节 Step1 AI 分析、Step2 AI
参考答案/示范、Step3–Step5 学员回答、AI 反馈与纠正、最终存入第 12 节的
Final Answer——必须永久使用中文，除非学员在当前 Session 中明确要求进行
英文面试练习。English Module（第 4 节）与 Java Module（第 5 节）是两个
完全独立的学习系统，AI 不得默认将 Java Interview 切换为英文模式，也不得
将英语学习内容渗入 Java Interview 的语言载体。专有技术名词本身（如 JVM /
Redis / Spring Boot / Kafka 等）允许保留英文原文，不视为违反本规则。本
规则不改变第 5.1 节 Interview Topic/Question 结构，也不改变第 5.2 节
Step1–Step5 的流程、顺序或数量，只约束语言载体本身。

**Continuous Flow Rule（连续提问规则，呼应本节"AI 必须：少讲、多问、多
聊天、多模拟"）**：在 Review / Practice / Conversation / Mixed
Conversation 等连续问答场景中，AI 完成一次反馈（Correct Fast-Path 或
Accurate Feedback）后，必须自动、立即提出下一个问题，不得停下等待学员
输入"继续"或类似确认。仅当学员明确表示暂停（Pause）、结束今天课程（End
today's lesson）、要求讲解（Explain）、或主动提问时，AI 才可以停止自动
连续提问、转为响应模式。本规则不改变第 3 节 Voice Listening First（仍
必须等待学员把一次回答说完，不得在学员说话过程中打断），也不改变 Session
步骤数量、Review Engine 选题算法或 Mastery/Progress 判定标准，只约束"两
次提问之间"的衔接方式。

## 7. Review Rules（复习规则）

- **英语 Review 覆盖范围（Coverage Rule，Hybrid）**：当已学 Topic 总数 **≤ 5**
  个时，Review 必须覆盖每一个已学 Topic **下的全部 Question**（不是每个
  Topic 只抽 1 个），保证学习初期不会遗漏任何已学内容；当已学 Topic 总数
  **> 5** 个后，回到下方 Priority-Based Review Engine 的抽样机制，不再要求
  每次全部覆盖。

  在 ≤ 5 Topic 阶段，本 Coverage Rule 通过以下递进阶段执行（复用第 4.2 节
  Review / Conversation 已有机制，不改变其步骤顺序）：
  - **Stage 1**：逐个复习全部已学 Question，随机顺序（不按 Topic 顺序）。
  - **Stage 2**：随机将 2–4 个已学 Question 合并成一句话一起问。
  - **Stage 3**：Role Switch——我用已学 Question 向 AI 提问。
  - **Stage 4**：Free Conversation——只使用已学 Question 的自由对话。

  只有以上阶段表现稳定，AI 才可以引入今天的新 Topic（呼应第 3 节"Review
  未完成不得直接学习新内容"与第 4.4 节 Topic Completion）。
- **英语 Review（Priority-Based Review Engine）**：每个 Session 开始时（超过
  5 个 Topic 后），AI 不做全量复习，也不做纯随机抽取，而是结合 **Mastery
  Status** 与 **Learning Recency（学习时间新旧）** 两个维度，智能选出本次的
  Review Question 集合，优先级如下（数值越高越优先被选入本次 Review）：

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

记录格式（V11.10 起，按第 4.1 节 English Learning Template 扩展；仅对未来
新增内容生效，不回填本节已有的历史条目）：

```
Topic:
Question:
  - English:
  - 中文翻译:
  - IPA:
  - 中文谐音:
Standard Answer:
  - English:
  - 中文翻译:
  - IPA:
  - 中文谐音:
Vocabulary:（如本条引入新词汇，按下列格式记录；无新词汇可省略本项）
  - English:
  - 中文含义:
  - IPA:
  - 中文谐音:
Example Sentence:（如有例句，可多条；无例句可省略本项）
  - English:
  - 中文翻译:
Mastery Status: New / Practicing / Mastered
```

以下为 V11.10 之前记录的历史条目，沿用旧格式，不追溯改写：

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

Topic: English Learning

1.
Question: Why are you learning English?
Standard Answer: I'm learning English because I want to work for an international company.
Mastery Status: Practicing

2.
Question: Do you like learning English?
Standard Answer: （Session 2 未逐字记录标准答案，下次 Session 确认后补全）
Mastery Status: Practicing

3.
Question: How do you learn English?
Standard Answer: I learn English by speaking with ChatGPT every day.
Mastery Status: Practicing

4.
Question: How long do you study English every day?
Standard Answer: I study English for about six hours every day.
Mastery Status: Practicing

5.
Question: What is your English goal?
Standard Answer: My goal is to speak English fluently.
Mastery Status: Practicing

Topic: Daily Routine

1.
Question:
  - English: What time do you usually get up?
  - 中文翻译: 你通常几点起床？
  - IPA: /wɒt taɪm duː juː ˈjuːʒuəli ɡet ʌp/
  - 中文谐音: 沃特 太姆 度 尤 尤磁尤力 盖特 阿普
Standard Answer:
  - English: I usually get up at seven o'clock.
  - 中文翻译: 我通常七点起床。
  - IPA: /aɪ ˈjuːʒuəli ɡet ʌp æt ˈsevən əˈklɒk/
  - 中文谐音: 埃 尤磁尤力 盖特 阿普 艾特 塞文 欧克拉克
Mastery Status: Practicing

2.
Question:
  - English: What time do you usually go to bed?
  - 中文翻译: 你通常几点睡觉？
  - IPA: /wɒt taɪm duː juː ˈjuːʒuəli ɡəʊ tuː bed/
  - 中文谐音: 沃特 太姆 度 尤 尤磁尤力 果 图 贝德
Standard Answer:
  - English: I usually go to bed at eleven o'clock.
  - 中文翻译: 我通常十一点睡觉。
  - IPA: /aɪ ˈjuːʒuəli ɡəʊ tuː bed æt ɪˈlevən əˈklɒk/
  - 中文谐音: 埃 尤磁尤力 果 图 贝德 艾特 伊勒文 欧克拉克
Mastery Status: Practicing

3.
Question:
  - English: What do you usually do after work?
  - 中文翻译: 你下班后通常做什么？
  - IPA: /wɒt duː juː ˈjuːʒuəli duː ˈɑːftə wɜːk/
  - 中文谐音: 沃特 度 尤 尤磁尤力 度 阿夫特 沃克
Standard Answer:
  - English: I usually study English after work.
  - 中文翻译: 我下班后通常学习英语。
  - IPA: /aɪ ˈjuːʒuəli ˈstʌdi ˈɪŋɡlɪʃ ˈɑːftə wɜːk/
  - 中文谐音: 埃 尤磁尤力 斯塔迪 英格利什 阿夫特 沃克
Mastery Status: Practicing

4.
Question:
  - English: What do you usually do before you go to bed?
  - 中文翻译: 你睡觉前通常做什么？
  - IPA: /wɒt duː juː ˈjuːʒuəli duː bɪˈfɔː juː ɡəʊ tuː bed/
  - 中文谐音: 沃特 度 尤 尤磁尤力 度 比佛 尤 果 图 贝德
Standard Answer:
  - English: I usually read a book before I go to bed.
  - 中文翻译: 我睡觉前通常看书。
  - IPA: /aɪ ˈjuːʒuəli riːd ə bʊk bɪˈfɔː aɪ ɡəʊ tuː bed/
  - 中文谐音: 埃 尤磁尤力 瑞德 尔 布克 比佛 埃 果 图 贝德
Mastery Status: Practicing

5.
Question:
  - English: What do you usually do on weekends?
  - 中文翻译: 你周末通常做什么？
  - IPA: /wɒt duː juː ˈjuːʒuəli duː ɒn ˈwiːkendz/
  - 中文谐音: 沃特 度 尤 尤磁尤力 度 昂 威肯兹
Standard Answer:
  - English: I usually study English on weekends.
  - 中文翻译: 我周末通常学习英语。
  - IPA: /aɪ ˈjuːʒuəli ˈstʌdi ˈɪŋɡlɪʃ ɒn ˈwiːkendz/
  - 中文谐音: 埃 尤磁尤力 斯塔迪 英格利什 昂 威肯兹
Mastery Status: Practicing

## 12. Java Answer Bank

记录格式：

```
Interview Question:
My Final Answer:
Mastery Status: New / Practicing / Mastered / Needs Review
Review History:
```

**说明（呼应第 6 节 Java Canonical Answer Rule）**：以下 "My Final Answer"
字段一旦保存即永久锁定，未来 Random Review 必须以此作为固定参照标准；仅在
学员明确要求修订时才可更新，并在 Review History 中注明修订原因与日期。

Interview Topic: Java Basics

Interview Question: What is Java?
My Final Answer:
Java 是一门面向对象、跨平台的编程语言。
它运行在 JVM 之上，能够实现"一次编写，到处运行"（Write Once, Run Anywhere）。
它具备自动垃圾回收、稳定性和安全性等特性。
它被广泛应用于电商、银行、金融、大数据等企业级应用开发场景。
在我的工作中，我主要使用 Java 开发高并发后端系统与微服务。
我主要使用的技术栈包括 Spring Boot、Redis、MySQL、Kafka、MQ 和 WebSocket。
Mastery Status: Practicing
Review History: Session 1 — Round1 88/100, Round2 95/100, Round3 98/100 (initial pass); Session 2 — reviewed multiple rounds, answer structure now clearly Definition → Platform (JVM) → Core characteristics → Typical enterprise scenarios → Personal project experience, noticeably more fluent than Session 1.

Interview Question: Why do you use Java?
My Final Answer：
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
Mastery Status: Practicing
Review History: Session 2 — introduced as this Session's Interview Question, multiple rounds practiced; user moved from reciting toward a logical structure rather than memorized sentences, wording not yet finalized. Session 3 — completed via AI demonstration → Round1 → Round2 → Round3; Round2 refined wording ("backend" instead of "backend management", "runs on the JVM"); Round3 produced a complete, fluent, structured interview-quality answer (Conclusion → Technical Advantages → Personal Experience → Summary), scored 99/100, saved above as the locked Final Answer per the Java Canonical Answer Rule (第 6 节). Kept at Practicing rather than Mastered per 9.1 Java Mastery Criteria — interview quality reached, but subsequent Random Review performance has not yet been observed.

## 13. Current Session

### 13.1 Active Review Window（执行层机制，每 Session 结束时整体覆盖重写，
不追加历史，不改变课程架构）

机制说明（呼应第 3 节 Session Context Grounding 与第 7 节 Review Rules，
纯执行层数据，不属于第一部分课程规范）：
- English Active Topics = 最近学习的 ≤ 5 个 English Topic；已学 Topic 总数
  ≤ 5 时全部纳入（与第 7 节 Coverage Rule 的 ≤5 阶段一致）。
- Java Active Questions = 最近学习的 ≤ 5 个 Java Interview Question；已学
  Question 总数 ≤ 5 时全部纳入。
- 一旦 Topic / Question 总数 > 5，Active Review Window 改为采用第 7 节
  Priority-Based Review Engine 本次 Session 实际选中的集合，而不是单纯按
  引入时间截取最近 5 个——避免仍标记为 Needs Review / 表现不稳定的旧内容
  被纯时间窗口永久排除；已 Mastered 的内容仍按第 7 节的低优先级长期抽查
  节奏处理，不放入每次的全量队列（不改变第 7 节抽查概率表本身）。
- 本 Session 内 English Speaking Practice 与 Java Interview Practice 只能
  从下方列出的 Active Topics / Questions 中提问或练习，不得超纲（呼应第 3
  节 Session Context Grounding）。Java 引入"下一个新 Interview Question"
  仍按第 5.1 节既有规则进行，不受本窗口限制——本窗口只约束"复习/练习哪些
  已学内容"，不约束"何时学新内容"。
- 本小节内容每个 Session 结束时整体覆盖重写为下一次对话的窗口快照，不保留
  历史版本；完整历史仍完整保存在第 11/12/14 节，不受本小节覆盖影响。

English Active Topics（当前 3 个，均 ≤ 5，全部纳入）：
- Topic: Self Introduction
- Topic: English Learning
- Topic: Daily Routine

Java Active Questions（当前 2 个，均 ≤ 5，全部纳入）：
- What is Java?
- Why do you use Java?

### 13.2 Session Detail

- Session: 3（已完成，等待开始 Session 4）
- English Topic 1: Self Introduction（5 组 Q&A，Practicing，Topic 未完成；本
  Session 完成 Combined Questions / Role Switch / Free Conversation 复习，
  表现流利、接近自动反应）
- English Topic 2: English Learning（5 组 Q&A，Practicing，Topic 未完成；
  复习情况同 Topic 1）
- English Topic 3: Daily Routine（5 组 Q&A，本 Session 新学，Practicing，
  Topic 未完成；已完成 Practice / Individual Review / Random Review /
  Combined Questions / Today's Final Review，全部 5 组均可正确、流利作答）
- Java Interview Topic: Java Basics
- Java Interview Question: What is Java? → Practicing（未变动）
- Java Interview Question: Why do you use Java? → Practicing（本 Session
  完成 AI 示范 + 三轮回答，Final Answer 已定稿并存入第 12 节，99/100；按
  9.1 标准仍需未来 Random Review 表现稳定后才能升级 Mastered）
- 状态：已学 English Topic 数为 3（≤ 5），第 7 节 Coverage Rule 仍要求 Review
  覆盖全部已学 Topic 下的全部 Question。Session 4 开始时，英语先 Review
  Topic 1 + Topic 2 + Topic 3 共 15 组 Question（随机顺序、纯英文/Chinese
  Prompt Method、Combined Questions、Role Switch、Free Conversation），
  表现稳定后才可引入 Topic 4；Java 在 "Java Basics" Topic 下引入下一个
  Interview Question。

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

### Session 2（2026-07-06）

- English：Review 了 Topic "Self Introduction" 全部 5 组 Q&A，多轮随机复习，
  能不经翻译自然回答，并开始连续回答多个问题；Topic 仍为 Practicing（尚未
  Mastered，需未来更多随机复习）。新学 Topic "English Learning" 5 组
  Q&A（Why are you learning English? / Do you like learning English? /
  How do you learn English? / How long do you study English every day? /
  What is your English goal?），已存入第 11 节，均为 Practicing。完成
  AI-asks/Role-Switch/Mixed Conversation/随机顺序/多问题合并/纯英文提问/
  连续重复练习。语法纠正：like + doing（I like learning English，非 learn）；
  "started English" → "learn English"；"wanted to work" → "want to work"
  （描述当前目标用现在时）。新增对疑问词类型（Why/How/How long/What/
  Which）的理解。
- Java：Review 了 Interview Topic "Java Basics" 中 "What is Java?"，结构更
  清晰稳定（Definition → Platform(JVM) → Core characteristics → Typical
  enterprise scenarios → Personal experience）。新学本 Session 的 Interview
  Question "Why do you use Java?"，多轮练习后从背诵逐渐转为逻辑结构
  （Reason → Technical advantages → Enterprise application → Personal
  experience），尚未定稿最终措辞，标记 Practicing。本 Session 的重要收获是
  "面试思维"而非技术知识本身——回答应遵循与问题类型匹配的逻辑结构，而不
  是逐句背诵。
- 架构：本 Session 中确认/修补了多项已在对话中处理的执行规则（Section 3/6：
  Voice Listening First 细化、Accurate Feedback Rule、No Assumption
  Feedback Rule；Section 5：训练目标、问题类型框架表、Review
  Checklist；Section 7：英语 Review Coverage Rule），对应 V11.4–V11.8，
  版本历史见文档开头说明，此处不重复列出。

### Session 3（2026-07-07）

- English：Review 了 Topic "Self Introduction"（4/5 组：name / from / live /
  do，Hello! 未在本次总结中列出）与 Topic "English Learning"（4/5 组：why /
  how / how long / goal，"Do you like learning English?" 未在本次总结中
  列出），完成 Combined Questions、Role Switch、Free Conversation，整体表现
  流利、接近自动反应（almost automatic responses）。新学 Topic "Daily
  Routine" 5 组 Q&A（What time do you usually get up? / go to bed? / What
  do you usually do after work? / before you go to bed? / on weekends?），
  已按 English Learning Template（含中文翻译/IPA/中文谐音）存入第 11 节。
  完成 Practice、Individual Review、Random Review、Combined Questions、
  Today's Final Review，初期纠正错误："du"→"do"、"do go"→"go"，并解决了
  get up ↔ go to bed、seven o'clock ↔ eleven o'clock 的混淆，最终 5 组
  Q&A 均能正确作答，均标记为 Practicing（Topic 未完成，需后续 Review/
  Conversation 环节表现稳定后才可能升级 Mastered，第 4.2 节 Conversation
  阶段本次尚未针对 Daily Routine 单独执行）。
- Java：Interview Question "Why do you use Java?"（Session 2 引入）本
  Session 完成 AI 示范 → Round1 → Round2 → Round3。Round2 修正措辞
  （"backend" 替代 "backend management"、明确 "runs on the JVM"）；Round3
  形成完整、流利、结构清晰（结论 → 技术优势 → 个人经验 → 总结）的面试
  级回答，得分 99/100，已作为 Final Answer（翻译为中文，专有名词保留英文，
  呼应第 6 节 Java Interview Language Rule）存入第 12 节。按第 9.1 节 Java
  Mastery Criteria，仍标记为 Practicing——面试水准已达标，但尚未经过后续
  Random Review 验证稳定性，因此未采用本次会话总结中 "Mastered" 的表述。
- 备注：本次 Session 内容以外部总结形式提交并由 Claude 补录入 SOT，第 11
  节 Daily Routine 的 IPA 与中文谐音由 Claude 根据标准发音补充（原始对话中
  未提供逐字 IPA），供后续发音练习参考。
