# 在 Agentic Coding 時代，純軟體工程師如何定位、轉型與保持價值

## 研究摘要

先講結論：未來五到十年，**最容易被壓縮的不是「工程師」這個職稱，而是把工程工作理解成「接需求、產 code、交 PR」的人**。AI coding 工具從 autocomplete、chat-based assistant，走到 agent mode、repo-level coding agent、背景執行的 coding agent、MCP 工具調用、多 agent workflow 之後，最先被商品化的，是可被明確描述、可被快速驗證、邊界清楚、失敗成本低的任務：CRUD、樣板、文件整理、測試骨架、基礎 refactor、簡單 bugfix、把 issue 變成初版 patch。這不是口號，而是多條證據共同指向的結果：開發者採用率已很高；Copilot、Google 內部 RCT、Microsoft/Accenture/Fortune 100 field experiments 都看到明顯效率提升；GitHub 與 OpenAI 也已把「指派 issue、背景產 PR、跑測試、要求人 review」產品化。citeturn20view0turn18view2turn25view0turn28search1turn38view1turn38view2

但同時，**「AI 能加速產生 code」不等於「AI 已經穩定接管 software engineering」**。2024 與 2025 DORA 研究很關鍵：AI 對個人 productivity、flow、文件品質、code review 速度有幫助，但 2024 研究同時觀察到 throughput 與 stability 負向效果；到 2025，throughput 與 product performance 的關係改善了，但 stability 的負向關係仍在。DORA 的總結不是「AI 讓團隊自動變強」，而是 **AI 是 amplifier**：流程好、測試好、架構鬆耦合、回饋快的團隊，會被放大；流程差、品質門檻鬆、review 能量不足、系統耦合重的團隊，問題也會被放大。citeturn24view0turn18view3turn18view4turn23search0

這也是為什麼未來工程師最稀缺的價值，會從「自己寫出多少 code」轉向 **定義問題、拆解任務、設計約束、驗證結果、治理 AI 輸出、承擔 production 後果**。GitHub 背景 agent 與 Copilot agent mode 已經能做 codebase analysis、規劃多步驟修改、執行指令、跑測試、生成 draft PR；OpenAI 與 Anthropic 官方文件則都把 agent 系統描述成「模型 + 工具 + guardrails + eval + orchestration」。這代表工程師的工作重心，正在從單純 coding 移向 **建立工作環境、上下文、工具界面、測試／eval／observability、review 與 human handoff**。citeturn38view3turn37view0turn37view2turn36view1turn36view2turn36view3

**真正的長期護城河，不是「高階一點的寫 code」，而是「控制複雜度與失敗半徑」**。Kent Beck 已經把 augmented coding 的影響講得很直白：語言熟練度這類舊杠桿會被折舊，而 vision、strategy、task breakdown、feedback loops 會被放大；軟體設計的價值在於替未來保留 optionality。Charity Majors 的觀點則補上另一半：真正的軟體擁有者不是個人，而是團隊；寫 code 的時間通常被整個 delivery lifecycle 其他環節淹沒；如果 AI 只是讓單一工程師更快地產更多 code，卻沒有測試、review、運維、incident、ownership 跟上，實際交付未必更快。Simon Willison 也明確主張：LLM coding 很難、很反直覺、context 非常關鍵，而且你**一定要測**它寫出來的東西。citeturn39view3turn39view2turn40view0

所以，未來五到十年最值得押注的，不是「prompt 熟不熟」，而是這五類能力。

第一，**複雜系統理解與控制能力**。包括資料流、狀態流、錯誤邊界、權限邊界、observability、rollback、release safety、incident response、technical debt judgment。AI 會越來越會生成局部正確的程式，但當程式產量上升，系統複雜度、變更頻率、 review 壓力、供應鏈風險與安全面也一起上升。GitHub 已經明確承認 open source 維護者面臨更多 AI slop；安全研究也反覆指出 LLM 產碼常出現漏洞、package hallucination、以及 iterative prompting 下的 security degradation。citeturn38view0turn16search6turn14search2turn14search4turn14search1turn14search15turn14search16

第二，**驗證能力比生成能力更稀缺**。這不是因為 AI 不會進步，而是因為越 powerful 的 agent，越需要可靠的 end-state evaluation、source grounding、tool correctness、policy compliance、監控與人類升級流程。Anthropic 在多 agent research 與 eval 文章裡反覆強調：先做 eval、小樣本快速驗證、用 rubric 檢查 groundedness／coverage／source quality、再持續用 human evaluation 校準；OpenAI 也把「先建立 baseline eval，再談成本和速度優化」寫成官方建議。這些都不是暫時 workaround，而是長期的 engineering discipline。citeturn36view2turn36view3turn37view0

第三，**模糊需求到可驗證技術方案的轉譯能力**。當 code 便宜，錯誤的方向反而更貴。Thoughtworks 的自主 code generation 實驗發現，模型會自己補需求空白、做沒被要求的功能、用 brute force 修法、甚至在紅測試時宣告成功。也就是說，AI 很會把模糊需求「快速實作成某種東西」，但不保證那個東西是對的、可維護的、可演進的。這使得 requirements clarification、domain modeling、acceptance criteria、quality bars 反而更值錢。citeturn39view0turn37view0

第四，**產品與 domain 理解會升值，但前提是你同時懂技術風險**。因為當實作成本下降，誰能更快把真正的 user problem / business constraint / legal-security boundary / data semantics 譯成正確系統，誰就更有價值。DORA 2024 把 user-centricity 列為 performance 的關鍵驅動；Simmon Willison 與實務社群也反覆指出，AI 讓 prototype 更快，但「throwaway prototype」和「要撐三年的 production system」不是同一件事。citeturn18view3turn40view1turn40view0

第五，**偏 infra / reliability / security / system complexity 的工程師，長期不一定最多，但更可能更貴**。原因不是 AI 不會碰這些領域，而是 AI 讓整體變更量、抽象層數、工具鏈與供應鏈複雜度提高之後，真正知道 failure mode、知道如何設定 guardrail、知道怎麼觀測與隔離風險的人，會更稀缺。從 JetBrains 調查看，Go、Rust、C++、Shell 等與 infra / performance / DevOps 高相關的技能，薪酬分布本來就偏高；Stack Overflow 2025 的 agent builder 也大量沿用 Grafana、Prometheus、Sentry、Snyk 這類既有 observability / security 工具，而不是全盤被「AI-native tooling」取代。citeturn18view1turn19view1

對不同工程師層級而言，風險是分化的。**Junior 的入口任務確實最先被壓縮**，因為 boilerplate、簡單測試、文件整理、簡單修補，本來就是 AI 目前最擅長的區域；**Mid-level generic engineer 反而可能是最危險的一群**，因為他們通常成本已上升，但還沒有真正掌控系統、需求、架構、incident、cross-team trade-off 的能力；**真正的 Senior 不是年資高，而是能定義 invariants、掌握 root cause、扛 production 責任、減少複雜度、教團隊建立可靠 AI workflow 的人**。Stack Overflow 2025 也呈現一個很重要的信號：經驗越高的開發者，越不信任 AI 輸出的準確性，越傾向保留 human verification，這和「高責任角色更重視驗證」是一致的。citeturn19view0turn19view3

最反直覺的結論是這個：**未來最有價值的純工程師，不一定是最會寫 code 的，而是最能讓「更多 AI 產出的 code」不要把系統搞爛的人。** 高價值角色會逐漸從「主力產碼者」轉成「複雜度擁有者」「驗證體系設計者」「需求到技術方案的翻譯者」「高風險系統守門員」。相反地，只會把 AI 當更快 autocomplete、卻無法說清楚自己 merge 了什麼、為何這樣設計、出錯會怎樣、六個月後誰來維護的人，最容易被商品化。這份報告的核心建議因此很直接：**不要把自己訓練成 AI 的打字員；要把自己訓練成 AI 的設計者、約束者、審核者、事故承擔者與系統簡化者。** citeturn39view3turn39view2turn36view2turn37view0turn38view0

## 證據地圖與判斷框架

