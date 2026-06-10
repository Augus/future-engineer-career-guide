# 第 4 章：未來工程師的七種定位

> 未來工程師的定位，不該被理解成七個互斥職稱，而該被理解成七種能力重心；真正耐久的策略，是選擇一個深技術面向，再搭配一個高階問題定義面向。

上一章談的是風險：哪些工程工作會被壓縮，哪些角色會升值。本章談定位：如果不能只靠「會寫 code」建立長期價值，那工程師應該往哪裡走？

這裡提出七種未來工程師定位：

1. AI-supervised Developer
2. AI Agent Builder
3. AI Workflow Architect
4. System Complexity Owner
5. Product-minded Engineer
6. Domain Engineer
7. Infra / Reliability / Security Engineer

這七種定位不是職稱清單，也不是要你選一個後放棄其他方向。現實職涯通常是混合型。一位產品工程師可以同時是 AI-supervised Developer 與 Domain Engineer；一位 Senior backend engineer 可以同時往 System Complexity Owner 與 Reliability 方向走；一位工具鏈工程師可以從 AI Agent Builder 升級成 AI Workflow Architect。

把它們當成能力模型，會比當成職稱更準確。

因為職稱會變，能力重心比較耐久。

## 定位一：AI-supervised Developer

AI-supervised Developer 的核心價值，是用 AI 放大日常交付，但由人負責 correctness。

這類工程師不是拒絕 AI，也不是把所有事情交給 AI。他會把 AI 當成實作助理、搜尋助理、測試初稿助理、重構草稿助理，但他自己負責判斷結果是否可合併。

AI-supervised Developer 的基本工作方式包括：

- 先定義任務邊界，再讓 AI 產出 patch。
- 要求 AI 說明變更理由，但不直接相信。
- 對照既有 codebase pattern，而不是只看新 code 能不能跑。
- 補上自己能理解的測試，而不是只接受 AI 產生的測試。
- 對重要變更做人工 review，能逐行說明關鍵邏輯。
- 遇到不確定處，縮小任務、補資料、查 log、問 owner，而不是讓 AI 猜。

這個定位會成為很多工程師的基本盤。未來大多數軟體工程師都會在某種程度上是 AI-supervised Developer，因為不用 AI 可能會失去效率，而盲目用 AI 又會增加風險。

它的耐久度中等。原因是：會使用 AI 交付工作會逐漸變成基本能力，不會長期構成明顯護城河。真正有價值的是「supervised」這個部分，而不是「AI」這個部分。也就是說，差異化不在於你能不能叫 AI 寫 code，而在於你能不能審核、約束、修正與承擔 AI 產出的後果。

容易平台化的部分，是提示技巧、常見重構、簡單測試生成、框架內的例行功能。比較耐久的部分，是 codebase context、風險判斷、驗證策略與對生產後果的責任。

## 定位二：AI Agent Builder

AI Agent Builder 的核心價值，是建構 agent workflow、工具介面、上下文供給與可重跑流程。

這個定位在短期內很有吸引力，因為 agentic coding 正在快速進入開發流程。能把 issue、repo context、工具呼叫、測試、PR、review、文件整理串成流程的人，會在一段時間內明顯提高團隊效率。

但這個定位也有很高的平台化風險。

如果 AI Agent Builder 的能力只停在 prompt、SDK 串接、MCP 拼裝、demo 級多 agent 協作，那它很可能是一到三年的紅利。平台會逐漸把常見 agent pattern 產品化，雲端工具、IDE、repo host、CI/CD 供應商也會把許多 workflow 內建。到那時，單純「會接工具」的價值會下降。

因此，AI Agent Builder 要往更深的方向走：

- 不只做 demo，而是做穩定可重跑的 workflow。
- 不只追求任務完成率，而是量測失敗模式。
- 不只讓 agent 能呼叫工具，而是設計權限、資料邊界與審核點。
- 不只看生成品質，而是設計 eval、成本監控、回滾與人工接手。
- 不只把流程接起來，而是知道哪些流程不該自動化。

AI Agent Builder 的長期價值，取決於他是否能跨過「工具熟練者」這一層，進入「workflow reliability owner」或「AI Workflow Architect」的位置。

這個定位不是不好，而是必須清楚知道：純工具紅利會折舊，治理與可靠性才比較耐久。

## 定位三：AI Workflow Architect

AI Workflow Architect 的核心價值，是設計團隊如何在 AI-assisted SDLC 中可靠交付。

這比 AI Agent Builder 更高一層。Agent Builder 偏重把工具與流程做出來；Workflow Architect 偏重定義責任邊界、審核機制、風險分級、handoff、rollback、metrics 與團隊規範。

一個 AI Workflow Architect 會關心：

