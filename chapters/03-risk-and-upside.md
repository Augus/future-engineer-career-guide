# 第 3 章：誰最危險，誰會升值

> AI coding 時代的風險，不是平均落在所有工程師身上；它會先壓縮可被規格化、可被重複、可被低責任交付的任務，然後把真正值錢的責任推向能定義、驗證、治理與承擔的人。

討論工程師職涯風險時，最容易犯的錯，是把問題說成「AI 會不會取代工程師」。這個問法太粗糙，也太容易讓人得到錯誤結論。

更準確的問法是：你現在的價值來源，是來自「把已經講清楚的工作做完」，還是來自「把沒有講清楚、不能出錯、會影響系統長期健康的問題處理好」？

前者會被壓縮。後者會變得更重要。

AI coding agent 會讓日常實作更便宜，讓 boilerplate、CRUD、簡單 bugfix、測試骨架、文件整理、框架拼裝、API glue code 這些任務逐步商品化。這不代表工程師消失，而是代表工程師的基本價值不再只由「寫出多少程式碼」決定。當產碼成本下降，市場會更在意誰能判斷需求是否清楚、設計是否合理、變更是否安全、系統是否可維護、事故是否能被預防與處理。

這就是本書的主線：任務被壓縮，責任上移。

## Junior：舊練功路徑被壓縮

Junior 的風險很直觀：很多傳統入門任務，正好是 AI 目前最容易吸收的區域。

過去一個新人進入團隊，常見路徑是先修小 bug、補測試、寫簡單頁面、接 CRUD、整理文件、照既有模式擴充功能。這些任務本來就有清楚範本、低架構風險、可由 reviewer 把關，也因此成為 AI 最容易介入的地方。

這會帶來一個現實問題：Junior 不是完全不需要了，而是「靠低風險票單慢慢累積經驗」的路徑變窄了。

未來的 Junior 不能只訓練自己變成更快的打字員。更重要的是提早建立幾種底層能力：

- 看懂資料流與狀態流，而不是只看單一函式。
- 能說明 bug 的 root cause，而不是只描述改了哪一行。
- 會讀 log、trace、error message、database query 與 API response。
- 會把需求拆成可驗證的小問題。
- 會檢查 AI patch 是否符合既有設計與測試邊界。
- 能指出不確定處，而不是把 AI 產出的答案當成完成品。

換句話說，Junior 仍然需要寫 code，但更早就必須學會「驗證 code」。如果一個新人只用 AI 完成任務，卻說不清楚變更的資料路徑、失敗情境與測試理由，他不是被 AI 放大，而是在把自己的學習路徑外包掉。

Junior 的機會也在這裡。因為 AI 可以降低查文件、理解範例、產生初稿的成本，願意主動追問系統行為的人，反而可能比以前更快接觸到完整上下文。差別在於：他不能停在「AI 給我答案」，必須把每一次 AI 產碼變成一次閱讀、驗證與復盤。

## Mid-level：最容易被商品化的一層

最危險的不一定是 Junior。更值得警覺的是 generic Mid-level。

Mid-level 過去的市場價值，很大一部分來自穩定交付。他熟悉框架、知道團隊慣例、可以獨立處理票單、可以把常見需求做完，不需要太多手把手指導。這在沒有 AI agent 的時代很值錢，因為大量工程工作都需要可靠的人力實作。

但當 coding agent 能處理越來越多日常實作，generic Mid-level 的核心工作會被直接壓縮。尤其是那些「會接需求、會套框架、會串 API、會修常見 bug，但不掌握系統責任」的人，會同時面臨兩種壓力：

第一，成本已經比 Junior 高。  
第二，不可替代性還沒有真正建立。

如果 Mid-level 的價值只在於「我可以穩定把 ticket 做完」，那麼他正在站在最容易被重新定價的位置。因為 agent 正是在吸收這一層日常工作：根據 issue 產生 patch、根據既有模式修改多個檔案、補簡單測試、整理 PR、修 lint、查文件、搬運常見實作模式。

Mid-level 要避開這個風險，不能只變成「更會用 AI 的 implementer」。他必須往責任更高的方向移動：

- 從單一 ticket owner 升級為小範圍 system owner。
- 從照需求實作升級為能澄清需求與定義 acceptance criteria。
- 從修表面 bug 升級為跨模組 root-cause analysis。
- 從只管功能能跑升級為理解 reliability、security、observability、performance 等 non-functional requirements。
- 從單次交付升級為能設計 review checklist、merge gate、rollback plan。
- 從使用 AI 升級為治理 AI workflow：哪些任務可交給 AI、哪些必須人工確認、哪些需要更強測試。