這份研究使用的證據分成五類：  
一是學術與研究機構資料，例如 Microsoft/GitHub、Google、MIT/SSRN、Harvard、METR、OpenAI 與 SWE-bench 研究；二是大型 developer survey，如 Stack Overflow 2025、JetBrains 2024；三是官方工程實務文件，如 OpenAI 與 Anthropic 的 agent 設計／eval 文件；四是具長期工程實務背景的專家原文，如 Simon Willison、Martin Fowler、Kent Beck、Charity Majors；五是廠商 early signal，例如 GitHub coding agent、OpenAI harness engineering。這些資料的共同限制也很清楚：survey 有自陳偏誤，vendor case study 有利益關係，benchmark 有污染與外部效度問題，實驗常只能量到特定任務與特定時間點。citeturn20view0turn18view1turn24view0turn25view0turn28search1turn33view0turn34view0turn34view1

### 核心判斷卡

#### 純 routine coding 會被大幅壓縮

**支持證據**：AI 工具在 bounded tasks 上已顯示可觀速度提升；Copilot 官方實驗報告 55.8% speedup；Google 企業 RCT 估計約 21% speedup；三個 field experiments 合併後對 PR throughput 有正向效果；GitHub 已把「issue 指派給 agent、背景開 draft PR、跑測試、等人 review」商品化。citeturn18view2turn26search16turn25view0turn28search1turn38view1turn38view2

**反方證據**：METR 在熟悉 repo 的資深 OSS 開發者 RCT 中觀察到 early-2025 AI 讓任務完成時間 **變慢 19%**；2024 DORA 也看到 throughput 與 stability 的下滑；Thoughtworks 的自動生成實驗顯示，複雜度一上升，模型會補需求空白、誤判成功。citeturn31view1turn24view0turn39view0

**暫定結論**：routine coding 會被壓縮，但壓縮速度受任務型態、repo 熟悉度、質量門檻、workflow 設計與驗證成本強烈影響。  
**證據強度**：強。  
**時間尺度**：一到三年最明顯。  
**信心等級**：高。  
**主要依據**：研究、公司報告、產品實作。  
**可能失效條件**：若 AI 在熟悉大型 codebase、隱含需求、長時間穩定代理上的能力出現非線性突破，壓縮範圍會擴大。citeturn33view0turn31view0

#### 工程師價值正從產碼轉向定義、驗證與治理

**支持證據**：OpenAI 將 agent 建構核心寫成 tools、guardrails、orchestration、eval baseline；Anthropic 強調小樣本 eval、rubric、human calibration；GitHub 的 coding agent 設計本身就是「AI 產出 PR、由人治理」。citeturn37view0turn37view2turn36view2turn36view3turn38view1turn38view2

**反方證據**：市場上仍有大量使用停留在 autocomplete 或 chat Q&A；多數團隊尚未把正式 eval / governance 建成標準流程。citeturn39view1turn20view0

**暫定結論**：方向幾乎確立，但不是所有團隊都完成轉型；會先在高品質團隊發生。  
**證據強度**：強。  
**時間尺度**：一到五年。  
**信心等級**：高。  
**主要依據**：官方 agent 文件、實務案例、survey。  
**可能失效條件**：若 agent 平台自動內建成熟的 verification / observability / rollback，人工治理比重可能下降，但不會歸零。citeturn37view3turn36view2

#### 高階工程能力會先升值，但不是全部都能長期保值

**支持證據**：經驗較高的開發者更不信任 AI 準確性；Stack Overflow 顯示多數開發者不願把 deployment/monitoring/project planning 直接交給 AI；Thoughtworks 也指出 human supervision 仍必要。citeturn19view3turn19view0turn39view0

**反方證據**：GitHub agent mode 已能分析 codebase、執行多步驟方案、跑指令與測試、提出架構建議；OpenAI、Anthropic、GitHub 都在把更高階的 repo-level 與 orchestration 能力平台化。citeturn38view3turn37view2turn36view1

**暫定結論**：真正保值的不是「會做高階任務」，而是**能對高階任務負責任**，包括在不完整資訊下做取捨、為長期可維護性與事故風險負責。  
**證據強度**：中強。  
**時間尺度**：三到十年。  
**信心等級**：中高。  
**主要依據**：survey、專家判斷、產品進展。  
**可能失效條件**：若模型在長期記憶、可驗證推理、狀態管理與 production toolchain 上顯著突破，高階能力中可模板化的部分會更快被吃掉。citeturn33view0turn34view0

#### System Complexity Owner 可能是最穩的長期定位

**支持證據**：DORA 指出 AI 會放大既有流程優缺點；GitHub 維護者已抱怨 AI slop 使 review 負擔上升；Charity 强調交付速度不只取決於人寫 code 的快慢，而是團隊 collectively test/review/ship/maintain 的速度；Kent Beck 強調 optionality 與 feedback loops。citeturn18view4turn38view0turn39view2turn39view3

**反方證據**：這不是標準職稱，許多公司未必有對應晉升結構；而且部分 complexity work 可能被平台團隊或 agent platform 吸收。citeturn24view0turn37view0

**暫定結論**：作為「能力組合」而非職稱，它是五到十年最穩的護城河之一。  
**證據強度**：中強。  
**時間尺度**：三到十年。  
**信心等級**：中高。  
**主要依據**：研究 + 實務推論。  
**可能失效條件**：若企業把大部分系統複雜度外包給極成熟平台，個體工程師的 complexity ownership 空間會縮小，但高風險系統仍需要人類 owner。citeturn23search0turn18view3

#### AI Agent Builder 是紅利，但純 prompt 工程不是長期護城河

**支持證據**：OpenAI 與 Anthropic 都傾向把工具定義、guardrail、eval、orchestration 做成標準 SDK 與平台能力；OpenAI 明確建議先把單 agent 用到極致，再按需要拆多 agent；Simon Willison 也把 coding agent 說穿成「LLM + system prompt + tools in a loop」。citeturn37view2turn37view0turn36view1

**反方證據**：在現階段，context engineering、tool schema、workflow 拆分、MCP 接法、agent failure analysis 仍然高度需要工程經驗；Anthropic 自己也指出 multi-agent 具有 emergent behavior，需要大量 eval 與人測。citeturn36view2turn38view2

**暫定結論**：**純 prompt/copy workflow 的價值偏短期；eval design、harness engineering、工具治理、權限與失敗分析偏長期。**  
**證據強度**：中強。  
**時間尺度**：一到五年。  
**信心等級**：高。  
**主要依據**：官方文件、專家實務。  
**可能失效條件**：如果平台層無法穩定抽象多 agent／tool use，而需要大量手工調參，紅利期會比預期更長。citeturn37view3turn36view3

#### Junior 入口被壓縮，最危險的不一定是 Junior，而是 generic Mid-level

**支持證據**：初階與中階日常大量依賴的 boilerplate、簡單測試、文件與簡單修補，正是 AI gain 最大的領域；Early-career dev 每日使用 AI 的比例高於 experienced dev；experienced dev 對準確性更不信任。citeturn19view0turn19view3turn18view2

**反方證據**：仍有公司公開表示會持續招 junior；開源與新貢獻者進入門檻因 AI 而降低。citeturn10search9turn38view0

**暫定結論**：Junior 任務會先被吃掉，但**最容易被市場擠壓的可能是「會用工具但仍缺 ownership 的 Mid-level」**。  
**證據強度**：中。  
**時間尺度**：一到五年。  
**信心等級**：中。  
**主要依據**：survey、任務分析、專家判斷。  
**可能失效條件**：若企業重新設計 apprenticeship，讓 Junior 直接在 AI-assisted flow 中學 debug、review、incident、ownership，則 Junior 不一定最慘。citeturn37view0turn36view2

#### Reliability、Security、Observability 會因 AI code volume 上升而升值

**支持證據**：DORA 顯示穩定性風險仍存在；多個安全研究指出 LLM 產碼常出現漏洞、package hallucination、以及 iterative interaction 下的 security degradation；Stack Overflow 2025 的 agent builder 主要沿用 Grafana/Prometheus/Sentry/Snyk 等觀測與安全工具。citeturn24view0turn18view4turn16search6turn14search2turn14search4turn19view1

**反方證據**：AI 也會逐步提升安全掃描、修復生成與 incident triage 的能力。citeturn14search5turn15search0

