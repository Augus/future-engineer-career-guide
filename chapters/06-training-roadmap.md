# 第 6 章：分層訓練路線圖

**訓練未來工程師，不能只安排更多實作任務；你要刻意練習定義問題、驗證結果、承擔 ownership，並逐步把自己從 ticket executor 推向 system owner。**

AI coding 壓縮的是任務，不是責任。這句話對訓練路線很重要。過去很多工程師的成長路徑，是從小 ticket、樣板功能、簡單 bug、測試補齊開始，慢慢累積系統理解。但這些入口任務正在被工具吃掉一部分。如果個人與團隊沒有重新設計訓練方式，工程師可能會得到更多 AI 輔助，卻失去真正練功的摩擦。

本章用六種角色設計訓練路線：

- Junior Engineer
- Mid-level Engineer
- Senior Engineer
- Tech Lead / Architect 候選人
- AI-native Engineer / Agent Builder
- Infra / Reliability / Security 工程師

每種角色都保留四個時間尺度：0-3 個月、3-12 個月、1-3 年、3-10 年。這些時間不是職級升遷保證，而是能力重心轉移的節奏。

## 全局訓練原則

在進入分層路線前，先建立幾個共同原則。

第一，所有 AI 產出都要可解釋。你可以用 AI 寫 code、產生測試、整理文件，但不能 merge 自己說不清楚的變更。說不清楚的 code，不是你的能力，只是你的風險。

第二，訓練要從「完成任務」轉向「控制後果」。未來工程師的驗收標準不是只看功能是否完成，而是看變更是否可測、可觀測、可回復、可維護。

第三，每一階段都要練習 review。AI 會讓 review 變成核心能力，不是附屬工作。越早訓練風險辨識，越不容易變成只會接受 AI 建議的人。

第四，訓練要保留摩擦。完全把困難部分交給 AI，短期會提高速度，長期會造成 skill atrophy。對於核心能力，應該設計「先自己推理，再用 AI 對照」的流程。

第五，驗收標準必須具體。只說「學好基礎」、「多看架構」、「提升 debug 能力」沒有訓練價值。好的訓練路線要說清楚：做什麼 exercise、產出什麼 artifact、由誰 review、用什麼標準判斷進步。

## 總覽路線表

| 角色 | 主要風險 | 0-3 個月 | 3-12 個月 | 1-3 年 | 3-10 年定位 | 關鍵驗收 |
|---|---|---|---|---|---|---|
| Junior Engineer | 入口任務被 AI 壓縮，缺少真實練功 | 讀懂 code path、修真 bug、建立 debug 習慣 | 練 tracing、DB、failure case、PR review | 接手小模組 ownership | AI-supervised developer / domain junior | 不用 AI 也能說清 bug 成因與變更風險 |
| Mid-level Engineer | routine implementation 不再稀缺 | 建立 PR 風險分級與 merge checklist | 主導跨模組功能與觀測儀表板 | 成為 workflow 或模組 owner | Product-minded engineer / workflow owner | 交付更快但返工、事故、債務沒有增加 |
| Senior Engineer | 年資若只代表寫碼量，會被壓縮 | 設定 AI 使用規範與 review bar | 建 test / eval / observability 標準 | 成為 codebase 或系統 owner | System complexity owner / tech lead | 團隊更穩、更可維護，不只是自己更快 |
| Tech Lead / Architect 候選人 | 只會產設計文件，不會治理後果 | 練 ADR、rollback plan、risk matrix | 建立人機分工與 approval gate | 主導架構演進與平台治理 | Technical leader / workflow architect | 模糊需求能落到可驗證、可回復的計畫 |
| AI-native Engineer / Agent Builder | 只會接工具與 prompt tricks | 做單 agent + eval harness | 接真工具、guardrail、成本與成功率 dashboard | 管理 agent portfolio | AI workflow architect | workflow 可測、可審、可復現，不只是 demo 能跑 |
| Infra / Reliability / Security | 把 AI 當腳本工具，忽略新風險 | 盤點權限、資料、供應鏈邊界 | 建 detection / review / rollback flow | 發展平台、可靠性或安全 ownership | Infra / reliability / security owner | 風險下降，而不是只有操作速度提高 |

