# 第 2 章：工程師價值的轉移

當產碼成本下降，工程師的價值會從「我能寫出多少 code」轉向「我能否定義正確問題、驗證結果、治理風險，並對 production 後果負責」。

## 從產碼者到問題定義者

過去很多工程組織會把工程師的日常價值簡化成 throughput：接多少 ticket、交多少 PR、關多少 issue、寫多少功能。這種衡量方式本來就不完整，只是 AI coding 讓它的不完整變得更明顯。

當 AI 能快速產生初版實作，真正昂貴的問題會提前出現：這是不是正確的需求？這是不是正確的切分方式？這個功能是否應該存在？資料模型是否能支撐後續演進？權限邊界是否清楚？驗收條件是否可測？失敗時是否能回退？誰對上線後的行為負責？

如果問題定義錯了，AI 只會讓錯誤方向更快落地。它可能補需求空白，做出沒被要求的功能；可能用看似合理的方式完成任務，卻和真正的業務約束不一致；可能讓 demo 成功，卻留下難以維護的 production code。

因此，工程師的第一個價值轉移，是從產碼者變成問題定義者。

問題定義不是寫一段更漂亮的 spec。它包含幾件具體工作：

- 把模糊需求拆成可驗證的子問題。
- 釐清 user problem、business constraint、legal/security boundary、data semantics。
- 定義功能完成的 acceptance criteria。
- 指出哪些情境不在本次範圍內。
- 決定哪些修改可以交給 AI，哪些必須由人先設計。
- 把風險寫進任務，而不是等 review 時才發現。

當 code 變便宜，錯誤的方向會變貴。能阻止錯誤方向被高速實作的人，會比單純實作更有價值。

## 從 implementation 到 verification

第二個價值轉移，是從 implementation 轉向 verification。

這不是說 implementation 不重要，而是說 implementation 的邊際價值正在下降。AI 會越來越能生成局部正確的程式，尤其是在有清楚上下文、範例、測試和限制條件時。但它是否真的滿足需求，是否破壞隱含契約，是否引入安全風險，是否讓系統更難維護，需要驗證。

驗證不是按下測試按鈕。測試通過只是驗證的一部分，而且常常是最容易被誤解的一部分。真正的 verification 包含：

- 需求驗證：這個解法是否解決真正問題？
- 行為驗證：外部 observable behavior 是否符合契約？
- 回歸驗證：既有流程是否被破壞？
- 風險驗證：權限、資料、資安、可靠性是否有新風險？
- 操作驗證：部署、監控、rollback、incident response 是否可行？
- 來源驗證：AI 產出的假設是否有 repo、文件或實際系統依據？

OpenAI 與 Anthropic 的 agent 文件都把 eval、guardrails、tool use、orchestration、人類升級流程當成正式工程問題。這個方向很重要：越 powerful 的 agent，越需要可靠的 end-state evaluation。工具越能替你做事，你越需要知道如何判斷「完成」是否真的完成。

未來工程師不會因為 AI 會寫測試而少做驗證。相反地，因為 AI 會產生更多 code、更多測試、更多候選修法，人類更需要建立驗證標準，判斷哪些結果可信，哪些只是看起來正確。

## 從 ticket owner 到 system owner

第三個價值轉移，是從 ticket owner 到 system owner。

ticket owner 關心的是：這張票是否完成，PR 是否合併，驗收是否通過。system owner 關心的是：這個變更進入系統後，資料流、狀態流、錯誤邊界、權限邊界、觀測性、部署風險、維護成本會如何改變。

AI coding 會讓 ticket-level execution 更快，但也會讓 system-level ownership 更重要。因為變更量上升後，系統複雜度、review 壓力、供應鏈風險、安全面、技術債累積速度都會上升。

如果一個團隊沒有清楚 owner，AI 會製造更多「沒有人真正擁有」的變更。這些變更可能單獨看都合理，合在一起卻讓系統邊界變模糊、資料模型變混亂、測試變脆弱、incident 更難定位。

system owner 的價值在於控制複雜度與失敗半徑。他會問：

- 這個修改是否增加跨模組耦合？
- 這個資料流是否有清楚 ownership？
- 這個錯誤會如何被觀測？
- 權限失效時會發生什麼？
- 部署失敗是否能快速回退？
- 六個月後新成員能否理解這個設計？
- 如果 AI 之後繼續在這個區域產碼，是否會放大現在的問題？

這些問題不會因為 agent 更強而消失。它們只會因為變更速度提高而更早、更頻繁地出現。

## 治理 AI 輸出，而不是崇拜 AI 輸出