- 哪些 issue 可以由 agent 先做 draft PR？
- 哪些變更必須先有設計文件或 acceptance criteria？
- 哪些系統需要更嚴格的 test / eval gate？
- 哪些 PR 需要安全、可靠性或資料正確性審查？
- 哪些任務可以自動修復，哪些必須停止並升級給 human owner？
- 如何衡量 AI workflow 是否真的降低返工，而不是只讓 PR 數增加？
- 如何避免工程師因過度依賴 AI 而退化 debugging、review、系統理解能力？

這個定位的耐久度較高，因為它處理的是組織層面的可靠性問題。工具會變，但只要團隊用 AI 寫 code，就會需要有人設計「如何安全使用」。

被平台化的部分，是常見 pipeline、預設 agent、標準 PR automation、簡單 policy template。比較難被平台化的部分，是針對特定團隊、特定系統、特定風險等級做出的流程設計。尤其是牽涉 production incident、資料邊界、跨團隊 owner、合規要求與長期維護成本時，平台只能提供能力，不能替組織承擔責任。

AI Workflow Architect 通常適合 Senior、Tech Lead、Architect 候選人，或已經熟悉 delivery workflow、review culture、CI/CD、incident response 的工程師。這不是單純工具職，而是治理職。

## 定位四：System Complexity Owner

System Complexity Owner 的核心價值，是控制大型 codebase、distributed system 或長期產品中的複雜度。

這可能是最耐久的定位之一。

AI 可以快速產生更多 code，但它不會自動讓系統更簡單。相反地，當產碼成本下降，團隊更容易累積過多邊界、重複抽象、隱性耦合、例外路徑、測試盲區與歷史包袱。AI 讓新增功能變快，也可能讓技術債生成變快。

System Complexity Owner 的任務不是寫最多 code，而是讓系統長期可理解、可修改、可測試、可恢復。

他會處理這些問題：

- 哪些模組邊界已經失效？
- 哪些資料流或狀態流讓系統變得不可預測？
- 哪些抽象讓表面簡潔、實際更難維護？
- 哪些技術債正在增加 incident risk？
- 哪些 agent 產生的 patch 雖然可跑，但會破壞系統一致性？
- 哪些地方需要刪除、合併、簡化，而不是再加一層？

這個定位的護城河來自三件事：深 codebase context、架構 trade-off 判斷、對長期後果的承擔。這些都很難完全平台化，因為每個成熟系統的複雜度都有自身歷史、組織決策與業務約束。

System Complexity Owner 不一定是正式 Architect。他可能是一個真正掌握核心服務的 Senior engineer，也可能是負責某個平台、資料流或關鍵模組的 codebase owner。重點不是頭銜，而是他能讓系統變穩、變清楚、變容易交付。

在 AI code volume 上升後，這個角色只會更重要。

## 定位五：Product-minded Engineer

Product-minded Engineer 的核心價值，是把模糊需求轉成可驗證的技術方案。

當實作成本下降，問題定義的價值會上升。因為如果需求本身錯了、驗收標準不清、使用情境缺失、資料語義混亂，再快的產碼也只會更快產生錯誤成果。

Product-minded Engineer 不只是「會跟 PM 溝通」的人。他要能理解產品問題，並把它轉成工程上可執行、可驗證、可維護的方案。

他會問：

- 使用者真正要完成的工作是什麼？
- 需求中的哪些詞其實還沒有定義清楚？
- 這個功能的成功標準是什麼？
- 哪些 edge case 會影響資料正確性或使用者信任？
- 哪些假設可以先用小實驗驗證？
- 哪些需求會讓系統複雜度不成比例上升？
- 這個方案上線後，如何觀測是否有效？

Product-minded Engineer 的耐久度高，因為他位於「問題定義」與「技術後果」的交界。AI 可以幫忙產生方案選項，但不會自動知道哪個產品問題值得解、哪個 trade-off 對業務合理、哪個驗收標準真的能代表成功。

比較容易平台化的部分，是規格草稿、user story 格式、常見方案模板、簡單分析報告。比較耐久的部分，是對產品脈絡、系統限制、使用者行為、資料語義與交付後果的綜合判斷。

這個定位特別適合在 SaaS、內部平台、工具型產品、資料產品、複雜 B2B 系統工作的工程師。因為這些環境裡，需求通常不是一句話可以說清楚，工程師若能補上問題定義能力，價值會明顯提高。

## 定位六：Domain Engineer

Domain Engineer 的核心價值，是把深 domain knowledge 與工程實作結合。

這個定位在 AI 時代會更重要，原因很簡單：泛用實作會變便宜，但 domain semantics 不容易被完整學到。

金融、醫療、製造、供應鏈、法遵、保險、教育、能源、物流、企業內部流程等領域，都有大量公開資料無法完整描述的規則。真正困難的地方，不只是把功能做出來，而是理解某個欄位在業務上代表什麼、某個例外情境為什麼存在、某個規則在不同客戶或市場下如何變形。