**暫定結論**：AI 不會讓 reliability/security 消失，反而會把它們推向更前面，因為 change volume 上升時，風險也同步放大。  
**證據強度**：強。  
**時間尺度**：一到十年。  
**信心等級**：高。  
**主要依據**：研究、安全論文、survey。  
**可能失效條件**：若安全與可靠性 verification 被高度自動化，個體工程師要把自己升級到 system-level governance 才能保持稀缺。citeturn17search0turn22search7

#### 底層能力與產品能力不是二選一；最佳組合是「一深一高」

**支持證據**：DORA 把 user-centricity 視為 performance driver；JetBrains 顯示偏 infra/低層語言相關角色薪酬較高；OpenAI/Anthropic 文件則顯示 orchestration、tool use、legacy integration、computer use 對舊系統與跨系統工作都很重要。citeturn18view3turn18view1turn37view0turn36view3

**反方證據**：對一般 Web / SaaS 工程師來說，把大量時間投入 compiler 或 OS kernel 級深度，未必有最好報酬。citeturn18view1

**暫定結論**：一般產品工程師最優投資組合是：**有一個不可替代的深技術面向，再加上一個 domain / product / orchestration 面向**。  
**證據強度**：中。  
**時間尺度**：三到十年。  
**信心等級**：中高。  
**主要依據**：研究 + 職能推論。  
**可能失效條件**：若你的產業高度法規化、資安化或性能密集，底層能力權重會顯著更高。citeturn19view1turn23search7

## 角色與技能經濟

### AI coding 到底正在改變什麼

| 階段 | AI 主要能力 | 吃掉哪些工作 | 讓誰更強 | 容易商品化誰 | 新責任 | 對 AI-native Engineer 的含義 |
|---|---|---|---|---|---|---|
| autocomplete / pair programmer | 行級、函式級補全 | 樣板、語法記憶、簡單 glue code | 熟悉問題本質、能快速判斷 suggestion 的工程師 | 只靠語法熟練吃飯的人 | 驗證 suggestion、避免錯誤複製 | 幾乎不是新職種，只是新工具 |
| chat-based assistant | 問答、說明、一次性生成 | 文件閱讀摘要、API 查詢、簡單測試、簡單重構 | 能給清楚上下文與需求的人 | 只會搜尋 stack answers 的人 | prompt/context 組織、測試與執行 | prompt 熟練有短期價值，但不穩 |
| agentic IDE | 多步驟修改、跑測試、依回饋迭代 | 小功能、修 bug、初版 refactor | 有好 repo hygiene、CI、lint、test 的團隊 | 只會「手動把機械步驟做完」的人 | review AI patch、觀測 agent 行為、設 boundary | 開始出現 workflow 設計需求 |
| repo-level coding agent | codebase 分析、跨檔修改、背景 PR | issue → draft PR 的大量日常工作 | Senior、codebase owner、能精確定義 acceptance criteria 的人 | generic mid-level implementer | 定義任務大小、風險分級、merge gate | 單純 agent 操作會被平台化 |
| multi-agent workflow | 分工、平行子任務、工具編排 | 大量資訊檢索、部分 spec-to-implementation pipeline | 會做 eval/harness/guardrail 的人 | 純 prompt operator | agent 邊界設計、失敗恢復、成本控制 | 角色價值向 eval / harness 轉移 |
| CI/CD integrated agent | PR 檢查、修測試、修 lint、根據評論再改 | 機械式 review iteration、品質門檻的低階工作 | 能設 gate 與 rubric 的工程師 | 只做機械 review 的人 | policy、審批、審計、fallback | 從 builder 轉為 governor |
| autonomous debugging / testing / refactoring | log/trace 分析、修復候選、測試生成 | 常見 root-cause、低風險測試生成、局部重構 | 擅長判斷 false positive / false fix 的人 | 只會根據表象修 bug 的人 | end-state 驗證、rollback、觀測 | failure analysis 變成核心 |
| self-healing / software factory | 自動處理變更、修復與部署 | 高度標準化、低風險服務的日常運作 | platform / SRE / governance 能力強者 | ticket-driven coder | policy-as-code、blast radius 控制 | 純 workflow 配置價值下降 |

這個演進路徑的核心不是「工具越來越強，所以工程師越來越沒用」，而是 **可標準化、可局部驗證的工作逐步被吸收；不可局部驗證、需要承擔後果的工作被留下來，且更貴。** GitHub 已使背景 coding agent 常態化，OpenAI 與 Anthropic 也都把 agent orchestration、guardrails、human-in-the-loop 視為正式工程問題，而非 demo 技巧。citeturn38view1turn38view2turn38view3turn37view0turn37view2turn36view2

### 高階工程能力會升值，還是只是晚一點被取代

| 能力 | 短期變化 | 長期風險 | 為何暫時升值 | 何處可能被 AI 壓縮 | 人類長期不可替代部分 |
|---|---|---|---|---|---|
| system design | 升值 | 中 | 需要把模糊需求轉成結構 | 架構草案、常見模式選型 | 在現實限制下負責 trade-off |
| architecture judgment | 升值 | 中 | 牽涉成本、團隊、遷移路徑 | pattern suggestion、diagram draft | 對未來演化與事故負責 |
| technical trade-off | 升值 | 中低 | 涉及業務、性能、治理、風險 | 比較文件與選項枚舉 | 在不確定下拍板並承擔 |
| code review | 先升值 | 中高 | AI PR 變多，治理需求暴增 | style/nit/comment automation | 審核 invariants、可維護性、風險 |
| debugging | 明顯升值 | 中 | code volume 增，錯誤仍需定位 | 常見 stacktrace 模式匹配 | 真 root cause 與跨邊界因果推理 |
| reliability | 升值 | 低中 | change volume 增，stability 壓力上升 | 基本 runbook、檢測與修補建議 | SLO／錯誤預算／事故指揮 |
| maintainability | 升值 | 低 | AI 容易寫出局部可跑但結構差的 code | 低階 lint/refactor | 簡化策略、模組界線、未來 optionality |
| incident handling | 升值 | 低 | 高壓、跨團隊、資訊不完整 | 初步 triage 與查詢 | 決策、溝通、風險權衡 |
| technical debt judgment | 升值 | 低 | 代碼產出更快，爛債累積更快 | debt list 盤點 | 哪些債可留、哪些必清、何時清 |
| requirements → plan | 升值 | 中低 | AI 會補空白、但不保證方向正確 | spec 初稿、task 分解 | 不讓錯誤 spec 被高速放大 |
| legacy understanding | 先升值 | 中高 | 長 context 與 repo QA 有幫助 | codebase summarization | 與實際運維歷史、隱性規則對照 |
| codebase ownership | 升值 | 低 | 誰來對 agent 產出負責更重要 | ticket-level ownership | 長期演進、邊界治理、團隊傳承 |
| failure analysis | 升值 | 低 | 系統更複雜，AI 也會引入新失敗模式 | log clustering、疑似原因產生 | 因果排除、系統性改進 |

表面上，很多高階能力都會被 AI 觸碰；但真正長期保值的，不是「會不會產出 architecture / review / debug 文字」，而是**對這些判斷的正確性、成本與後果負責**。這也是「System Complexity Owner」比「會畫幾張架構圖的人」更耐久的原因。citeturn39view0turn39view1turn39view3turn39view2turn24view0

### 底層技術 vs 產品 / domain / orchestration

這題不該用價值觀回答，應該用工作分布與風險結構回答。

**底層能力升值的情境**：  
當你處在高性能、分散式、資安敏感、資料一致性、網路行為、runtime / memory、kernel / compiler、platform / infra、observability / reliability 密集的工作裡，底層能力會更珍貴。AI 會產生更多抽象層，但抽象層越多，真正看得懂底層 failure mode 的人越少，反而更值錢。JetBrains 的薪酬資料也反映出，與 DevOps / infra / systems 關聯較高的語言與角色，薪酬分位通常較高。citeturn18view1

**高抽象能力升值的情境**：  
當實作成本下降、你需要在多個方案間快速選擇、面對模糊需求、跨職能協作、做 domain 建模、設計 eval / HITL 流程、讓 agent 與既有工具整合時，高抽象能力會更珍貴。DORA 指出 user-centricity 是 performance driver；OpenAI/Anthropic 文件則都把 eval、guardrails、tooling、orchestration 當成 agent 成敗核心。citeturn18view3turn37view0turn36view2turn36view3