generic Mid-level 的危險，不在於他完全沒有能力，而在於他的能力剛好處在「過去稀缺、未來變便宜」的位置。這是很現實的分水嶺：往 ownership 走，會升值；停在 routine implementation，會被壓縮。

## Senior：年資不等於護城河

Senior 這個稱呼在 AI 時代會被重新檢驗。

真正的 Senior 不是「工作很多年的人」。年資可以帶來經驗，但不必然帶來判斷力、責任感、系統理解或複雜度控制能力。當 AI 把部分高階實作也變得更便宜時，只有年資、但沒有 ownership 的 Senior，並不安全；他只是比 generic Mid-level 晚一點被壓縮。

真正 Senior 的價值，會集中在四件事。

第一，他知道什麼不該自動化。  
不是所有任務都適合交給 AI。牽涉安全邊界、資料正確性、金流、權限、隱私、production migration、跨系統狀態一致性的變更，不能只看「AI 產得出來」。Senior 要能判斷任務風險，決定哪些地方可以用 AI 加速，哪些地方需要人工設計與審核。

第二，他能在資訊不完整時找到 root cause。  
真正的事故與複雜 bug，很少是一個清楚錯誤訊息對應一個修正。Senior 要能從 log、metric、trace、部署紀錄、資料狀態、使用者回報、系統變更中建立假設，逐步排除錯誤原因。AI 可以協助整理線索，但責任仍在人。

第三，他能為長期 maintainability 與生產風險負責。  
AI 可以快速增加 code volume，也可能快速增加技術債。Senior 的任務不是讓團隊 merge 更多 code，而是讓系統在變更後仍然可理解、可測試、可回復、可演進。他要能看出某個 patch 眼前可用，但會讓未來擴充成本上升。

第四，他能把團隊流程改造成 AI-assisted 之後仍可靠。  
這包括 PR 風險分級、AI 產碼 review 標準、測試與 eval 要求、human sign-off 範圍、rollback 路徑、incident 復盤方式。Senior 的價值不只是自己把關，而是讓整個團隊在使用 AI 後仍維持工程紀律。

因此，Senior 會分裂成兩種人。

一種是 codebase owner：掌握系統脈絡、能承擔事故、能控制複雜度、能訓練團隊。他會升值。

另一種是 senior implementer：寫過很多 code，但主要價值仍是親手實作、依經驗套模式、補洞。他會被壓縮，只是壓縮速度較慢。

這個差異非常關鍵。未來公司需要的不是更多資深打字員，而是能對系統後果負責的人。

## Tech Lead / Architect：從設計者變成治理者

Tech Lead 與 Architect 的角色也會改變。

過去 Lead 的工作常被理解為定技術方向、拆任務、review 架構、協調跨團隊交付。這些仍然重要，但在 agentic coding 時代，Lead 還要承擔另一層責任：設計 AI-assisted SDLC 的責任邊界。

也就是說，Lead 不只要問「這個系統怎麼設計」，還要問：

- 哪些任務可以交給 agent 先做 draft？
- 哪些任務需要人先寫設計或 acceptance criteria？
- 哪些變更必須有 human sign-off？
- 哪些系統不允許靠 vibe coding 推進？
- 哪些 PR 需要 stronger eval、security review 或 rollback plan？
- 團隊如何避免速度提升，但故障率與技術債也同步上升？

未來的 Tech Lead / Architect 候選人，價值會更取決於能否同時掌握四個面向：product ambiguity、architecture trade-off、delivery workflow、AI governance。

如果只懂架構圖，但無法處理模糊需求，他會離產品問題太遠。  
如果只懂 delivery，但無法控制技術債，他會讓團隊變快但變脆。  
如果只懂 AI 工具，但不懂系統風險，他會把工具效率誤認為工程成熟度。  
如果只懂治理，但不懂開發現場，他會制定沒有人能執行的流程。

Lead 的難處在於，他必須讓 AI 成為團隊能力，而不是讓 AI 放大團隊的混亂。

## 可讀版工程師類型風險表

下面這張表不是要替每個人貼標籤，而是幫讀者辨認自己的主要價值來源。如果你在多個類型之間，都可以對照最接近目前日常工作的那一欄。

