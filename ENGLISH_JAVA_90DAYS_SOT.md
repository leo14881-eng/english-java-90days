# English + Java 90-Day Program — Single Source of Truth (V11.19 — FROZEN)

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

**V11.16 是冻结后的执行改进（Java Scenario Interview Mode 默认化 +
Canonical Answer Style Rule + Canonical Thinking Rule）。** 用户提交五项
"Java Stage 2"提议，逐条审计如下（三项判定为 Execution Improvement、两项
判定为 ALREADY SATISFIED）：

- **Item 1（Scenario Interview Mode 默认化）**——提议：Java Basics 主题的
  两个基础问题（What is Java? / Why do you use Java?）达到 Canonical
  Answer 锁定状态后，永久从"每日新内容"来源中移出，仅保留在 Random
  Review 池中；此后每个 Session 新增的 Interview Question 默认必须是场景
  型（Scenario）。审计确认：(a)"两个问题均完成 Step5 锁定后，该 Topic 不
  再提供每日新内容"本就是第 5.1 节既有规则的自然结果（"一个 Interview
  Topic 下的所有 Interview Question 都完成后，该 Topic 才算完成，才能进入
  下一个 Topic"），判定为 ALREADY SATISFIED 的部分；(b)"此后所有新
  Interview Question 默认使用场景型框架"是真正新增的内容——第 5.2 节
  Step1 框架表本已包含"场景型"作为 5 种类型之一，但从未规定过任何类型的
  默认优先级或排他性，此次新增的是一条内容选择策略，不改变 Step1–Step5
  流程本身、不改变 Topic/Question 层级结构（场景型 Question 仍归属某个
  Interview Topic，只是该 Topic 此后默认为场景/生产事故类主题）、不改变
  Review Engine 选题算法（第 7 节）、不改变 Session Workflow（第 8 节）或
  9.1 节 Mastery Criteria，判定为 Execution Improvement，加入第 5.1 节。
- **Item 2（Fixed Scenario Workflow，9 步流程）**——审计确认 **ALREADY
  SATISFIED**：所列 9 步与第 5.2 节既有 Step1–Step5（分析 → 参考答案 →
  Round1+评分 → Round2+评分 → Round3+锁定）以及第 6 节 Java Canonical
  Answer Rule（锁定后未来仅 Random Review）逐一对应，未新增机制，未重复
  建规则。
- **Item 3（Canonical Answer Style Rule）**——审计确认为真正新增：第 6 节
  既有 Senior / CTO Thinking Rule 只规定回答的思维深度（工程/架构思维），
  从未规定回答的表达风格（是否允许"第一...第二...第三..."式罗列、时长、
  是否口语化）。核对第 12 节现有已锁定的"Why do you use Java?" Final
  Answer，其结构为"1. 结论 2. 技术优势 3. 个人经验 4. 总结"的编号列表式
  写法，与本次新规则（禁止 First/Second/Third 式罗列，口语化、自然、约 1
  分钟）直接冲突——这一发现方式与 V11.13 相同（历史数据反证规则空白确实
  存在）。判定为 Execution Improvement，加入第 6 节，与 Senior / CTO
  Thinking Rule 并列；按 V11.10/V11.11/V11.13 已确立的"新规则仅对未来内容
  生效，不回填历史条目"惯例，不 retroactively 改写第 12 节现有的两条
  Final Answer，已在实施报告中向用户说明这一冲突。
- **Item 4（Canonical Thinking Rule，双层模型）**——审计确认为真正新增：
  明确区分 Layer 1（Canonical Answer，实际说出的内容）与 Layer 2
  （Canonical Thinking，内部思维框架，例如 Impact Assessment → Business
  Recovery → Root Cause Analysis → Recovery Validation → RCA / Long-term
  Prevention），永远不直接说出该框架列表本身。与第 5.2 节 Step1 既有框架
  表（例如场景型："Problem → Analysis → Solution → Result"）是同一概念在
  不同层面的进一步明确——框架表本就是 AI 内部用来生成/评分参考答案的思维
  模型，从未明确规定"该框架不得原样说出"，本次新增的是这一条禁止事项，
  属于对既有机制的补充说明，不改变框架表本身、不改变 Step1–Step5 流程。
  判定为 Execution Improvement，加入第 6 节，紧接 Item 3 新规则之后，两者
  共同解释"内部框架"与"口语表达"的关系。
- **Item 5（One Scenario Per Day Rule）**——审计确认 **ALREADY
  SATISFIED**：与第 5.1 节既有"每个 Session 只学习一个 Interview
  Question"、第 5.2 节三轮流程、第 5.3/7 节 Random Review 机制完全一致，
  "不得同一 Session 内引入多个新场景"本就是"只学习一个 Interview
  Question"的直接推论，未新增规则。

本次修补未改变 Session Workflow（第 8 节）、Review Engine 选题算法（第 7
节）、Mastery Criteria（9.1 节）、Progress Rules（第 9 节）、Step1–Step5
流程数量与顺序、Output Format（第 10 节）。

**V11.17 是冻结后的执行改进（Scenario 记录格式扩展：持久化 Interviewer
Intent 与 Canonical Thinking）。** 用户提议第 12 节记录格式为场景型
Interview Question 增加 Interviewer Intent（第 5.2 节 Step1 已生成但从未
持久化的"为什么面试官会问这个问题"分析）与 Canonical Thinking（V11.16
新增的内部思维框架层）两个字段，与 Canonical Answer 一并永久保存。审计
确认为真正新增：第 5.2 节 Step1 每次都会生成 Interviewer Intent 分析与
框架选择，但架构从未规定这些内容需要持久化——只有 Step5 的最终答案被存入
第 12 节；这意味着同一 Interview Question 在不同 Session 的 Random Review
中，AI 有可能重新生成不同版本的 Interviewer Intent 或 Canonical Thinking，
与 Java Canonical Answer Rule "同一 Interview Question 逻辑结构与要点永久
不变"的目标产生潜在漂移风险——这是"已声明的永久性目标"与"从未存在、用于
保证该目标的持久化机制"之间的真实缺口，性质与 V11.3/V11.4/V11.14/V11.15
系列架构缺陷修补相同，但由于其结构是"扩展第 12 节记录格式 + 第 5.2 节新增
一句存档要求"而非修改 Step1–Step5 流程本身、不改变 Review Engine 选题
算法、不改变 Session Workflow，故归类为 Execution Improvement（与 V11.10
英语模板扩展同一类别：Part 1 新增一条最小规则 + Part 2 record 格式相应
扩展，一并版本递增）。

审计中发现一处真实冲突并已与用户确认解决方案：用户原提议的 "Mastery:
Learning / Practicing / Locked" 字段与第 9 节已冻结的 Mastery Status
四值词汇（New / Practicing / Mastered / Needs Review）及 9.1 节三条件
Mastered 判定标准不兼容——"Locked" 描述的是 Canonical Answer 内容是否已
锁定（第 6 节 Java Canonical Answer Rule 的范畴），与 Mastery Status 追踪
的跨 Session 稳定表现是不同的维度，混用会破坏第 9 节已冻结的状态词汇表。
已通过 AskUserQuestion 向用户确认，采纳推荐方案：Scenario 记录格式沿用
第 9 节既有 Mastery Status 四值字段，不引入 "Locked" 作为状态值；Canonical
Answer 字段一旦有内容即视为已锁定（第 6 节规则本身已保证），不需要额外的
Locked 字段。

具体修补（均为最小、可加性修改）：(1) 第 5.2 节 Step5 新增一句——保存到
Java Answer Bank 时，Interviewer Intent 与 Canonical Thinking 必须与
Canonical Answer 一并存入；(2) 第 6 节 Canonical Thinking Rule 尾部新增
一句交叉引用，说明该内部框架必须持久化到第 12 节；(3) 第 12 节新增
"Scenario 类型记录格式"模板（Interview Question / Interviewer Intent /
Canonical Thinking / Canonical Answer / Mastery Status[沿用第 9 节四值] /
Review History），仅适用于场景型 Interview Question，Java Basics 等既有
非场景型条目沿用旧格式，不追溯改写（沿用 V11.10/V11.11/V11.13 已确立的
"新规则仅对未来内容生效"惯例）。本次修补未改变 Session Workflow（第 8
节）、Review Engine 选题算法（第 7 节）、Mastery Criteria（9.1 节）、
Progress Rules（第 9 节）、Step1–Step5 流程数量与顺序、Output Format（第
10 节）。

**关于第 4/11 节（English）是否需要同步修改**：审计确认不需要。Interviewer
Intent 与 Canonical Thinking 是 Java Interview 特有的概念（面试官意图分析
与内部思维框架），English 的 Question → Answer → Conversation 模型不存在
对应的"面试官视角分析"阶段（第 4.2 节 Step1 是 Review 而非分析），因此没有
可类比的字段需要新增。两个系统在设计原则上仍然一致——都遵循"第一部分定义
必须持久化哪些内容，第二部分按模板存档"的同一模式（English 侧此原则已由
V11.10 English Learning Template 体现），只是具体字段因领域不同而不同，
无需为了表面对称而在 English 侧添加无意义字段。

**V11.18 是冻结后的架构变更（Architecture Change，非执行改进）：为第 7 节
Priority-Based Review Engine 新增"7 天 Active Window 分层"。** 用户提出
英语与 Java 均改为"只复习最近 7 天内学习的内容，超过 7 天自动移出，不再
随机复习旧内容，除非用户明确要求 full review"的滚动窗口规则，并声明为
永久 maintainer 规则。审计发现直接冲突：第 7 节 Priority-Based Review
Engine 明确设计成按 Mastery Status + Learning Recency 优先级抽样，第
13.1 节已有的机制说明原文即写明"而不是单纯按引入时间截取最近 5
个——避免仍标记为 Needs Review / 表现不稳定的旧内容被纯时间窗口永久排
除"；用户提议的纯 7 天截断会直接推翻这一已冻结设计的核心理由，且会削弱
第 9.1 节 Mastery Criteria（内容一旦超过 7 天不再被抽到，可能永远无法
积累"跨 Session 持续稳定表现"从而升级为 Mastered）。已通过
AskUserQuestion 向用户说明冲突并提供三个方案，用户选择推荐的**分层
方案**：7 天窗口成为默认的高频复习池（日常 Random Review / Combined
Questions / Java Random Review 优先从窗口内抽取），窗口外内容不退出
复习体系，而是继续由第 7 节既有 Priority-Based Review Engine 做低频
抽查（沿用第 13.1 节原本就对"已 Mastered 内容"采用的低优先级长期抽查
节奏，本次将其适用范围从"仅 Mastered"扩展到"任何窗口外内容"）；用户
显式要求"全面复习 / full review"时，不受 7 天窗口限制，按第 7 节完整
优先级集合执行。Java 新场景/新 Question 引入节奏（用户原话"每天引入一个
新 Java 面试题"）与第 5.1 节既有"每 Session 新增一个 Interview
Question"实质等价（Session 近似按天进行），未修改第 5.1 节。具体修补：
第 7 节新增"7-Day Active Window 分层规则"小节（英语、Java 各一条，均为
分层，不替换既有 Priority-Based Review Engine 本身）；未改变 Session
Workflow（第 8 节）、Mastery Criteria（9.1 节）措辞、Step1–Step5
流程、Output Format（第 10 节）。第 13.1 节机制说明与当前窗口快照同步
更新（Part 2 执行层数据，随每个 Session 常规更新，不属于本次版本历史的
一部分）。

**V11.19 是冻结后的架构变更（Architecture Change，非执行改进）：引入 Level
System、Daily Native Expressions 模块，重构第 4.2 节 Session 流程为六步，
并将 Java Interview 移出每日固定环节。** 用户提交一份 Session 12 学习总结，
其中"新永久课程规则"部分提出四项与已冻结架构直接相关的变更，逐项审计并已
通过 AskUserQuestion 与用户确认处理方式：

1. **Level 1 → Level 2 → Level 3 进度体系**——现有架构中 Topic 只有第 4.1
   节固定 5 组 Q&A + 第 9 节 Mastery Status（New/Practicing/Mastered）两层，
   没有"同一 Topic 内容由简到繁分层"的概念。用户确认这是真正的新机制，采纳为
   第 4.1 节新增小节：Level 1（入门，简单单句 Answer）→ Level 2（每个 Answer
   +1 句）→ Level 3（规则留待学员实际进入该阶段后再定义，不预先编造，沿用
   V11.10 起"不臆测未提供内容"的既有惯例）。Level 与 Mastery Status 是两个
   独立维度，不合并、不互相替代。
2. **Daily Native Expressions 模块**——与 Topic-based Question/Answer 系统
   并列的全新内容流，现有第 4 节完全没有为其定义规则。采纳为新增第 4.5
   节，复用第 4.1 节 English Learning Template 记录格式与第 9 节 Mastery
   Status 四值词汇，不新增状态值，不新增独立的 Review 引擎（与英语 Topic
   共享第 7 节 Priority-Based Review Engine + 7-Day Active Window）。
3. **六步 Session 流程**（Review 昨天 Topic → Review 昨天 Daily Native
   Expressions → 7 天随机复习 → 学今天新 Topic Level1 → 学今天 Daily Native
   Expressions → 生成总结）——与第 4.2 节既有 5 步结构（Review /
   Conversation / Today's Lesson / Practice / Mixed Conversation）不同。
   审计确认新六步是对既有执行机制的重新分组与顺序明确化，而不是发明新机制：
   Chinese Prompt Method、随机顺序提问、2–4 合并提问、Role Switch/Free
   Conversation、Immediate Reinforcement、Today's Final Review 等第 4.2 节
   原有机制全部保留，只是重新归入新的 Step 编号之下。第 4.2 节整体按此重写。
4. **Java Interview 移出每日固定流程**——新六步流程完全没有提到 Java，用户
   确认这是有意为之：Java 正式从"每个 Session 默认包含"改为"学员另行安排/
   明确要求才进行"的独立模块，其余 Java 规则（第 5.1/5.2 节 Interview
   Topic/Question 结构、Step1–Step5 三轮流程、第 6 节 Canonical Answer 相关
   规则）本身不变，只是触发时机与英语 Session 解耦。第 3/5/8 节相应调整
   Java 与英语 Session 的关系描述。

另确认一项与第 7 节已冻结的 Priority-Based Review Engine + V11.18 7 天窗口
分层机制的冲突：用户提出的"7 天内随机复习需覆盖完整题库才可重复"与
Mastery+Recency 优先级选题算法存在张力（同类冲突在 V11.18 已出现过一次）。
已通过 AskUserQuestion 确认采用叠加式方案（与 V11.18 处理方式一致）：保留
既有 Mastery+Recency 优先级选题算法作为选题依据，新增"轮内去重"细则——
同一轮 Step3 随机复习内避免立即重复同一题，直到窗口内其它内容至少被问过
一轮才允许重复；不要求"覆盖完整题库"（题库会持续增长，第 7 节已有说明解释
了为何不要求全量复习）。写入第 7 节新增小节。

另确认一处数据顺序问题：Topic 9（Travel）仍为 Practicing，但 Topic
10（Technology）已经开始且标记"Level 1 Graduated"，与第 4.4 节既有"当前
Topic 完成（Mastered）才能进入下一个 Topic"的规则冲突。已通过
AskUserQuestion 确认：这正是 Level System 生效后的预期行为——第 4.4 节
拆分为"Topic 推进门槛"（完成 Level 1 即可开始下一个新 Topic）与"Topic
完全完成标准"（仍要求所有 Question 达到 Mastered，判定标准本身不变）两层，
已开始新 Topic 后，此前 Topic 仍需继续通过 Review 循环推进到更高 Level 并
最终达到完全完成标准。

