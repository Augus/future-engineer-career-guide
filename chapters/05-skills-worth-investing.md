# 第 5 章：真正值得投資的能力

**未來工程師最值得投資的，不是更快把程式碼打出來，而是能定義問題、驗證結果、控制風險、理解系統，並對 AI 放大的後果負責。**

AI coding 讓「把需求翻成程式碼」這件事變快，也讓很多工程師的工作看起來更有效率。但真正的變化不只是速度提高，而是任務被重新分層：低風險、低脈絡、可模板化的實作會被壓縮；高風險、高脈絡、需要判斷與承擔的工作會上移。

這一章要回答的是：在這樣的變化裡，工程師應該投資哪些能力？哪些能力只是短期紅利？哪些能力雖然也會被 AI 輔助，但不容易被商品化？

答案不是「放棄 coding」。coding fluency 仍然是工程師的基本讀寫能力。沒有足夠的程式閱讀與實作能力，你無法有效 review AI 產出的 code，也無法判斷它在什麼地方偷換假設、破壞 invariant、製造未來維護成本。真正的問題是，coding fluency 會越來越像基本門檻，而不是長期差異化來源。

## 能力投資的判斷標準

一個能力值不值得長期投資，可以用四個問題檢查。

第一，它是否需要深度脈絡？如果一項任務只需要局部檔案、常見框架慣例與明確輸入，AI 很容易壓縮它。相反地，如果任務需要理解歷史債務、團隊能力、資料流、故障模式與業務約束，它就不容易完全平台化。

第二，它是否牽涉錯誤成本？錯了可以直接重產的東西，會快速商品化。錯了會造成事故、資安風險、資料不一致、營收損失或長期維護困難的東西，需要人類 owner 負責。

第三，它是否需要跨邊界推理？單一函式、單一 ticket、單一錯誤訊息都容易被工具處理；跨服務、跨團隊、跨時間尺度的因果推理，仍然需要工程師掌握。

第四，它是否會隨著 AI 使用增加而更重要？有些能力不是被 AI 取代，而是因為 AI 產出更多 code、更多變更、更多隱含假設而變得更重要。debugging、code review、testing strategy、observability、reliability、security、eval design 都屬於這一類。

## 技能投資表

下表把能力分成投資優先級。它不是要你一次把所有能力練滿，而是幫你判斷：哪些能力只需要維持基本熟練，哪些能力值得成為你的護城河。

| 能力 | AI 壓縮風險 | 未來 1-3 年變化 | 3-10 年價值 | 建議投入 | 投資重點 |
|---|---:|---|---|---:|---|
| Coding fluency | 中 | 仍是必要門檻，但差異化下降 | 必要但不稀缺 | 中 | 保持閱讀、修改、驗證能力，不以產碼速度作為唯一指標 |
| Framework familiarity | 高 | 常見用法與樣板快速商品化 | 多數成為工具知識 | 低中 | 熟悉主流框架即可，把深度轉向架構、狀態與錯誤邊界 |
| CRUD implementation | 很高 | 明顯被壓縮 | 幾乎沒有長期護城河 | 低 | 不把職涯押在 routine implementation |
| Debugging / root cause analysis | 中 | 明顯升值 | 長期高價 | 很高 | 從症狀追到真因，能跨服務、資料、部署與時間線分析 |
| Code review | 中 | 從 style review 轉向風險治理 | 形式改變但仍重要 | 很高 | 審核 invariant、可維護性、資料邊界、rollback 與長期成本 |
| System design | 中 | 升值，但常見草案會被輔助 | 仍重要 | 很高 | 把模糊需求轉成可演化、可觀測、可回復的系統方案 |
| Architecture trade-off | 中 | 升值 | 長期高價 | 很高 | 在成本、風險、團隊能力、遷移路徑間做可辯護決策 |
| Reliability | 低中 | 升值 | 升值 | 很高 | SLO、錯誤預算、incident response、failure mode、降級策略 |
| Observability | 低 | 升值 | 升值 | 很高 | 讓系統在失敗時可追蹤、可解釋、可定位 |
| Security | 低中 | 升值 | 升值 | 很高 | 權限、資料邊界、供應鏈、威脅模型、AI 產碼風險 |
| Testing strategy | 中 | 生成測試折舊，策略升值 | 長期重要 | 很高 | 測什麼、在哪一層測、如何避免假安全感 |
| Eval design | 低中 | 明顯升值 | 長期高價 | 很高 | 為 AI workflow 建立可重現、可比較、可審核的品質標準 |
| Domain modeling | 低中 | 升值 | 升值 | 很高 | 把業務規則、狀態、例外與名詞邊界建模清楚 |
| Requirements clarification | 低中 | 升值 | 升值 | 很高 | 在實作前找出不完整、矛盾、不可驗證的需求 |
| Prompt / context engineering | 高 | 有短期紅利 | 多數平台化，只剩困難場景 | 中低 | 作為工作效率技能，不作為長期職涯核心 |
| Technical debt judgment | 低 | 升值 | 升值 | 很高 | 判斷哪些債可留、哪些必須清、何時清、如何不讓 AI 放大爛債 |
| Codebase ownership | 低 | 升值 | 升值 | 很高 | 對模組演進、邊界、品質與團隊傳承負責 |