## Junior Engineer：先把 AI 變成教練，不要變成代打

### 主要風險

Junior 最大的風險不是立刻被取代，而是失去原本用小任務累積判斷力的路徑。Boilerplate、簡單 CRUD、測試骨架、文件整理、低風險 bugfix 都會更容易交給 AI。如果 Junior 只學會讓 AI 完成 ticket，卻沒有學會系統如何運作，很快會卡在「看似能交付，實際無法獨立負責」的位置。

### 0-3 個月：建立 code path 與 debug 基礎

訓練目標是：看得懂真實系統的資料流、控制流與錯誤流。

具體 exercise：

1. 每週手畫一條真實 code path。從 API endpoint、UI action、job trigger 或 message consumer 開始，畫到資料庫、外部服務、cache、queue、錯誤處理與 response。
2. 每週選一個已 merged PR，寫一頁「我如何驗證它是安全的」。
3. 修 2-3 個真 bug，不准只交 diff，必須附 root cause memo。
4. 對每個 AI 產出的變更，用自己的話口頭解釋：改了哪些檔案、為什麼改、風險在哪、怎麼測。
5. 練習讀 log。挑一次真實錯誤或測試失敗，整理時間線與初步假設。

驗收標準：

- 能不用 AI 讀懂一條中等複雜度 code path。
- 能說清楚一個 bug 的觸發條件，而不只是說「某行壞了」。
- 能指出 PR 中至少三種風險：資料、權限、錯誤處理、相容性、測試缺口、rollback。
- 能區分「AI 建議看起來合理」與「我已驗證它符合系統脈絡」。

常見假進步：

- Prompt 變熟，但根因分析沒有進步。
- AI 產碼速度變快，但自己無法解釋變更。
- 測試覆蓋率上升，但測試只是重述 implementation。
- 只會修 happy path，不會處理資料、權限、部署或並發問題。

### 3-12 個月：從局部實作進到小範圍 ownership

訓練目標是：能獨立處理小功能，並對風險、測試與觀測負責。

具體 exercise：

1. 主導一個小功能，從需求釐清、設計、實作、測試到 release 後觀測。
2. 為功能寫 acceptance criteria，至少包含 happy path、edge cases、錯誤處理與不可做事項。
3. 練習 DB query 與資料狀態分析。每次 bugfix 必須確認資料是否需要修補。
4. 為一個小流程補上必要 log 或 metrics，讓下次出錯更容易定位。
5. 參與 code review，不只留言 style，也要問「這個假設在哪裡被測到？」

驗收標準：

- 能把模糊需求拆成可驗證條件。
- 能為自己的 PR 提供測試證據，而不是只說「我跑過」。
- 能在 review 中抓到至少一類非表面問題，例如狀態轉換、資料一致性、授權缺口。
- 能為小功能說明 rollback 或 mitigation 方式。

常見假進步：

- Ticket 完成數增加，但每次都需要 Senior 收尾。
- 會用 AI 補測試，但不知道測試保護的是哪個風險。
- 會查文件，但不會把文件轉成系統脈絡下的決策。

### 1-3 年：成為可靠的小模組 owner

訓練目標是：不只是完成任務，而是讓一個小模組長期變得更穩、更清楚。

具體 exercise：

1. 接手一個低到中風險模組，整理 module map、主要資料模型、常見 failure mode、測試缺口。
2. 每季做一次 technical debt review，列出三項最該處理的債與不處理的代價。
3. 為模組建立最小 observability：核心事件、錯誤率、latency、資料異常指標。
4. 主動改善一個 onboarding pain point，讓下一個人更容易理解模組。
5. 在 AI 輔助下完成重構，但必須保留行為驗證與 rollback 計畫。

驗收標準：

- 別人問到該模組時，你能說明現況、風險、邊界與演進方向。
- 模組的 incident 或 recurring bug 減少，或至少更容易定位。
- 你的 PR 不再只是局部 diff，而能附帶設計理由與驗證策略。

常見假進步：

- 變成「AI + ticket executor」，沒有 ownership。
- 能處理更多需求，但模組結構越來越亂。
- 寫了大量文件，但文件沒有反映真實系統。