本次修补涉及第 3、4.1、4.2、4.4、4.5（新增）、5、5.1、7、8、9.1 节，均为
最小、可加性修改或结构重排——不改变第 6 节 AI Behavior 现有规则、不改变第
9 节 Mastery Status 四值词汇、不改变第 10 节 Output Format、不改变 Java
Step1–Step5 流程本身。版本由 V11.18 推进至 V11.19。

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
- 每天新增内容量固定为小份：英语 Topic 新内容按第 4.1 节 Level System 分层
  引入（Level 1 简化版 Q&A，Level 2/3 逐步加深）；Daily Native Expressions
  每天固定新增约 3 句（见第 4.5 节）；Java Interview 不再是每日固定环节，
  改为学员另行安排/明确要求时进行，每次仍只学习 1 个 Interview Question
  （见第 5 节）。
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
  Session 内，今天新引入的英语 Question 必须先完成第 4.2 节 Step4 之后
  的 Immediate Reinforcement（Individual Review / Random Review / Combined
  Questions），达到"正确、流利、自然、无明显犹豫"后，才可以进入 Step5/
  Step6；若同一次对话内还安排了 Java Interview 练习（第 5 节，V11.19 起
  非默认环节），同样需在该次 Java 练习开始前完成本条强化。本强化不是
  Mastery——Mastery 判定仍以第 9.1 节 Mastery Criteria 为准，Topic 完成
  标准仍以第 4.4 节为准，Progress Rules（第 9 节）不因本条改变。
- **Session Context Grounding（Session 启动前必须加载当前学习状态，防止
  超纲提问）** — 每个 Session 开始时，AI 必须先加载并明确当前状态：第 13
  节 Current Session（当前 English Topic / Daily Native Expressions 列表、
  Java Interview Topic/Question——若本次安排了 Java）、第 11 节 English
  Conversation Bank 中已学 Topic 与 Question、第 11 节 Daily Native
  Expressions Bank 中已学表达、第 12 节 Java Answer Bank 中已学 Interview
  Question。此后本 Session/Java 练习内任何步骤中 AI 提出的问题，必须逐字或
  语义等价于已加载的 Bank 内容，禁止改写、扩写、临场编造"相似"或"顺理成章"
  的新问题（例如已学"Why are you learning English?"不得改问成"Why do you
  want to work for an international company?"；已学 Daily Routine 的 get
  up/go to bed 不得改问"What time do you usually go to work?"）。只有第
  4.2 节 Step4（学今天新 Topic）与 Step5（学今天 Daily Native Expressions）
  明确进入引入新内容环节时，才允许引入新问题。本规则是对既有"超纲"禁止
  （第 6 节）与 Bank-only 限制（第 4.2 节）的启动前置保证，不改变这些规则
  本身。

## 4. English System（英语系统）

彻底取消 Vocabulary Learning、Grammar Learning、Sentence Learning 作为独立模块。
以后所有英语学习，全部围绕：

```
Question → Answer → Conversation → Automatic Response
```

### 4.1 每日新增（Level System，V11.19 起生效）

Topic 内容不再要求一次性引入完整难度的内容，而是按 **Level 体系** 分阶段
引入与加深：

- **Level 1（入门）**：为该 Topic 新增一组简单 Q&A（数量按当天实际内容确定，
  通常 5–6 组），必须属于同一个 Topic，每个 Answer 为单句、简单直接，目标是
  先建立最基础的自动反应，而不是学习完整难度的表达。完成 Level 1 初次练习
  流利后，即满足第 4.4 节"可以开始下一个新 Topic"的门槛（见第 4.4 节 Topic
  推进门槛，不再要求 Mastered）。
- **Level 2（加深，第一层扩展）**：在已完成 Level 1 的 Topic 基础上，为每个
  Answer 增加一句话（每个 Answer 恰好 +1 句），使回答更完整、更接近真实
  表达，仍保持简单直接、不引入复杂从句。
- **Level 3（进一步加深）**：在 Level 2 基础上继续扩展的下一层级，具体规则
  与内容深度待学员实际进入该阶段后由学员与 AI 共同确定并补充到本节，本文件
  暂不预先定义，避免凭空编造未验证的规则。

Level 与第 9 节 Mastery Status 是两个独立维度：Level 描述"当前练习的是哪一层
难度的内容"，Mastery Status 描述"当前这一层内容是否已经稳定掌握（跨 Session
持续正确）"。同一 Topic 可以同时记录当前 Level 与当前 Mastery Status；进入
更高 Level 后，该 Level 的新增内容需重新经历 Practicing 阶段直至满足第 9.1
节标准，不因此前 Level 已 Mastered 而自动继承。

示例 Topic 池（可扩展）：Self Introduction / Work / Travel / Restaurant /
Phone Call / Meeting / English Learning 等。

**English Learning Template（固定模板，此后每次新增内容均按此格式呈现/记录，
仅对未来新增内容生效，不回填已记录的历史条目）：**

- Question：English / 中文翻译 / 国际音标（IPA）/ 中文谐音标注
- Standard Answer：English / 中文翻译 / 国际音标（IPA）/ 中文谐音标注
- 每个新增词汇：English / 中文含义 / 国际音标（IPA）/ 中文谐音标注
- 每个例句：English / 中文翻译

本模板用于提升发音准确度、理解与长期肌肉记忆，不改变每日新增数量（Level 1
通常 5–6 组，具体见上方 Level System）、Topic 结构，也不改变第 3 节 Voice
First 的优先级——书面模板仍只是语音练习的辅助确认材料。第 4.5 节 Daily
Native Expressions 同样沿用本模板记录格式。

### 4.2 固定流程（V11.19 起，六步流程；每个 Session 结束时输出 Step6 总结）

**提问机制（跨 Step1–Step3 通用，均为第 4.2 节原有机制，本次改版只调整了
执行顺序与 Step 划分，机制本身未改变）**：
- 选出的内容必须以**随机顺序**提问，不得按 Topic/Bank 原始顺序依次提问
  （例如 Topic2 → Topic1 → Topic3 → Topic1 …），避免靠"顺序"而不是"自动
  反应"答题。
- AI 有时可将 **2–4 个已学 Question/Expression 合并成一句话一起问**（例如
  "What's your name, and where are you from?"），次数随机，不必每次只问
  一个。
- 同样采用**双向提问**：多数时候 AI 问、我答；也要随机出现我问、AI 答，
  训练听与说两个方向——**Role Switch（角色互换）**：我向 AI 提问，AI 回答
  （Question Muscle）；**Free Conversation（自由对话）**：双方自然互相
  提问、互相回答。只能使用已经学习过的内容，任何一方都不得引入尚未学过的
  新内容。
- **Chinese Prompt Method（默认触发方式）**：AI 默认只给出**中文提示**
  （该 Question/Expression 的中文含义），不直接给出英文原文；由我自己先
  构造英文 Question，再自己给出英文 Answer（Question → Answer 连续说
  出）。AI 在我尝试之前不得提前给出英文原文，只有在我回答完毕后才可以用
  中文讲解纠错（呼应第 3 节 Voice First）。此模式同时训练 Question Muscle
  与 Answer Muscle。AI 仍可随机穿插直接用英文提问的方式变换节奏，Combined
  场景下也可一次给出 2–4 个中文提示，但 Chinese Prompt 为默认方式。
- **English Question Mode Progression（Chinese Prompt Method 的阶段推进，
  不再依赖 AI 临场判断）**：
  - **Stage A（默认）**：适用于尚未完成 Step4/Step5 Immediate
    Reinforcement + Today's Final Review 的内容。AI 只给中文提示，我自己
    说出英文 Question 与 Answer。
  - **Stage B（触发条件：该内容已完成 Immediate Reinforcement + Today's
    Final Review，进入第 7 节正常 Review 轮换）**：改为 AI 直接用英文
    提问、我直接用英文回答，不再提供中文提示，呼应第 9.1 节 English
    Mastered "不经过翻译"的要求。
  - **Stage C（进度终点标注）**：Role Switch / Free Conversation，全程
    英文，不引入中文提示或翻译。
- 我用语音回答（Voice First，见第 3 节）。回答完毕后，若完全正确，AI 按第
  6 节 Correct Fast-Path Rule 简短确认后立即进入下一题；若存在语法/用词/
  表达/发音问题，AI 按顺序检查：语法 → 用词 → 表达是否自然 → 发音提示
  （如需要）→ 流利度，立即纠正错误，禁止把错误的英文变成肌肉记忆（呼应第
  6 节 Accurate Feedback Rule）。我重复练习，直到回答正确为止。

1. **Step1 — Review 昨天的 Topic**
   - 优先复习上一个 Session 新学的 Topic（呼应第 7 节 Priority-Based
     Review Engine 中"最近一个 Session 新学的 Question"最高优先级），
     确保刚学的内容不会被跳过，方式沿用上方"提问机制"。

2. **Step2 — Review 昨天的 Daily Native Expressions**
   - 复习上一个 Session 新学的 Daily Native Expressions（见第 4.5 节），
     方式同上方"提问机制"。

3. **Step3 — 最近 7 天随机复习**
   - AI 按第 7 节 Review Rules 定义的优先级 Review Engine（Mastery Status
     + Learning Recency + 7-Day Active Window，见第 7 节）智能选出本次要
     复习的内容集合（覆盖范围规则见第 7 节 Coverage Rule 与"轮内去重
     规则"），涵盖英语 Topic 与 Daily Native Expressions，方式沿用上方
     "提问机制"。
   - 目标同时是自动反应（Automatic Response），随机混合"最近内容"与"更早
     内容"，不是死记硬背。

4. **Step4 — 学习今天的新 Topic（Level 1）**
   - 新增一个 Topic 的 Level 1 内容（见第 4.1 节 Level System），必须属于
     同一个 Topic。
   - AI 逐个提出新 Question，我回答，AI 立即纠正错误，重复练习直到回答
     流利为止。
   - **Immediate Reinforcement Rule（同 Session 即时强化，非 Mastery，见
     第 3 节）**：初次练习流利后，AI 必须继续对今天新学的全部 Question 做
     同 Session 强化，包括：Individual Review（逐个重新提问今天新学的全部
     Question）、Random Review（随机顺序提问，不按今天引入顺序）、
     Combined Questions（随机合并 2–4 个今天新学的 Question 一起问，复用
     上方"提问机制"的合并机制）。强化持续到今天新学的全部 Question 都能
     正确、流利、自然、无明显犹豫地回答为止，才可以进入 **Today's Final
     Review**：AI 只给中文提示（复用上方 Chinese Prompt Method），我需对
     今天新学的每一个 Question 独立说出英文 Question 与英文 Answer，全部
     通过后才可以进入 Step5。达到本条标准即满足第 4.4 节"Topic 推进门槛"
     （Level 1 完成，可以开始下一个新 Topic），但仍标记为 Practicing，不
     因此改变第 9.1 节 Mastery 判定或第 4.4 节 Topic 完全完成标准。

5. **Step5 — 学习今天的 Daily Native Expressions**
   - 新增当天的 Daily Native Expressions（见第 4.5 节），流程同 Step4——
     逐句练习 → AI 立即纠正 → 重复至流利 → Immediate Reinforcement/
     Today's Final Review 验证 → 全部通过后标记 Graduated（见第 4.5 节）。

6. **Step6 — 生成 Today's Learning Summary**
   - Session 结束时输出学习总结，对应第 10 节 Output Format 的既有目标。

**Java Interview（V11.19 起非默认环节）**：Java Interview 练习不包含在
上方六步流程内，改为学员另行安排/明确要求时进行的独立模块，规则见第 5
节；若同一次对话内还安排了 Java 练习，第 3 节 Immediate Reinforcement 仍
需先于该次 Java 练习完成。

### 4.3 课程比例

- 80% Review（Step1–Step3）
- 20% 新内容（Step4–Step5：新 Topic Level1 + Daily Native Expressions）

### 4.4 Topic Completion（Topic 完成标准，V11.19 起分为两层）

**Topic 推进门槛（可以开始下一个新 Topic 的条件）**：一个 Topic 完成第 4.2
节 Step4 标准的 Level 1 内容初次流利练习后，即可开始下一个新 Topic 的 Level
1 内容（第 4.2 节 Step4），不再要求先达到 Mastered。已开始新 Topic 后，此前
的 Topic 仍需继续通过第 4.2 节 Step1/Step3 的复习循环推进到 Level 2、Level 3
（见第 4.1 节 Level System），并最终达到下方"Topic 完全完成"标准。

**Topic 完全完成（Fully Completed）标准（判定标准本身不变，只是与上方推进
门槛分离）**：一个 Topic 只有在其下所有 Question（含 Level 2/3 加深后的
内容）都达到 Mastered 状态（见第 9.1 节 Mastery Criteria）后，才算完全完成。
是否达到完全完成不影响是否可以开始新 Topic（该门槛已改为上方 Level 1），
但仍是长期追踪该 Topic 是否真正建立跨 Session 稳定自动反应的标准。

### 4.5 Daily Native Expressions（V11.19 新增，与 Topic 系统并列的独立内容流）

与 Topic-based Question/Answer 系统并列，训练日常最自然、最地道的英语表达
（围绕真实生活场景的陈述句，而不是面试问答式的 Q&A）。

**每日新增**：固定新增约 3 句 Daily Native Expressions，围绕同一个真实生活
场景（例如今天的起床流程）。记录格式沿用第 4.1 节 English Learning
Template（English / 中文翻译 / IPA / 中文谐音）。

**学习流程**：与第 4.2 节 Step5 一致——逐句练习 → AI 纠正语法/介词/用词
错误 → 重复练习至流利 → Immediate Reinforcement（Individual Review /
Random Review）→ Today's Final Review 验证 → 全部通过后标记为 Graduated
（Day N Graduated）。

**Graduated 判定标准**：与第 9.1 节 English Mastered 判定原则一致——需要
至少完成 3 轮 Review 且能不经翻译自然回应，才可标记为该 Day 已 Graduated；
同 Session 内首次流利只是初步达标，最终判定仍遵循第 9.1 节的跨 Session
稳定要求（若后续 Session 复习中出现反复错误，应回退为 Practicing 状态并
重新计入第 7 节复习优先级）。

Daily Native Expressions 与英语 Topic 共享同一个第 7 节 Review Rules
（Priority-Based Review Engine + 7-Day Active Window），按 Day 为单位管理
Mastery Status（New / Practicing / Mastered，沿用第 9 节既有词汇表，不
新增状态值）。

## 5. Java System（Java 系统）

前 90 天全部使用中文。目标是形成中文 Java 面试回答肌肉记忆，不是英文面试。

**Java 不再是每日固定环节（V11.19 起）**：自 V11.19 起，Java Interview
练习不再自动包含在第 4.2 节的六步 Session 流程内，改为学员另行安排/明确
要求时才进行的独立模块。当学员明确开始一次 Java Interview 练习时，仍完整
遵循下方 5.1/5.2 节的 Interview Topic/Question 结构与 Step1–Step5 三轮
流程，第 6 节 Java Canonical Answer Rule / Senior CTO Thinking Rule /
Java Interview Language Rule 等既有内容规则不变。

**启动条件**：若某次对话内同时安排了英语 Session 与 Java Interview 练习，
Java 部分必须在第 3 节 Immediate Reinforcement 完成后才能开始（今天新学的
英语 Question 已通过 Individual Review / Random Review / Combined
Questions 强化，见第 4.2 节 Step4）；若该次对话只进行 Java 练习、未安排
英语 Session，则本条不适用。

**训练目标**：目标不是背诵标准答案，而是训练面试思维——识别面试官真正
在考察什么、快速组织回答结构、在忘记细节时也能继续说下去而不卡壳、自信
自然地表达而不是背稿。学员最大的弱点通常不是技术知识本身，而是忘词、
卡壳、丢失回答结构、紧张。因此训练应持续围绕：结构化表达、保持语流、
使用过渡句、忘记细节后的恢复、保持自信——面试流畅度与临场应变，与内容
准确度同等重要。

### 5.1 每 Session 内容

一个 **Interview Topic**（例如 Redis / JVM / Spring / Kafka / MySQL / MQ /
缓存 / 高并发 / 微服务 / 订单系统 / 支付系统 / 区块链 等）下包含多个
**Interview Question**。**每次 Java Interview 练习只学习一个 Interview
Question**（V11.19 起不再与英语 Session 一一绑定，见第 5 节开头），不在
一次练习内学习整个 Topic。例如：

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