Domain Engineer 的工作包括：

- 把業務規則轉成清楚的 domain model。
- 理解資料語義，而不只是資料格式。
- 找出規則中的例外、衝突與優先順序。
- 和 domain expert 一起把模糊知識變成可測試規格。
- 判斷 AI 產出的泛用方案是否破壞領域規則。
- 設計可維護的規則系統，而不是把例外寫成散落各處的 if-else。

Domain Engineer 的耐久度高，被平台化風險低到中。平台可以內建通用流程，AI 可以查到常見 domain 知識，但每個組織的資料、流程、客戶約束、歷史決策與例外規則往往不同。能把這些東西翻譯成可靠系統的人，會比一般 framework engineer 更難被替代。

這個定位不是要工程師變成純業務人員，而是要工程師掌握「技術如何承載領域規則」。深 domain 加上良好工程能力，是很強的組合。

## 定位七：Infra / Reliability / Security Engineer

Infra / Reliability / Security Engineer 的核心價值，是控制 AI 時代的變更風險與系統邊界。

當 AI 讓 code volume 增加，可靠性與安全性的價值不會下降。相反地，它會上升。

原因很直接：更多自動產生的 code、更多 agent 操作、更多工具串接、更多背景 PR、更多 dependency、更多自動化權限，都會擴大風險面。低階維運腳本可能被 AI 壓縮，但風險控制、權限設計、observability、incident response、supply chain security、policy enforcement 會更重要。

這個定位會關心：

- AI 產出的 code 是否引入安全漏洞？
- agent 有哪些 repo、secret、資料庫、部署環境權限？
- 自動化流程失敗時，誰會接手？
- 如何偵測 AI 造成的品質退化或安全退化？
- 如何設計 rollback、rate limit、approval gate？
- 如何確保 dependency、package、生成指令不造成供應鏈風險？
- 如何讓 production incident 更快被發現、定位與恢復？

Infra / Reliability / Security Engineer 的耐久度很高，被平台化風險低。平台可以提供工具，AI 可以產生腳本，雲服務可以內建防護，但組織仍然需要有人理解自身系統邊界、威脅模型、故障模式與營運責任。

這個定位也會與前幾種定位交會。AI Workflow Architect 需要 reliability 與 security 思維；System Complexity Owner 需要 observability；Product-minded Engineer 需要理解哪些產品決策會帶來生產風險。Infra / Reliability / Security 不只是後端支援，而是 AI-assisted engineering 的控制面。

## 哪些定位較耐久，哪些較容易平台化

七種定位可以用兩個問題判斷耐久度：

第一，它是否依賴可被平台封裝的技巧？  
第二，它是否承擔特定系統、特定組織、特定 domain 的不可外包責任？

越依賴通用技巧，越容易平台化。越依賴本地脈絡、風險判斷、責任邊界與長期後果，越耐久。

| 定位 | 長期耐久度 | 平台化風險 | 判斷理由 |
|---|---|---|---|
| AI-supervised Developer | 中 | 中 | 會成為基本工作方式；差異化在審核與驗證，不在工具使用本身 |
| AI Agent Builder | 中 | 高 | prompt、SDK、常見 workflow 容易被產品化；eval、guardrail、failure analysis 較耐久 |
| AI Workflow Architect | 高 | 中 | 平台可提供流程元件，但無法替團隊定義責任、風險分級與治理邊界 |
| System Complexity Owner | 很高 | 低 | 深 codebase context、架構取捨、長期維護責任難以通用化 |
| Product-minded Engineer | 高 | 低中 | 問題定義、驗收設計、產品與技術後果的連接不容易被完全外包 |
| Domain Engineer | 高 | 低 | domain semantics、組織例外、資料意義與規則系統具有本地性 |
| Infra / Reliability / Security Engineer | 很高 | 低 | AI code volume 增加後，風險控制、權限邊界、事故處理更重要 |

這張表的重點不是說某些定位「不能選」。AI Agent Builder 即使平台化風險高，仍可能是很好的切入點；AI-supervised Developer 即使耐久度中等，仍會是幾乎所有工程師都需要具備的基本能力。

真正的問題是：你是否停在容易被平台吸收的那一層。

如果你做 AI Agent Builder，但只會接 SDK，風險高。  
如果你做 AI Agent Builder，並且能設計 eval、failure analysis、權限邊界、可重跑 workflow，風險就下降。  
如果你是 AI-supervised Developer，但只會叫 AI 寫 code，差異化低。  
如果你能定義 acceptance criteria、審核 AI patch、補測試、控制 production risk，你就更接近 owner。

每個定位都有淺層與深層。淺層會折舊，深層才耐久。

## 「一個深技術面向 + 一個高階問題定義面向」