**對一般 Web / SaaS / App 工程師的最佳投資組合**：  
不是去追求 OS / compiler 專家級，也不是只做 product generalist，而是：

1. 把 **database、networking、runtime/concurrency、caching、auth、observability、testing** 練到「能畫資料流、狀態流、錯誤邊界」的程度。  
2. 補上 **domain modeling、requirements clarification、acceptance criteria、AI workflow design、eval/test strategy**。  
3. 至少選一個深水區做 moat：可為 reliability、security、performance、data systems、frontend state complexity、mobile runtime、platform engineering。  

換句話說，對大多數產品工程師，最佳配置不是「全棧皮毛 + 工具很熟」，而是 **一個難取代的技術深區 + 一個難外包的問題定義能力**。這是本報告最重要的能力配置建議之一。citeturn18view3turn19view1turn39view3turn40view1

### 未來工程團隊型態對個人的影響

未來團隊更可能出現的不是「工程師消失」，而是以下變化同時發生：

工程師更容易同時管理多個 agent 任務，單人可覆蓋的變更面增加；Junior/Mid/Senior 的比例可能朝「更少純 implementer、更多 reviewer / owner / platform / reliability 能力」移動；QA、DevOps、PM、Designer 與 Engineer 的邊界在低風險任務上模糊，但在高責任決策上反而更需要明確 owner；code review 會有更大比例轉向 **govern AI output**；而個人工程師會被迫承擔更多 product clarification、test/eval、ops、architecture、agent supervision。citeturn38view1turn38view2turn37view3turn39view2turn24view0

這對個人的意義很現實：**不是自動升值，而是責任上移**。如果你原本就有 ownership、debug 與判斷能力，這是升值；如果你原本只靠搬運 ticket，這會是壓力與淘汰。citeturn39view2turn39view3turn31view1

## 分化、風險與未來定位

### Junior、Mid、Senior、Tech Lead 的分化

**Junior** 確實最容易先失去舊練功路徑。因為 boilerplate、CRUD、簡單 bugfix、測試骨架、文件整理，都是 AI 今天已經相對強的區域。這不表示 Junior 不需要了，而是傳統「先刷票、慢慢長」的路徑正在縮窄。未來 Junior 若要活下來，必須更早學會：畫資料流、解釋 root cause、讀 log、設 assertion、把需求拆成可驗證子問題、review AI patch，而不是只提交能跑的 code。citeturn19view0turn18view2turn40view0

**Mid-level** 反而是我認為最危險的一層。因為市場過去願意為這群人付錢，部分原因是他們能穩定處理大量日常工程工作。但未來這部分會被 agent 大幅吸收。如果 Mid-level 不能往 ownership、跨模組 debug、non-functional requirements、技術取捨、AI workflow governance 升級，他的價格與不可替代性會同時下降。這是本報告最「殘酷但實際」的判斷。citeturn38view1turn38view3turn39view2

**真正的 Senior** 不是當過很多年工程師，而是符合四件事：  
一，知道什麼不該自動化、什麼能安全交給 AI；  
二，能在資訊不完整時找 root cause，而不是只修 symptom；  
三，能為長期 maintainability 與生產事故風險負責；  
四，能把團隊流程改造成 AI-assisted 之後仍可靠。  
這種 Senior 會升值。只有年資、但沒有 system ownership 的 Senior，會晚一點被壓縮，而不是安全。citeturn39view3turn39view2turn36view2turn24view0

**Tech Lead / Architect 候選人** 的價值會更取決於能否同時掌握 product ambiguity、architecture trade-off、delivery workflow、AI governance。未來 Tech Lead 不只是技術方向提出者，也會是 agentic workflow 的責任邊界制定者：哪些任務可交 agent、哪些必須 human sign-off、哪些要有 stronger eval、哪些系統不允許 vibe coding。citeturn37view0turn39view0turn40view1

### 技能升值、貶值、過渡期判斷表

| 技能 | 目前價值 | AI 壓縮風險 | 一到三年 | 三到五年 | 五到十年 | 證據強度 | 信心 | 建議投入 |
|---|---|---:|---|---|---|---|---|---|
| coding fluency | 高 | 中 | 小幅折舊 | 持續折舊 | 仍必要但非差異化 | 強 | 高 | 中 |
| framework familiarity | 中高 | 高 | 折舊 | 明顯折舊 | 商品化 | 強 | 高 | 低中 |
| CRUD implementation | 中 | 很高 | 明顯折舊 | 高度商品化 | 幾乎無 moat | 強 | 高 | 低 |
| debugging | 高 | 中 | 升值 | 升值 | 仍高 | 強 | 高 | 很高 |
| code review | 高 | 中 | 升值 | 轉為治理 AI | 仍高但形式變 | 中強 | 高 | 很高 |
| system design | 高 | 中 | 升值 | 部分平台化 | 仍重要 | 中強 | 中高 | 很高 |
| architecture trade-off | 很高 | 中 | 升值 | 升值 | 仍高 | 中強 | 中高 | 很高 |
| performance optimization | 中高 | 中低 | 穩定/升值 | 升值於高負載場景 | 高價少數 | 中 | 中高 | 中高 |
| security | 很高 | 低中 | 升值 | 升值 | 升值 | 強 | 高 | 很高 |
| reliability | 很高 | 低 | 升值 | 升值 | 升值 | 強 | 高 | 很高 |
| observability | 很高 | 低 | 升值 | 升值 | 升值 | 強 | 高 | 很高 |
| testing | 高 | 中 | 生成層折舊、策略層升值 | 同前 | 同前 | 強 | 高 | 很高 |
| eval design | 中高 | 低中 | 明顯升值 | 升值 | 長期高價 | 強 | 高 | 很高 |
| AI workflow design | 中高 | 中 | 升值 | 分化 | 核心留在高風險流程 | 中強 | 中高 | 高 |
| prompt / context engineering | 中 | 高 | 短期紅利 | 平台化 | 只留在困難場景 | 中強 | 高 | 中低 |
| domain modeling | 高 | 低中 | 升值 | 升值 | 升值 | 中強 | 高 | 很高 |
| product thinking | 中高 | 低中 | 升值 | 升值 | 升值 | 中強 | 高 | 高 |
| requirements clarification | 很高 | 低中 | 升值 | 升值 | 升值 | 強 | 高 | 很高 |
| codebase ownership | 很高 | 低 | 升值 | 升值 | 升值 | 強 | 高 | 很高 |
| technical debt management | 很高 | 低 | 升值 | 升值 | 升值 | 中強 | 高 | 很高 |
| production incident handling | 很高 | 低 | 升值 | 升值 | 升值 | 強 | 高 | 很高 |

本表是綜合 DORA、Stack Overflow、JetBrains、GitHub/Google/Microsoft/MIT 實驗，以及 security / maintainability 研究和資深工程師原文後的判斷；其中「功能生成層折舊、策略驗證層升值」是最穩的總趨勢。citeturn24view0turn18view4turn20view0turn18view1turn18view2turn25view0turn28search1turn16search6turn14search2turn39view3

### 工程師類型風險表

| 工程師類型 | 目前價值來源 | 最容易被 AI 吃掉的部分 | 商品化風險 | 五到十年出路 | 建議訓練方向 |
|---|---|---|---|---|---|
| 只會接需求寫 CRUD | 產能 | 主要工作本體 | 很高 | 轉 QA/eval、domain support，否則危險 | debug、需求拆解、資料流理解 |
| 只會套框架 | framework 熟手 | scaffolding、拼裝、升級 | 很高 | 要嘛成為 domain engineer，要嘛被替代 | domain model、架構與測試 |
| 只會拼 API | 整合速度 | glue code、文件查閱 | 高 | 轉 workflow owner | 邊界錯誤、auth、state flow |
| 只會修簡單 bug | 票單產能 | 常見 bugfix | 高 | 升級到 root-cause debug 才能活 | tracing、profiling、incident drill |
| 不理解系統資料流/狀態流 | 局部交付 | 大部分工作 | 很高 | 危險 | 系統圖、狀態圖、資料契約 |
| generic Mid-level | 穩定交付 | 大量日常實作 | 很高 | 兩極分化 | ownership、trade-off、AI governance |
| Senior 但無 ownership | 經驗年資 | 可模板化高階工作 | 中高 | 晚一點被壓縮 | incident、mentoring、architecture |
| 真正 Senior / codebase owner | 判斷與責任 | 局部寫碼 | 低中 | 升值 | 組織化 AI workflow、複雜度控制 |
| Product-minded Engineer | 問題定義 | 細碎實作 | 中低 | 升值 | domain、spec、驗證策略 |
| Domain Engineer | 行業知識 + 技術 | 泛用實作 | 低中 | 升值 | data semantics、規則系統 |
| AI Agent Builder | workflow 搭建 | prompt 拼裝 | 中高 | 分化 | eval、tooling、governance |
| Infra / Reliability / Security | NFR 與風險控制 | 低階維運腳本 | 低 | 升值 | platform、policy、observability |