**Scenario Interview Mode（V11.16 起默认生效）**：Interview Topic "Java
Basics" 下的两个基础问题（What is Java? / Why do you use Java?）均已完成
Step5 并锁定 Final Answer（第 6 节 Java Canonical Answer Rule），该 Topic
不再作为每日新内容来源，两个问题永久保留在 Random Review 池中（第 5.3/7
节），与本节既有"Topic 内全部 Question 完成后进入下一 Topic"规则一致。此
后新引入的 Interview Topic 默认均为场景型（Scenario）——即真实生产/业务
场景问题（例如"API 响应时间从 50ms 突增到 3 秒，作为 on-call 工程师你会
如何处理？"），对应第 5.2 节 Step1 框架表中的"场景型"框架（Problem →
Analysis → Solution → Result）。每个 Session 仍只新增一个 Interview
Question（不变），不得在同一 Session 内引入多个新场景。

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
   作为当前最佳答案，保存到 Java Answer Bank；保存时须将 Step1 的
   Interviewer Intent 分析与 Canonical Thinking 一并存入（V11.17，见第 6
   节 Canonical Thinking Rule 与第 12 节 Scenario 记录格式），不得只保存
   最终答案本身。

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

**Canonical Answer Style Rule（Canonical Answer 表达风格永久规则，V11.16
新增）**：Canonical Answer（第 5.2 节 Step2 参考答案与第 12 节 Final
Answer）必须听起来像真实 Senior 工程师在自然说话，而不是背诵模板。要求：
自然口语化表达；禁止"First... Second... Third..."式的显式编号罗列；逻辑
清晰但不生硬，符合真实对话节奏；时长约一分钟；体现真实生产环境经验；适合
Senior / Tech Lead 级别面试。目标是"自然地思考，而不是自然地背诵"。本规则
约束的是回答的表达风格，不改变 Senior / CTO Thinking Rule 已规定的内容
深度要求，两者共同适用、互不冲突。

**Canonical Thinking Rule（内部思维模型永久规则，V11.16 新增）**：每个
Interview Question 存在两层：Layer 1 是 Canonical Answer（学员实际说出的
内容，受上方 Canonical Answer Style Rule 约束）；Layer 2 是 Canonical
Thinking（AI 在第 5.2 节 Step1 用于生成/评分参考答案的内部思维框架，例如
场景型问题的 Impact Assessment → Business Recovery → Root Cause Analysis
→ Recovery Validation → RCA / Long-term Prevention）。Canonical Thinking
永远不得在面试作答中被直接说出或列举为显式框架清单，学员应当围绕该框架
自然组织语言，而不是复述框架本身。本规则不改变第 5.2 节 Step1 框架表的
内容或数量，只明确该框架属于内部思维层，不属于口语输出层。自 V11.17
起，Canonical Thinking 与 Step1 的 Interviewer Intent 分析必须与
Canonical Answer 一并永久存入第 12 节（见 Scenario 记录格式），防止同一
Interview Question 在不同 Session 被重新生成出不同版本的内部框架，呼应
Java Canonical Answer Rule 的永久性目标。

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
- **7-Day Active Window 分层规则（V11.18，英语 + Java 均适用，叠加在上方
  Priority-Based Review Engine 之上，不替换其本身）**：
  - 最近 7 天内学习/引入的 English Topic 与 Java Interview
    Question/Scenario 组成"7 天窗口"，作为日常 Random Review / Combined
    Questions / Java Random Review 的**默认高频复习池**——日常复习优先
    从窗口内抽取。
  - 超过 7 天的内容**不退出复习体系**，而是继续按上方 Priority-Based
    Review Engine 的 Mastery Status + Learning Recency 优先级表处理，
    但采用低频抽查节奏（与既有对"已 Mastered 内容"的低优先级长期抽查
    节奏相同，本条将该低频节奏的适用范围从"仅 Mastered"扩展到"任何
    窗口外内容"）——标记为 Needs Review / Practicing 的窗口外内容仍会
    被低频抽到，不会被 7 天窗口永久排除。
  - 学员显式要求"全面复习 / full review"时，不受 7 天窗口限制，按
    Priority-Based Review Engine 的完整集合执行。
  - 本规则不改变 Mastery Status 判定标准（9.1 节）、Session Workflow
    （第 8 节）、Java 每次学习一个 Interview Question 的节奏（5.1 节）。
- **轮内去重规则（V11.19，叠加在上方 7-Day Active Window 与
  Priority-Based Review Engine 之上，不替换其选题算法本身）**：第 4.2 节
  Step3 同一轮随机复习中，避免立即重复同一 Topic/Question/Daily Native
  Expressions，直到窗口内其它内容都至少被问过一轮，才允许重复；窗口内
  内容较少、不足以支撑"问一轮不重复"时，可按既有 Priority-Based Review
  Engine 优先级正常重复。本规则不改变窗口外内容的低频抽查机制，也不要求
  "覆盖完整题库"——题库会随学习进度持续增长，第 7 节上方已有说明解释了为
  何不要求全量复习。

## 8. Session Workflow（Session 工作流程）

取消 Day 概念，统一采用 **Session**。Session 不等于一天，只有真正掌握才能
进入下一 Session。英语 Session 遵循第 4.2 节六步流程；Java Interview 练习
为独立模块（第 5 节，V11.19 起），按学员安排单独进行，不与英语 Session 的
六步流程绑定。

每个 Session/Java 练习结束时输出（见第 10 节 Output Format）。

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

**Level 与 Mastered 的关系（V11.19）**：以上标准适用于当前所处的具体 Level
（见第 4.1 节 Level System）。Topic 进入更高 Level 后，该 Level 新增的内容
需重新经历 Practicing 阶段直至满足以上三条，不因较低 Level 已 Mastered 而
自动继承或跳过判定。

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

### 11.1 English Topic Bank

记录格式（V11.10 起，按第 4.1 节 English Learning Template 扩展；V11.19
起新增 Level 字段，见第 4.1 节 Level System；仅对未来新增内容生效，不回填
本节已有的历史条目）：