### 3-10 年：AI-supervised developer / domain junior

Junior 的長期定位不是永遠當 Junior，而是成為能在特定 domain 或模組中負責的工程師。AI 可以當加速器，但不能取代你建立 domain sense。三到十年的目標，是逐步形成「我知道這個系統為什麼這樣設計、哪裡容易壞、哪些需求不能照字面做」的能力。

## Mid-level Engineer：從 routine implementation 升級成 owner

### 主要風險

Mid-level 最危險的位置，是只比 Junior 快、只比 Senior 便宜，但沒有清楚 ownership。Routine implementation 會被 AI 壓縮，單純 ticket throughput 不再足以證明價值。Mid-level 要升級的是：能主導一段流程、辨識風險、讓團隊交付速度提高但品質不惡化。

### 0-3 個月：建立風險分級與 review 習慣

具體 exercise：

1. 為自己的 PR 建立風險分級：低風險、需注意、高風險、不可無人審核。
2. 每個 PR 附上 merge checklist：測試、資料影響、權限、observability、rollback。
3. 對 AI 產碼做二階段 review：先看需求是否正確，再看 code 是否正確。
4. 選一個最近的返工案例，分析它原本可以在哪個節點被發現。
5. 每週 review 一個跨模組 PR，刻意找出 integration risk。

驗收標準：

- 能清楚說明不同變更的風險等級。
- 能在實作前指出需求或設計缺口。
- 能把 review 從 style 提升到 invariant、資料流與 rollback。

常見假進步：

- Code 變快，但 review 水準沒有提升。
- PR 變大，卻沒有更好的驗證策略。
- 用 AI 產出設計文件，但文件沒有影響實際決策。

### 3-12 個月：主導跨模組功能

具體 exercise：

1. 主導一個跨模組小功能，包含需求釐清、簡短設計、風險矩陣、測試策略。
2. 為該功能建立一個觀測儀表板或最低限度的 metrics / logs。
3. 在實作前列出至少兩個方案與 trade-off。
4. 設計 release plan：feature flag、分批 rollout、rollback、資料修補。
5. 量測 AI 使用後的返工率、review comment 類型與缺陷來源。

驗收標準：

- 功能交付後，團隊能知道它是否正常運作。
- 速度提高沒有伴隨明顯事故、返工或技術債增加。
- 你能把模糊需求轉成可交付、可驗證、可回復的計畫。

常見假進步：

- 會拆 task，但不會拆風險。
- 會協調多人實作，但沒有人對整體品質負責。
- dashboard 做了，但 incident 時回答不了關鍵問題。

### 1-3 年：成為 workflow 或模組 owner

具體 exercise：

1. 接手一段核心 workflow，例如 onboarding、checkout、billing、deployment、approval flow。
2. 定義該 workflow 的核心 SLO 或品質指標。
3. 建立 recurring bug / incident 分析表，找出最常見的系統性原因。
4. 主導一次流程瘦身：刪除不必要分支、合併重複邏輯、清楚化邊界。
5. 設計人機分工：哪些步驟可交 AI，哪些需要人工 review，哪些必須禁止自動化。

驗收標準：

- 該 workflow 的變更更容易 review、測試與 rollback。
- 團隊對該 workflow 的理解不只存在你腦中，而有可維護的 artifact。
- 你能培養其他工程師參與該 workflow，而不是變成單點。

常見假進步：

- 變成最會救火的人，但沒有降低火災發生率。
- 大量依賴個人記憶，沒有建立系統性 ownership。
- 把所有問題都交給 AI 加速，卻沒有改善流程品質。

### 3-10 年：Product-minded engineer / workflow owner

Mid-level 的長期路線，是把自己從「可替代的實作者」升級成「一段產品或工程流程的 owner」。你要能理解使用者、domain、技術限制與營運風險，並在 AI 加速下維持品質。這類工程師不只是會做功能，而是知道功能應該如何被定義、驗證、發布與維護。

## Senior Engineer：從個人產能升級成複雜度控制

### 主要風險