### 未來工程師定位模型

| 定位名稱 | 核心價值 | 長期護城河程度 | 被平台化風險 | 適合對象 | 訓練方式 | 驗收標準 |
|---|---|---:|---:|---|---|---|
| AI-supervised Developer | 用 AI 放大日常交付，但自己把關 correctness | 中 | 中 | Web / SaaS / App 工程師 | 建立 review 與測試習慣 | 能清楚解釋每個 AI patch |
| AI Agent Builder | 組 agent workflow、工具、上下文 | 中 | 高 | 對工具鏈敏感者 | 做真實 workflow、接工具與 eval | 不是 demo，而是穩定可重跑 |
| AI Workflow Architect | 設計 agentic SDLC、權限、gate、handoff | 高 | 中 | Senior / Lead | 做 team-level workflow 改造 | 能降低返工/故障率 |
| System Complexity Owner | 控制大型 codebase / distributed system 複雜度 | 很高 | 低 | Senior / Architect 候選人 | 事故復盤、架構 simplification | 能讓系統更簡單且更穩 |
| Product-minded Engineer | 模糊需求 → 可驗證技術方案 | 高 | 低中 | 產品工程師 | 規格撰寫、domain 建模、驗收設計 | 方案落地後返工少 |
| Domain Engineer | 深 domain + 實作 | 高 | 低 | SaaS、金融、醫療、製造等 | 深入業務規則與資料語義 | 能定義別人講不清楚的規則 |
| Infra / Reliability / Security Engineer | 控制 AI 時代的變更風險與系統邊界 | 很高 | 低 | 偏 infra / SRE / sec | observability、policy、chaos drill | 事故更少、恢復更快 |
| Technical Leader / Codebase Owner | 定方向、立標準、帶人與帶 workflow | 很高 | 低 | 真 Senior、Lead 候選人 | 做 owner、做 review、做復盤 | 沒你寫也能穩定交付 |

其中幾個重點判斷：  
**AI Agent Builder** 作為獨立職稱，確實可能只是一到三年的紅利；如果能力停在 prompt、接 SDK、拼 MCP，很容易被平台吸收。  
**System Complexity Owner** 比較可能是長期護城河，因為它對應的是組織永遠存在的問題：複雜度失控、邊界失序、交付脆弱。  
**Product-minded Engineer** 在實作成本下降後大機率升值，但前提是能對技術後果負責，不是只會聊需求。  
**Domain Engineer** 幾乎一定比一般 framework engineer 更難被替代，因為 domain semantics 無法僅靠公開資料學完整。  
**Infra / Reliability / Security** 在 AI code volume 增加後，重要性只會更高。citeturn37view0turn36view2turn39view3turn39view2turn24view0turn19view1

## 訓練路線、自我檢查與團隊影響

### 分層能力訓練路線圖

| 角色 | 主要風險 | 被 AI 壓縮的能力 | 可能升值的能力 | 0–3 個月 | 3–12 個月 | 1–3 年 | 3–10 年定位 | 推薦 project / exercise | 驗收標準 | 常見假進步 |
|---|---|---|---|---|---|---|---|---|---|---|
| Junior Engineer | 入口任務被吃掉 | boilerplate、簡單測試、文件整理 | debug、系統圖、review 能力 | 每週手畫一個 code path；所有 AI 產碼都要口頭解釋 | 做 tracing、DB query、failure case 練習 | 接手小模組 ownership | AI-supervised developer / domain junior | 修 10 個真 bug 並寫 root cause memo | 不用 AI 也能說清 bug 成因 | prompt 變熟，但根因分析沒進步 |
| Mid-level Engineer | 成本升高但不可替代性不足 | routine implementation | ownership、trade-off、incident 協作 | 建立 PR 風險分級與 merge checklist | 主導一個跨模組小功能 + 觀測儀表板 | 帶一段流程改造 | Product-minded engineer / workflow owner | 將 AI 納入真實功能交付並量測返工率 | 速度加快但故障沒變多 | code 變快但 review 水準沒升 |
| Senior Developer | 被更便宜的 agent 吃掉 implement 部分 | 大量親手寫碼 | 複雜度控制、mentoring、governance | 為團隊建立 AI 使用規範 | 建 eval / test / observability 標準 | 成為 codebase owner | System complexity owner / tech lead | 做一次架構瘦身與 incident 復盤 | 能讓團隊更穩而非只自己更快 | merge 更快但 technical debt 暴增 |
| Tech Lead / Architect 候選人 | 只會紙上談兵 | 可模板化設計文件 | trade-off、boundary setting、workflow governance | 練習寫 ADR 與 rollback plan | 建立風險矩陣與人機分工 | 主導平台/架構演進 | Technical leader / workflow architect | 設計高風險任務不可交 AI 的規則 | 能把模糊需求落到可驗證計畫 | 會畫圖但不會定 quality bar |
| AI-native Engineer / Agent Builder | 純工具熟練度被平台化 | prompt tricks、接 SDK | eval、harness、failure analysis、policy | 先做單 agent + eval，不追求花俏多 agent | 接真工具、做 guardrail、成本/成功率 dashboard | 管理 agent portfolio | AI workflow architect | 建一個端到端 agent workflow 並持續量測 | 不是能跑，而是可測、可審、可復現 | 只會用工具，不懂 failure mode |
| Infra / Reliability / Security 工程師 | 把 AI 當成方便腳本卻忽略新風險 | 低階腳本化操作 | observability、policy、supply chain、incident AI governance | 盤點 AI 引入的權限與資料邊界 | 建 detection / review / rollback flow | 發展成 platform / sec owner | Infra / reliability / security owner | 建 AI 代碼進入生產前的 gates | 風險降低、不是只有速度提高 | 工具用了很多，控制面沒變強 |

### 分層殘酷自我檢查清單

以下清單是基於前文證據綜合提煉的**危險度自測工具**。若你有大量題目答「否」，代表你不是「還沒跟上工具」，而是**位置本身在變危險**。citeturn39view3turn39view2turn40view0turn36view2turn24view0

#### Junior

1. 你能不用 AI，把自己最近一次改動的 code path 從入口講到出口嗎？  
2. 你能畫出該功能的資料流嗎？  
3. 你知道這段 code 的狀態何時建立、何時失效嗎？  
4. 你能說明這個 bug 真正的 root cause，而不是只描述現象嗎？  
5. 你知道這個 PR 最重要的三個 failure case 是什麼嗎？  
6. 你有親手跑過測試，而不是只相信 AI 說綠燈嗎？  
7. 你能解釋自己加的每個 assertion 在防什麼嗎？  
8. 你知道這次改動碰到哪些外部依賴嗎？  
9. 你能說出這段 code 的 rollback 方式嗎？  
10. 你知道 production 上會怎麼觀測這個功能嗎？  
11. 你能分辨「能跑」與「可維護」的差別嗎？  
12. 你有沒有 merge 過自己其實講不清楚的 code？  
13. 你知道 AI 產出的套件／API 是否真的存在嗎？  
14. 你知道哪部分是業務規則、哪部分只是實作細節嗎？  
15. 你能把一個 ticket 拆成可驗證的小步驟嗎？  
16. 你有沒有一週至少一次手動 debug，而不是全靠聊天視窗？  
17. 你會看 log / trace / network panel / SQL plan 嗎？  
18. 你知道測試通過不等於需求成立嗎？  
19. 你能指出這段 AI code 可能在六個月後造成什麼維護麻煩嗎？  
20. 你是否開始擁有「模組責任」，而不只是「票單責任」？  

#### Mid-level