AI coding 時代的高價值工程師，會治理 AI 輸出，而不是崇拜 AI 輸出。

治理不是否定 AI。治理的意思是建立邊界、標準、審核與回退機制，讓 AI 的產能能進入工程流程，而不是直接衝進 production。

治理至少包含五個層次：

| 層次 | 工程師要做的事 | 目的 |
|---|---|---|
| 任務邊界 | 把大任務切成可驗證的小任務 | 降低 agent 偏航與失敗成本 |
| 上下文治理 | 提供 repo、規格、限制、非目標與範例 | 避免模型自行補錯空白 |
| 權限治理 | 限制可改範圍、可執行工具、可觸碰資料 | 控制失敗半徑 |
| 驗證治理 | 設定測試、eval、rubric、review gate | 判斷結果是否可信 |
| 上線治理 | 保留 human owner、rollback、monitoring、escalation | 確保 production 後果有人承擔 |

這也是為什麼純 prompt 工程不是長期護城河。prompt 熟練在短期有用，但平台會逐步吸收大量 prompt pattern。更耐久的是 eval design、harness engineering、工具治理、權限邊界、失敗分析，以及把 AI workflow 接進真實 SDLC 的能力。

未來的差距不會只在「誰比較會叫 AI 寫 code」。差距會在「誰能設計一個讓 AI 產出可驗證、可審核、可回退、可維護的工作系統」。

## 五類長期能力

研究材料指向五類長期能力。它們不是互斥角色，而是未來工程師需要逐步建立的能力組合。

### 1. System complexity：理解並控制複雜系統

第一類能力是複雜系統理解與控制。

這包含資料流、狀態流、錯誤邊界、權限邊界、observability、rollback、release safety、incident response、technical debt judgment。這些能力的共同點是：它們都處理「局部正確之外的問題」。

AI 很可能越來越會生成局部正確的程式。它能照著範例新增 endpoint，能依照現有 pattern 補一個 adapter，能修改多個檔案讓測試變綠。但局部正確不等於系統正確。

系統複雜度會隨著變更量上升而上升。當 AI 讓更多人更快產生更多 code，真正稀缺的是能看見整體結構的人：哪裡耦合太重、哪裡缺少觀測、哪裡權限邊界模糊、哪裡的資料語意正在漂移、哪裡的技術債會在下一次 incident 爆開。

這種能力不一定對應到單一職稱。它可能在 Tech Lead 身上，也可能在 SRE、平台工程師、資深產品工程師或 security engineer 身上。但作為能力組合，它是五到十年最穩的護城河之一。

### 2. Verification：比生成更稀缺的驗證能力

第二類能力是驗證能力。

驗證能力會升值，不是因為 AI 不會進步，而是因為 AI 越進步，越需要可靠的 end-state evaluation。當 agent 能自行讀檔、改檔、跑測試、修錯、提交 PR，人類更不能只看「它完成了」。

你需要知道：

- 什麼是正確結果？
- 哪些測試能代表正確？
- 哪些測試只是表面覆蓋？
- 哪些 failure mode 沒有被測到？
- AI 是否引用了不存在的 API、錯誤的假設或過期文件？
- 如果結果錯了，系統會如何失敗？

驗證能力包含測試策略、eval baseline、rubric、source grounding、tool correctness、policy compliance、monitoring、人類升級流程。這些不是暫時 workaround，而是 AI-assisted engineering 的核心紀律。

會生成的人會越來越多。能驗證的人會更少，也更重要。

### 3. Requirements translation：把模糊需求翻譯成可驗證方案

第三類能力是需求轉譯。

AI 很會把模糊需求快速實作成某種東西，但不保證那個東西是對的。這是危險所在。當實作成本下降，模糊需求不再慢慢暴露問題，而是會被快速固化成 code、資料結構、API、流程與使用者體驗。

需求轉譯能力包含：

- 問出缺失的約束。
- 分辨需求、解法、假設與非目標。
- 做 domain modeling。
- 定義 acceptance criteria。
- 把風險和不確定性寫進任務。
- 讓 AI 能在清楚邊界內工作。

這項能力對所有層級都重要。Junior 可以從學會把任務拆清楚開始，Mid-level 可以用它升級成真正 owner，Senior 和 Tech Lead 則需要把它變成團隊工作流。

當 code 便宜，錯誤需求更貴。需求轉譯能力就是防止錯誤被高速放大的能力。

### 4. Product/domain understanding：理解產品與領域，但不能脫離技術風險

第四類能力是產品與 domain 理解。

