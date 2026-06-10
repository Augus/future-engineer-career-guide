# 第 9 章：團隊與組織會怎麼變

AI coding agent 帶來的主要變化，不是工程團隊可以不再負責，而是同樣的人會推動更多變更，因此團隊必須把 ownership、review、approval、rollback 與培訓制度重新設計。

如果只看個人工程師，AI coding 很容易被理解成「我寫得更快」。但在團隊裡，真正的問題不是某個人快了多少，而是整個 codebase 每週進入多少變更、多少變更跨過多少模組、多少判斷被壓縮到 review 與 merge 前最後幾分鐘。

當 agent 能協助產生 feature、bugfix、測試、文件與重構草稿，code volume 上升幾乎是必然結果。即使每個變更本身不大，總量增加後，團隊會面臨三種壓力：

- review queue 變長，資深工程師被迫審更多 PR。
- 變更來源更分散，原本不熟悉某模組的人也能快速產出看似合理的修改。
- 風險不再只來自「寫不出來」，而是來自「寫得出來但沒有人真的理解後果」。

這一章談的不是個人怎麼使用 AI，而是團隊如何避免被 AI 放大的速度反噬。主線很簡單：任務被壓縮，責任上移；個人章談能力要往上移，團隊章則談制度也必須往上移。

## 團隊會少一點純執行，多一點責任密度

在 AI-assisted development 裡，團隊最先被壓縮的通常不是所有工程工作，而是明確、局部、低模糊度的 implementation 任務。CRUD、樣板程式、簡單測試骨架、文件初稿、局部 bugfix，都會變得更容易被 agent 起草。

這不等於團隊可以直接減少所有工程師。更務實的變化是：同樣規模的團隊，能同時啟動更多任務；同一位工程師，可能同時 supervision 多個 agent 工作流；原本需要排隊等人手的低風險修改，現在更容易被推進。

但這也代表團隊內的責任密度會上升。過去一個工程師自己寫一個變更，他至少在寫的過程中被迫碰過細節。現在 agent 可以把細節先填好，工程師有機會跳過部分「辛苦但有學習價值」的過程。這讓 review、測試、ownership 與運維責任變得更重。

因此，未來團隊可能不是單純少人，而是角色比例改變：

| 團隊面向 | 過去常見重心 | AI coding 後更重要的重心 |
|---|---|---|
| Junior 工作 | 實作小 ticket、修樣板、補測試 | 在約束下學會讀 code、驗證、debug、理解 production 後果 |
| Mid-level 工作 | 完成功能、串接 API、修常見問題 | 成為模組 owner，拆任務、審風險、維持可維護性 |
| Senior 工作 | 設計方案、解複雜問題、review | 建立治理規則、掌控複雜度、守住可靠性與安全 |
| Tech Lead 工作 | 分配任務、定架構、協調跨組 | 設計 AI-assisted SDLC，包括 gate、rollback、escalation 與 review capacity |
| QA / DevOps / PM / Designer 邊界 | 分工較明確 | 低風險任務邊界模糊，高責任決策 owner 更明確 |

低風險工作可能跨角色流動，但高責任工作不能跟著模糊。誰允許變更進 production？誰知道 rollback 怎麼做？誰在事故後說得清楚當初為什麼接受這個風險？這些問題不能交給 agent，也不能交給「大家」。

## Code review 會從 style 轉向 risk

AI 會讓 style review 的價值下降。這不是因為 style 不重要，而是因為格式、命名、簡單 lint、重複樣板與表層一致性，越來越適合交給 formatter、linter、static analysis、CI 與 agent 自檢處理。

真正稀缺的是 risk review。

過去 review 常常卡在「這個 function 名稱要不要改」、「這段能不能拆小一點」、「這裡少了一個空白」這類問題。AI 時代不是完全不能談這些，而是如果 senior review capacity 被大量 style issue 吃掉，團隊會在真正需要人工判斷的地方失守。

AI-generated code 的 review 應該至少問七類問題：

| Review 問題 | 要看的不是 |
|---|---|
| 這個變更是否真的符合需求？ | 只看 PR 描述是否流暢 |
| 這個解法是否改變了系統邊界？ | 只看單一檔案是否能編譯 |
| 失敗時會怎樣？ | 只看 happy path |
| 測試是否覆蓋真正風險？ | 只看 coverage 數字 |
| 是否引入安全、權限、資料外洩或供應鏈風險？ | 只看功能是否可用 |
| 是否增加長期維護成本？ | 只看這次 ticket 是否完成 |
| 是否有清楚 rollback 或 kill switch？ | 只看 merge 當下是否綠燈 |