1. 你能定義一個功能的 acceptance criteria，而不是只問別人要怎麼做嗎？  
2. 你能判斷哪些任務可以交 AI、哪些不行嗎？  
3. 你能估計一段改動的 blast radius 嗎？  
4. 你能設計最小可回滾方案嗎？  
5. 你能指出這個系統最脆弱的邊界在哪裡嗎？  
6. 你會因為 AI 讓你更快，就放寬品質門檻嗎？  
7. 你知道什麼時候應該先補測試再改功能嗎？  
8. 你能把模糊需求轉成技術計畫與驗收點嗎？  
9. 你能 review AI 產出的 architecture suggestion，而不只是照單全收嗎？  
10. 你是否知道自己所在系統的核心 invariants？  
11. 你能帶一個較 Junior 的工程師一起 debug 嗎？  
12. 你能解釋為什麼某個技術債現在不該還、某個債一定要還嗎？  
13. 你知道什麼是非功能需求，且會主動問嗎？  
14. 你能辨識「AI 幫你更快」和「AI 幫你堆更多未來問題」的差別嗎？  
15. 你會主動建立 observability，而不是出事再補嗎？  
16. 你知道自己的 AI workflow 哪一步最常產生假正確嗎？  
17. 你有沒有把 agent 產出的 patch 分級，而不是一視同仁？  
18. 你能獨立接手一個模組一季以上嗎？  
19. 你能在不新增複雜度的前提下完成需求嗎？  
20. 你是否已經從 implementer 變成 owner？  

#### Senior

1. 你能在高壓 incident 中快速縮小搜尋空間嗎？  
2. 你能定義什麼叫「足夠可靠」嗎？  
3. 你能用標準化流程而非個人英雄主義帶團隊用 AI 嗎？  
4. 你能看出 AI code 哪裡「方向對但做法差」嗎？  
5. 你能判斷某個 refactor 會不會破壞未來 optionality 嗎？  
6. 你能讓別人接手你的系統而不失速嗎？  
7. 你能把問題簡化，而不只是把複雜度藏起來嗎？  
8. 你會拒絕高風險 vibe coding 嗎？  
9. 你能分辨工具升級和工作方法升級的差異嗎？  
10. 你能設計人機協作的 approval gate 嗎？  
11. 你能判斷現階段該用單 agent 還是多 agent 嗎？  
12. 你會要求 eval，而不是只看 demo 成功嗎？  
13. 你能指出 agent failure 是模型、上下文、工具還是流程造成的嗎？  
14. 你會把 AI 當 junior 還是當不可靠但有力的 subsystem？  
15. 你能把複雜需求拆成可平行處理的任務但仍維持一致性嗎？  
16. 你知道何時應該人工起草，而不是讓 AI 先寫嗎？  
17. 你是否仍保有親手 trace、profiling、讀 source 的能力？  
18. 你有沒有建立量測 AI 真的帶來何種改善，而非只靠感覺？  
19. 你是否能把 AI 導入後的品質成本算進來？  
20. 你是否真正擁有 codebase，而不是只有影響力？  

#### Tech Lead / Architect 候選人

1. 你能明確定義哪些系統不允許 agent 直接改嗎？  
2. 你能為 AI-assisted development 設計風險分級嗎？  
3. 你能說明團隊目前最大的交付瓶頸是不是寫 code 嗎？  
4. 你是否知道哪些流程應該先自動化，哪些應該先治理？  
5. 你能讓設計、需求、測試、觀測形成閉環嗎？  
6. 你能用一張圖講清楚系統資料流、控制流與責任邊界嗎？  
7. 你能把架構判斷變成可執行的 guardrail 嗎？  
8. 你會要求每個高風險變更都有 rollback 與 owner 嗎？  
9. 你能檢查 agent workflow 是否創造了新的單點故障嗎？  
10. 你能處理「團隊變快但系統更不穩」這種矛盾嗎？  
11. 你能讓 review 標準從「看 style」升級成「看風險」嗎？  
12. 你是否明白平台工程、產品工程與可靠性責任如何分界？  
13. 你能把 vendor demo 拆成可驗證的導入假設嗎？  
14. 你能拒絕速度看似更快但長期不可維護的方案嗎？  
15. 你有沒有為 AI workflow 設 exit condition 與 escalation path？  
16. 你能用數據而不是熱情推動工具導入嗎？  
17. 你是否知道團隊的 review 容量是否跟得上 agent 產量？  
18. 你能讓 Junior 在 AI 時代仍然有可成長的責任嗎？  
19. 你能把責任上移而不是把壓力亂丟給工程師嗎？  
20. 你是否已能定義「什麼叫值得用 AI、自動化、或人工保留」？  

#### AI-native Engineer / Agent Builder

1. 你清楚知道自己的 agent 真正成功率，而不是只記得 demo 嗎？  
2. 你有 evaluation baseline 嗎？  
3. 你有 failure taxonomy 嗎？  
4. 你能區分模型問題、prompt 問題、工具問題、資料問題與流程問題嗎？  
5. 你是否先把單 agent 做穩，再考慮多 agent？  
6. 你是否能量測成本、延遲、成功率與人工返工時間？  
7. 你知道 agent 什麼時候應該停下來找人嗎？  
8. 你知道自己的 tool schema 是否造成 tool confusion 嗎？  
9. 你有沒有設計 end-state evaluation？  
10. 你是否能重現 agent 某次失敗，而不是只說「偶爾會錯」？  
11. 你知道哪些資料與權限不能暴露給 agent 嗎？  
12. 你有沒有考慮 prompt injection 與資料外洩？  
13. 你是否已建立 source quality / groundedness 檢查？  
14. 你做的是 workflow，還是只是把人工步驟包成花哨鏈條？  
15. 你是否把人類審核看成核心能力，而不是低效阻礙？  
16. 你能證明多 agent 比單 agent 更好，而不是只是更複雜嗎？  
17. 你有為 agent 保留可觀測性與審計軌跡嗎？  
18. 你知道哪部分能力會很快被平台吃掉嗎？  
19. 你是否具備足夠軟體工程能力來判斷 agent 寫出的東西好不好？  
20. 你是在打造能力，還是在製造新的一層不可維護複雜度？  

## 工程師的 AI 使用守則

### 讓 AI 先做的工作

可以優先交給 AI 的，通常同時滿足四個條件：  
任務邊界清楚、失敗成本低、可以快速自動驗證、且不涉及深層隱含規則。典型例子包括：測試骨架、文件初稿、重複性 refactor、簡單 migration script 草稿、觀測 query 草稿、低風險 internal tool、小型原型、repo 問答、把 issue 拆成子任務、產生 review checklist、對既有 code 生成功能說明。citeturn40view0turn38view1turn38view3

### 不應直接交給 AI 的工作

不要直接整包交給 AI 的，通常是下列類型：  
模糊需求本身、資料模型變更、權限與認證設計、公開 API 邊界、金流／資安／隱私邏輯、核心性能優化、分散式一致性問題、incident 中的關鍵決策、沒有可靠測試或 rollback 的高風險改動、以及任何「錯一次就可能很痛」的 production 變更。這些地方，AI 可以當輔助，但不該當主導。citeturn19view0turn39view1turn24view0turn14search15turn14search16

### 必須自己先想清楚的事

工程師在呼叫 AI 前，至少要先想清楚五件事：  
這次修改的**成功條件**是什麼；  
不能破壞的 **invariants** 是什麼；  
風險最大的 **failure modes** 是什麼；  
要如何 **驗證**；  
如果 AI 方向錯了，誰來 **接手與回滾**。  
沒有這五件事，AI 只會更快把模糊變成 technical debt。citeturn39view0turn39view3turn37view0

### review AI code 的方法

review AI code 時，不要問「看起來對不對」，要問：

1. 我能否解釋控制流、資料流、狀態流？  
2. 這段 code 引入了哪些新依賴、隱性假設、耦合？  
3. 它的錯誤邊界在哪裡？  
4. 它如何被測？有哪些未測到？  
5. 如果今天 production 出錯，我要去哪裡看？  
6. 這段寫法六個月後別人看得懂嗎？  
7. 若需求變了，這裡會變成 seed corn 還是 optionality？  

這也是 Kent Beck 所說的「不要讓 AI 吃掉你的 seed corn」的工程化版本。citeturn39view3turn40view0turn39view1

### 驗證 AI output 的方法