這張表背後的共同邏輯是：越接近「可局部生成」的能力，越容易折舊；越接近「跨邊界判斷、風險承擔、系統演進」的能力，越值得投資。

## Debugging：從修錯誤升級成因果推理

Debugging 在 AI coding 時代會升值，原因很直接：code 產出速度變快，變更量增加，錯誤也會以更快速度進入系統。AI 可以幫你讀 stack trace、猜測常見錯誤、列出可能原因，但這不等於它已經找到 root cause。

真正有價值的 debugging 不只是把錯誤修掉，而是回答五個問題：

1. 這個錯誤第一次出現在哪個時間點？
2. 哪個變更讓系統狀態從正常變成異常？
3. 錯誤是在程式邏輯、資料狀態、外部依賴、部署環境，還是需求假設？
4. 修補方案是否只處理症狀，還是消除了導致錯誤的條件？
5. 這次錯誤是否揭露了測試、監控、review 或 ownership 的缺口？

很多工程師以為自己在 debug，其實只是在嘗試修補。AI 會讓這種嘗試更快，但也可能讓人更快地堆出錯誤假設。未來有價值的工程師，要能建立時間線、縮小搜尋空間、排除不可能原因，並把問題回推到系統設計或流程缺口。

你可以用三種練習強化 debugging。

第一，為每個真 bug 寫 root cause memo。不要只寫「修了什麼」，而要寫「為什麼原本的系統允許這個錯誤發生」。memo 至少包含：症狀、影響範圍、觸發條件、根因、修復方案、防止重發的改進。

第二，練習不用 AI 先說明 bug。你可以使用 AI 協助查找，但在接受建議前，先用自己的話描述目前假設。這能避免你被 AI 的第一個合理敘事帶走。

第三，刻意處理跨邊界錯誤。不要只修單一函式的錯誤；要練習處理資料庫查詢、cache、queue、外部 API、部署設定、concurrency、permission 相關問題。這些問題更接近未來高價 debugging 的形狀。

## Code review：從挑毛病變成風險治理

AI 會讓 PR 數量增加，也會讓 PR 表面看起來更完整。格式正確、命名合理、測試看似存在，並不代表變更安全。Code review 的價值會從 style 與 syntax 轉向風險治理。

未來的 code review 至少要審四層。

第一層是局部正確性。程式是否符合需求？是否處理邊界條件？是否有明顯 bug？

第二層是 invariant。這個變更是否破壞資料一致性、授權規則、狀態轉換、交易邊界、idempotency、rate limit、隱私假設？

第三層是可維護性。AI 很容易產出局部可跑但結構鬆散的 code。reviewer 要看模組邊界是否變差、重複是否增加、錯誤處理是否分散、未來修改是否變難。

第四層是營運風險。這個變更如何觀測？如何 rollback？失敗時會影響誰？是否需要 feature flag、migration plan、逐步 rollout 或手動補救流程？

如果你的 review 主要停留在命名、格式與「這段可以簡化」，那會快速被工具吸收。真正值得投資的是審核變更背後的假設與後果。AI 可以幫你列 checklist，但它不能替團隊承擔 merge 後的事故。

## System design 與 architecture trade-off：不是畫圖，而是負責取捨

System design 會被 AI 輔助。常見架構圖、設計文件初稿、模式比較、資料流程草案，都會越來越容易生成。這不代表 system design 不重要，而是把價值從「能產出設計文件」推向「能做有約束的取捨」。

真實架構決策通常不是在理想條件下選最佳解，而是在不完整資訊下選擇可承擔的解。你要同時處理：

- 現有系統的限制
- 團隊能力與維運成本
- 資料一致性與延遲需求
- 安全與合規要求
- 可觀測性與故障恢復
- 遷移路徑與 rollback 可能性
- 未來需求變化下的 optionality

架構能力的核心不是知道更多 pattern，而是知道某個 pattern 在你的情境下會帶來什麼代價。微服務、event-driven、CQRS、serverless、monolith、edge computing、LLM agent workflow 都不是價值本身。價值在於你能說清楚：為什麼這次選它、放棄什麼、何時會後悔、如何偵測它已經不適合。

一個成熟的 architecture trade-off 應該包含：