Senior 的風險不是 AI 立刻取代所有能力，而是年資與大量親手寫碼不再自動代表價值。如果 Senior 仍把主要貢獻定義為「我能寫最多最難的 code」，其中一部分會被 agent 壓縮。Senior 需要升級成複雜度控制者、品質標準建立者、codebase owner 與團隊判斷力的放大器。

### 0-3 個月：建立 AI 使用規範與品質底線

具體 exercise：

1. 為團隊寫一版 AI-assisted coding guideline，區分可自動化、需 review、不可直接交 AI 的任務。
2. 建立 AI-generated PR 的最低 review bar：需求、測試、security、observability、rollback。
3. 選三個近期 AI 或快速產碼造成的問題，整理成 failure pattern。
4. 為一個高風險模組定義不可破壞的 invariants。
5. 在 review 中要求作者說明 AI 產出如何被驗證。

驗收標準：

- 團隊知道哪些變更不能只靠 AI 產出與自動測試通過。
- 高風險 PR 的 review 更聚焦在後果，而不是風格。
- 你能把個人經驗轉成團隊可使用的標準。

常見假進步：

- 自己用 AI 變快，但團隊品質沒有提高。
- 寫了規範，卻沒有落到 review、CI、release gate。
- 只禁止風險，沒有設計可行替代流程。

### 3-12 個月：建立 test / eval / observability 標準

具體 exercise：

1. 為核心系統定義測試金字塔或測試矩陣，說明每層保護什麼風險。
2. 為 AI workflow 或高風險功能建立 eval / acceptance harness。
3. 補齊一段核心流程的 observability，讓 incident 時能快速回答「誰受影響、從何時開始、哪個版本造成」。
4. 主導一次 incident review，把結論轉成系統或流程改進。
5. 建立 technical debt decision log，記錄哪些債被接受、期限與觸發條件。

驗收標準：

- 團隊的測試不是只追 coverage，而能對應風險。
- 重要 workflow 有明確品質指標與觀測資料。
- incident 後的行動不只是補丁，而包含防止重發的機制。

常見假進步：

- Merge 更快，但 technical debt 暴增。
- 設計更多流程，但工程師覺得只是負擔，沒有降低風險。
- Eval 做成展示，不進入日常 release 判斷。

### 1-3 年：成為 codebase 或系統 owner

具體 exercise：

1. 主導一次架構瘦身，目標是減少未來變更成本，而不是導入新技術。
2. 建立系統邊界文件：資料 ownership、API contract、failure mode、dependency map。
3. 設計一套高風險變更治理流程：ADR、reviewer、release gate、rollback、escalation。
4. 培養一到兩位工程師接手部分 ownership，避免知識單點。
5. 定期審視 AI 工具導入後的品質指標：返工率、incident、review 負擔、cycle time。

驗收標準：

- 你負責的系統變得更容易改，而不是只有你能改。
- 團隊能用你建立的標準做決策。
- AI 導入後，速度提高的同時，穩定性與可維護性沒有被犧牲。

常見假進步：

- 成為所有困難問題的 bottleneck。
- 只做大型重構，沒有明確風險減少或維護成本下降。
- 把架構討論變成文件產出，而不是決策與行動。

### 3-10 年：System complexity owner / tech lead

Senior 的長期價值，是能對複雜系統負責。這代表你不只是解最難的 bug，而是讓 bug 更少、更容易被發現、更容易被修復。你不只是寫最核心的 code，而是讓系統邊界更清楚、團隊判斷更穩、AI 工具被放在受控流程中。

## Tech Lead / Architect 候選人：從設計文件升級成治理能力

### 主要風險

Tech Lead 或 Architect 候選人的風險，是只會產生漂亮設計文件與架構圖。AI 會越來越擅長產生設計草案、圖表與比較表。真正稀缺的不是畫圖，而是在現實限制下做取捨、設 quality bar、安排人機分工、建立 rollback 與 escalation。

### 0-3 個月：練 ADR、rollback plan、risk matrix

具體 exercise：

1. 每週寫一份短 ADR，限定一頁，包含背景、選項、決策、代價、撤退條件。
2. 為每個中高風險方案寫 rollback plan。
3. 建立 risk matrix：資料、權限、可靠性、成本、團隊能力、遷移風險。
4. 對 AI 產生的架構草案做反向審查：它漏掉了哪些現實限制？
5. 練習把模糊需求改寫成可驗證的 engineering plan。