```
Topic:
Level: 1 / 2 / 3（见第 4.1 节 Level System）
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

以下为 V11.10 之前记录的历史条目，沿用旧格式，不追溯改写（Level 字段自
Topic 10 起才开始记录，Topic 1–9 均为 Level 1 阶段的既有内容，未显式标注
Level，不影响其 Mastery Status 判定）：

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

Topic: Family

1.
Question:
  - English: Do you have a family?
  - 中文翻译: 你有家庭吗？
  - IPA: /duː juː hæv ə ˈfæməli/
  - 中文谐音: 度 尤 哈夫 尔 法弭力
Standard Answer:
  - English: Yes, I do. I have a happy family.
  - 中文翻译: 是的，我有一个幸福的家庭。
  - IPA: /jes aɪ duː aɪ hæv ə ˈhæpi ˈfæməli/
  - 中文谐音: 耶斯 埃 度 埃 哈夫 尔 黑皮 法弭力
Mastery Status: Practicing

2.
Question:
  - English: How many people are there in your family?
  - 中文翻译: 你家里有几口人？
  - IPA: /haʊ ˈmeni ˈpiːpəl ɑː ðeər ɪn jɔː ˈfæməli/
  - 中文谐音: 好 美尼 皮泼 阿 淝儿 因 尤 法弭力
Standard Answer:
  - English: There are three people in my family.
  - 中文翻译: 我家有三口人。
  - IPA: /ðeər ɑː θriː ˈpiːpəl ɪn maɪ ˈfæməli/
  - 中文谐音: 淝儿 阿 斯瑞 皮泼 因 买 法弭力
Mastery Status: Practicing

3.
Question:
  - English: Who do you live with?
  - 中文翻译: 你和谁一起住？
  - IPA: /huː duː juː lɪv wɪð/
  - 中文谐音: 呼 度 尤 立弗 威兹
Standard Answer:
  - English: I live with my wife.
  - 中文翻译: 我和我妻子一起住。
  - IPA: /aɪ lɪv wɪð maɪ waɪf/
  - 中文谐音: 埃 立弗 威兹 买 歪弗
Mastery Status: Practicing

4.
Question:
  - English: What does your wife do?
  - 中文翻译: 你妻子是做什么工作的？
  - IPA: /wɒt dʌz jɔː waɪf duː/
  - 中文谐音: 沃特 达兹 尤 歪弗 度
Standard Answer:
  - English: She is a teacher.
  - 中文翻译: 她是一名老师。
  - IPA: /ʃiː ɪz ə ˈtiːtʃə/
  - 中文谐音: 希 伊兹 尔 提切
Mastery Status: Practicing

5.
Question:
  - English: Do you often spend time with your family?
  - 中文翻译: 你经常和家人在一起吗？
  - IPA: /duː juː ˈɒfən spend taɪm wɪð jɔː ˈfæməli/
  - 中文谐音: 度 尤 欧分 斯奔德 太姆 威兹 尤 法弭力
Standard Answer:
  - English: Yes, I do. I often spend time with my family.
  - 中文翻译: 是的，我经常和家人在一起。
  - IPA: /jes aɪ duː aɪ ˈɒfən spend taɪm wɪð maɪ ˈfæməli/
  - 中文谐音: 耶斯 埃 度 埃 欧分 斯奔德 太姆 威兹 买 法弭力
Mastery Status: Practicing

Topic: Food

1.
Question:
  - English: What is your favorite food?
  - 中文翻译: 你最喜欢的食物是什么？
  - IPA: /wɒt ɪz jɔː ˈfeɪvərɪt fuːd/
  - 中文谐音: 沃特 伊兹 尤 费沃瑞特 福德
Standard Answer:
  - English: My favorite food is hot pot.
  - 中文翻译: 我最喜欢的食物是火锅。
  - IPA: /maɪ ˈfeɪvərɪt fuːd ɪz hɒt pɒt/
  - 中文谐音: 买 费沃瑞特 福德 伊兹 哈特 帕特
Mastery Status: Practicing

2.
Question:
  - English: What food do you eat most often?
  - 中文翻译: 你最常吃什么食物？
  - IPA: /wɒt fuːd duː juː iːt məʊst ˈɒfən/
  - 中文谐音: 沃特 福德 度 尤 意特 莫斯特 欧分
Standard Answer:
  - English: I eat rice most often.
  - 中文翻译: 我最常吃米饭。
  - IPA: /aɪ iːt raɪs məʊst ˈɒfən/
  - 中文谐音: 埃 意特 莱斯 莫斯特 欧分
Review History: Session 9 — 本次 Review 实际使用的提问是 "What do you usually
  eat?"（非本条 Canonical Question），未据此覆盖或修改上方 Canonical
  Question；今后 Review 仍以本条已存 Canonical Question 为准，除非用户明确
  要求修订。
Mastery Status: Practicing

3.
Question:
  - English: Can you cook?
  - 中文翻译: 你会做饭吗？
  - IPA: /kæn juː kʊk/
  - 中文谐音: 坎 尤 库克
Standard Answer:
  - English: Yes, I can. I can cook simple meals.
  - 中文翻译: 是的，我会。我会做简单的饭菜。
  - IPA: /jes aɪ kæn aɪ kæn kʊk ˈsɪmpəl miːlz/
  - 中文谐音: 耶斯 埃 坎 埃 坎 库克 森泼 米尔兹
Mastery Status: Practicing

4.
Question:
  - English: What do you usually drink?
  - 中文翻译: 你通常喝什么？
  - IPA: /wɒt duː juː ˈjuːʒuəli drɪŋk/
  - 中文谐音: 沃特 度 尤 尤磁尤力 追恩克
Standard Answer:
  - English: I usually drink water.
  - 中文翻译: 我通常喝水。
  - IPA: /aɪ ˈjuːʒuəli drɪŋk ˈwɔːtə/
  - 中文谐音: 埃 尤磁尤力 追恩克 沃特
Mastery Status: Practicing

5.
Question:
  - English: Do you like spicy food?
  - 中文翻译: 你喜欢吃辣的食物吗？
  - IPA: /duː juː laɪk ˈspaɪsi fuːd/
  - 中文谐音: 度 尤 莱克 斯派西 福德
Standard Answer:
  - English: I like spicy food very much.
  - 中文翻译: 我非常喜欢吃辣的食物。
  - IPA: /aɪ laɪk ˈspaɪsi fuːd ˈveri mʌtʃ/
  - 中文谐音: 埃 莱克 斯派西 福德 维瑞 玛奇
Mastery Status: Practicing

Topic: Shopping

1.
Question:
  - English: Where do you usually go shopping?
  - 中文翻译: 你通常在哪里购物？
  - IPA: /weər duː juː ˈjuːʒuəli ɡəʊ ˈʃɒpɪŋ/
  - 中文谐音: 威尔 度 尤 尤磁尤力 果 沙鄙
Standard Answer:（本 Session 未逐字记录标准答案，下次 Session 确认后补全）
Mastery Status: Practicing
Review History: Session 10 — 语法纠正："I usually shopping..." → "I usually
  go shopping..."。

2.
Question:
  - English: How often do you go shopping?
  - 中文翻译: 你多久购物一次？
  - IPA: /haʊ ˈɒfən duː juː ɡəʊ ˈʃɒpɪŋ/
  - 中文谐音: 好 欧分 度 尤 果 沙鄙
Standard Answer:（本 Session 未逐字记录标准答案，下次 Session 确认后补全）
Mastery Status: Practicing

3.
Question:
  - English: What do you usually buy?
  - 中文翻译: 你通常买什么？
  - IPA: /wɒt duː juː ˈjuːʒuəli baɪ/
  - 中文谐音: 沃特 度 尤 尤磁尤力 拜
Standard Answer:（本 Session 未逐字记录标准答案，下次 Session 确认后补全）
Mastery Status: Practicing

4.
Question:
  - English: Do you like shopping online?
  - 中文翻译: 你喜欢网上购物吗？
  - IPA: /duː juː laɪk ˈʃɒpɪŋ ˈɒnˌlaɪn/
  - 中文谐音: 度 尤 莱克 沙鄙 昂来恩
Standard Answer:（本 Session 未逐字记录标准答案，下次 Session 确认后补全）
Mastery Status: Practicing
Review History: Session 10 — 语法纠正："I like shop online..." → "I like
  shopping online..."。

5.
Question:
  - English: Do you usually pay by cash or by card?
  - 中文翻译: 你通常用现金还是刷卡支付？
  - IPA: /duː juː ˈjuːʒuəli peɪ baɪ kæʃ ɔː baɪ kɑːd/
  - 中文谐音: 度 尤 尤磁尤力 佩 拜 卡什 哦 拜 卡德
Standard Answer:（本 Session 未逐字记录标准答案，下次 Session 确认后补全）
Mastery Status: Practicing

Topic: Weather

1.
Question:
  - English: What's the weather like today?
  - 中文翻译: 今天天气怎么样？
  - IPA: /wɒts ðə ˈweðə laɪk təˈdeɪ/
  - 中文谐音: 沃茨 泽 威泽 莱克 特得
Standard Answer:
  - English: The weather is sunny today. It's warm and comfortable.
  - 中文翻译: 今天天气晴朗，天气温暖而且很舒服。
  - IPA: /ðə ˈweðə ɪz ˈsʌni təˈdeɪ. ɪts wɔːm ənd ˈkʌmftəbl/
  - 中文谐音: 泽 威泽 伊兹 桑尼 特得。伊茨 沃姆 安德 康福特布
Mastery Status: Practicing

2.
Question:
  - English: Do you like sunny weather?
  - 中文翻译: 你喜欢晴天吗？
  - IPA: /duː juː laɪk ˈsʌni ˈweðə/
  - 中文谐音: 杜 优 莱克 桑尼 威泽
Standard Answer:
  - English: Yes, I do. I like sunny weather because I can go outside.
  - 中文翻译: 是的，我喜欢晴天，因为我可以出去。
  - IPA: /jes aɪ duː. aɪ laɪk ˈsʌni ˈweðə bɪˈkɒz aɪ kən ɡəʊ ˌaʊtˈsaɪd/
  - 中文谐音: 耶斯 艾 杜。艾 莱克 桑尼 威泽 比考兹 艾 肯 高 奥特赛德
Mastery Status: Practicing
Review History: Session 9 — 本 Session 出现一次 Topic Interference：错误回答
  "Yes, I do. I like sunny weather because it's convenient."，已纠正并最终
  稳定为上方 Standard Answer（"...because I can go outside."），Standard
  Answer 本身未被修改。

3.
Question:
  - English: Do you like rainy weather?
  - 中文翻译: 你喜欢雨天吗？
  - IPA: /duː juː laɪk ˈreɪni ˈweðə/
  - 中文谐音: 杜 优 莱克 瑞尼 威泽
Standard Answer:
  - English: No, I don't. I don't like rainy weather because it's inconvenient.
  - 中文翻译: 不，我不喜欢雨天，因为下雨天不方便。
  - IPA: /nəʊ aɪ dəʊnt. aɪ dəʊnt laɪk ˈreɪni ˈweðə bɪˈkɒz ɪts ˌɪnkənˈviːniənt/
  - 中文谐音: 诺 艾 东特。艾 东特 莱克 瑞尼 威泽 比考兹 伊茨 因肯维尼恩特
Mastery Status: Practicing

4.
Question:
  - English: What's your favorite season?
  - 中文翻译: 你最喜欢哪个季节？
  - IPA: /wɒts jɔːr ˈfeɪvərɪt ˈsiːzn/
  - 中文谐音: 沃茨 尤儿 菲沃瑞特 西森
Standard Answer:
  - English: My favorite season is spring because the weather is pleasant.
  - 中文翻译: 我最喜欢春天，因为天气很宜人。
  - IPA: /maɪ ˈfeɪvərɪt ˈsiːzn ɪz sprɪŋ bɪˈkɒz ðə ˈweðə ɪz ˈpleznt/
  - 中文谐音: 麦 菲沃瑞特 西森 伊兹 斯普林 比考兹 泽 威泽 伊兹 普莱曾特
Mastery Status: Practicing
备注: 允许用户口语中使用完整形式 "What is your favorite season?"，但 Bank 中
  Standard Question 保持本次教学版本 "What's your favorite season?"。

5.
Question:
  - English: Is it hot in summer?
  - 中文翻译: 夏天很热吗？
  - IPA: /ɪz ɪt hɒt ɪn ˈsʌmə/
  - 中文谐音: 伊兹 伊特 哈特 因 萨默
Standard Answer:
  - English: Yes, it is. Summer is usually very hot.
  - 中文翻译: 是的，夏天通常很热。
  - IPA: /jes ɪt ɪz. ˈsʌmə ɪz ˈjuːʒuəli ˈveri hɒt/
  - 中文谐音: 耶斯 伊特 伊兹。萨默 伊兹 优日厄利 维瑞 哈特
Mastery Status: Practicing
Review History: Session 9 — 语序纠正：错误 "Summer usually is very hot." →
  正确 "Summer is usually very hot."。

Topic: Hobbies

1.
Question:
  - English: What is your hobby?
  - 中文翻译: 你的爱好是什么？
  - IPA: /wɒt ɪz jɔːr ˈhɒbi/
  - 中文谐音: 沃特 伊兹 尤儿 哈比
Standard Answer:
  - English: My hobby is reading books. I enjoy reading because I can learn new things.
  - 中文翻译: 我的爱好是读书。我喜欢读书，因为我可以学到新东西。
  - IPA: /maɪ ˈhɒbi ɪz ˈriːdɪŋ bʊks. aɪ ɪnˈdʒɔɪ ˈriːdɪŋ bɪˈkɒz aɪ kən lɜːn njuː θɪŋz/
  - 中文谐音: 麦 哈比 伊兹 瑞丁 布克斯。艾 恩乔伊 瑞丁 比考兹 艾 肯 勒恩 纽 星斯
Mastery Status: Practicing
Review History: Session 10 — 发音纠正：hobby 曾误读为 "hoppy"/"habby"，已纠正。

2.
Question:
  - English: Do you like reading books?
  - 中文翻译: 你喜欢读书吗？
  - IPA: /duː juː laɪk ˈriːdɪŋ bʊks/
  - 中文谐音: 度 尤 莱克 瑞丁 布克斯
Standard Answer:
  - English: Yes, I do. I like reading books because they help me learn new knowledge.
  - 中文翻译: 是的，我喜欢。我喜欢读书，因为它们能帮助我学到新知识。
  - IPA: /jes aɪ duː. aɪ laɪk ˈriːdɪŋ bʊks bɪˈkɒz ðeɪ help miː lɜːn njuː ˈnɒlɪdʒ/
  - 中文谐音: 耶斯 艾 度。艾 莱克 瑞丁 布克斯 比考兹 泽 海尔普 米 勒恩 纽 那力奇
Mastery Status: Practicing

3.
Question:
  - English: What do you usually do in your free time?
  - 中文翻译: 你通常在空闲时间做什么？
  - IPA: /wɒt duː juː ˈjuːʒuəli duː ɪn jɔːr friː taɪm/
  - 中文谐音: 沃特 度 尤 尤磁尤力 度 因 尤儿 福瑞 泰姆
Standard Answer:
  - English: I usually read books and study English in my free time.
  - 中文翻译: 我通常在空闲时间读书和学习英语。
  - IPA: /aɪ ˈjuːʒuəli riːd bʊks ənd ˈstʌdi ˈɪŋɡlɪʃ ɪn maɪ friː taɪm/
  - 中文谐音: 艾 尤磁尤力 瑞德 布克斯 安德 斯达蒂 英格利什 因 麦 福瑞 泰姆
Mastery Status: Practicing

4.
Question:
  - English: Do you like watching movies?
  - 中文翻译: 你喜欢看电影吗？
  - IPA: /duː juː laɪk ˈwɒtʃɪŋ ˈmuːviz/
  - 中文谐音: 度 尤 莱克 沃庆 木维兹
Standard Answer:
  - English: Yes, I do. I like watching movies because they help me relax.
  - 中文翻译: 是的，我喜欢。我喜欢看电影，因为它们能帮助我放松。
  - IPA: /jes aɪ duː. aɪ laɪk ˈwɒtʃɪŋ ˈmuːviz bɪˈkɒz ðeɪ help miː rɪˈlæks/
  - 中文谐音: 耶斯 艾 度。艾 莱克 沃庆 木维兹 比考兹 泽 海尔普 米 瑞莱克斯
Mastery Status: Practicing

5.
Question:
  - English: What do you usually do to relax?
  - 中文翻译: 你通常做什么来放松？
  - IPA: /wɒt duː juː ˈjuːʒuəli duː tuː rɪˈlæks/
  - 中文谐音: 沃特 度 尤 尤磁尤力 度 图 瑞莱克斯
Standard Answer:
  - English: I usually read books or watch movies to relax.
  - 中文翻译: 我通常通过读书或看电影来放松。
  - IPA: /aɪ ˈjuːʒuəli riːd bʊks ɔː wɒtʃ ˈmuːviz tuː rɪˈlæks/
  - 中文谐音: 艾 尤磁尤力 瑞德 布克斯 哦 沃奇 木维兹 图 瑞莱克斯
Mastery Status: Practicing

Topic: Travel

1.
Question:
  - English: Do you like traveling?
  - 中文翻译: 你喜欢旅行吗？
  - IPA: /duː juː laɪk ˈtrævəlɪŋ/
  - 中文谐音: 度 尤 莱克 特拉沃林
Standard Answer:（本 Session 未提供逐字标准答案，下次 Session 确认后补全）
Mastery Status: Practicing

2.
Question:
  - English: Where do you want to travel in the future?
  - 中文翻译: 你将来想去哪里旅行？
  - IPA: /weər duː juː wɒnt tuː ˈtrævəl ɪn ðə ˈfjuːtʃə/
  - 中文谐音: 威尔 度 尤 万特 图 特拉沃 因 泽 服丘
Standard Answer:（本 Session 未提供逐字标准答案，下次 Session 确认后补全）
Mastery Status: Practicing

3.
Question:
  - English: Who do you want to travel with?
  - 中文翻译: 你想和谁一起旅行？
  - IPA: /huː duː juː wɒnt tuː ˈtrævəl wɪð/
  - 中文谐音: 呼 度 尤 万特 图 特拉沃 威兹
Standard Answer:（本 Session 未提供逐字标准答案，下次 Session 确认后补全）
Mastery Status: Practicing

4.
Question:
  - English: How do you usually travel?
  - 中文翻译: 你通常怎么旅行？
  - IPA: /haʊ duː juː ˈjuːʒuəli ˈtrævəl/
  - 中文谐音: 好 度 尤 尤磁尤力 特拉沃
Standard Answer:（本 Session 未提供逐字标准答案，下次 Session 确认后补全）
Mastery Status: Practicing
Review History: Session 12 — 本次 Random Review 实际使用的提问是 "How
  often do you usually travel?"（非本条 Canonical Question，且与
  Shopping Topic "How often do you usually go shopping?" 句式相近，
  会话总结中记录为一次混淆点），未据此覆盖或修改上方 Canonical
  Question；今后 Review 仍以本条已存 Canonical Question 为准，除非用户
  明确要求修订（沿用 Food Q2 / Session 9 已确立的同类先例）。

5.
Question:
  - English: What do you usually do when you travel?
  - 中文翻译: 你旅行时通常做什么？
  - IPA: /wɒt duː juː ˈjuːʒuəli duː wen juː ˈtrævəl/
  - 中文谐音: 沃特 度 尤 尤磁尤力 度 温 尤 特拉沃
Standard Answer:（本 Session 未提供逐字标准答案，下次 Session 确认后补全）
Mastery Status: Practicing

Topic: Technology
Level: 1（Session 12 新增，6 组 Q&A，按第 4.1 节 Level System Level 1
  标准——每个 Answer 为单句、简单直接；数量为当天实际学习数量，不强制 5
  组）

1.
Question:
  - English: Do you like technology?
  - 中文翻译: 你喜欢科技吗？
  - IPA: /duː juː laɪk tekˈnɒlədʒi/
  - 中文谐音: 度 尤 莱克 泰克诺勒吉
Standard Answer:
  - English: Yes, I do. Technology makes my life easier.
  - 中文翻译: 是的，我喜欢。科技让我的生活更轻松。
  - IPA: /jes aɪ duː tekˈnɒlədʒi meɪks maɪ laɪf ˈiːziə/
  - 中文谐音: 耶斯 埃 度 泰克诺勒吉 妹克斯 买 莱夫 伊季厄
Mastery Status: Practicing

2.
Question:
  - English: What technology do you use every day?
  - 中文翻译: 你每天使用什么科技产品？
  - IPA: /wɒt tekˈnɒlədʒi duː juː juːz ˈevri deɪ/
  - 中文谐音: 沃特 泰克诺勒吉 度 尤 尤兹 埃夫瑞 得
Standard Answer:
  - English: I use my computer and smartphone every day. I use them for work and study.
  - 中文翻译: 我每天使用电脑和智能手机。我把它们用于工作和学习。
  - IPA: /aɪ juːz maɪ kəmˈpjuːtər ənd ˈsmɑːtfəʊn ˈevri deɪ aɪ juːz ðəm fɔː wɜːk ənd ˈstʌdi/
  - 中文谐音: 埃 尤兹 买 康皮尤特 安德 斯马特风 埃夫瑞 得 埃 尤兹 泽姆 佛 沃克 安德 斯塔迪
Mastery Status: Practicing

3.
Question:
  - English: How does technology help you at work?
  - 中文翻译: 科技如何帮助你工作？
  - IPA: /haʊ dʌz tekˈnɒlədʒi help juː æt wɜːk/
  - 中文谐音: 好 达兹 泰克诺勒吉 海尔普 尤 艾特 沃克
Standard Answer:
  - English: It helps me write code. It makes my work easier.
  - 中文翻译: 它帮助我写代码。它让我的工作更轻松。
  - IPA: /ɪt helps miː raɪt kəʊd ɪt meɪks maɪ wɜːk ˈiːziə/
  - 中文谐音: 伊特 海尔普斯 米 莱特 扣德 伊特 妹克斯 买 沃克 伊季厄
Mastery Status: Practicing

4.
Question:
  - English: What is your favorite app?
  - 中文翻译: 你最喜欢的 App 是什么？
  - IPA: /wɒt ɪz jɔː ˈfeɪvərɪt æp/
  - 中文谐音: 沃特 伊兹 尤 费沃瑞特 阿普
Standard Answer:
  - English: My favorite app is ChatGPT. I use it every day.
  - 中文翻译: 我最喜欢的 App 是 ChatGPT。我每天都使用它。
  - IPA: /maɪ ˈfeɪvərɪt æp ɪz ˌtʃæt dʒiː piː ˈtiː aɪ juːz ɪt ˈevri deɪ/
  - 中文谐音: 买 费沃瑞特 阿普 伊兹 恰特 吉皮提 埃 尤兹 伊特 埃夫瑞 得
Mastery Status: Practicing

5.
Question:
  - English: Do you think AI is useful?
  - 中文翻译: 你觉得 AI 有用吗？
  - IPA: /duː juː θɪŋk ˌeɪ ˈaɪ ɪz ˈjuːsfəl/
  - 中文谐音: 度 尤 星克 诶挨 伊兹 尤斯佛
Standard Answer:
  - English: Yes, I do. AI helps people save time.
  - 中文翻译: 是的，我觉得有用。AI 帮助人们节省时间。
  - IPA: /jes aɪ duː ˌeɪ ˈaɪ helps ˈpiːpəl seɪv taɪm/
  - 中文谐音: 耶斯 埃 度 诶挨 海尔普斯 皮泼 塞夫 泰姆
Mastery Status: Practicing

6.
Question:
  - English: What new technology would you like to learn?
  - 中文翻译: 你想学习什么新科技？
  - IPA: /wɒt njuː tekˈnɒlədʒi wʊd juː laɪk tuː lɜːn/
  - 中文谐音: 沃特 纽 泰克诺勒吉 伍德 尤 莱克 图 勒恩
Standard Answer:
  - English: I'd like to learn AI. I think it is very useful.
  - 中文翻译: 我想学习 AI。我觉得它非常有用。
  - IPA: /aɪd laɪk tuː lɜːn ˌeɪ ˈaɪ aɪ θɪŋk ɪt ɪz ˈveri ˈjuːsfəl/
  - 中文谐音: 艾德 莱克 图 勒恩 诶挨 埃 星克 伊特 伊兹 维瑞 尤斯佛
Mastery Status: Practicing
Review History: Session 14 — Recent 7-Day Random Review 中语法纠正："I'd
  like to learn is AI." → "I'd like to learn AI. I think it is very
  useful."（多余的 is），已当场纠正，Standard Answer 未被修改。

Topic: Sports
Level: 1（Session 13 新增，6 组 Q&A，按第 4.1 节 Level System Level 1
  标准——每个 Answer 为单句或双子句、简单直接；数量为当天实际学习数量）

1.
Question:
  - English: Do you like sports?
  - 中文翻译: 你喜欢运动吗？
  - IPA: /duː juː laɪk spɔːts/
  - 中文谐音: 度 尤 莱克 斯颇茨
Standard Answer:
  - English: Yes, I do. I like sports because it's good for my health.
  - 中文翻译: 是的，我喜欢。我喜欢运动，因为它对我的健康有好处。
  - IPA: /jes aɪ duː aɪ laɪk spɔːts bɪˈkɒz ɪts ɡʊd fɔː maɪ helθ/
  - 中文谐音: 耶斯 埃 度 埃 莱克 斯颇茨 比考兹 伊茨 古德 佛 买 海尔思
Mastery Status: Practicing
Review History: Session 13 — 语法纠正："It's good for my healthy." → "It's
  good for my health."（health 与 healthy 混淆）。

2.
Question:
  - English: What is your favorite sport?
  - 中文翻译: 你最喜欢的运动是什么？
  - IPA: /wɒt ɪz jɔː ˈfeɪvərɪt spɔːt/
  - 中文谐音: 沃特 伊兹 尤 费沃瑞特 斯颇特
Standard Answer:
  - English: My favorite sport is badminton. It's fun and good exercise.
  - 中文翻译: 我最喜欢的运动是羽毛球。它很有趣，也是很好的锻炼。
  - IPA: /maɪ ˈfeɪvərɪt spɔːt ɪz ˈbædmɪntən ɪts fʌn ənd ɡʊd ˈeksəsaɪz/
  - 中文谐音: 买 费沃瑞特 斯颇特 伊兹 拜德敏顿 伊茨 芬 安德 古德 埃克塞赛兹
Mastery Status: Practicing
Review History: Session 13 — 提问错误纠正：误将本题问成 "Why is your
  favorite sport?" → 正确 "What is your favorite sport?"。

3.
Question:
  - English: How often do you play sports?
  - 中文翻译: 你多久做一次运动？
  - IPA: /haʊ ˈɒfən duː juː pleɪ spɔːts/
  - 中文谐音: 好 欧分 度 尤 普雷 斯颇茨
Standard Answer:
  - English: I usually play sports once or twice a week. It helps me stay healthy.
  - 中文翻译: 我通常每周运动一到两次。这有助于我保持健康。
  - IPA: /aɪ ˈjuːʒuəli pleɪ spɔːts wʌns ɔː twaɪs ə wiːk ɪt helps miː steɪ ˈhelθi/
  - 中文谐音: 埃 尤磁尤力 普雷 斯颇茨 万斯 哦 拓外斯 尔 维克 伊特 海尔普斯 米 斯得 海尔西
Mastery Status: Practicing
Review History: Session 13 — 语法纠正："It helps me healthy." → "It helps
  me stay healthy."（缺少动词 stay）。Session 14 — 同一错误再次出现一次
  （"healthy" 误用为名词，缺少 stay），已当场再次纠正；本 Session 该题
  在最终 Review 中标记 ✅ 通过。

4.
Question:
  - English: Who do you usually play sports with?
  - 中文翻译: 你通常和谁一起做运动？
  - IPA: /huː duː juː ˈjuːʒuəli pleɪ spɔːts wɪð/
  - 中文谐音: 呼 度 尤 尤磁尤力 普雷 斯颇茨 威兹
Standard Answer:
  - English: I usually play sports with my friends. We enjoy playing together.
  - 中文翻译: 我通常和朋友一起运动。我们喜欢一起玩。
  - IPA: /aɪ ˈjuːʒuəli pleɪ spɔːts wɪð maɪ frendz wiː ɪnˈdʒɔɪ ˈpleɪɪŋ təˈɡeðə/
  - 中文谐音: 埃 尤磁尤力 普雷 斯颇茨 威兹 买 弗兰兹 威 恩乔伊 普勒英 特盖泽
Mastery Status: Practicing
Review History: Session 13 — 与 Question 5（Where）串题一次：被问
  "Where do you usually play sports?" 时误答成本条 Standard Answer
  内容（"I usually play sports with my friends. We enjoy playing
  together."），已纠正为 Question 5 正确答案，已通过重复练习纠正，
  未修改本条 Standard Answer；下次 Session 需优先交叉强化 Q4/Q5。
  Session 14 — 按 Session 13 计划优先交叉强化 Q4/Q5，本题在 Recent
  7-Day Random Review 中标记 ✅ 通过，未再出现与 Q5 混用，混淆点已解决。

5.
Question:
  - English: Where do you usually play sports?
  - 中文翻译: 你通常在哪里做运动？
  - IPA: /weər duː juː ˈjuːʒuəli pleɪ spɔːts/
  - 中文谐音: 威尔 度 尤 尤磁尤力 普雷 斯颇茨
Standard Answer:
  - English: I usually play sports at the park or at the gym. They are good places to exercise.
  - 中文翻译: 我通常在公园或健身房运动。它们是锻炼的好地方。
  - IPA: /aɪ ˈjuːʒuəli pleɪ spɔːts æt ðə pɑːk ɔːr æt ðə dʒɪm ðeɪ ɑː ɡʊd ˈpleɪsɪz tuː ˈeksəsaɪz/
  - 中文谐音: 埃 尤磁尤力 普雷 斯颇茨 艾特 泽 帕克 哦 艾特 泽 吉姆 泽 阿 古德 普雷西斯 图 埃克塞赛兹
Mastery Status: Practicing
Review History: Session 13 — 语法纠正："They are good place to exercise."
  → "They are good places to exercise."（单复数）；被问本题时曾误答成
  Question 4（Who）的 Standard Answer 内容，已纠正为本条正确答案；下次
  Session 需优先交叉强化 Q4/Q5。Session 14 — 按 Session 13 计划优先
  交叉强化 Q4/Q5，本题在 Recent 7-Day Random Review 中标记 ✅ 通过，
  未再出现与 Q4 混用，混淆点已解决。

6.
Question:
  - English: Why is exercise important?
  - 中文翻译: 为什么锻炼很重要？
  - IPA: /waɪ ɪz ˈeksəsaɪz ɪmˈpɔːtənt/
  - 中文谐音: 歪 伊兹 埃克塞赛兹 因颇特恩特
Standard Answer:
  - English: Exercise is important because it keeps me healthy. It also helps me relax.
  - 中文翻译: 锻炼很重要，因为它让我保持健康。它也帮助我放松。
  - IPA: /ˈeksəsaɪz ɪz ɪmˈpɔːtənt bɪˈkɒz ɪt kiːps miː ˈhelθi ɪt ˈɔːlsəʊ helps miː rɪˈlæks/
  - 中文谐音: 埃克塞赛兹 伊兹 因颇特恩特 比考兹 伊特 基普斯 米 海尔西 伊特 奥索 海尔普斯 米 瑞莱克斯
Mastery Status: Practicing

Topic: Music
Level: 1（Session 14 新增，6 组 Q&A，第 7 组 Question 已在会话总结中预告
  但未在本 Session 内学习/练习，按第 3 节 Session Context Grounding，
  下次 Session 正式学习后才计入本节；按第 4.1 节 Level System Level 1
  标准——每个 Answer 为单句或双子句、简单直接）

1.
Question:
  - English: Do you like music?
  - 中文翻译: 你喜欢音乐吗？
  - IPA: /duː juː laɪk ˈmjuːzɪk/
  - 中文谐音: 度 尤 莱克 缪季克
Standard Answer:
  - English: Yes, I do. I like music because it helps me relax.
  - 中文翻译: 是的，我喜欢。我喜欢音乐，因为它能帮助我放松。
  - IPA: /jes aɪ duː aɪ laɪk ˈmjuːzɪk bɪˈkɒz ɪt helps miː rɪˈlæks/
  - 中文谐音: 耶斯 埃 度 埃 莱克 缪季克 比考兹 伊特 海尔普斯 米 瑞莱克斯
Mastery Status: Practicing

2.
Question:
  - English: What kind of music do you like?
  - 中文翻译: 你喜欢什么类型的音乐？
  - IPA: /wɒt kaɪnd əv ˈmjuːzɪk duː juː laɪk/
  - 中文谐音: 沃特 凯恩德 欧夫 缪季克 度 尤 莱克
Standard Answer:
  - English: I like pop music because it is relaxing and enjoyable.
  - 中文翻译: 我喜欢流行音乐，因为它让人放松且愉悦。
  - IPA: /aɪ laɪk pɒp ˈmjuːzɪk bɪˈkɒz ɪt ɪz rɪˈlæksɪŋ ənd ɪnˈdʒɔɪəbəl/
  - 中文谐音: 埃 莱克 帕普 缪季克 比考兹 伊特 伊兹 瑞莱克辛 安德 恩乔尔勃
Mastery Status: Practicing

3.
Question:
  - English: When do you usually listen to music?
  - 中文翻译: 你通常什么时候听音乐？
  - IPA: /wen duː juː ˈjuːʒuəli ˈlɪsən tuː ˈmjuːzɪk/
  - 中文谐音: 温 度 尤 尤磁尤力 里森 图 缪季克
Standard Answer:
  - English: I usually listen to music in my free time. It helps me relax.
  - 中文翻译: 我通常在空闲时间听音乐。它能帮助我放松。
  - IPA: /aɪ ˈjuːʒuəli ˈlɪsən tuː ˈmjuːzɪk ɪn maɪ friː taɪm ɪt helps miː rɪˈlæks/
  - 中文谐音: 埃 尤磁尤力 里森 图 缪季克 因 买 福瑞 泰姆 伊特 海尔普斯 米 瑞莱克斯
Mastery Status: Practicing

4.
Question:
  - English: Who do you usually listen to music with?
  - 中文翻译: 你通常和谁一起听音乐？
  - IPA: /huː duː juː ˈjuːʒuəli ˈlɪsən tuː ˈmjuːzɪk wɪð/
  - 中文谐音: 呼 度 尤 尤磁尤力 里森 图 缪季克 威兹
Standard Answer:
  - English: I usually listen to music by myself. Sometimes I listen to music with my friends.
  - 中文翻译: 我通常自己一个人听音乐。有时候我会和朋友一起听。
  - IPA: /aɪ ˈjuːʒuəli ˈlɪsən tuː ˈmjuːzɪk baɪ maɪˈself ˈsʌmtaɪmz aɪ ˈlɪsən tuː ˈmjuːzɪk wɪð maɪ frendz/
  - 中文谐音: 埃 尤磁尤力 里森 图 缪季克 拜 买赛尔弗 桑泰姆兹 埃 里森 图 缪季克 威兹 买 弗兰兹
Mastery Status: Practicing
Review History: Session 14 — 遗漏词纠正：曾漏说句尾 "with"（"Who do you
  usually listen to music?"）→ "Who do you usually listen to music
  with?"，已当场纠正。

5.
Question:
  - English: Why do you like music?
  - 中文翻译: 你为什么喜欢音乐？
  - IPA: /waɪ duː juː laɪk ˈmjuːzɪk/
  - 中文谐音: 歪 度 尤 莱克 缪季克
Standard Answer:
  - English: I like music because it helps me relax and makes me feel happy.
  - 中文翻译: 我喜欢音乐，因为它能帮助我放松，也能让我感到快乐。
  - IPA: /aɪ laɪk ˈmjuːzɪk bɪˈkɒz ɪt helps miː rɪˈlæks ənd meɪks miː fiːl ˈhæpi/
  - 中文谐音: 埃 莱克 缪季克 比考兹 伊特 海尔普斯 米 瑞莱克斯 安德 妹克斯 米 菲尔 黑皮
Mastery Status: Practicing

6.
Question:
  - English: Can you play any musical instruments?
  - 中文翻译: 你会演奏任何乐器吗？
  - IPA: /kæn juː pleɪ ˈeni ˈmjuːzɪkəl ˈɪnstrəmənts/
  - 中文谐音: 坎 尤 普雷 埃尼 缪季扣 因斯特鲁门茨
Standard Answer:
  - English: No, I can't. But I'd like to learn to play the guitar.
  - 中文翻译: 不，我不会。但我想学习弹吉他。
  - IPA: /nəʊ aɪ kɑːnt bʌt aɪd laɪk tuː lɜːn tuː pleɪ ðə ɡɪˈtɑː/
  - 中文谐音: 诺 埃 咖恩特 巴特 埃德 莱克 图 勒恩 图 普雷 泽 吉塔
Mastery Status: Practicing
Review History: Session 14 — 语法纠正："No, I don't." → "No, I can't."
  （can/don't 混淆，本题为 Can you...? 一般疑问句）；另提醒不得省略句首
  "But"（"I'd like to learn to play the guitar." 需保留 "But I'd
  like..."），均已当场纠正。

### 11.2 Daily Native Expressions Bank（V11.19 新增，见第 4.5 节）

记录格式（沿用第 4.1 节 English Learning Template，按 Day 为单位）：

```
Day:
Scenario:（本 Day 表达围绕的真实生活场景）
Expression 1:
  - English:
  - 中文翻译:
  - IPA:
  - 中文谐音:
Expression 2: ...
Mastery Status: New / Practicing / Mastered
```

Day 1（Session 12 新增，场景：早晨起床流程）

Expression 1:
  - English: I wake up at seven o'clock every morning.
  - 中文翻译: 我每天早上七点起床。
  - IPA: /aɪ weɪk ʌp æt ˈsevən əˈklɒk ˈevri ˈmɔːnɪŋ/
  - 中文谐音: 埃 维克 阿普 艾特 塞文 欧克拉克 埃夫瑞 摩宁
Expression 2:
  - English: I check my phone after I wake up.
  - 中文翻译: 我起床后会看手机。
  - IPA: /aɪ tʃek maɪ fəʊn ˈɑːftər aɪ weɪk ʌp/
  - 中文谐音: 埃 切克 买 风 阿夫特 埃 维克 阿普
Expression 3:
  - English: After that, I take a shower before breakfast.
  - 中文翻译: 之后，我会在早餐前洗澡。
  - IPA: /ˈɑːftə ðæt aɪ teɪk ə ˈʃaʊər bɪˈfɔː ˈbrekfəst/
  - 中文谐音: 阿夫特 泽特 埃 太克 尔 少沃 比佛 布莱克费斯特
Mastery Status: Practicing（3 轮 Review 已完成，会话总结判定 Graduated；按
  第 4.5 节标准与第 9.1 节跨 Session 稳定要求，本 Session 内完成 3 轮只是
  初步达标，标记为 Practicing，需未来 Session 持续稳定表现后才升级
  Mastered，判定方式与英语 Topic 的既有 Practicing→Mastered 惯例一致）
Review History: Session 12 — 完成 3 轮 Review，纠正 after/before 混淆、
  "my phone" 冠词遗漏、"after I wake up" 语序，三处错误均已当场纠正。

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

**Scenario 类型记录格式（V11.17 起，呼应第 5.1 节 Scenario Interview Mode、
第 5.2 节 Step5 与第 6 节 Canonical Thinking Rule；仅适用于场景型 Interview
Question，Java Basics 等既有非场景型条目沿用上方旧格式，不追溯改写）：**

```
Scenario N
Interview Question:
Interviewer Intent:（呼应第 5.2 节 Step1 分析，面试官为什么问这个问题）
Canonical Thinking:（内部思维框架，永不直接说出，见第 6 节 Canonical
  Thinking Rule）
Canonical Answer:（锁定的 Round3 答案，锁定规则同上方 Java Canonical
  Answer Rule 的 "My Final Answer"）
Mastery Status: New / Practicing / Mastered / Needs Review（沿用第 9 节
  既有四值，不引入新状态值；Canonical Answer 一旦有内容即视为已锁定，
  见第 6 节 Java Canonical Answer Rule，不需要单独的 Locked 字段）