| 問題 | 好答案應該包含 |
|---|---|
| 我們在解什麼問題？ | 明確需求、非目標、成功指標、失敗成本 |
| 有哪些可行選項？ | 至少兩到三個方案，包含保守方案 |
| 每個方案的代價是什麼？ | 成本、複雜度、維運負擔、資料風險、團隊學習成本 |
| 決策依據是什麼？ | 可觀測證據、約束條件、業務優先級 |
| 如何驗證？ | 測試、load test、eval、pilot、觀測指標 |
| 如何撤退？ | rollback、migration reversal、feature flag、資料補救 |
| 誰負責？ | owner、reviewer、on-call、escalation path |

AI 可以產生比較表，但工程師必須知道比較表是否抓到真正的約束。

## Reliability 與 observability：速度越快，穩定性越不能靠運氣

當變更速度提高，系統穩定性不能只靠「工程師小心一點」。Reliability 會升值，因為 AI 產碼並不自動理解生產環境的故障模式。Observability 會升值，因為當系統出錯時，團隊需要知道發生了什麼，而不是在一堆看似合理的 AI 猜測中選一個。

Reliability 的投資重點包括：

- 為核心流程定義 SLO，而不是只看平均 uptime。
- 為高風險變更設計 rollback 與降級策略。
- 為常見 failure mode 建立 runbook。
- 用錯誤預算討論速度與穩定性的取捨。
- 在 incident 後做真正的系統性修正，而不是只補一行判斷式。

Observability 的投資重點包括：

- 讓 log、metrics、traces 對應到使用者行為與業務流程。
- 為關鍵狀態轉換留下可追蹤紀錄。
- 讓錯誤能被定位到服務、版本、資料條件與外部依賴。
- 避免只建立漂亮 dashboard，卻無法回答 incident 當下最重要的問題。

未來工程師不能只問「這段 code 會不會跑」。更重要的是：它壞掉時，我們多久會知道？誰會被通知？如何縮小影響？如何判斷恢復？如何避免下次重演？

## Security：AI 讓風險更容易被複製

Security 不是只屬於資安團隊。當 AI 能快速產出整段功能、設定、CI 腳本、依賴更新與基礎設施程式碼，權限錯誤、資料外洩、供應鏈風險與不安全預設也會被更快複製。

一般工程師至少要投資幾個資安基本面：

- 授權與認證的差異，特別是 object-level authorization。
- 資料分類、敏感資料處理、log 中不可出現的內容。
- secret management，不把 token、key、credential 暴露到 code、prompt 或工具輸出。
- dependency 與 supply chain risk。
- injection、XSS、CSRF、SSRF、deserialization、path traversal 等常見攻擊面。
- AI agent 使用工具時的權限邊界與審批流程。

Security 的長期價值來自「知道哪些錯誤不能被允許進入系統」。AI 可以幫你掃描與建議，但它不會自動知道你的資料分級、合規要求與組織風險承受度。

## Testing 與 eval design：從寫測試升級成設計驗證系統

AI 會讓寫測試變容易，尤其是單元測試骨架、常見 case、mock、fixture、測試資料生成。這部分能力會折舊。但 testing strategy 會升值，因為問題變成：測試是否真的驗證了該驗證的東西？

有價值的 testing 能回答：

- 哪些邏輯需要 unit test？
- 哪些流程需要 integration test？
- 哪些行為必須用 end-to-end test 才能保護？
- 哪些風險更適合用 contract test、property-based test、load test 或 chaos test？
- 哪些測試只是為了覆蓋率，沒有真正降低風險？
- AI 生成的測試是否只是重述 implementation，而不是驗證 requirement？

在 AI-native workflow 裡，eval design 會變成新的核心能力。當你把 agent 接上工具、資料庫、搜尋、內部 API 或程式碼修改權限時，不能只問「它能不能跑一次」。你要能設計 eval harness，持續量測它在不同案例下的成功率、錯誤類型、成本、延遲、可復現性與人工介入需求。

Eval design 至少要包含：

| 面向 | 問題 |
|---|---|
| 任務定義 | 成功與失敗如何判定？是否有明確 acceptance criteria？ |
| 測試集 | 是否包含常見案例、邊界案例、惡意輸入與真實失敗案例？ |
| 評分方式 | 是規則評分、人工評分、模型輔助評分，還是混合？ |
| 可復現性 | 同一輸入多次執行是否能比較？版本與上下文是否可追蹤？ |
| 風險控制 | 失敗時是否會造成資料、權限、生產環境或使用者傷害？ |
| 成本與延遲 | 成功率是否值得成本？是否會拖慢關鍵流程？ |
| 人機分工 | 哪些情況必須升級給人類？誰批准？如何記錄？ |