最低要求不是「編譯能過」，而是：

1. 跑單元測試與整合測試。  
2. 驗證 assertion 是否真的對準需求。  
3. 做至少一次反例測試。  
4. 檢查安全與權限邊界。  
5. 確認 log / metric / trace 可觀測。  
6. 輸出前做人工 walkthrough。  
7. 高風險變更加 rollback 與 feature flag。  

Simon Willison 已經把最核心的原則講得很簡單：**You have to test what it writes.** 這句話對工程師的翻譯就是：**驗證責任不能外包。** citeturn40view0turn36view2turn24view0

### 避免 blind coding / vibe coding 的流程

給一般產品工程師最實用的流程是：

1. **先拆問題，不先叫 AI 寫大段 code。**  
2. **先定驗收條件與風險。**  
3. **讓 AI 產生成熟度適合當下階段的產物**：prototype、測試、方案比較、patch draft，而不是直接當 final answer。  
4. **要求 AI 解釋它的假設與未知。**  
5. **先在小範圍跑通，再擴大。**  
6. **人工 review + 自動化測試 + observability 三關都過才 merge。**  
7. **對高風險改動保留人工主導。**  

Prototype 可以 vibe，production 不可以 vibe。這不是道德說教，而是實務成本問題。citeturn40view1turn39view0turn39view2

### 避免 skill atrophy 的訓練方式

若你每天都讓 AI 先想，你會很快失去拆解、debug、建模能力。最低限度請保留這些手動肌肉：

- 每週至少做一次**不用 AI 的 root-cause 分析**。  
- 每週至少做一次**手動畫系統資料流／錯誤邊界**。  
- 每月接一次**從 log / trace / DB 查詢下手的真實 bug**。  
- 每月做一次**對 AI 方案的反駁練習**：逼自己說出為什麼不能這樣寫。  
- 定期閱讀你負責系統的關鍵模組 source，而不是只看 summary。  

### merge AI code 前的最低檢查標準

在團隊層級，建議把以下內容寫成強制 checklist：

1. 誰是這段變更的 human owner。  
2. 任務風險等級。  
3. 是否有人能口頭解釋 code path。  
4. 測試是否覆蓋主路徑與關鍵反例。  
5. security / privacy / permission 是否檢查。  
6. observability 是否到位。  
7. rollback / feature flag 是否準備。  
8. 是否引入新依賴與其風險。  
9. technical debt 是否被記錄。  
10. 若屬 AI 生成，是否標記來源與 review 責任。  

### 團隊的 code ownership 規範

AI-assisted development 之下，最危險的情況不是 AI 寫錯，而是**沒有人真正擁有它寫的東西**。因此團隊至少要有四條規範：

- **AI 產出永遠必須有 human owner。**  
- **ownership 是 codebase/module ownership，不是 ticket ownership。**  
- **每個 agent workflow 都要有 exit condition 與 escalation path。**  
- **review 標準看風險與長期維護，不只看 style。**  

## 附錄與註解式來源表

### 開放問題與限制

這份研究的最高不確定性主要有四個來源。  
第一，2023–2026 的工具進展非常快，外推到 2031–2036 充滿風險。  
第二，benchmark 可靠性本身正在變動，SWE-bench Verified 已被 OpenAI 與其他研究指出存在污染與測試設計問題。  
第三，survey 與 self-report 普遍高估速度增益；METR 就明確指出開發者主觀感覺常比實際 uplift 樂觀。  
第四，Junior 招募與薪資市場的長期變化，目前仍缺乏足夠嚴格的一手資料。citeturn34view0turn34view1turn32search2turn31view1

### 註解式來源表