驗收標準：

- 你的設計文件能幫助團隊做決策，而不是只描述理想架構。
- 每個重要決策都有「為什麼不是另一個方案」。
- 方案包含觀測、測試、rollout、rollback，而不是只包含 component diagram。

常見假進步：

- 會畫圖，但不會定 quality bar。
- 會列 pattern，但不會說明代價。
- 文件很多，決策仍然模糊。

### 3-12 個月：建立人機分工與 AI-assisted SDLC

具體 exercise：

1. 為團隊定義 AI-assisted SDLC：需求、設計、實作、review、測試、release 各階段 AI 可做什麼。
2. 設計 approval gate：哪些變更需要 human owner 批准。
3. 建立高風險任務不可完全交給 AI 的規則，例如 auth、payment、migration、security-sensitive change。
4. 建立 review checklist，明確要求 invariants、observability、rollback、security。
5. 選一個流程試行，量測 cycle time、返工率、incident、review 負擔。

驗收標準：

- AI 使用不再是個人習慣，而是受控 workflow。
- 團隊能分辨自動化提升速度與自動化增加風險的差異。
- 高風險變更有 owner、gate、rollback、escalation。

常見假進步：

- 工具導入很多，但責任邊界沒有變清楚。
- 只追求 cycle time，沒有看返工與事故。
- 把 governance 做成流程負擔，沒有真正降低風險。

### 1-3 年：主導平台或架構演進

具體 exercise：

1. 主導一項跨團隊架構演進，包含 migration path 與階段性驗收。
2. 建立 platform 或 shared service 的 ownership model。
3. 為 AI 產碼進入核心系統設計 gate：測試、eval、security scan、manual approval。
4. 定期審查架構債與組織能力是否匹配。
5. 培養其他 Tech Lead 候選人，讓治理能力可傳承。

驗收標準：

- 架構演進不是一次性重寫，而是可分階段、可回退、可觀測。
- 團隊能用共同標準處理 AI-assisted change。
- 你的影響力體現在系統與流程品質，而不只是個人決策權。

常見假進步：

- 把架構職責理解成最後拍板，而不是建立決策系統。
- 遷移計畫只考慮理想終態，沒有處理中間狀態。
- 所有架構知識集中在少數人身上。

### 3-10 年：Technical leader / workflow architect

Tech Lead / Architect 的長期定位，是設計工程組織如何安全地使用 AI，而不只是選技術。你要讓更多產出通過更嚴格的驗證，讓責任邊界更清楚，讓系統在快速變更下仍可維護。

## AI-native Engineer / Agent Builder：從工具拼裝升級成可驗證 workflow

### 主要風險

AI-native Engineer 的短期紅利很明顯：會 prompt、會接 SDK、會用 agent framework、會串 tool。問題是，這些技能會被平台快速吸收。長期價值不在於能做 demo，而在於能建立可測、可審、可復現、可治理的 AI workflow。

### 0-3 個月：先做單 agent + eval，不追求花俏多 agent

具體 exercise：

1. 選一個真實但低風險任務，建立單 agent workflow。
2. 在寫 agent 前先定義成功標準、失敗類型與不可做事項。
3. 建立最小 eval set，包含常見案例、邊界案例、錯誤輸入。
4. 記錄每次執行的 prompt、model、tool call、輸出、成本與結果。
5. 刻意做 failure analysis，而不是只展示成功案例。

驗收標準：

- Agent 不是只能跑一次 demo，而是能在固定 eval set 上重複比較。
- 你能說明主要 failure mode 與改進方向。
- 你能指出哪些場景必須 HITL，而不是讓 agent 自動完成。

常見假進步：

- 只會用工具，不懂 failure mode。
- 多 agent 架構很複雜，但沒有 eval。
- 成功案例很漂亮，失敗案例沒有被記錄。

### 3-12 個月：接真工具、加 guardrail、建 dashboard

具體 exercise：