這裡的重點不是把 review 變成更慢的官僚流程，而是把人工注意力放到最不該自動化的地方。formatter 可以處理格式，CI 可以擋一部分錯誤，agent 可以幫忙產生測試候選；但系統後果、需求是否被誤解、資料與權限邊界是否被破壞，仍需要 human owner 做判斷。

因此，團隊應該明確區分三種 review：

| Review 類型 | 適合自動化程度 | 人的重點 |
|---|---:|---|
| Style review | 高 | 設定規則，不在 PR 裡反覆爭論 |
| Correctness review | 中 | 看測試是否對準需求與 failure mode |
| Risk review | 低 | 判斷架構、資料、安全、可靠性、維護成本與 production 後果 |

如果團隊沒有這個區分，AI 只會讓 review queue 更擁擠。表面上大家 merge 更快，實際上風險被延後到 incident、hotfix、資料修補與技術債裡支付。

## Human owner 不能被 ticket owner 取代

AI 產出的每一段 code 都必須有 human owner。這個 owner 不是形式上的 assignee，也不是「叫 agent 跑的人」，而是能對該變更在 codebase 裡的後果負責的人。

這裡要區分兩件事：

- Ticket ownership：誰負責把這張票關掉。
- Module ownership：誰理解這個模組的設計邊界、依賴、測試策略、運維風險與長期維護方向。

AI 時代最危險的情況，是 ticket owner 可以很快產出修改，但 module owner 沒有真正參與；或者根本沒有 module owner，只有一群人在 PR 上互相假設別人看過。這會讓 codebase 變成「每個變更都有人發起，但沒有人擁有系統」。

比較健康的規則是：

- 低風險、局部、可逆的變更，可以由 ticket owner 送審，但必須有清楚測試與 rollback。
- 觸及核心資料模型、權限、付款、資安、部署、跨服務契約的變更，必須有 module owner 或 domain owner approval。
- 若 agent 修改了不屬於 requester 熟悉範圍的模組，review 不能只找同組方便的人，必須找該模組 owner。
- 沒有 owner 的模組，本身就是風險；AI 只會把這個風險放大。

Human owner 的責任也要寫清楚。最少包含：

| Owner 責任 | 具體含義 |
|---|---|
| 需求理解 | 確認 agent 解的是正確問題，不只是完成 prompt |
| 技術判斷 | 確認解法符合模組邊界與長期方向 |
| 驗證策略 | 確認測試、eval、manual check 覆蓋主要 failure mode |
| 上線責任 | 知道如何監控、rollback、通知與處理事故 |
| 維護責任 | 接受未來這段 code 需要被讀、改、刪、重構 |

這不是要讓每個變更都變重，而是要避免「AI 寫的」變成責任模糊的藉口。Production 不會因為 code 是 agent 產生的就降低代價。

## Approval gate 要看風險，不要看自尊

AI-assisted workflow 需要 approval gate，但 gate 的目的不是維持階級感，也不是讓 senior 成為每行 code 的人工編譯器。Gate 的目的，是在風險穿過邊界前，讓正確的人做正確的判斷。

團隊可以把變更分成三層：

| 風險層級 | 例子 | Gate 建議 |
|---|---|---|
| 低風險 | 文件、測試補強、UI 文案、局部內部工具 | 自動檢查通過後，輕量 review 或 owner 抽查 |
| 中風險 | 一般 feature、非核心 API、可回復的資料流程 | 至少一位熟悉模組的人 review，確認測試與 rollback |
| 高風險 | 權限、付款、帳務、資安、資料遷移、部署流程、跨服務契約 | module owner / domain owner approval，必要時加 security、SRE、EM 或 PM gate |

好的 approval gate 應該有三個特徵。

第一，gate 應該事前定義，而不是等 PR 出現後靠感覺爭論。團隊要知道哪些目錄、服務、資料表、API、設定檔屬於高風險區。

第二，gate 應該綁定風險，而不是綁定「是不是 AI 寫的」。AI 寫的低風險文件不需要過度審查；人寫的權限變更也不該因為不是 AI 寫的就放鬆。

第三，gate 應該能被執行。若所有 PR 都需要同一位 senior approval，最後只會製造瓶頸。Review capacity 是真實資源，不能用口號解決。

## Rollback 是 AI 時代的基本工程能力

當 code volume 上升，錯誤不會消失，只會以更高頻率測試團隊的復原能力。這使 rollback 從「上線後才想」變成「merge 前就要想」。

每個中高風險 agent-assisted change，至少要回答：

- 這個變更能不能 feature flag？
- 如果資料被寫錯，是否可修補？修補成本是什麼？
- 如果新行為造成錯誤，能否快速回到舊行為？
- 監控指標是什麼？誰會看？
- 上線後多久內要特別觀察？
- rollback 會不會破壞已經產生的新資料或新狀態？