| 工程師類型 | 目前主要價值來源 | 最容易被壓縮的部分 | 商品化風險 | 可能出路 | 優先訓練方向 |
|---|---|---|---|---|---|
| 只會接需求寫 CRUD | 穩定產出功能 | 主要工作本體 | 很高 | 轉向 QA / eval / domain support，或升級成小模組 owner | 資料流、測試策略、需求拆解 |
| 只會套框架 | 熟悉框架慣例與 scaffold | 建專案、拼頁面、套範例、版本升級 | 很高 | 成為 domain engineer 或具架構判斷的產品工程師 | domain model、架構邊界、測試 |
| 只會拼 API | 整合速度與文件查閱 | glue code、常見 SDK 串接、範例搬運 | 高 | 轉成 workflow owner 或 integration reliability owner | 權限、狀態流、錯誤處理、重試策略 |
| 只會修簡單 bug | 處理票單與常見修補 | 表層 bugfix、已知模式修正 | 高 | 升級成 root-cause debugger | tracing、profiling、incident drill |
| 不理解資料流 / 狀態流 | 局部交付 | 多數日常實作與修補 | 很高 | 必須補系統理解，否則風險最高 | 系統圖、狀態圖、資料契約 |
| generic Mid-level | 穩定完成 ticket | 大量 routine implementation | 很高 | 兩極分化：升級成 owner，或被重新定價 | ownership、trade-off、AI governance |
| Senior 但無 ownership | 年資、經驗、熟悉模式 | 可模板化的高階工作與親手實作 | 中高 | 晚一點被壓縮；必須轉向系統責任 | incident、mentoring、architecture |
| 真正 Senior / codebase owner | 判斷、責任、系統脈絡 | 局部寫碼 | 低中 | 升值 | 複雜度控制、團隊 AI workflow、可靠交付 |
| Product-minded Engineer | 把模糊問題轉成可驗證方案 | 細碎實作 | 中低 | 升值 | 需求澄清、domain modeling、驗收設計 |
| Domain Engineer | 行業知識加技術實作 | 泛用實作 | 低中 | 升值 | data semantics、規則系統、例外情境 |
| AI Agent Builder | 建 workflow、工具與上下文 | prompt 拼裝、SDK 串接、demo 級 agent | 中高 | 分化；必須往 eval、tooling、governance 升級 | failure analysis、可重跑流程、guardrail |
| Infra / Reliability / Security Engineer | 控制風險、邊界與非功能需求 | 低階維運腳本 | 低 | 升值 | observability、policy、supply chain、incident response |

這張表可以濃縮成一個判斷：越靠近「可規格化實作」的位置，越容易被壓縮；越靠近「不可出錯的判斷與責任」的位置，越耐久。

但這不是宿命。很多高風險類型都可以轉型。只會寫 CRUD 的人，可以補資料流與驗證策略；只會修簡單 bug 的人，可以訓練 tracing 與 root-cause analysis；generic Mid-level 可以主動接小範圍 ownership；Senior implementer 可以轉向複雜度控制與團隊治理。

真正危險的不是起點低，而是不承認自己的價值來源正在折舊。

## 風險判斷的正確讀法

本章的風險分析不是要製造恐慌，也不是要宣判某一層工程師沒有未來。它要指出的是：AI 會改變不同工作內容的市場價格。

有些能力會折舊，因為它們被工具吸收。  
有些能力會升值，因為工具使用越多，越需要人來驗證、治理與承擔後果。  
有些人會被壓縮，不是因為他們不努力，而是因為他們努力的方向仍停在低責任任務。  
有些人會升值，不是因為他們會更多工具，而是因為他們能把工具放進可靠流程。

所以，判斷自己的位置時，不要只問「我會不會用 AI」。更重要的是問：

- 我是否能解釋 AI 產出的每個重要變更？
- 我是否能判斷哪些任務不應交給 AI？
- 我是否能定義完成標準，而不是只接收需求？
- 我是否能設計測試、eval、observability 與 rollback？
- 我是否能在事故發生時找到 root cause？
- 我是否能讓系統更簡單，而不是只讓功能更多？

這些問題，比「我的職稱是 Junior、Mid 還是 Senior」更能反映未來風險。

## 對讀者的職涯含義

如果你是 Junior，不要把 AI 當成逃過基本功的捷徑。你要用 AI 加速閱讀、實驗與驗證，但每個產出都要逼自己說清楚資料流、失敗情境與測試理由。

如果你是 Mid-level，請把警覺拉高。generic Mid-level 是最容易被商品化的一層。你的下一步不是學更多 prompt trick，而是接 ownership、做跨模組 debug、理解 non-functional requirements，並建立 AI-assisted 交付的把關能力。

如果你是 Senior，請檢查自己是 codebase owner，還是只是經驗較多的 implementer。未來真正升值的是能控制複雜度、承擔 production 風險、設計可靠 workflow、帶團隊一起變穩的人。

如果你想走向 Tech Lead / Architect，你要把自己的責任從「設計系統」擴大成「設計人與 AI 一起交付系統的責任邊界」。AI 不會自動讓工程團隊成熟；它只會放大團隊已經有的能力與混亂。你的價值，在於讓這個放大過程可控。