1. 將 agent 接入真實工具，例如 ticket system、repo、search、database read-only API。
2. 設計權限邊界：哪些 tool read-only，哪些需要 approval，哪些禁止。
3. 建立 guardrail：輸入驗證、輸出檢查、policy、敏感資料處理。
4. 建立 dashboard：成功率、人工介入率、成本、延遲、錯誤類型。
5. 設計 rollback 或人工補救流程。

驗收標準：

- Workflow 可觀測，不是黑箱。
- 失敗時不會直接傷害生產資料或使用者。
- 成本與成功率能被比較，而不是只憑體感。

常見假進步：

- Agent 能做更多事，但權限控制沒有跟上。
- 用更強模型掩蓋流程設計問題。
- dashboard 只看使用量，不看品質與風險。

### 1-3 年：管理 agent portfolio

具體 exercise：

1. 管理多個 agent workflow，依風險分級與 owner 維護。
2. 建立共用 eval infrastructure，而不是每個 agent 各自測。
3. 定期淘汰低成功率、高成本或難治理的 agent。
4. 設計 agent change management：版本、prompt、tool、model 更新如何驗證。
5. 與 security、legal、domain owner 合作建立 policy。

驗收標準：

- Agent workflow 有生命週期管理。
- 每個 agent 有 owner、eval、監控、升級流程。
- 組織能判斷哪些任務適合 agent，哪些不適合。

常見假進步：

- Agent 數量增加，但維護成本失控。
- 只追逐新框架，沒有累積可重用的 eval 與治理能力。
- 沒有人能回答某個 agent 為什麼做出某次決策。

### 3-10 年：AI workflow architect

AI-native Engineer 的長期價值，是設計可靠的人機協作系統。你不是單純把 AI 接到更多工具，而是建立一個受控的 workflow：可測、可審、可追蹤、可中止、可交接、可改善。

## Infra / Reliability / Security 工程師：把 AI 速度納入控制面

### 主要風險

Infra、Reliability、Security 工程師看似比較安全，因為底層 failure mode、事故處理、權限與供應鏈風險不容易被完全商品化。但這些角色也有風險：如果只是把 AI 當成寫腳本的工具，卻沒有處理 AI 引入的新權限、新資料流、新供應鏈與新 incident 模式，就會錯過真正升值的部分。

### 0-3 個月：盤點 AI 引入的權限與資料邊界

具體 exercise：

1. 盤點團隊使用的 AI 工具：IDE、agent、CI bot、chatbot、internal assistant。
2. 列出它們可讀取與可寫入的資料、repo、ticket、log、secret、production tool。
3. 檢查 sensitive data 是否可能進入 prompt、log、第三方工具或模型上下文。
4. 為 AI-generated infrastructure change 設定 review bar。
5. 分析一次 AI 可能造成的 incident scenario。

驗收標準：

- 團隊知道 AI 工具的資料與權限邊界。
- 高風險操作不會由 agent 無審批執行。
- secret、credential、production data 有明確保護規則。

常見假進步：

- 工具用了很多，控制面沒有變強。
- AI 讓腳本產出更快，但審核與 rollback 沒有更新。
- 只關注 prompt 外洩，忽略 tool permission 與 supply chain。

### 3-12 個月：建立 detection / review / rollback flow

具體 exercise：

1. 為 AI-generated code 或 config 建立 CI gate。
2. 對 infrastructure、security-sensitive、data migration 變更加 manual approval。
3. 建立 detection：異常 deploy、權限變更、依賴風險、secret exposure。
4. 為常見 AI-assisted failure mode 寫 runbook。
5. 在 incident drill 中加入 AI 工具失誤情境。

驗收標準：

- AI 加速變更後，仍能偵測、阻擋、回復高風險錯誤。
- Review flow 能區分低風險自動化與高風險人工審核。
- Runbook 不只是文件，而在演練中可用。

常見假進步：

- CI 檢查增加很多，但 false positive 過高，團隊開始忽略。
- 把所有 AI 變更都擋住，導致流程不可用。
- 只看技術風險，沒有處理 owner 與 escalation。

### 1-3 年：發展成 platform / reliability / security owner

具體 exercise：