對個人工程師最實用的策略，不是把七種定位全部學滿，而是建立「一深一高」組合。

一個深技術面向，讓你有不可替代的工程根基。  
一個高階問題定義面向，讓你不只是執行者，而能決定什麼值得做、怎麼做才算完成、怎麼做才不會留下風險。

深技術面向可以是：

- reliability / observability
- security
- distributed systems
- data systems
- performance
- platform engineering
- testing / eval infrastructure
- complex frontend state / product architecture
- domain-specific backend systems

高階問題定義面向可以是：

- product thinking
- domain modeling
- requirements clarification
- architecture trade-off
- AI workflow governance
- system complexity ownership
- incident and risk management

幾個組合例子：

| 深技術面向 | 高階問題定義面向 | 可能形成的定位 |
|---|---|---|
| Backend / distributed systems | System complexity ownership | 核心服務 codebase owner |
| Observability / reliability | AI workflow governance | AI-assisted delivery reliability owner |
| Security | Agent permission / supply chain policy | AI security / platform governance engineer |
| Data systems | Domain modeling | Data-heavy Domain Engineer |
| Frontend architecture | Product thinking | Product-minded frontend / app engineer |
| Testing / eval infrastructure | AI workflow architecture | Agentic SDLC quality owner |
| Platform engineering | Requirements clarification | Internal developer platform owner |

這個策略的好處是，它避免兩種常見錯誤。

第一種錯誤，是只追逐工具。  
只追工具的人，短期看起來很快，但平台一旦內建同樣能力，差異化就消失。prompt trick、工具串接、demo workflow 都可能遇到這個問題。

第二種錯誤，是只談高階抽象。  
只談產品、架構、治理，卻沒有深技術支撐，最後容易變成無法落地的建議。未來工程師不是純顧問，他仍然要能判斷技術細節，理解系統限制，並對交付結果負責。

一深一高的意思是：你既有足夠深的工程能力，讓別人相信你能處理困難問題；也有足夠高的問題定義能力，讓你不被困在可被壓縮的實作層。

## 如何選擇自己的定位

選定位時，不要先問「哪個最熱門」。應該問三個更實際的問題。

第一，我目前最接近哪個風險區？

如果你的日常工作主要是 CRUD、框架拼裝、API glue code、簡單 bugfix，那你應該優先補 AI-supervised Developer 的驗證能力，再往 Product-minded Engineer、Domain Engineer 或小範圍 System Owner 移動。

如果你已經是 Mid-level，但缺少 ownership，你的重點不是換一個新潮稱呼，而是主動接跨模組問題、non-functional requirements、review gate、incident 協作。

如果你是 Senior，你要檢查自己是否真的掌握系統脈絡。若沒有，就該往 System Complexity Owner、AI Workflow Architect 或 Infra / Reliability / Security 的責任面靠近。

第二，我所在的產品或公司，哪種責任最缺？

有些團隊缺 domain understanding，需求常反覆，適合往 Domain Engineer 或 Product-minded Engineer 走。  
有些團隊 codebase 複雜度失控，適合往 System Complexity Owner 走。  
有些團隊正在大量導入 AI agent，卻沒有 review、eval、rollback、權限設計，適合往 AI Workflow Architect 或 Reliability / Security 方向走。  
有些團隊工具鏈破碎，適合從 AI Agent Builder 切入，但要盡快補治理與可重跑能力。

第三，我願意承擔哪一種後果？

定位不是技能標籤，而是責任選擇。

Product-minded Engineer 要承擔需求判斷後果。  
Domain Engineer 要承擔規則理解錯誤的後果。  
System Complexity Owner 要承擔系統長期可維護性的後果。  
Infra / Reliability / Security Engineer 要承擔事故、邊界與風險控制後果。  
AI Workflow Architect 要承擔團隊使用 AI 後的交付品質與治理後果。

如果一個方向看起來很有前途，但你不願承擔它的後果，那它就不是你的定位，只是你的興趣。

## 對讀者的職涯含義

未來工程師不應該只問自己要成為哪一種職稱，而要問自己要承擔哪一種責任。

AI-supervised Developer 會成為基本盤，但不該停在「我會用 AI」。AI Agent Builder 是好的切入點，但純 prompt 與工具拼裝容易被平台吸收。更耐久的方向，通常靠近 System Complexity Owner、Product-minded Engineer、Domain Engineer、Infra / Reliability / Security Engineer，以及能把 AI 納入可靠流程的 AI Workflow Architect。

對多數工程師來說，最務實的策略是選一個深技術面向，再選一個高階問題定義面向。這能讓你既不脫離工程現場，也不被困在低責任實作層。

未來不缺能讓 AI 寫 code 的人。比較稀缺的是能定義正確問題、約束 AI 行為、驗證產出品質、控制系統複雜度、承擔生產風險的人。你的定位，應該往這些責任靠近。