很多團隊把 rollback 當成 DevOps 或 SRE 的事，這在 AI coding 時代會更危險。因為 agent 可以讓 application code 變動更快，如果 application owner 不理解 rollback 代價，部署層再成熟也只能處理一部分問題。

對工程團隊來說，merge 前 checklist 應該加入一句很硬的問題：如果這個變更在 production 出錯，負責人能不能在十分鐘內說出回復路徑？

如果答案是否定的，這不是「比較謹慎」而已，而是還沒有準備好接受這個變更帶來的責任。

## Escalation path 要明確，不要等事故時才找人

Agent workflow 需要 exit condition，也需要 escalation path。否則工程師容易卡在兩種低品質狀態：一種是一直叫 agent 修，直到表面測試過；另一種是遇到複雜問題時直接把 AI 產出的半成品丟給 reviewer。

Exit condition 是：什麼情況下你停止讓 agent 繼續嘗試。

Escalation path 是：停止後找誰、帶什麼資訊、如何讓下一個人有效接手。

團隊可以要求 agent-assisted work 在送審前留下簡短紀錄：

- 原始需求與 acceptance criteria。
- 讓 agent 做了哪些任務。
- 人工修改了哪些關鍵部分。
- 哪些測試跑過，哪些沒有跑。
- 哪些地方仍不確定。
- 如果 reviewer 要深入，應該先看哪些檔案或哪個決策點。

當以下情況發生時，應該升級，而不是繼續堆 prompt：

| 升級情境 | 為什麼不能硬推 |
|---|---|
| Agent 連續修同一類錯誤，沒有收斂 | 代表模型可能不理解系統約束 |
| 變更跨過不熟悉的 module boundary | requester 可能看不出長期破壞 |
| 測試綠燈但行為仍無法解釋 | 綠燈不能取代理解 |
| 涉及安全、權限、資料遷移 | 事故代價高，不能用速度抵押 |
| PR diff 過大，reviewer 無法有效審 | review capacity 已經被超載 |

Escalation 不是失敗，而是工程制度的一部分。AI 時代成熟的工程師不是永遠能靠 agent 解完，而是知道何時停下來，把問題升級成可以被團隊理解與處理的形式。

## Review capacity 會成為瓶頸

AI 讓產出 code 變便宜，但沒有讓高品質 review 同等變便宜。這會讓團隊出現一個常被低估的瓶頸：review capacity。

如果每個人都能用 agent 快速送出更多 PR，資深工程師的 review queue 會變成新的塞車點。更糟的是，這些 PR 可能都「看起來」品質不錯，因為格式一致、命名合理、測試也有，但真正風險藏在需求理解、資料邊界、錯誤處理與長期維護成本裡。

團隊需要把 review capacity 當成一級資源管理，而不是靠 senior 自己加班消化。可行做法包括：

- 限制同時開啟的 agent-assisted PR 數量。
- 將大型 agent output 拆成可審的小 PR。
- 對高風險區域設定更嚴格 owner review。
- 對低風險變更提高自動化檢查，減少人工消耗。
- 建立「review readiness」標準，不符合就退回，不進入正式 review queue。
- 培養 Mid-level 成為某些模組的 reviewer，不讓所有判斷集中在少數 senior。

Review readiness 可以很簡單：

| 送審前要求 | 不符合時的處理 |
|---|---|
| PR 說明包含需求、解法、風險與驗證 | 退回補齊 |
| Diff 大小合理，能在有限時間內審完 | 拆 PR |
| 測試結果明確，不用 reviewer 猜 | 補測試或補說明 |
| 高風險變更標明 rollback | 補 rollback plan |
| AI 參與部分有註明不確定點 | 補人工驗證紀錄 |

這些規則不是為了增加文件負擔，而是保護 reviewer 的注意力。AI 時代的工程組織，誰能管理注意力，誰才有機會管理風險。

## Junior apprenticeship 要重新設計

AI 對 Junior 最大的衝擊，不只是某些入門任務被自動化，而是傳統 apprenticeship 的練功路徑被壓縮。

以前 Junior 透過修小 bug、寫 CRUD、補測試、改文案、跟著 review 被糾正，慢慢建立對 codebase、debug、需求與 production 的直覺。這些任務本身不一定高價值，但它們是學習系統的入口。

如果團隊把這些入口全部交給 agent，Junior 可能得到短期產出，卻失去長期形成判斷力的材料。結果是：履歷上做過很多事，但遇到非標準問題時不知道怎麼定位、驗證、回復，也不知道什麼時候該問人。