| 來源 | 作者 / 機構 | 年份 | 類型 | 可信度 | 一手資料 | 作者背景 | 利益關係 | 支持哪些結論 | 限制 |
|---|---|---:|---|---|---|---|---|---|---|
| Stack Overflow Developer Survey 2025 | Stack Overflow | 2025 | developer survey | 高 | 是 | 全球開發者平台 | 有 AI / 知識商業利益 | AI 採用率、agent 非主流、信任不足 | 自陳偏誤、樣本偏向 SO 使用者 |
| Stack Overflow 2025 AI 專頁 | Stack Overflow | 2025 | developer survey | 高 | 是 | 同上 | 同上 | experienced dev 更保守、部署/監控不願交 AI | 自陳，非行為資料 |
| JetBrains State of Developer Ecosystem 2024 | JetBrains | 2024 | developer survey | 高 | 是 | 開發工具公司 | 有工具商利益 | AI 普及、公司政策、薪酬結構 | 自陳、樣本偏差 |
| Research: quantifying GitHub Copilot’s impact | GitHub | 2023 | company research / experiment | 中高 | 是 | 開發平台研究團隊 | 強烈產品利益 | bounded task speedup、開發者主觀效益 | 任務單一、外部效度有限 |
| Survey reveals AI's impact on developer experience | GitHub | 2023 | company report | 中 | 是 | 開發平台 | 產品利益 | 開發者對品質、協作、學習的看法 | survey，自陳 |
| DORA 2024 report page | DORA / Google Cloud | 2024 | research report | 高 | 是 | 長期 DevOps 研究計畫 | 贊助商與雲端平台利益 | AI 對個人生產力與 delivery trade-off | 組織層面，非單純工程師個體 |
| Google Cloud blog on DORA 2024 | Google Cloud | 2024 | company research summary | 中高 | 是 | 雲平台與研究團隊 | 雲商利益 | 7.5% docs、3.4% code quality、7.2% stability decline 等 | 摘要，完整方法需看報告 |
| DORA 2025 report page | DORA / Google Cloud | 2025 | research report | 高 | 是 | 同上 | 同上 | AI 是 amplifier、流程質量重要 | 組織資料、非長期因果定論 |
| Google Cloud blog on DORA 2025 | Google Cloud | 2025 | company research summary | 中高 | 是 | 同上 | 同上 | 90% 使用 AI、80% 感到 productivity 提升、stability 仍有負效應 | 摘要性質 |
| How much does AI impact development speed? | Google | 2024 | preprint / RCT | 高 | 是 | Google 研究者 | 公司利益 | 企業任務約 21% speedup，seniority 仍重要 | CI 大、單一企業與工具 |
| The Impact of AI on Developer Productivity | Microsoft Research / GitHub Next | 2023 | paper / controlled experiment | 高 | 是 | 微軟與 GitHub 研究 | 產品利益 | 55.8% 更快完工 | 任務受控、與真實大型 repo 有距離 |
| The Effects of Generative AI on High-Skilled Work | MIT / SSRN | 2025 | field experiments / working paper | 高 | 是 | 經濟學研究者 | 與企業合作，非純獨立 | PR throughput 提升、任務配置變化 | 仍是工作論文、場景限定 |
| Generative AI and the Nature of Work | Harvard Business School | 2025 | working paper | 高 | 是 | 商學院研究者 | 無明顯產品利益 | AI 改變工作組成與任務配置 | 開源場景外部效度有限 |
| GitHub Copilot and Developer Productivity | Microsoft | 2026 | observational preprint | 中高 | 是 | 微軟研究 | 產品利益 | steady-state 使用下 PR efficiency 提升 | 非隨機、需假設條件成立 |
| Experience with GitHub Copilot at ZoomInfo | ZoomInfo 等 | 2025 | case study / preprint | 中 | 是 | 企業工程團隊 | 公司導入利益 | 組織導入評估、治理做法 | 單一公司外部效度有限 |
| Measuring the Impact of Early-2025 AI on Experienced OSS Dev Productivity | METR | 2025 | RCT / research note | 高 | 是 | 獨立 AI 評估非營利 | 相對低 | 在熟悉 repo 上 early-2025 AI 可拖慢資深開發者 | 樣本小、場景特殊 |
| Frontier Risk Report | METR | 2026 | research report | 中高 | 是 | 獨立評估機構 | 低 | late-2025 agents 對開發 productivity 可能有小幅收益 | 估計受選樣效應影響 |
| Measuring AI Ability to Complete Long Tasks | METR | 2025 | preprint / benchmark research | 高 | 是 | 同上 | 低 | 長時任務 horizon 約 7 個月翻倍 | 對未來外推仍高不確定 |
| Task-Completion Time Horizons page | METR | 2026 | benchmark dashboard | 中高 | 是 | 同上 | 低 | 前沿模型長任務能力快速進步 | 方法更新頻繁 |
| A practical guide to building agents | OpenAI | 2025 | official guide | 中高 | 是 | 模型與平台供應商 | 強烈平台利益 | eval first、單 agent 優先、tools/guardrails/orchestration | 規範性文件，不是嚴格實驗 |
| New tools for building agents | OpenAI | 2025 | official product / docs | 中 | 是 | 同上 | 平台利益 | agent 平台化趨勢、tooling 商品化 | 廠商觀點 |
| Harness engineering | OpenAI | 2026 | engineering case study | 中 | 是 | OpenAI 產品工程團隊 | 強烈自我宣傳利益 | no manually-written code、harness/eval/feedback loop 重要 | 極端案例、不可廣泛外推 |
| Introducing SWE-bench Verified | OpenAI | 2024 | benchmark note | 中高 | 是 | 研究與 preparedness 團隊 | 評測制定者利益 | repo-level coding benchmark 初期意義 | 後續已承認限制 |
| Why SWE-bench Verified no longer measures frontier coding capabilities | OpenAI | 2026 | benchmark audit | 中高 | 是 | 同上 | 可能影響自家比較口徑 | benchmark contamination、test flaws | 來自單一模型公司 |
| The SWE-Bench Illusion | Purdue / Microsoft | 2025 | preprint | 中高 | 是 | 學術與業界研究者 | 微軟作者參與 | 記憶污染、file path memorization | preprint，非正式標準替代 |
| SWE-bench Goes Live | SWE-bench 團隊 | 2025 | benchmark paper | 中高 | 是 | benchmark 作者 | 低 | live benchmark 對污染問題的回應 | 新 benchmark 仍待長期驗證 |
| How coding agents work | Simon Willison | 2026 | expert essay / guide | 高 | 是 | 長期開源與資料工具作者 | 個人品牌利益低 | coding agent 本質是 LLM + tools + system prompt | 屬實務解釋，不是量化研究 |
| Here’s how I use LLMs to help me write code | Simon Willison | 2025 | expert essay | 高 | 是 | 同上 | 低 | context、測試、人工接手的重要性 | 個人經驗，非普遍統計 |
| AI-assisted coding for teams that can’t get away with vibes | Simon Willison linkpost / Nilenso 原文轉介 | 2025 | expert commentary | 中高 | 否 | 開源工程師轉介實務 | 低 | 好測試/CI/文件會讓 AI 更可靠 | 非實驗研究 |
| Some thoughts on LLMs and Software Development | Martin Fowler | 2025 | expert essay | 高 | 是 | 軟體架構與工程思想領袖 | 低 | workflow 差異重要，LLM 非決定論、不能盲信測試綠燈宣告 | 非量化研究 |
| How far can we push AI autonomy in code generation? | Thoughtworks / Birgitta Böckeler | 2025 | practical experiment | 高 | 是 | Distinguished Engineer | 公司品牌利益 | 自主產碼在複雜度增加時容易失真，人仍要在迴圈內 | 場景刻意設計 |
| charity.wtf AI essays | Charity Majors | 2025–2026 | expert essay | 高 | 是 | 可觀測性與運維實務領袖 | 低 | 團隊擁有、delivery lifecycle、大於個人打字速度 | 觀點型、非量化 |
| Kent Beck augmented coding site / essays summary | Kent Beck | 2025–2026 | expert essay | 高 | 是 | XP / TDD / software design 先驅 | 個人 newsletter 利益 | language expertise 折舊，vision / breakdown / feedback 升值 | 觀點型 |
| GitHub: What to expect for open source in 2026 | GitHub | 2026 | official maintainer essay | 中高 | 是 | 平台與開源關係團隊 | 平台利益 | AI slop、review 壓力、maintainer burden | 非普遍抽樣 |
| Copilot coding agent is now generally available | GitHub | 2025 | official product note | 中 | 是 | 平台產品團隊 | 產品利益 | 背景 agent 已商品化，可做 feature/bug/tech debt/test/docs | 廠商功能聲明 |
| Agents panel on GitHub | GitHub | 2025 | official product note | 中 | 是 | 同上 | 產品利益 | GitHub/MCP/背景任務/PR review 的工作流轉移 | 廠商功能聲明 |
| Agent mode 101 | GitHub | 2025 | official explainer | 中 | 是 | 同上 | 產品利益 | repo-level analysis、tool use、迭代修錯 | 廠商功能聲明 |
| Anthropic multi-agent research system | Anthropic | 2025 | engineering case study | 中高 | 是 | 模型與產品工程團隊 | 平台利益 | 並行子 agent、eval、小樣本測試、human testing | 非中立比較 |
| Demystifying evals for AI agents | Anthropic | 2025 | engineering guide | 中高 | 是 | 同上 | 平台利益 | groundedness、coverage、human calibration 的長期重要性 | 規範性文件 |
| Asleep at the Keyboard? | Pearce et al. | 2021/2022 | peer-reviewed / arXiv | 高 | 是 | 資安研究者 | 低 | 早期 Copilot 產碼漏洞風險 | 模型舊，但風險類型仍 relevant |
| We Have a Package for You! | USENIX Security | 2025 | peer-reviewed paper | 高 | 是 | 資安與軟體供應鏈研究者 | 低 | package hallucination 供應鏈風險 | 專注特定風險類型 |
| Security Degradation in Iterative AI Code Generation | 研究者團隊 | 2025 | preprint | 中高 | 是 | 安全研究者 | 低 | 多輪互動不保證更安全 | preprint |
| Security and Quality in LLM-Generated Code | 研究者團隊 | 2026 | measurement study / preprint | 中高 | 是 | SE / security 研究者 | 低 | 多語言、多模型下的品質與安全風險 | preprint，方法待更多重複 |
| Secure coding with AI – from detection to repair | Empirical Software Engineering | 2026 | journal article | 高 | 是 | 軟體工程研究者 | 低 | AI-assisted secure coding 需流程化治理 | 議題範圍偏 secure coding |
| Do LLMs consider security? | Empirical Software Engineering | 2025 | journal article | 高 | 是 | SE / security 研究者 | 低 | 模型不會穩定自帶安全意識 | 任務設計影響結果 |
| Challenges and Paths Towards AI for Software Engineering | 研究者團隊 | 2025 | perspective / preprint | 中高 | 是 | AI4SE 研究者 | 低 | 從能力到真正自動化仍有研究缺口 | 前瞻性較高 |
| DORA ROI of AI-assisted Software Development | DORA / Google Cloud | 2025 | report | 中高 | 是 | DevOps 研究 | 雲商利益 | AI ROI 取決於系統能力，不是單純工具 | 組織層面偏多 |
| GitHub Copilot usage metrics docs | GitHub Docs | 2026 | official documentation | 中 | 是 | 開發平台文件 | 產品利益 | PR throughput / cycle time 可被量測，治理會制度化 | 不是效果研究 |
| Professional Cloud Developer certification page | Google Cloud | 2026 | official documentation | 中 | 是 | 資格認證與雲開發團隊 | 品牌利益 | cloud developer 職能已納入 genAI、AI debugging、context engineering | 非研究，屬職能信號 |

### 總結路線圖

如果把未來五到十年的工程師路線壓縮成一句話，那會是：

**從「會寫」升級到「會定義、會驗證、會治理、會承擔、會簡化」。**

對大部分 Web / SaaS / App 工程師，最務實的選擇不是轉職當 AI evangelist，也不是跑去硬啃只有極少數職位需要的底層專家路線，而是盡快把自己升級成這樣的人：

- 能看穿系統而不是只看檔案  
- 能驗證 AI 而不是只使用 AI  
- 能對 production 後果負責而不是只交付 ticket  
- 能把模糊需求變成有 acceptance criteria 的技術方案  
- 能在速度上升時維持可靠性、可維護性與安全  

未來最危險的工程師，不是不用 AI 的人；而是**用了 AI，卻讓自己失去理解、判斷與 ownership 的人**。未來最值錢的工程師，也不是最會下 prompt 的人；而是**最能在 AI 讓產碼變廉價之後，仍然維持系統正確、可演進、可恢復、可交接的人**。citeturn39view3turn39view2turn36view2turn37view0turn24view0turn38view0