Review History:
```

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
Review History: Session 1 — Round1 88/100, Round2 95/100, Round3 98/100 (initial pass); Session 2 — reviewed multiple rounds, answer structure now clearly Definition → Platform (JVM) → Core characteristics → Typical enterprise scenarios → Personal project experience, noticeably more fluent than Session 1. Session 6 — Random Review, answer reproduced successfully, Senior-level structure maintained, more natural and fluent than prior sessions; this is the second post-lock Random Review (after Session 2). Kept at Practicing — 9.1 requires consistently satisfying performance across future reviews; two consistent instances is progress toward Mastered but not yet treated as sufficient confirmation on its own.

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
Review History: Session 2 — introduced as this Session's Interview Question, multiple rounds practiced; user moved from reciting toward a logical structure rather than memorized sentences, wording not yet finalized. Session 3 — completed via AI demonstration → Round1 → Round2 → Round3; Round2 refined wording ("backend" instead of "backend management", "runs on the JVM"); Round3 produced a complete, fluent, structured interview-quality answer (Conclusion → Technical Advantages → Personal Experience → Summary), scored 99/100, saved above as the locked Final Answer per the Java Canonical Answer Rule (第 6 节). Kept at Practicing rather than Mastered per 9.1 Java Mastery Criteria — interview quality reached, but subsequent Random Review performance has not yet been observed. Session 4 — first post-finalization review: repeated the full interview answer, structure unchanged (Conclusion → Technical Advantages → Personal Experience → Summary) per the Java Canonical Answer Rule, terminology correction (Backend/后端, not 后台). Fluent, stable, technically accurate. Kept at Practicing — this is only the first Random Review since Final Answer was locked; 9.1 requires consistently satisfying performance across future reviews, not a single instance, before promotion to Mastered. Session 6 — second Random Review, answer reproduced successfully, Senior-level structure maintained, more natural and fluent than prior sessions. Kept at Practicing — two consistent post-lock instances now observed (Session 4, Session 6); progress toward Mastered but 9.1's "consistently satisfying" bar is not yet treated as met after only two instances.

**Topic 状态（V11.16 Scenario Interview Mode）**：以上两个 Interview
Question 均已锁定 Canonical Answer，"Java Basics" 不再作为每日新内容来源，
永久保留在 Random Review 池中，此后新 Interview Topic 默认均为场景型，见
下方 "Production Incident Scenarios"。

Interview Topic: Production Incident Scenarios（生产故障场景）

Scenario 1
Interview Question: 线上接口 RT 从 50ms 飙升到 3 秒，作为值班负责人你会如何处理？
Interviewer Intent: 考察线上故障处理能力、处理优先级、线上经验以及
Senior / Tech Lead 的决策思维。
Canonical Thinking:
Impact Assessment
→ Business Recovery
→ Root Cause Analysis
→ Recovery Validation
→ RCA / Long-term Prevention
Canonical Answer:
如果线上接口 RT 突然从 50ms 飙升到 3 秒，我首先会确认问题影响范围，看是
单个接口、单个服务还是整个系统，同时确认哪些核心业务受到了影响。

确认影响范围以后，我会优先恢复业务。如果是新版本导致的问题，我会优先
回滚；如果系统压力过大，我会根据情况做限流、降级、熔断或者扩容，先让
业务恢复正常。

业务恢复以后，我会结合监控、日志和链路追踪继续定位原因，看问题是在
JVM、数据库、Redis、MQ，还是第三方接口，尽快找到真正的故障点。

最后，我会持续观察系统是否已经恢复正常，并组织团队做一次 RCA，把根因
分析清楚，同时完善监控和告警，避免同样的问题再次发生。
Mastery Status: Practicing
Review History: Session 5 — 完成 Step1 分析 → AI 示范 → Round1 → Round2 →
Round3（均 PASS），Round3 作为 Canonical Answer 存入本记录，Interviewer
Intent 与 Canonical Thinking 按 V11.17 记录格式一并存档，符合第 6 节 Java
Canonical Answer Rule 与 Canonical Thinking Rule。按 9.1 节 Java Mastery
Criteria，本次三轮属于初次完成流程（非"之后的" Random Review），尚未经过
后续 Session 的 Random Review 验证，因此标记为 Practicing 而非
Mastered，与 Java Basics 既有两条记录的判定方式一致。

Scenario 2
Interview Question: 线上 CPU 突然达到 100%，你会如何处理？
Interviewer Intent: 本题考察的不是 CPU 本身的知识，而是考察候选人是否具备
真实的生产故障处理经验、是否遵循正确的故障处理顺序、是否优先保证业务恢复
而不是先做根因分析、能否系统性定位根因、是否具备 RCA 与长期改进意识——
一句话概括：本题考察生产故障处理能力，而不是 CPU 知识本身。
Canonical Thinking:
Confirm impact
→ Recover business
→ Locate root cause
→ Verify recovery
→ RCA
Canonical Answer:
如果线上 CPU 突然达到100%，我会先看影响范围，确认是不是已经影响核心业务。

如果业务已经受影响，我会先恢复服务，比如扩容、限流、降级或者切流量，先
保证业务恢复正常。

然后我再定位原因，一般会结合监控、日志和链路追踪，重点看看是不是 GC、
线程、数据库、Redis、MQ，或者代码本身的问题。

找到根因以后，我会修复问题，然后持续观察系统运行情况，确认业务已经恢复
正常。

最后我会组织团队做一次 RCA，把根因分析清楚，同时完善监控、告警和预案，
避免同样的问题再次发生。
Mastery Status: Practicing
Review History: Session 7 — 完成 Interviewer Intent 分析 → Canonical
Thinking → 三轮回答（99 / 99 / 95），Round3 作为 Canonical Answer 存入本
记录，Interviewer Intent 与 Canonical Thinking 按 V11.17 记录格式一并
存档，符合第 6 节 Java Canonical Answer Rule 与 Canonical Thinking Rule。
Final Improvement 笔记：Recovery Verification 阶段应包含"先修复问题、再
观察系统状态"两个子步骤（已体现在上方 Canonical Answer 的第四段）；补充
讲解了 Error Rate 概念；面试第一轮回答应优先"确认业务已恢复"这一结论，
CPU/RT/Error Rate 等具体指标留待面试官追问时再展开。按 9.1 节 Java
Mastery Criteria，本次三轮属于初次完成流程，尚未经过后续 Session 的
Random Review 验证，标记为 Practicing 而非 Mastered，与 Scenario 1 判定
方式一致。Session 8 — 首次 Random Review（Final Answer 锁定后第一次复
查），复述结构与已锁定 Canonical Answer 一致（确认影响范围 → 优先恢复
业务 → 结合监控/日志/链路追踪定位原因 → 修复并持续观察 → 组织 RCA），
评分 99/100，未改写 Canonical Answer 本身。本次补充的执行层改进笔记：
定位原因时应先通过监控/链路追踪确定 CPU 消耗集中在哪个环节，再基于证据
针对性排查具体组件，而不是先罗列所有可能原因再逐一排查——与已锁定
Canonical Answer 中"结合监控、日志和链路追踪，重点看看是不是 GC、线程、
数据库、Redis、MQ，或者代码本身的问题"的顺序一致，此处作为强调，不构成
对 Canonical Answer 文本的修订（学员未提出修订请求，遵循 Java Canonical
Answer Rule）。按 9.1 节标准，这是锁定后的第一次 Random Review，仍标记
Practicing。Session 10 — 第二次 Random Review，结构与已锁定 Canonical
Answer 一致，表现稳定（用户总结为 "Stable"），未改写 Canonical Answer
本身。按 9.1 节标准，锁定后已观察到两次一致表现（Session 8、Session 10），
向 Mastered 推进但尚未视为已满足"持续稳定"的判定门槛，仍标记 Practicing。

Scenario 3
Interview Question: 线上某个核心接口突然大量返回 HTTP 500：只有一个接口受影响；
Error Rate 从 0% 上升到 35%；RT 从 80ms 上升到约 300ms；CPU 正常；Memory 正常；
Database 正常；Redis 正常；MQ 正常。如果你是 on-call 工程师，你会如何分析和
处理？
Interviewer Intent: 面试官重点考察：(1) 是否知道 HTTP 500 只是服务端异常结果，
不是根因；(2) 是否会根据现象缩小范围，而不是无证据猜测空指针、参数异常或某个
具体 Bug；(3) 是否能够区分系统整体问题、公共依赖问题、单接口自身代码链路/业务
数据/独有下游问题；(4) 是否知道通过 TraceID、日志和异常堆栈获取证据；(5) 是否
能够根据证据再选择回滚、修复或降级；(6) 是否有恢复验证和 RCA 意识；(7) 回答是否
简洁、口语化，控制在约 20-30 秒。
Canonical Thinking:
HTTP 500 is a symptom, not the root cause
→ Analyze the scope
→ Exclude obvious system-wide resource and shared dependency failures
→ Narrow the scope to the affected endpoint
→ Use TraceID + logs + exception stack to obtain evidence
→ Choose rollback / fix / degradation based on evidence
→ Verify error-rate recovery
→ RCA
中文说明：
1. 不直接猜根因；
2. 根据题目现象判断只有单个接口异常；
3. 系统资源和公共依赖正常，只能排除明显的整体故障，不能因此直接断言具体 Bug；
4. 先把范围缩小到该接口自身；
5. 使用 TraceID 找到该请求的完整调用链；
6. 结合日志和异常堆栈确认真正原因；
7. 有证据以后再决定回滚、修复或降级；
8. 最后验证错误率是否恢复，并做 RCA。
Canonical Thinking 仅用于内部组织与评分，不得在面试回答中机械列举完整框架。
Canonical Answer:
我不会直接猜原因，因为 HTTP 500 只是异常结果。

从现象来看，只有一个接口出问题，而系统资源和公共依赖都正常，所以我会先把范围
缩小到这个接口本身。

我会先通过 TraceID 找到这次请求的完整调用链，再结合日志和异常堆栈定位真正的
原因。

确认原因以后，再决定是回滚、修复还是降级。

最后观察错误率是否恢复正常，确认没问题后再做 RCA。
不得自行扩写成一分钟长答案；不得重新加入未经证据支持的具体根因猜测（例如空
指针、参数异常、JSON 转换失败、第三方接口异常、数据库异常数据）——这些只能
作为拿到异常堆栈后的可能分支，不属于本题的 Canonical Answer。
Mastery Status: Practicing
Review History: Session 9 — 初始 AI 回答过度套用通用故障模板（确认影响 → 恢复
业务 → 查日志 → RCA），用户指出未抓住场景核心；AI 随后又无证据猜测空指针、
参数异常、数据转换失败等具体根因，用户再次指出不能直接猜具体根因；最终确认
核心原则：HTTP 500 是异常结果而非根因、根据现象缩小范围、通过 TraceID/日志/
异常堆栈取得证据、根据证据决定回滚/修复/降级、最后验证并做 RCA。用户进一步
学习了 Trace/TraceID 含义：Trace 是一次请求的完整调用链，TraceID 用于串联一次
请求经过的服务、日志和异常，TraceID 本身不是根因，而是定位证据的入口。上方
Canonical Answer 为最终锁定版本，按第 6 节 Java Canonical Answer Rule，未来
Random Review 不得重新生成不同逻辑版本，除非用户明确要求修订。按 9.1 节 Java
Mastery Criteria，尚未经过后续 Session 的 Random Review 验证，标记为
Practicing。Session 10 — 锁定后第一次 Random Review，结构与上方已锁定
Canonical Answer 一致，表现稳定（用户总结为 "Stable"），未改写 Canonical
Answer 本身。按 9.1 节标准，仅为锁定后首次复习，仍标记 Practicing。

## 13. Current Session

### 13.1 Active Review Window（执行层机制，每 Session 结束时整体覆盖重写，
不追加历史，不改变课程架构）

机制说明（呼应第 3 节 Session Context Grounding 与第 7 节 Review Rules，
纯执行层数据，不属于第一部分课程规范）：
- **7 天窗口（V11.18，主要机制）**：English Active Topics / Java Active
  Questions = 最近 **7 天内**学习/引入的 Topic / Interview
  Question/Scenario，作为日常 Random Review / Combined Questions / Java
  Random Review 的默认高频复习池。
- 窗口外内容（引入日期超过 7 天）不退出复习体系，改为按第 7 节
  Priority-Based Review Engine（Mastery Status + Learning Recency）做
  低频抽查，不放入每次的默认队列，但仍会被抽到，不被永久排除；已
  Mastered 的窗口外内容抽查频率最低。学员显式要求"全面复习 / full
  review"时不受 7 天窗口限制。
- 本 Session 内 Step1–Step3 的 Review 只能从下方列出的 Active Topics /
  Expressions / Questions 中提问或练习，不得超纲（呼应第 3 节 Session
  Context Grounding）。第 4.2 节 Step4/Step5 引入"今天的新 Topic /
  Daily Native Expressions"、以及 Java 引入下一个新 Interview
  Question（若安排 Java 练习）均不受本窗口限制——本窗口只约束"复习/练习
  哪些已学内容"，不约束"何时学新内容"。Java 自 V11.19 起不再是每日固定
  环节（第 5 节），未安排 Java 练习的 Session 不涉及 Java Active
  Questions。
- 本小节内容每个 Session 结束时整体覆盖重写为下一次对话的窗口快照，不保留
  历史版本；完整历史仍完整保存在第 11/12/14 节，不受本小节覆盖影响。

English Active Topics（截至 Session 14 / 2026-07-19【本 Session 学习总结
标题仍写 2026-07-18，但内容明确将 Sports 称为"昨天的 Topic"，Sports 已
记录学习日期为 2026-07-18，故本 Session 判定为次日 2026-07-19；此推断
与本节下方 Weather 恰好滚出窗口的计算结果一致，已在 13.2 中注明】。**本
Session 是 7 天窗口第三次出现内容滚出**：Weather（2026-07-11，已 8 天）
超过 7 天，按第 7 节说明移出默认高频复习池，改为低频抽查，不代表内容被
排除或删除；下列窗口内内容按 Learning Recency 排序）：
- Topic: Music（最新学习，Level 1，Practicing，2026-07-19）
- Topic: Sports（Practicing，2026-07-18）
- Topic: Technology（Practicing，2026-07-16）
- Topic: Travel（Practicing，2026-07-14）
- Topic: Hobbies（2026-07-12，第 7 天边界，仍计入窗口）

已滚出 7 天窗口、转入第 7 节低频抽查池：
- Topic: Weather（2026-07-11）
- Topic: Shopping（2026-07-10）
- Topic: Food（2026-07-09）
- Topic: Family（2026-07-09）
- Topic: Daily Routine（2026-07-07）
- Topic: English Learning（2026-07-06）
- Topic: Self Introduction（2026-07-06）

Daily Native Expressions Active Window（V11.19 新增，见第 4.5/11.2 节。本
Session 仍未安排 Step2/Step5，连续第二个 Session 未新增 Day 2，快照维持
不变，详见 13.2）：
- Day 1（场景：早晨起床流程，Practicing，3 轮 Review 已完成，2026-07-16）

Java Active Questions（截至 Session 11，本 Session 未安排 Java 练习，快照
按 7 天窗口重新计算；"JVM Full GC"（Session 10）与 "Database Connection Pool
Exhausted"（Session 11）两个场景仍因缺少逐字中文信息未写入第 12 节，详见
13.2；V11.19 起 Java 练习本身已非默认环节，窗口状态仅供下次安排 Java 练习时
参考）：
- （无——Scenario 3 本 Session 起已滚出 7 天窗口，窗口内暂无 Java 内容）

已滚出窗口、转入低频抽查池：
- Scenario 3：线上某个接口突然返回大量 HTTP 500 错误，你会如何处理？（2026-07-11）
- Scenario 1：线上接口 RT 从 50ms 飙升到 3 秒，作为值班负责人你会如何处理？（2026-07-09）
- Scenario 2：线上 CPU 突然达到 100%，你会如何处理？（2026-07-09）
- What is Java?（2026-07-06）
- Why do you use Java?（2026-07-06）

### 13.2 Session Detail

- Session: 14（英语部分已同步；本 Session 未涉及 Java，符合 V11.19 起
  Java 非每日固定环节的新架构；本 Session 会话总结标题写 2026-07-18，
  但内容明确将 Sports 称为"昨天的 Topic"——Sports 学习日期已记录为
  2026-07-18，因此本 Session 判定为次日 **2026-07-19**，标题日期视为
  笔误，未采用；该判定与本 Session 计算得出的 Weather 恰好滚出 7 天
  窗口一致，互相印证。本 Session 连续第二次未安排 Daily Native
  Expressions Step2/Step5，未新增 Day 2，与第 4.2 节六步流程存在偏差，
  已在下方记录，未回填修改第 11.2 节）
- 架构：本 Session 未发现新的架构缺陷，未修改第一部分课程规范，版本保持
  V11.19。
- English：Review 昨天 Topic（Sports）全部 6 组，会话总结逐题标记 ✅，
  均通过；出现一次重复性错误 "It helps me healthy."（Q3 "It helps me
  stay healthy." 的同类错误，Session 13 已出现过一次），已当场再次纠正，
  已记入第 11 节 Sports Q3 Review History。Sports Q4（Who）/Q5（Where）
  按 Session 13 计划做了交叉强化，本次两题均标记 ✅ 通过，混淆点已解决，
  已记入对应条目 Review History。另完成 Recent 7-Day Random Review，
  覆盖 Travel / Weather / Shopping / Food / Technology 等已学 Topic
  （会话总结另提到 "English"/"Reading"/"Weekends"/"Lunch" 等描述，其中
  "English" 可能指 English Learning Topic、"Reading"/"Weekends" 对应
  Hobbies/Daily Routine 内已学 Question 的口语化简称，"Lunch" 未对应
  任何已存 Topic/Question——按第 3 节 Session Context Grounding，本节
  仅如实记录会话总结原文，未据此新增或修改任何 Bank 条目，也不代表
  该内容已正式进入 Bank）；语法纠正一处（已记入第 11 节 Technology Q6
  Review History）："I'd like to learn is AI." → "I'd like to learn
  AI. I think it is very useful."。用户明确要求 Sports 全部通过 Random
  Review（含 Q4/Q5 交叉强化）后再开始新 Topic，本 Session 判定 Sports
  已满足该条件（6/6 通过、Q4/Q5 混淆解决），随即新学 Topic 12: Music
  （Level 1），6 组 Q&A（Do you like music? / What kind of music do you
  like? / When do you usually listen to music? / Who do you usually
  listen to music with? / Why do you like music? / Can you play any
  musical instruments?），用户提供逐字 Question/Standard Answer（均为
  两句式，完整保留未缩短），中文翻译/IPA/中文谐音由 Claude 根据标准
  发音补充，已按第 11.1 节模板存入第 11 节，Level 标注为 1。完成
  Random Review、Today's Final Review、Extra Reinforcement 三轮，
  最终整体 Accuracy 100%（经当场纠正后）。纠正 3 处（均已记入第 11 节
  Music 对应条目 Review History）：(1) "No, I don't." → "No, I can't."
  （Q6，can/don't 混淆）；(2) Q4 句尾遗漏 "with"，已纠正；(3) Q6 提醒
  不得省略句首 "But"（"But I'd like to learn to play the guitar."）。
  会话总结预告 Music 第 7 题（What is your favorite singer? / My
  favorite singer is Jay Chou. I like his songs very much.），按第 3
  节 Session Context Grounding，本题尚未正式学习/练习，未写入第 11
  节，留待下次 Session 正式进行。已学 Topic 总数达到 12 个。
- Daily Native Expressions：本 Session 未涉及，连续第二个 Session 未
  新增 Day 2，第 11.2 节 Day 1 快照维持不变。
- Java：本 Session 未安排 Java Interview 练习，符合 V11.19 架构变更（Java
  正式移出每日固定流程）。Session 10 遗留的 "JVM Full GC causing high
  RT" 场景与 Session 11 遗留的 "Database Connection Pool Exhausted"
  场景仍因缺少逐字中文 Interview Question/Interviewer Intent/Canonical
  Answer 文本，未写入第 12 节，按 Session 7/10/11 已确立的先例继续保留
  待补充状态，下方 SOT Check 中继续标记 FAIL。
- Next Session：先做最近 7 天随机复习（覆盖窗口内 Music / Sports /
  Technology / Travel / Hobbies，随机顺序、避免立即重复同一题，见第 7
  节轮内去重规则；Weather 本 Session 起转入低频抽查池，仍需偶尔覆盖），
  再正式学习 Music 第 7 题（What is your favorite singer?），并对
  Music 已学 6 组做 Immediate Reinforcement。只有 Music 全部内容达到
  稳定后，才开始下一个新 Topic（Topic 13），每次新增仍不超过 6 组
  问答。另建议尽快补上已连续两个 Session 缺失的 Daily Native
  Expressions Step2/Step5（Day 2）。Java 若用户安排练习，优先补充
  "JVM Full GC" 与/或 "Database Connection Pool Exhausted" 的逐字信息
  以正式写入第 12 节并锁定。

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

### Session 4（2026-07-08）

- English：全程 Review + Speaking Practice，未引入新 Topic。完整复习 Topic
  1（Self Introduction）/ Topic 2（English Learning）/ Topic 3（Daily
  Routine），完成 Individual Q&A、Random Question Review、Consecutive
  Question Practice、Continuous Speaking Practice（呼应 V11.15 新增的
  Continuous Flow Rule，长时间连续对话未出现逐题等待"继续"的情况）。发音/
  用词强化：usually、weekends、before、get up、go to bed。学员在练习中
  自行识别出两个超纲变体并被纠正：误将 "How do you learn English?" 说成
  "What do you usually do to learn English?"；以及提出 "Where do you
  usually live?" 作为 "Where do you live now?" 的变体——均被指出不属于当前
  Question Bank，验证了第 3 节 Session Context Grounding 规则（V11.15）
  在实际对话中生效。三个 Topic 均保持 Practicing（尚未达到 9.1 节 Mastered
  标准，需未来 Random Review 持续稳定）。
- Java：Random Review "Why do you use Java?"——完整复述一次，结构保持
  稳定（结论 → 技术优势 → 个人经验 → 总结），未改写逻辑与要点，符合第 6
  节 Java Canonical Answer Rule；术语纠正：正确使用"后端"而非"后台"。保持
  Practicing——这是 Final Answer 定稿后的第一次复习，按 9.1 节标准仍需未来
  多次 Random Review 持续稳定表现才能升级 Mastered。
- 架构：本 Session 未发现新的架构缺陷，未修改第一部分课程规范，版本保持
  V11.15。

### Session 5（2026-07-09）

- 架构：本 Session 新增 V11.16（Java Scenario Interview Mode 默认化 +
  Canonical Answer Style Rule + Canonical Thinking Rule，详见文档开头版本
  历史与第 5.1/6 节）与 V11.17（Scenario 记录格式扩展——Interviewer Intent
  与 Canonical Thinking 须与 Canonical Answer 一并永久存入第 12 节，详见第
  5.2/6/12 节）。两次均判定为冻结后的 Execution Improvement，未改变 Session
  Workflow、Review Engine 选题算法、Progress Rules 或 Step1–Step5 流程结构；
  version 由 V11.15 依次推进至 V11.17。V11.17 审计中发现用户原提议的
  "Locked" Mastery 状态与第 9 节已冻结的四值词汇冲突，已通过
  AskUserQuestion 确认解决方案：沿用第 9 节既有 Mastery Status 四值，不
  新增状态值。
- Java：Interview Topic "Java Basics"（What is Java? / Why do you use
  Java?）两个基础问题均已锁定 Canonical Answer，按第 5.1 节 Scenario
  Interview Mode 永久移出每日新内容来源，仅保留在 Random Review 池。新开
  Interview Topic "Production Incident Scenarios"，首个场景 Scenario 1
  （线上接口 RT 从 50ms 飙升到 3 秒）完成 Step1 分析 → AI 示范 → Round1 →
  Round2 → Round3（均 PASS），Canonical Answer 已按新的 Scenario 记录格式
  （含 Interviewer Intent、Canonical Thinking）存入第 12 节，标记
  Practicing（按 9.1 节标准，尚未经过后续 Session 的 Random Review 验证）。
- English：本 Session 未涉及。

### Session 6（2026-07-09）

- English：新学 Topic "Family" 5 组 Q&A（Do you have a family? / How many
  people are there in your family? / Who do you live with? / What does
  your wife do? / Do you often spend time with your family?），已按
  English Learning Template（含中文翻译/IPA/中文谐音）存入第 11 节——原始
  会话总结未提供逐字 IPA 与中文谐音，由 Claude 根据标准发音补充，供后续
  发音练习参考（沿用 Session 3 Daily Routine 的既有做法）。通过中文→英文
  反复翻译练习完成 Immediate Reinforcement，另完成 3 道语法强化追加问题
  （Is your wife a teacher? / Is your wife happy? / Is your family
  happy?），强化 Do/Does/Is 疑问句型、she vs it、live with vs spend time
  with 等语法点，未作为独立 Bank 条目记录（超出每 Topic 5 组的固定数量，
  按叙述方式记录于此，不违反第 4.1 节数量规定）。Session 结束时 5 组问答
  均能独立正确作答，标记为 Practicing。
- Java：Random Review "What is Java?" 与 "Why do you use Java?"，均成功
  复述，Senior 级别答案结构保持稳定，表达更自然流利（详见第 12 节 Review
  History）；均为该问题锁定后的第二次 Random Review，按 9.1 节标准仍标记
  Practicing。
- 架构：本 Session 未发现新的架构缺陷，未修改第一部分课程规范，版本保持
  V11.17（本 Session 沿用的 Scenario Interview Mode / Canonical Thinking
  Rule / Scenario 记录格式均为 Session 5 内新增，Scenario 1 相关数据已在
  Session 5 记入第 12 节，本 Session 不重复记录，仅记录新增的 Random
  Review 与英语学习内容）。

### Session 7（2026-07-09）

- English：完整 Review 了 Topic 1–4（Self Introduction / English Learning /
  Daily Routine / Family），并针对 Family Topic 完成 Role Switch（学员成功
  用英文向 AI 提问）。Review 中出现的语法纠正："at home"（非 "in my
  home"）、"one child"（非 "one children"）——出现在自由表达延伸中，未对应
  第 11 节某条固定 Standard Answer，未回填改写历史条目。新学 Topic 5:
  Food，5 组 Q&A（What is your favorite food? / What food do you eat most
  often? / Can you cook? / What do you usually drink? / Do you like spicy
  food?），已按 English Learning Template 存入第 11 节；其中 "Do you like
  spicy food?" 的 Standard Answer 已确认为 "I like spicy food very much."
  （纠正了误加的 "is"），其余 4 组 Standard Answer 本次总结未提供逐字文本，
  沿用 Session 2 "Do you like learning English?" 的既有做法，标注待下次
  Session 确认后补全——已于本 Session 内后续补充完整（My favorite food is
  hot pot. / I eat rice most often. / Yes, I can. I can cook simple
  meals. / I usually drink water.），第 11 节 4 组占位说明已替换为正式
  Standard Answer，不再是待补全状态。完成 Immediate Reinforcement、Random
  Review、Combined Questions、Today's Final Review，5 组问答 Session
  结束时均能正确作答，标记为 Practicing（Topic 未完成）。
- Java：Interview Topic "Production Incident Scenarios" 新场景 Scenario 2
  "线上 CPU 突然达到 100%"，完成 Interviewer Intent 分析 → Canonical
  Thinking（Confirm impact → Recover business → Locate root cause →
  Verify recovery → RCA）→ 三轮回答（99 / 99 / 95）的训练流程，Round3 已
  作为 Canonical Answer 连同 Interviewer Intent、Canonical Thinking 一并
  锁定存入第 12 节（Interviewer Intent 与 Canonical Answer 原文由用户在
  同一 Session 内补充提供后完成同步）。Final Improvement 笔记（已体现在
  锁定的 Canonical Answer 中）：Recovery Verification 阶段包含"先修复
  问题、再观察系统状态"；补充讲解 Error Rate 概念；面试第一轮回答优先
  "确认业务已恢复"，具体指标留待追问时展开。标记 Practicing（按 9.1 节
  标准，尚未经过后续 Session 的 Random Review 验证）。
- Course Improvement（Validation Only，未采纳，未修改第一部分课程规范，
  版本保持 V11.17）：本 Session 验证了一种更口语化、更贴近真实 Senior
  工程师表达（约 60–90 秒）的 Java 面试回答风格候选方向，核心流程 Impact →
  Recovery → Investigation → Verification → RCA 不变；同时提出新教学模板
  候选（Interviewer Intent → Thinking Process → Canonical Answer →
  Review）。仅在本场景（CPU）验证成功，用户明确要求需在 OOM / Database /
  Redis / MQ / RT Spike 等更多场景验证后才考虑正式采纳。
- 架构：本 Session 未发现新的架构缺陷，未修改第一部分课程规范，版本保持
  V11.17。

### Session 8（2026-07-10）

- English：完整 Review Topic 1–5（Self Introduction / English Learning /
  Daily Routine / Family / Food，Food 为 full review），Immediate
  Reinforcement 与 Today's Final Review 均完成 5/5。新学 Topic 6:
  Shopping，5 组 Question（Where do you usually go shopping? / How often
  do you go shopping? / What do you usually buy? / Do you like shopping
  online? / Do you usually pay by cash or by card?）已按 English Learning
  Template（中文翻译/IPA/中文谐音由 Claude 根据标准发音补充）存入第 11
  节，Standard Answer 本次未逐字提供，沿用 Session 2/7 已确立的占位做法，
  待下次 Session 确认后补全。完成 Immediate Reinforcement (5/5)、Today's
  Final Review (5/5)，标记 Practicing（Topic 未完成）。本 Session 学习后
  已学 Topic 总数达到 6 个，首次超过第 7 节 Coverage Rule 的 ≤5 阈值，Review
  覆盖范围自下次 Session 起切换为 Priority-Based Review Engine 抽样机制。
  语法纠正（5 项，按 Accurate Feedback Rule 记录）：
  1. study vs learn：❌ How long do you learn English every day? → ✅ How
     long do you study English every day?
  2. three vs there：❌ There are there people in my family. → ✅ There
     are three people in my family.
  3. How often vs How long：❌ How long do you eat hot pot? → ✅ How often
     do you eat hot pot?
  4. Favorite drink 句型：❌ I favorite drink water. → ✅ My favorite
     drink is water.
  5. Shopping Question Pattern：❌ What do you usually pay by cash or by
     card? → ✅ Do you usually pay by cash or by card?——本 Session 唯一
     重复出现多次的错误，下次 Session 需重点复习。
- Java：Random Review "线上 CPU 突然达到 100%"（Scenario 2，Final Answer
  已于 Session 7 锁定）——复述结构（确认影响范围 → 优先恢复业务 → 结合
  监控/日志/链路追踪定位原因 → 修复并持续观察 → 组织 RCA）与已锁定
  Canonical Answer 一致，评分 99/100，符合第 6 节 Java Canonical Answer
  Rule（未改写 Canonical Answer 文本）。补充执行层改进笔记：定位原因前
  应先通过监控/链路追踪确定 CPU 消耗集中在哪个环节，再基于证据针对性排查
  具体组件，而不是先罗列所有可能原因再逐一排查。按 9.1 节标准，这是锁定
  后第一次 Random Review，标记 Practicing。
- 架构：本 Session 未发现新的架构缺陷，未修改第一部分课程规范，版本保持
  V11.17。

### Session 9（2026-07-11）

- English：完整 Review Topic "Shopping"（5/5 正确，稳定复现）与 Topic
  "Food"（5/5 正确，稳定复现；Review 时使用了 Food Question 2 的非
  Canonical 变体 "What do you usually eat?"，未覆盖第 11 节已存 Canonical
  Question "What food do you eat most often?"，已在第 11 节该条 Review
  History 中注明）。新学 Topic 7: Weather，5 组 Question & Standard
  Answer（What's the weather like today? / Do you like sunny weather? /
  Do you like rainy weather? / What's your favorite season? / Is it hot
  in summer?，含中文翻译/IPA/中文谐音）已存入第 11 节。完成 Initial
  Practice (5/5)、Immediate Reinforcement、Random Review、Combined
  Questions、Today's Final Review，5 题最终均能正确回答。纠正两处：(1)
  "because it's convenient" 与 "because I can go outside" 理由句混用
  （Topic Interference），已纠正，Standard Answer 未被修改；(2) 语序错误
  "Summer usually is very hot." → "Summer is usually very hot."。Weather
  全部 5 组标记为 **Practicing**，不得标记为 Mastered——本 Session 内完成
  的 Immediate Reinforcement/Today's Final Review 只是同一 Session 内的
  流利度达标，不满足第 9.1 节 Mastery Criteria 所要求的跨 Session 持续
  稳定表现。已学 Topic 总数达到 7 个，继续处于第 7 节 Priority-Based
  Review Engine 抽样机制下（自 Session 8 起）。
- Java：Interview Topic "Production Incident Scenarios" 新增 Scenario 3
  ——单个核心接口大量返回 HTTP 500（只有一个接口受影响；Error Rate 从 0%
  上升到 35%；RT 从 80ms 上升到约 300ms；CPU/Memory/Database/Redis/MQ
  均正常）。训练过程：AI 最初套用通用故障模板（确认影响 → 恢复业务 → 查
  日志 → RCA），用户指出未抓住场景核心；AI 随后又无证据猜测空指针、参数
  异常、数据转换失败等具体根因，用户再次指出不能直接猜具体根因；最终确认
  核心原则：HTTP 500 是异常结果而非根因、根据现象缩小范围、通过
  TraceID/日志/异常堆栈取得证据、根据证据决定回滚/修复/降级、最后验证并
  做 RCA。用户在此过程中学习了 Trace/TraceID 的含义（Trace 为一次请求的
  完整调用链，TraceID 用于串联该请求经过的服务/日志/异常，TraceID 本身
  不是根因，而是定位证据的入口）。Interviewer Intent、Canonical
  Thinking、Canonical Answer 均已按第 6 节 Java Canonical Answer Rule 与
  Canonical Thinking Rule 存入第 12 节 Scenario 3，Canonical Answer 与
  用户最终确认版本逐字一致，未来 Random Review 不得重新生成不同逻辑版本。
  标记 Practicing（按 9.1 节标准，尚未经过后续 Session 的 Random Review
  验证）。
- Execution Audit（Content/Data Synchronization + Execution Failure
  Recording，逐项审计后均判定为现行规则已覆盖，非架构缺陷，未修改第一
  部分，版本继续保持 V11.17）：
  1. Session Context Grounding 执行失败——Session 开始时未正确加载第
     11/12/13/14 节的最新学习状态，先后错误地把 Family 当作最新 Topic、
     漏掉 Shopping、漏掉 Food，用户纠正后又虚构了一个不存在的 "Good"
     Topic。结论：Existing Session Context Grounding rule was not
     executed correctly（第 3 节已要求 Session 开始前加载 Current
     Session/English Conversation Bank/Java Answer Bank，属执行失败，非
     规则缺失）。
  2. Review 顺序执行失败——本应优先复习最新的 Shopping、Food（第 7 节
     Priority-Based Review Engine 按 Mastery Status + Learning Recency
     排序），却反复复习 Family/Self Introduction/English
     Learning/Daily Routine 并提前宣布 Review 完成，经用户多次纠正后才
     补齐 Shopping 5/5、Food 5/5。判定为 Review Engine 执行错误，非架构
     缺陷。
  3. 提前进入 Java——在 Shopping Review、Food Review、Today's Lesson、
     Immediate Reinforcement、Today's Final Review 均未完成前提前进入
     Java，违反第 3/4/5 节已有的顺序要求，判定为执行失败。
  4. Correct Fast-Path 执行不一致——用户完全正确时仍多次输出长篇评价、
     发音建议、额外解释、重复列出完整答案等，未遵守既有 Correct
     Fast-Path Rule（应仅输出 "Correct. 100/100." 后立即下一题），判定为
     执行失败。
  5. Accurate Feedback / No Assumption Feedback 执行不准确——出现将有
     小错误的回答判为满分、混淆书面大小写问题与真实口语错误、对非
     Canonical 变体做未经核实的引用、先肯定后纠正、"because it's
     convenient" 用于 sunny weather 时未第一时间按 Standard Answer 纠正
     等情况，判定为既有 Accurate Feedback Rule / No Assumption Feedback
     Rule / Correct Fast-Path Rule 执行不稳定，非规则缺失。
  6. Continuous Flow 执行失败——多次在每题后停下、输出长篇解释、要求用户
     喊"继续"，与已声明的"不会停"矛盾，判定为既有 Continuous Flow Rule
     的执行失败。
  7. Today's Learning Summary 内容错误——本 Session 结束时生成的总结采用
     不符合第 10 节 Output Format 的长篇报告格式，且错误地将 Weather
     标记为 Mastered（实际应为 Practicing），混入大量额外分析。结论：The
     generated summary was not authoritative and must not be copied
     verbatim；以本次修复后的 SOT 数据为准，不新增第二套 Summary 模板。
  以上 7 项均为 EXECUTION FAILURE — NO ARCHITECTURE CHANGE，未重复新增
  同义规则，第一部分（Sections 1–10）未被修改，文档版本保持 V11.17。

### Session 10（2026-07-12）

- English：随机复习 Topic 1–7，整体表现稳定，多数问答 100/100。纠正：
  Shopping Q1 "I usually shopping..." → "I usually go shopping..."；
  Shopping Q4 "I like shop online..." → "I like shopping online..."（均
  已记入第 11 节对应条目 Review History）；一般性纠正 "Yes, it's." →
  "Yes, it is."（未指明具体 Topic 条目，仅记录于此，未回填改写任何固定
  Standard Answer）。新学 Topic 8: Hobbies，5 组 Q&A（What is your
  hobby? / Do you like reading books? / What do you usually do in your
  free time? / Do you like watching movies? / What do you usually do
  to relax?）已按 English Learning Template 存入第 11 节；IPA 与中文
  谐音本次会话总结未逐字提供，由 Claude 根据标准发音补充（沿用既有
  做法）。完成首次 Review，5 题均能正确作答，发音纠正："hobby" 曾误读
  为 "hoppy"/"habby"，已按用户提供的 Topic 8 标准答案原文纠正。Topic 8
  标记 Practicing；Topic 1–7 保持原有 Mastery Status。已学 Topic 总数
  达到 8 个。
- Java：Random Review "线上 CPU 突然达到 100%"（Scenario 2）与"线上核心
  接口大量返回 HTTP 500"（Scenario 3），复述结构均与已锁定 Canonical
  Answer 一致，用户总结为 "Stable"，未改写任一 Canonical Answer 文本，
  已记入第 12 节对应 Review History。用户另报告完成了一个新场景
  "JVM Full GC causing high RT" 的三轮训练并"固化"了一份 Final
  Canonical Answer（约 98/100），但提供的是英文要点列表，缺少逐字的
  Interview Question 中文措辞、Interviewer Intent 分析，以及符合第 6 节
  Java Interview Language Rule 与既有 Scenario 1–3 格式的完整中文
  Canonical Answer 正文。按 Session 7 已确立的先例，未凭要点/评分自行
  重构正文写入第 12 节，本 Session 未新增 Scenario 4，已向用户请求补充
  逐字信息。
- 架构：本 Session 新增 V11.18（7-Day Active Window 分层规则，详见文档
  开头版本历史与第 7 节）。用户提出英语+Java 均改为"只复习最近 7 天内
  学习内容，超过 7 天自动移出"的滚动窗口规则；审计发现与第 7 节已冻结的
  Priority-Based Review Engine（及其"不是单纯按时间截断"的设计初衷，见
  第 13.1 节既有说明）直接冲突，也影响第 9.1 节 Mastery Criteria。已通过
  AskUserQuestion 向用户说明冲突并提供三个方案，用户选择推荐的分层方案：
  7 天窗口作为默认高频复习池，窗口外内容继续由 Priority-Based Review
  Engine 做低频抽查而非永久排除，"全面复习/full review"时不受窗口限制。
  已写入第 7 节新增小节，第 13.1 节机制说明与当前窗口快照同步更新；版本
  由 V11.17 推进至 V11.18。

### Session 11（2026-07-14）

- English：复习 Topic "Self Introduction"（100%）、"Daily Routine"
  （100%）、"Family"（100%），以及 Food / Shopping / Weather / Hobbies
  （合并汇报，100%），整体表现优秀，未出现需要回填第 11 节 Standard
  Answer 的具体语法错误。发音/语法一般性纠正："local" 曾误读为 "loal"；
  its（所有格）与 it's（= it is）的混淆，均已纠正（未指明对应具体
  Topic 条目，未回填改写第 11 节任何固定 Standard Answer）。新学 Topic
  9: Travel，5 组 Question（Do you like traveling? / Where do you want
  to travel in the future? / Who do you want to travel with? / How do
  you usually travel? / What do you usually do when you travel?）已按
  English Learning Template 存入第 11 节；Question 的中文翻译/IPA/中文
  谐音由 Claude 根据标准发音补充，Standard Answer 本次会话总结未提供
  逐字文本，5 组均标注待下次 Session 确认后补全（沿用 Session 2/7/8 的
  既有占位做法）。完成 Round1/Round2/Round3/Random Review，均为 100%
  Accuracy，Topic 9 标记 Practicing——同一 Session 内达标只是流利度
  达标，不满足第 9.1 节跨 Session 持续稳定表现的 Mastered 标准（沿用
  Session 9 Weather 的既有判定方式），不采用会话总结中"进入 Active
  Review Window 即视为稳定"的表述。已学 Topic 总数达到 9 个。
- Java：用户报告新学场景 "Database Connection Pool Exhausted"，完成
  三轮训练，Final Score 100/100，标准处理流程为确认影响 → 恢复服务 →
  定位根因 → 修复问题 → 验证恢复 → RCA，涉及根因方向包括慢 SQL、长
  事务、连接泄漏、连接未释放、连接池监控、线程 Dump、数据库会话，核心
  原则为"不得盲目扩大连接池大小"。但会话总结仅提供英文流程要点与根因
  列表，缺少逐字的 Interview Question 中文措辞、Interviewer Intent
  分析，以及符合第 6 节 Java Interview Language Rule 与既有 Scenario
  1–3 记录格式的完整中文 Canonical Answer 正文。按 Session 7/10 已确立
  的先例，未凭要点/评分自行重构正文写入第 12 节，本 Session 未新增
  Scenario 记录。Session 10 遗留的 "JVM Full GC causing high RT" 场景
  同样仍未补充逐字信息、仍未写入第 12 节。已在下方 SOT Check 中标记
  FAIL，并向用户请求补充这两个场景的逐字中文信息。
- 架构：本 Session 未发现新的架构缺陷，未修改第一部分课程规范，版本
  保持 V11.18。

### Session 12（2026-07-16）

- 架构：本 Session 新增 V11.19（Architecture Change）——用户提交学习总结中
  的"新永久课程规则"部分提出四项架构级变更：Level 1→2→3 进度体系、Daily
  Native Expressions 独立内容流、第 4.2 节六步 Session 流程、Java Interview
  移出每日固定环节。逐项审计后确认均非现有规则的简单执行改进，通过
  AskUserQuestion 与用户逐条确认处理方式（均采纳推荐方案，其中 7 天窗口
  "覆盖完整题库才可重复"与已冻结的第 7 节 Priority-Based Review Engine 存在
  冲突，采用与 V11.18 一致的叠加式方案解决；Topic 9 未 Mastered 时 Topic 10
  已开始的疑点，确认为 Level 1 完成即可开新 Topic 的预期行为，非执行失误）。
  详见文档开头 V11.19 说明与第 3/4.1/4.2/4.4/4.5/5/7/8/9.1 节改动。版本由
  V11.18 推进至 V11.19。
- English：新学 Topic 10: Technology（Level 1），6 组 Q&A（数量超出以往
  Topic 惯用的 5 组，按第 4.1 节 Level System 说明，Level 1 数量按当天
  实际内容确定，不强制 5 组），已按第 11.1 节模板存入第 11 节，用户提供
  逐字 Standard Answer，中文翻译/IPA/中文谐音由 Claude 补充。完成 5 轮
  Review，标记 Practicing。Topic 9（Travel）仍为 Practicing，Topic 10 已
  按第 4.4 节 V11.19 新规则（Level 1 完成即可推进）开始，不违反架构规则。
  完成 Recent 7-Day Random Review，覆盖全部 10 个已学 Topic，整体表现
  稳定（会话总结评分 99/100）。语法纠正两处："My favorite hobby is read
  books" → "reading books"（hobby is + doing）；"They helps me relax" →
  "They help me relax"（第三人称单复数一致）。Random Review 中出现一次
  非 Canonical Question 变体："How often do you usually travel?"
  （实际存储为 "How do you usually travel?"），已记入第 11 节 Travel Q4
  的 Review History，未据此修改 Canonical Question；用户会话总结另指出
  该变体与 Shopping "How often do you usually go shopping?" 句式相近、
  "once a week"（Shopping）与"once or twice a year"（Travel）两个答案
  内容相近，均属易混淆点，供后续 Session 重点复习，未修改任何已存
  Standard Answer。已学 Topic 总数达到 10 个。
- Daily Native Expressions：新学 Day 1（场景：早晨起床流程），3 句已按
  第 4.1 节模板存入新增的第 11.2 节。完成 3 轮 Review，纠正 after/before
  混淆、"my phone" 冠词遗漏、"after I wake up" 语序三处错误。用户会话
  总结判定为 Graduated；按第 9.1 节跨 Session 稳定要求，SOT 记录为
  Practicing（同 Session 内 3 轮达标只是初步达标，与英语 Topic 的既有
  Practicing→Mastered 判定惯例一致），需后续 Session 持续稳定表现后才
  升级 Mastered。
- Java：本 Session 未安排 Java Interview 练习，符合 V11.19 起 Java 非每日
  固定环节的新架构（并非遗漏）。Session 10 遗留的 "JVM Full GC causing
  high RT" 场景与 Session 11 遗留的 "Database Connection Pool Exhausted"
  场景仍因缺少逐字中文信息未写入第 12 节，继续保留待补充状态。

### Session 13（2026-07-18）

- English：Review Topic 10（Technology），6/6 正确——该 Topic 锁定
  Session 12 内容后的首次跨 Session Random Review，按 9.1 节标准保持
  Practicing。新学 Topic 11: Sports（Level 1），6 组 Q&A（Do you like
  sports? / What is your favorite sport? / How often do you play
  sports? / Who do you usually play sports with? / Where do you
  usually play sports? / Why is exercise important?），已按 English
  Learning Template（用户提供逐字 Question/Standard Answer，中文翻译/
  IPA/中文谐音由 Claude 根据标准发音补充）存入第 11 节，Level 标注为
  1。完成约 6 轮随机顺序 Immediate Reinforcement（Individual Review /
  Random Review / Combined Questions，会话总结称为 Muscle Memory
  Training），最终随机复习准确率约 100%，标记 Practicing（同 Session
  内达标不满足第 9.1 节跨 Session 稳定要求）。语法/审题纠正 5 处："It
  helps me healthy." → "It helps me stay healthy."；"It's good for my
  healthy." → "It's good for my health."；"They are good place to
  exercise." → "They are good places to exercise."；Who/Where 两题
  混用；提问错误 "Why is your favorite sport?" → "What is your
  favorite sport?"（均已记入第 11 节对应条目 Review History）。已学
  Topic 总数达到 11 个。按第 4.4 节 Topic 推进门槛（V11.19），Topic 9
  （Travel）与 Topic 10（Technology）仍为 Practicing 的情况下开始
  Topic 11，属预期行为（Level 1 完成即可开新 Topic），非执行失误。用户
  明确要求本次不新开下一个 Topic，持续对 Sports 做肌肉记忆强化训练，
  优先在 Sports 稳定掌握后再推进——第 4.4 节 Topic 推进门槛（Level 1
  完成）只是"允许开始"的最低条件，不强制必须立即开始，本 Session 选择
  暂不推进，不违反第 4.4 节，也不构成对该节的修改。
- Daily Native Expressions：本 Session 未安排 Step2/Step5，未新增
  Day 2，与第 4.2 节六步流程存在偏差；第 11.2 节 Day 1 快照维持不变，
  未回填修改。已在第 13.2 节 Next Session 中记录，建议下次 Session
  优先补上。
- Java：本 Session 未安排 Java Interview 练习，符合 V11.19 起 Java 非每日
  固定环节的新架构。Session 10/11 遗留的两个场景（"JVM Full GC causing
  high RT" / "Database Connection Pool Exhausted"）仍因缺少逐字中文信息
  未写入第 12 节，继续保留待补充状态。
- 架构：本 Session 未发现新的架构缺陷，未修改第一部分课程规范，版本保持
  V11.19。

### Session 14（2026-07-19，会话总结标题误写为 2026-07-18，按内容"昨天
的 Topic"指向 Sports[2026-07-18]推定为次日，详见 13.2 说明）

- English：Review 昨天 Topic Sports 全部 6 组，均标记 ✅ 通过；"It helps
  me healthy."（Q3 同类错误）重复出现一次，已再次纠正。Sports Q4（Who）/
  Q5（Where）按 Session 13 计划完成交叉强化，均标记 ✅ 通过，混淆点已
  解决。完成 Recent 7-Day Random Review（覆盖 Travel/Weather/Shopping/
  Food/Technology 等，另有 "English"/"Reading"/"Weekends"/"Lunch" 等
  口语化描述，其中 "Lunch" 未对应任何已存 Bank 条目，仅如实记录，未据此
  新增内容），语法纠正一处："I'd like to learn is AI." → "I'd like to
  learn AI. I think it is very useful."（Technology Q6，已记入 Review
  History）。Sports 通过完整 Random Review 且 Q4/Q5 混淆解决后，用户
  确认满足 Session 13 设定的"稳定后再推进"条件，新学 Topic 12: Music
  （Level 1），6 组 Q&A（Do you like music? / What kind of music do you
  like? / When do you usually listen to music? / Who do you usually
  listen to music with? / Why do you like music? / Can you play any
  musical instruments?），Standard Answer 均为两句式、完整保留未缩短，
  已按 English Learning Template 存入第 11 节。完成 Random Review、
  Today's Final Review、Extra Reinforcement 三轮，最终 Accuracy 100%
  （经当场纠正）。纠正 3 处（均记入第 11 节 Music 对应条目 Review
  History）："No, I don't." → "No, I can't."（can/don't 混淆）；Q4
  句尾遗漏 "with"；Q6 提醒不得省略句首 "But"。会话总结预告的 Music 第
  7 题（What is your favorite singer?）尚未正式学习，未写入第 11 节，
  留待下次 Session。已学 Topic 总数达到 12 个。
- Daily Native Expressions：本 Session 仍未涉及，连续第二个 Session 未
  新增 Day 2，第 11.2 节 Day 1 快照维持不变。
- Java：本 Session 未安排 Java Interview 练习，符合 V11.19 架构。Session
  10/11 遗留的两个场景仍因缺少逐字中文信息未写入第 12 节，继续保留待
  补充状态。
- 架构：本 Session 未发现新的架构缺陷，未修改第一部分课程规范，版本保持
  V11.19。