1. 建立 AI-assisted SDLC 的安全與可靠性標準。
2. 為高風險 repo 或服務建立 policy-as-code。
3. 將 observability、SLO、incident review 與 AI change governance 串起來。
4. 設計平台能力，讓工程師安全使用 AI，而不是各自繞過流程。
5. 定期回顧：AI 是否降低 toil，還是增加隱性風險？

驗收標準：

- 工程團隊能更快交付，但高風險操作更受控。
- AI 導入後，incident detection 與 recovery 沒有退化。
- 安全與可靠性要求被嵌入平台，而不是靠口頭提醒。

常見假進步：

- 安全規則越來越多，但工程師找 workaround。
- 平台只包裝工具，沒有降低風險。
- Reliability 指標沒有和 AI change volume 一起分析。

### 3-10 年：Infra / reliability / security owner

這條路線的長期價值，是成為 AI 加速工程組織的控制面 owner。當產碼與變更速度提高，真正稀缺的是能讓系統仍然安全、穩定、可觀測、可回復的人。

## 跨角色共同 exercise

以下 exercise 可以被不同職級使用，只是深度不同。

### Exercise 1：十個真 bug root cause memo

做法：選十個真實 bug，不限大小。每個 bug 寫一頁 memo：症狀、影響、時間線、根因、修復、防止重發。

驗收：看完 memo 的人，能理解為什麼錯誤會發生，以及下次如何更早發現。

假進步：只寫「改了哪一行」，沒有分析系統為什麼允許錯誤發生。

### Exercise 2：PR 風險分級

做法：連續二十個 PR 都標記風險等級，並附上風險理由與驗證方式。

驗收：reviewer 認同你的風險判斷，或能指出你漏看的風險類型。目標不是永遠判對，而是讓風險討論明確化。

假進步：所有 PR 都標低風險，或所有 PR 都標高風險，沒有判斷力。

### Exercise 3：一頁 ADR

做法：對每個中等以上技術決策寫一頁 ADR。限制篇幅能逼你說清楚重點。

驗收：ADR 包含背景、選項、決策、代價、撤退條件。半年後回看仍能理解當時為什麼這樣選。

假進步：ADR 只是記錄最後決定，沒有記錄 trade-off。

### Exercise 4：AI workflow eval harness

做法：為一個 AI 輔助流程建立固定測試集與評分方式。每次改 prompt、model、tool 或 policy 都跑 eval。

驗收：你能比較不同版本的成功率、成本、錯誤類型與人工介入率。

假進步：只看 demo 成功，不量測失敗分布。

### Exercise 5：觀測性反推

做法：選一個核心流程，假設使用者回報「它壞了」，反問目前 log、metrics、traces 能不能回答：誰受影響、從何時開始、哪個版本、哪個依賴、是否恢復。

驗收：至少補上一項能縮短定位時間的觀測資料。

假進步：新增 dashboard，但 incident 時仍無法回答關鍵問題。

## 如何判斷自己真的進步

你可以用四個問題檢查訓練是否有效。

第一，你是否能在 AI 介入前先提出自己的假設？如果你只能等待 AI 給答案，再選一個看起來合理的，你的判斷力沒有真正成長。

第二，你是否能解釋變更的風險？未來工程師不能只說「功能完成」。你要能說明哪裡可能壞、如何測、如何觀測、如何回復。

第三，你是否讓系統變得更容易理解？如果你每次都能快速完成任務，但下一個人更難接手，你是在累積債務。

第四，你是否降低了未來錯誤成本？真正的進步不是永遠不犯錯，而是讓錯誤更早被發現、更小範圍爆炸、更容易被修復。

## 對讀者的職涯含義

未來三到十二個月，你應該把 AI 當成加速器，但不要把訓練外包給它。Junior 要保留 debug 與 code path 的基本功；Mid-level 要升級成 owner；Senior 要建立團隊品質系統；Tech Lead 要設計治理；AI-native Engineer 要做可驗證 workflow；Infra、Reliability、Security 工程師要把 AI 速度納入控制面。

長期來看，最危險的不是不會用 AI 的工程師，而是只會用 AI 完成任務、卻無法定義問題、驗證結果、控制風險與承擔後果的工程師。訓練路線的目的，是把你從「更快完成 ticket」推向「能負責系統結果」。