未來的測試能力，不只是寫更多測試，而是把驗證設計成系統。

## Domain modeling 與 requirements clarification：不讓錯誤需求被高速放大

AI 很擅長補空白。這也是危險之處。當需求模糊時，AI 會根據常見模式產出合理但未必正確的方案。如果工程師沒有釐清需求與 domain 的能力，錯誤方向會被更快實作、更快包裝成完整 PR、更快進入 review。

Requirements clarification 的價值在於把模糊語句拆成可驗證條件。例如：

- 「使用者可以取消訂單」要拆成：哪些狀態可取消？付款已完成怎麼辦？部分出貨怎麼辦？取消後庫存、折扣、退款、通知如何處理？
- 「系統要支援多租戶」要拆成：資料隔離、權限模型、billing、quota、audit log、跨 tenant 管理、測試策略。
- 「新增 AI 客服」要拆成：可回答範圍、資料來源、拒答規則、人工轉接、錯誤責任、eval、監控與資料保留。

Domain modeling 的價值在於建立正確名詞、狀態、關係與約束。很多長期 bug 不是語法錯，而是模型錯。工程師把「訂單」、「付款」、「出貨」、「退款」、「發票」混成一個流程；把「使用者」、「帳號」、「成員」、「租戶」、「角色」混成一個概念；把「狀態」當成字串，而不是受約束的轉換。

AI 可以幫你畫狀態圖，但你要知道狀態圖是否符合真實業務。AI 可以幫你列 edge cases，但你要知道哪些 edge cases 真的會發生，哪些會造成重大損失。

## Prompt / context engineering：有短期價值，但不是長期護城河

Prompt engineering 與 context engineering 有實際價值。短期內，會拆任務、會提供相關檔案、會寫清楚 acceptance criteria、會要求 AI 自我檢查、會限制輸出格式的人，確實會比只丟一句需求的人更有效率。

但它不足以成為長期護城河，原因有三個。

第一，平台會吸收常見技巧。今天需要手動指定的 prompt pattern，明天可能變成 IDE、agent、repo assistant 或 workflow tool 的預設行為。

第二，prompt 技巧本身不保證判斷正確。你可以把 AI 指揮得很順，但如果需求錯、測試錯、架構取捨錯、風險理解錯，產出只會更快偏離正確方向。

第三，prompt/context engineering 的價值依賴你本來懂什麼。真正有效的 context 不是把大量檔案塞進模型，而是知道哪些上下文重要、哪些不重要、哪些假設必須明講、哪些輸出需要驗證。

因此，prompt/context engineering 應該被看成工作效率技能，而不是職涯核心定位。它像是會用 debugger、會查文件、會寫 shell script：有用，應該學，但不能把自己定義成只會操作工具的人。

更耐久的投資方式是：把 prompt/context 技巧綁到高階能力上。

- 用它加速 requirements clarification，但你要負責判斷需求是否完整。
- 用它產生 architecture options，但你要負責 trade-off。
- 用它產生測試案例，但你要負責測試策略。
- 用它輔助 code review，但你要負責 merge 風險。
- 用它整理 incident 資料，但你要負責 root cause 與後續改進。

## 一深一高：大多數產品工程師的最佳配置

對一般 Web、SaaS、App 工程師來說，最務實的能力配置不是追求每個底層領域都成為專家，也不是只做產品泛用型人才。更合理的方向是「一個難取代的技術深區，加上一個難外包的問題定義能力」。

技術深區可以是：

- Reliability / observability
- Security
- Performance
- Data systems
- Frontend state complexity
- Mobile runtime
- Platform engineering
- Distributed systems
- AI workflow / eval infrastructure

問題定義能力可以是：

- Domain modeling
- Requirements clarification
- Acceptance criteria design
- Technical trade-off
- Cross-functional planning
- Risk analysis
- User-centric workflow design

「一深一高」的重點是，你既能處理抽象問題，也能在至少一個技術深水區真正負責。只懂高層概念，容易變成空泛協調者；只懂局部技術，容易被壓在可替代的實作層。未來更穩定的位置，是能把問題定義、系統約束與工程落地連起來。

## 對讀者的職涯含義

如果你的價值主要來自「我比別人更快寫出常見功能」，那 AI 會直接壓縮你的差異化。如果你的價值來自「我能判斷該不該做、怎麼驗證、哪裡會壞、壞了誰負責、如何讓系統長期更簡單」，AI 反而會放大你的影響力。

下一階段的職涯投資，不是把 prompt 背得更熟，而是把自己訓練成能負責複雜度的人。你仍然要會寫 code，但更要會 debug、review、設計、驗證、觀測、保護、建模、釐清需求，並在不確定下做出可承擔的工程決策。