AI 讓 prototype 更快，但 prototype 和 production system 不是同一件事。能快速做出 demo，不代表能支撐真實使用者、真實資料、真實法規、真實安全邊界與真實維運。

產品與 domain 理解會升值，因為當實作成本下降，真正的瓶頸會轉向：你是否理解 user problem、business constraint、資料語意、法規限制、組織流程與安全邊界。

但這裡有一個重要前提：產品與 domain 理解不能脫離技術風險。只懂產品、不懂系統風險，容易要求 AI 快速堆出不可維護的功能；只懂技術、不懂 domain，容易把錯問題做得很漂亮。

未來更有價值的是兩者結合：能把真正的業務問題翻譯成正確系統，並且知道哪些地方會影響可靠性、安全、成本與演進。

### 5. Reliability/security/infra risk control：控制可靠性、安全與基礎設施風險

第五類能力是 reliability、security、infra risk control。

AI 不會讓可靠性與安全性消失。相反地，當 code volume、變更頻率、工具鏈、抽象層與供應鏈複雜度上升，可靠性與安全風險會被推到更前面。

LLM 產碼可能出現漏洞、package hallucination、錯誤依賴、過度寬鬆權限、缺少輸入驗證、錯誤錯誤處理。即使 AI 也會逐步提升安全掃描、修復生成與 incident triage，仍然需要人類設定 guardrail、判斷 false positive、處理高壓事故、設計 SLO、管理錯誤預算、限制 blast radius。

偏 infra、reliability、security、system complexity 的工程師，長期不一定人數最多，但更可能更貴。原因不是他們不會被 AI 觸碰，而是他們處理的是 AI 放大後更難逃避的問題：系統如何在變更量上升時仍然可觀測、可回退、可防護、可恢復。

## 高階能力也會被 AI 觸碰，但責任不會消失

這裡需要保留一個重要 nuance：高階能力不是完全免疫。

AI 已經能產生架構草案、列出 trade-off、摘要 legacy code、提出 review comment、分析 log、生成測試、建議重構方案。未來這些能力會更強。也就是說，不能把「我做 system design」或「我會 code review」當作永久安全保證。

真正保值的不是會產出高階文字，而是能對高階判斷的正確性、成本與後果負責。

架構圖可以由 AI 草擬，但遷移成本、團隊能力、風險順序、資料邊界、上線策略，需要 owner 決策。review comment 可以由 AI 產生，但哪些 invariants 不可破壞、哪些技術債可以接受、哪些改動不能 merge，需要人承擔。debug 候選原因可以由 AI 列出，但真正 root cause、跨系統因果、事故溝通與系統性修復，需要人負責。

因此，未來的分界不是「AI 會不會做這件事」，而是「你是否能為這件事負責」。

## 從個人能力到後續章節

本章建立的是全書的概念橋樑。

第 1 章說明了任務如何被壓縮：CRUD、樣板、測試骨架、文件整理、簡單 bugfix、bounded refactor 會先被吸收。第 2 章說明了責任如何上移：工程師價值從產碼轉向問題定義、驗證、治理與 production accountability。

接下來的問題會更具體：

- Junior 的舊練功路徑被壓縮後，該如何重新學基本功？
- Mid-level generic engineer 為什麼可能比 Junior 更危險？
- Senior 如何證明自己不是只有年資，而是有 system ownership？
- Tech Lead / Architect 如何從設計者變成 AI-assisted SDLC 的治理者？
- 個人工程師該選擇哪一種定位，建立什麼「一深一高」組合？

這些問題都建立在同一個前提上：AI 讓 execution 更便宜，但讓正確方向、可靠驗證、風險治理與後果承擔更重要。

## 對讀者的職涯含義

對讀者而言，本章的職涯含義很現實：不要再把「我能寫 code」當作主要定位。你仍然必須能寫，但你的下一階段價值要建立在定義、驗證、治理、承擔與簡化上。

如果你是 Junior，現在就要把學習重心從「多交幾個可跑的 patch」擴大到「我能否解釋需求、資料流、錯誤邊界與測試意義」。如果你是 Mid-level，你要盡快從穩定 implementer 升級成能處理模糊需求、跨模組風險與 production 後果的人。如果你是 Senior 或 Tech Lead，你的責任會更明確地轉向建立可靠的 AI-assisted workflow，讓團隊在產碼速度上升時不犧牲系統穩定性。

未來最稀缺的工程師，不一定是最會手寫 code 的人，而是能讓更多 AI 產出的 code 不把系統搞壞的人。這就是「任務被壓縮，責任上移」對個人職涯最直接的含義。