因此，AI 時代的 Junior apprenticeship 不應該是「禁止用 AI」，也不應該是「什麼都先問 AI」。比較合理的設計，是把 Junior 的學習任務從單純 implementation 改成受控的 ownership 練習。

### 1. 讓 Junior 先讀，再改

Junior 使用 agent 前，應該先做 code reading。不是讀完整個 repo，而是針對要改的模組回答幾個問題：

- 這個模組負責什麼？
- 它依賴誰？誰依賴它？
- 現有測試測了哪些行為？
- 最常見的 failure mode 是什麼？
- 這次變更可能碰到哪個邊界？

這些問題能避免 Junior 只學會「描述任務給 agent」，卻沒有建立 codebase map。

### 2. 讓 Junior 寫驗證，不只寫功能

AI 可以很快產生功能草稿，但 Junior 的訓練價值應該轉向驗證能力。給 Junior 的任務可以要求：

- 先寫 acceptance criteria。
- 先列出至少三個 failure case。
- 用 agent 產生測試後，人工解釋每個測試為什麼存在。
- 對 agent 產生的測試做刪減，移除只測 implementation detail 的測試。
- 對一個 bugfix 說明 root cause，而不是只貼 diff。

這些要求看似慢，但它們訓練的是未來不容易被壓縮的能力。

### 3. 讓 Junior 做 supervised ownership

Junior 不應該永遠只做被切碎的小任務。更好的方式，是讓 Junior 在小範圍內擁有一個明確模組或流程，但配上清楚的 guardrail：

- 有一位指定 reviewer。
- 有固定 rollback 模板。
- 有送審前 checklist。
- 有事故或失敗後的復盤。
- 有逐步提高風險等級的任務安排。

這讓 Junior 學會的不是「我能用 AI 做完很多 ticket」，而是「我能在可控範圍內對一段系統負責」。

### 4. 讓 review 成為教學，而不只是擋錯

AI 會讓 review queue 更滿，因此團隊很容易把 Junior PR 當成負擔。但如果 apprenticeship 被犧牲，團隊未來會缺少能承接 ownership 的 Mid-level。

對 Junior 的 review，應該至少保留一部分教學功能。Reviewer 不需要解釋每個 style 問題，但應該指出：

- 哪些是需求理解錯誤。
- 哪些是風險判斷不足。
- 哪些測試沒有對準 failure mode。
- 哪些地方看似簡潔，實際增加長期維護成本。
- 哪些問題應該在呼叫 agent 前先想清楚。

換句話說，Junior apprenticeship 的核心從「你會不會寫」轉向「你怎麼理解、驗證、解釋與承擔」。

## 給 Tech Lead、EM 與 CTO 的建議

如果你負責團隊，不要只問「我們有沒有導入 AI coding 工具」。更重要的問題是：

- 我們是否知道哪些任務可以交給 agent，哪些不能？
- 我們是否定義了高風險區域與 approval gate？
- 每個 agent-assisted change 是否有 human owner？
- Review capacity 是否被管理，還是被默默透支？
- Junior 是否仍有學習系統與承擔責任的路徑？
- Rollback、monitoring、incident ownership 是否跟得上 code volume？

工具導入本身不是成熟度。真正的成熟度，是團隊能在速度上升時，仍然維持可靠性、可維護性與責任清楚。

可以從四個制度開始：

| 制度 | 最小可行版本 |
|---|---|
| AI-assisted PR template | 要求寫明需求、agent 參與、驗證、風險、rollback |
| Module ownership map | 標明高風險目錄、服務、資料表與 owner |
| Risk-based review policy | 依風險決定 approval，而不是所有 PR 一視同仁 |
| Junior apprenticeship path | 設計 code reading、verification、supervised ownership 任務 |

這些不需要一次做到完美。最糟的不是制度不完整，而是 code volume 已經上升，團隊卻仍用舊的 review、舊的 ownership、舊的培訓方式假裝一切沒有改變。

## 對讀者的職涯含義

對個人工程師來說，團隊章的重點不是「你要懂管理」，而是你要理解未來工程價值會越來越出現在責任交界處。

如果你只會把 agent 產出的 code 送進 review，卻說不清楚需求、風險、測試、rollback 與維護後果，你會把自己的價值壓在最容易被商品化的層級。相反地，如果你能成為某個模組、某段流程、某類風險的可靠 owner，你就不只是比較會使用 AI 的工程師，而是團隊在速度上升後仍然敢交付的理由。

未來團隊不會只獎勵最快產 code 的人。它會更需要能讓更多 code 安全進入、必要時安全退出、並在事故中說得清楚的人。
