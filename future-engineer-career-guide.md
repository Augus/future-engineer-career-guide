# 未來工程師職業指南

## 在 Agentic Coding 時代，如何定位、轉型與保持價值

## 目錄

1. 前言：不要把自己訓練成 AI 的打字員
2. AI Coding 正在壓縮哪一種工程工作
3. 工程師價值的轉移
4. 誰最危險，誰會升值
5. 未來工程師的七種定位
6. 真正值得投資的能力
7. 分層訓練路線圖
8. 殘酷自我檢查清單
9. 工程師的 AI 使用守則
10. 團隊與組織會怎麼變
11. 結語：從會寫，升級到會定義、會驗證、會治理
12. 附錄：研究來源與不確定性

---

# 前言：不要把自己訓練成 AI 的打字員

這本書的主張很直接：未來被壓縮的不是「工程師」這個職稱，而是把工程工作縮減成接需求、產 code、交 PR 的那一種工作方式。

## 這本書為什麼存在

過去幾年，工程師對 AI coding 的討論很容易落入兩種極端。

一種說法是：「AI 會取代工程師。」這個說法太粗糙。它把工程工作看成單一活動，好像工程師每天只是在螢幕前把需求翻譯成程式碼。只要模型會寫程式，工程師就沒有位置。

另一種說法是：「AI 只是工具，工程師不用擔心。」這個說法也太輕。它低估了工具演進的速度，也低估了日常工程工作中有多少部分其實是標準化、可描述、可局部驗證、失敗成本不高的任務。這些任務一旦被 agentic coding workflow 吸收，職涯市場不會因為你仍然懂語法就自動保護你。

這本書不是要製造恐慌，也不是要安慰你。它要回答一個更精確的問題：在 agentic coding 時代，哪一種工程工作會被壓縮，哪一種工程能力會升值，而個人工程師應該如何重新定位自己。

這個問題值得寫成一本完整的職業指南，而不是幾篇工具教學。因為 AI coding 的影響不只發生在編輯器裡。它會改變任務分配、code review、測試策略、系統 ownership、事故責任、Junior 的練功路徑、Mid-level 的市場價值，以及 Tech Lead 對團隊流程的設計方式。

如果你只把它理解成「補全更快」或「prompt 寫得更好」，你會錯過真正重要的變化：任務被壓縮，責任上移。

## 你真正面對的問題

工程師真正要問的，不是 AI 是否會取代工程師，而是哪一種工程工作會被 AI 壓縮。

目前最容易被壓縮的工作有共同特徵：

- 需求可以被清楚描述。
- 修改邊界相對明確。
- 可用測試、lint、型別檢查或人工 review 快速驗證。
- 失敗成本低，出錯後容易回退或重做。
- 主要價值來自執行，而不是判斷。

這類工作包括 CRUD、樣板碼、文件整理、測試骨架、基礎重構、簡單 bugfix，以及把清楚的 issue 變成初版 patch。這些工作不會一夜消失，但會逐步變便宜、變快、變得更像工具平台提供的標準能力。

這裡要小心一個常見誤解：說某些任務被壓縮，不等於說那些任務完全沒有價值。工程師仍然需要懂 code，仍然需要能讀 code、改 code、debug code，也仍然需要在必要時自己動手寫。差別在於，單純「我能把需求寫成程式」不再足以構成穩定護城河。

當產碼變快，真正昂貴的地方會移到其他環節：需求是否正確、修改是否安全、測試是否覆蓋真正風險、架構是否留下可演進空間、事故發生時誰能判斷與承擔、六個月後這段 code 是否仍然能被團隊理解。

也就是說，問題不是「AI 會不會寫 code」。問題是：當 AI 能更快寫出更多 code，你是否有能力讓這些 code 不把系統變得更脆弱、更難維護、更難治理。

## 本書的核心結論

本書的核心結論是：

不要把自己訓練成 AI 的打字員；要把自己訓練成定義、驗證、治理、承擔與簡化的人。

「AI 的打字員」不是指使用 AI 的人。未來幾乎所有工程師都會使用 AI。這裡指的是一種危險的工作方式：你把模糊需求丟給工具，接受工具產出的 patch，做一點表面修補，然後把責任推給「AI 這樣寫」。你能讓 code 出現，但說不清楚它為什麼是對的；你能讓測試變綠，但不知道測試是否驗證了真正的風險；你能 merge，但不知道出事時該看哪裡。

這種工程師會被壓縮。

未來更有價值的工程師，會把 AI 當成產能放大器，但不把判斷外包給 AI。他能定義問題，讓任務邊界清楚；能設計 acceptance criteria，讓結果可以被驗證；能治理 AI 輸出，辨認局部正確但系統上危險的改動；能承擔 production 後果，不把 merge 當作任務結束；能簡化系統，避免更快的產碼速度累積出更快的技術債。

這不是抽象的職涯建議，而是來自目前 AI coding 演進方向的直接推論。AI 工具已經從 autocomplete、chat assistant，走到 agent mode、repo-level coding agent、背景產 PR、工具調用、多 agent workflow。工具越能處理局部任務，人類越需要處理邊界、驗證、風險、治理與責任。

## 什麼是「未來工程師」

本書所說的「未來工程師」，不是某個新職稱，也不是只會做 AI agent 的工程師。

未來工程師是一種能力組合：

- 他仍然懂實作，但不把價值停在實作。
- 他能把模糊需求翻譯成可驗證的技術方案。
- 他能設計測試、eval、observability、rollback 與 review gate。
- 他知道哪些任務可以交給 AI，哪些必須由人類 owner 決策。
- 他能看見資料流、狀態流、錯誤邊界、權限邊界與 failure mode。
- 他能在 AI 產碼量上升時，控制系統複雜度與失敗半徑。

這種人可能是 Senior engineer、Tech Lead、SRE、平台工程師、資安工程師、產品工程師、domain engineer，也可能是仍在成長中的 Junior。它不是年資，而是責任結構。

相反地，一個只會操作工具、只會把 ticket 轉成 patch、只會在 AI 給出答案後做表面確認的人，即使職稱是 Mid-level 或 Senior，也會越來越危險。

## 本書如何使用研究材料

本書基於同一份研究報告整理而成，但不會把研究報告逐段搬進來。研究報告提供的是判斷基礎：AI coding 工具在 bounded tasks 上已經有明顯速度收益；但速度收益不等於團隊 delivery、stability、maintainability 會自動改善；DORA、實驗研究、官方 agent 文件與實務專家觀點都指向同一條主線：AI 會放大既有流程。

流程好、測試好、架構邊界清楚、feedback loop 快、review 有品質的團隊，會被 AI 放大。流程混亂、品質門檻低、測試薄弱、系統耦合重、ownership 不清的團隊，也會被 AI 放大，只是放大的是問題。

因此，本書不會把 AI 描述成魔法，也不會把工程師描述成注定被淘汰的一群。比較準確的說法是：AI 正在重新定價工程工作。它降低某些任務的執行成本，也提高了人類對方向、驗證與後果的責任。

後面的章節會依序回答幾個問題：

- AI coding 正在壓縮哪些工作？
- 工程師價值為什麼從產碼轉向定義、驗證與治理？
- Junior、Mid-level、Senior、Tech Lead 的風險分化是什麼？
- 未來工程師有哪些可選定位？
- 哪些能力值得投資，哪些只是短期紅利？
- 不同層級的工程師接下來三到十二個月該怎麼訓練？
- 團隊應該如何重設 AI-assisted SDLC？

這些問題的答案不會是「所有人都去做 AI」。更務實的答案是：每個工程師都要決定自己的「一深一高」組合。一個難取代的技術深區，加上一個難外包的問題定義能力。

## 對讀者的職涯含義

對讀者而言，這本書的第一個要求是停止用職稱安慰自己。Junior 不一定完蛋，Senior 也不一定安全；真正的分界在於你是否能對問題、系統與 production 後果負責。

第二個要求是停止把 AI 使用能力等同於職涯護城河。會用工具是基本門檻，不是長期優勢。長期優勢來自你能否定義正確問題、驗證 AI 輸出、治理風險、承擔事故、簡化系統。

第三個要求是把自己的工作從「完成 ticket」重新理解成「控制變更」。未來工程師的價值，不是讓更多 code 被寫出來，而是讓更多變更在正確邊界內、安全地進入系統，並且在出錯時有人知道如何處理。


---

# 第 1 章：AI Coding 正在壓縮哪一種工程工作

AI coding 的核心變化不是工程師消失，而是可描述、可局部驗證、低失敗成本的工程任務正在被快速壓縮。

## 從 autocomplete 到 repo-level coding agent

最早進入日常開發流程的 AI coding 工具，主要是 autocomplete。它在你打字時補出下一行、下一段、下一個函式。這一階段壓縮的是語法記憶、樣板碼、簡單 glue code，以及部分「我知道要寫什麼，只是懶得手打」的工作。

接著是 chat-based assistant。工程師開始把 API 使用方式、錯誤訊息、測試範例、重構想法丟給模型，讓它解釋、摘要、生成初稿。這一階段壓縮的是搜尋、文件閱讀、簡單問答、一次性產碼與局部修改。它的價值很依賴上下文品質：你給的問題越清楚，它越可能幫你省時間；你給的問題越模糊，它越可能替你補出一個看似合理但方向錯誤的答案。

再往後是 agentic IDE。工具不只回答問題，而是能在 repo 裡讀檔、改檔、跑測試、根據失敗訊息修正，再提出一個 patch。這裡壓縮的已經不是單行或單函式，而是小功能、簡單 bugfix、初版重構、測試補齊與機械式 review iteration。

repo-level coding agent 把這件事再推遠一步。任務可以從 issue 開始，由 agent 分析 codebase、規劃修改、跨檔編輯、執行指令、跑測試，最後開出 draft PR 等人 review。這種工作流不代表 agent 已經理解整個業務與系統責任，但它代表「清楚 issue 到初版 PR」這段流程正在平台化。

multi-agent workflow 則把任務拆成多個代理：有的讀文件，有的改 code，有的寫測試，有的整理結果，有的做 review。再加上 CI/CD integrated agent，低階品質門檻、lint 修補、測試修補、根據 reviewer comment 做機械調整，都可能被更多自動化吸收。

這條演進線可以用一句話概括：AI coding 工具正在從「幫你打字」走向「幫你完成有邊界的工程任務」。

但這句話的重點是「有邊界」。邊界越清楚、驗證越便宜、失敗成本越低，AI 壓縮越快。邊界越模糊、驗證越困難、後果越重，人的責任越難消失。

## 最先被商品化的任務

最暴露的任務不是所有 coding，而是 routine coding。這些任務的共同點是輸入明確、輸出可檢查、風險局部化。

### CRUD 與常見資料流程

CRUD 任務通常有明確模式：新增欄位、加 endpoint、接資料庫、處理表單、回傳狀態、補上基本錯誤處理。這類任務不是毫無價值，但許多部分高度重複。當 codebase 有固定架構、命名習慣、測試範例與既有 endpoint 可參照，AI 很容易生成初稿。

真正的風險不在於它會不會產生一個可跑的 CRUD，而在於它是否理解資料一致性、權限邊界、隱私限制、錯誤處理與日後演進。也因此，CRUD 的「打字部分」會被壓縮，但 CRUD 所在系統的設計與風險判斷不會因此消失。

### 樣板碼與機械式 glue code

樣板碼是 AI 最容易吸收的區域。設定檔、常見 adapter、資料轉換、型別定義、簡單 client wrapper、重複 UI state wiring，都屬於這類工作。

這不代表工程師不用懂它們。相反地，工程師更需要能快速看懂 AI 產出的樣板是否符合專案慣例。當樣板碼產生速度上升，review 的重點會從「這段是不是你親手寫的」轉向「這段是否符合系統邊界，是否引入隱性耦合」。

### 測試骨架

AI 很適合產生測試骨架：建立 test file、補 mock、列出常見 case、填入 happy path、整理 assertion。這些工作過去很耗時間，現在可以變快。

但測試骨架不是驗證能力本身。AI 可以寫很多測試，卻不保證測到真正重要的風險。它可能測實作細節，不測行為契約；可能補齊覆蓋率，卻沒有覆蓋邊界條件；可能讓測試變綠，卻沒有證明產品需求被滿足。

因此，測試的機械生成會被壓縮，但測試策略會升值。

### 文件整理

文件摘要、API 說明、變更紀錄、README 初稿、migration note、PR 描述，都是 AI 擅長處理的工作。這類任務通常依賴現有上下文，且結果可由人快速掃過。

問題是，文件整理不等於知識治理。AI 可以把現有內容變得更流暢，但如果原始資訊錯誤、決策理由缺失、系統真實行為和文件不一致，它也可能把錯誤整理得更像真的。未來更重要的不是誰能寫出漂亮文件，而是誰能確保文件和系統事實一致。

### 簡單 bugfix

明確錯誤訊息、可重現步驟、單一模組內的錯誤、測試能穩定重現的 bug，會越來越適合交給 AI 產生候選修法。這包括 null check、型別錯誤、簡單 off-by-one、已知 API misuse、缺少錯誤處理等。

但 bugfix 的難度不在表面修改，而在 root cause。AI 可能修 symptom，不修原因；可能讓當前測試通過，卻破壞另一條流程；可能用 brute force 繞過問題，使系統更難理解。這也是為什麼 debugging 能力不會因為 AI 會提出修法而貶值，反而會因為候選修法變多而更重要。

### Bounded refactor

局部重命名、抽函式、移檔、拆小模組、替換已知 API、依照既有 pattern 改寫，都是 bounded refactor。只要範圍清楚、測試足夠、回退容易，AI 能節省大量時間。

但 refactor 的核心不是「把 code 變不一樣」，而是「在不改變外部行為的前提下改善結構」。如果沒有測試、沒有行為契約、沒有清楚模組邊界，AI 可能製造出一個看似更乾淨、實際更危險的版本。

## 為什麼「會寫 code」仍必要，但不再足夠

有些人聽到 routine coding 被壓縮，就推論工程師不需要會寫 code。這是錯誤結論。

你仍然需要會寫 code，因為你需要讀懂 AI 的輸出。你需要知道哪些地方違反專案慣例，哪些地方有 race condition，哪些地方錯用了資料模型，哪些地方破壞權限邊界，哪些地方只是讓測試看起來通過。

你仍然需要會寫 code，因為關鍵時刻你不能只會要求 AI 重試。當 production incident 發生、上下文不完整、系統行為和文件不一致、工具給出的答案互相矛盾時，你要能回到程式、log、trace、資料與狀態流，判斷真正發生了什麼。

你仍然需要會寫 code，因為 AI 生成的 patch 需要 owner。PR 被 merge 進系統後，責任不會留在模型身上。責任會回到按下 merge 的人、review 的人、擁有系統的人。

真正改變的是：會寫 code 從「主要價值」變成「基本能力」。就像會打字不再讓你成為作家，會產碼本身也不再足以讓你成為高價值工程師。你要能說清楚為什麼這段 code 應該存在、它滿足什麼需求、風險在哪裡、如何驗證、出事如何回退、未來誰維護。

## Bounded tasks 的速度收益，不等於 delivery 自動變好

研究材料裡最重要的 nuance 是：AI 對 bounded tasks 有速度提升，但這不等於 AI 已經穩定接管 software engineering，也不等於團隊 delivery 或 stability 會自動改善。

多項實驗和企業研究都觀察到 AI coding 工具能提升特定任務速度，例如完成清楚的程式題、產生初版 patch、提高 PR throughput、加快文件與 review 相關流程。這些結果足以支持一個判斷：routine coding 會被壓縮，而且壓縮會先發生在一到三年的近端時間尺度。

但反方證據同樣重要。研究也觀察到，在熟悉大型 repo 的資深開發者、複雜任務、隱含需求、多步驟修改、品質門檻較高的場景中，AI 不一定讓任務更快，甚至可能讓完成時間變慢。DORA 的研究也提醒，AI 對個人 productivity、flow、文件品質與 code review 速度有幫助，但 stability 的負向關係仍是必須嚴肅面對的訊號。

原因很簡單：軟體交付不是只有產碼。

一個功能從想法到 production，中間包含需求澄清、方案取捨、資料設計、權限設計、實作、測試、review、部署、監控、rollback、事故處理、後續維護。AI 如果只加速其中的產碼環節，卻讓 review 壓力上升、測試品質不足、架構耦合變重、錯誤更難追，整體 delivery 未必會變好。

更快產生 code，不等於更快交付價值。更快產生 patch，也不等於更穩定的系統。

## AI 是 amplifier

本章最重要的工程判斷是：AI 是 amplifier。它會放大好流程，也會放大壞流程。

如果一個團隊有清楚的需求寫法、良好的 issue hygiene、穩定 CI、合理測試、明確 ownership、乾淨架構邊界、快速 feedback loop，那麼 AI 會讓這些優點更有用。agent 能讀到清楚上下文，能根據測試修正，能在小邊界內快速迭代，人類 review 也比較容易聚焦在風險。

如果一個團隊需求混亂、測試不足、CI 不穩、review 只是走形式、系統耦合嚴重、沒有明確 owner，AI 也會放大這些問題。它會更快產生更多需要 review 的 patch，更快引入看似合理的錯誤，更快把模糊需求實作成某種東西，更快累積技術債。

這就是為什麼同一個 AI 工具，在不同團隊裡會有完全不同結果。工具能力不是唯一變數。repo hygiene、workflow、品質門檻、驗證成本、任務切分方式、review 能量，都是決定 AI 是否真的提升交付的關鍵。

對個人工程師也一樣。AI 會放大你的優點，也會放大你的盲點。

如果你本來就能拆問題、定義邊界、寫驗收標準、讀測試結果、判斷風險，AI 會讓你更快。如果你本來就不清楚需求、不懂系統、不會驗證、不知道出錯後怎麼追，AI 會讓你更快交出一個你無法負責的東西。

## 如何判斷自己的任務是否正在被壓縮

你可以用以下問題檢查自己日常工作中有多少比例正在被壓縮：

| 問題 | 如果答案是「是」 | 職涯含義 |
|---|---|---|
| 任務是否能用幾句話清楚描述？ | AI 容易產生初稿 | 你的價值不能只停在執行 |
| 修改是否主要侷限在少數檔案？ | agentic IDE 容易處理 | 你需要提高邊界與風險判斷 |
| 是否已有類似範例可模仿？ | 生成品質通常較高 | pattern 識別會商品化 |
| 是否有測試能快速驗證？ | AI 迭代成本低 | 你要能設計更好的測試 |
| 出錯是否容易回退？ | 更適合交給 AI 嘗試 | 你要懂什麼不能輕易嘗試 |
| 任務是否不需要理解業務取捨？ | 執行面更容易被壓縮 | 你要往 problem definition 升級 |
| 任務是否不涉及 production 風險？ | 自動化空間更大 | 你要累積高責任場景經驗 |

這張表不是要你逃離所有 routine work。Junior 仍然需要透過 routine work 學習基本功，Mid-level 也仍然需要處理大量日常工程。但你不能讓自己的市場價值永久綁在這些任務上。

真正危險的不是做過 CRUD、寫過樣板、補過測試，而是工作多年後仍然只能做這些，而且做完後說不清楚系統風險、驗證策略與長期維護成本。

## 這一章的結論

AI coding 的演進不是單點工具升級，而是一條從 autocomplete 到 repo-level agent、多 agent workflow、CI/CD integrated agent 的連續路徑。每往前一步，可標準化、可局部驗證、低風險的工程任務就更容易被吸收。

最暴露的任務包括 CRUD、樣板碼、測試骨架、文件整理、簡單 bugfix、bounded refactor。這些任務會先變便宜、變快、變得更像工具能力。

但這不代表軟體工程被完整自動化。AI 對 bounded tasks 的速度收益是真實的；同時，delivery、stability、maintainability 不會因此自動改善。產碼只是整個工程生命週期的一段，甚至常常不是最慢、最貴、最危險的那一段。

所以本章的重點不是「少寫 code」，而是「不要只靠寫 code 定義自己」。你仍然要會寫，但更要會定義、驗證、治理與承擔。

## 對讀者的職涯含義

如果你的日常價值主要來自把清楚需求快速寫成 code，你需要承認這個區域正在被壓縮。這不表示你沒有未來，但表示你不能把下一階段職涯押在同一種任務上。

你應該開始把自己從 implementer 升級成變更 owner：在接任務時釐清需求，在交給 AI 前定義邊界，在 review 時檢查風險，在 merge 前確認驗證，在上線後理解 production 後果。

AI 會讓能掌控流程的人更強，也會讓只會執行流程的人更容易被商品化。你要站在哪一邊，取決於你是否願意把工作重心從「產出更多 code」移到「控制更高品質的變更」。


---

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


---

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


---

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


---

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



---

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



---

# 第 7 章：殘酷自我檢查清單

如果你在這份清單中大量回答「否」，危險的不是你還不熟 AI 工具，而是你的職涯位置正在被壓縮到更低價值的區域。

這一章不是心理測驗，也不是拿來製造焦慮的清單。它的用途比較接近工程診斷：幫你判斷自己目前到底是在「使用 AI 提高產能」，還是在「把本來該由自己承擔的理解、驗證與責任外包出去」。

AI coding 讓許多任務變快了，但速度不是唯一變數。當產碼、樣板、簡單修 bug、測試骨架、文件初稿都更容易取得時，工程師真正被檢查的地方會上移：你能不能定義問題、看出風險、驗證結果、擁有系統、處理事故，並且在工具輸出看似合理時仍保持工程判斷。

請用「最近三個月的真實工作」回答，而不是用「我理論上知道」回答。

## 使用方式

每題請只回答「是」或「否」。

- 「是」代表你在真實工作中做得到，且能拿出最近例子。
- 「否」代表你做不到、不穩定、需要別人補位，或只有在 AI 提醒後才會想到。
- 如果答案是「有時候」，請先記為「否」。工程能力的風險通常出現在壓力、時間不足、需求模糊、測試不足、production 出事的時候，不是在最理想的情境裡。

你不需要追求全部答「是」。不同職級的責任不同，Junior 不需要假裝自己能做 Architect 的治理判斷。但你需要看見兩件事：

1. 你所在職級的核心題目是否大量答「否」。
2. 你下一個職級的題目是否完全沒有起步。

第二點很重要。AI 時代的升遷不只是「寫更多 code」或「關更多 ticket」。任務被壓縮後，職涯往上走的條件會更接近 owner、reviewer、system thinker、risk controller。你如果只在 AI 旁邊加速完成小任務，卻沒有往這些責任移動，短期看起來變快，長期位置會變脆弱。

## 解讀方式

你可以用很簡單的方式解讀：

| 否的數量 | 初步判讀 | 應採取的動作 |
|---:|---|---|
| 0-4 題 | 目前基礎相對穩定 | 選 2-3 題作為下一季訓練重點，不要停在舒適區 |
| 5-9 題 | 有明顯能力缺口 | 找出缺口屬於理解、驗證、風險、ownership 或 AI workflow 哪一類 |
| 10 題以上 | 職涯位置正在變危險 | 不要只補工具課；要重新安排工作責任、訓練方式與 review 習慣 |
| 15 題以上 | 目前角色可能只剩任務執行價值 | 需要有人協助重建基本工程能力，並減少直接接高風險 AI 產出 |

這個分數不是績效評分。它是在問：如果明天 AI 能更便宜、更快地完成你現在主要做的任務，你還留下什麼不可替代的工程價值？

大量回答「否」時，最常見的誤判是把問題歸因為「我還不會用某個工具」。但很多題目其實跟工具無關：你是否理解 code path、是否知道 failure case、是否能定義 acceptance criteria、是否能看懂 observability、是否知道 rollback、是否能擁有模組。這些才是位置本身。

## Junior 自測：你是否真的在建立工程基本功

Junior 最危險的地方，不是 AI 會取代初階工程師，而是舊的練功路徑被壓縮了。以前你可能透過寫樣板、修小 bug、補測試、讀 code review 慢慢學會系統感；現在 AI 可以快速產出這些表面成果，但不會自動把理解轉移到你身上。

Junior 的核心問題是：你是否還在親手建立「看懂、拆解、驗證、debug」的能力。

請回答：

1. 你能不用 AI，把自己最近一次改動的 code path 從入口講到出口嗎？
2. 你能畫出該功能的資料流嗎？
3. 你知道這段 code 的狀態何時建立、何時失效嗎？
4. 你能說明這個 bug 真正的 root cause，而不是只描述現象嗎？
5. 你知道這個 PR 最重要的三個 failure case 是什麼嗎？
6. 你有親手跑過測試，而不是只相信 AI 或工具摘要說綠燈嗎？
7. 你能解釋自己加的每個 assertion 在防什麼嗎？
8. 你知道這次改動碰到哪些外部依賴嗎？
9. 你能說出這段 code 的 rollback 方式嗎？
10. 你知道 production 上會怎麼觀測這個功能嗎？
11. 你能分辨「能跑」與「可維護」的差別嗎？
12. 你有沒有避免 merge 自己其實講不清楚的 code？
13. 你知道 AI 產出的套件、API 或設定是否真的存在嗎？
14. 你知道哪部分是業務規則，哪部分只是實作細節嗎？
15. 你能把一個 ticket 拆成可驗證的小步驟嗎？
16. 你一週至少有一次手動 debug，而不是全靠聊天視窗嗎？
17. 你會看 log、trace、network panel 或 SQL plan 嗎？
18. 你知道測試通過不等於需求成立嗎？
19. 你能指出這段 AI code 可能在六個月後造成什麼維護麻煩嗎？
20. 你是否開始擁有「模組責任」，而不只是「票單責任」？

### Junior 的解讀

如果你在第 1-7 題大量答「否」，問題是基本理解與驗證能力不足。這代表你可能正在用 AI 跳過學習，而不是加速學習。

如果你在第 8-14 題大量答「否」，問題是你還沒有建立系統邊界感。你可能能完成單點修改，但不知道它跟外部依賴、業務規則、狀態生命週期與 rollback 的關係。

如果你在第 15-20 題大量答「否」，問題是你還停留在 ticket executor。這在早期可以接受，但不能長期停留。AI 會壓縮單純執行票單的價值；你需要開始承擔一小塊模組、一條資料流或一種錯誤類型。

對 Junior 來說，最務實的下一步不是「多學十個 AI 工具」，而是每週保留固定時間做三件事：不用 AI trace 一段 code、親手重現一個 bug、把自己 PR 的 failure case 寫出來。

## Mid-level 自測：你是否已經從 implementer 變成 owner

Mid-level 是 AI 時代最容易被誤判的一層。因為許多中等難度的實作任務、重複性修改、既有模式延伸，AI 都能明顯加速。這會讓人看起來產出變多，但也可能掩蓋一個問題：你是否真的能獨立擁有一個功能、一個模組或一條交付鏈。

Mid-level 的核心問題是：你是否能把模糊需求變成可驗證的技術計畫，並對風險、品質與長期維護負責。

請回答：

1. 你能定義一個功能的 acceptance criteria，而不是只問別人要怎麼做嗎？
2. 你能判斷哪些任務可以交 AI，哪些不行嗎？
3. 你能估計一段改動的 blast radius 嗎？
4. 你能設計最小可回滾方案嗎？
5. 你能指出這個系統最脆弱的邊界在哪裡嗎？
6. 你會避免因為 AI 讓你更快，就放寬品質門檻嗎？
7. 你知道什麼時候應該先補測試再改功能嗎？
8. 你能把模糊需求轉成技術計畫與驗收點嗎？
9. 你能 review AI 產出的 architecture suggestion，而不是照單全收嗎？
10. 你知道自己所在系統的核心 invariants 嗎？
11. 你能帶一個較 Junior 的工程師一起 debug 嗎？
12. 你能解釋為什麼某個技術債現在不該還、某個債一定要還嗎？
13. 你知道什麼是非功能需求，且會主動問嗎？
14. 你能辨識「AI 幫你更快」和「AI 幫你堆更多未來問題」的差別嗎？
15. 你會主動建立 observability，而不是出事再補嗎？
16. 你知道自己的 AI workflow 哪一步最常產生假正確嗎？
17. 你有把 agent 產出的 patch 分級，而不是一視同仁嗎？
18. 你能獨立接手一個模組一季以上嗎？
19. 你能在不新增不必要複雜度的前提下完成需求嗎？
20. 你是否已經從 implementer 變成 owner？

### Mid-level 的解讀

如果你在第 1-5 題大量答「否」，你還沒有真正接住需求定義與風險估計。這會讓你依賴別人把問題切好，再用 AI 加速實作。這種位置會被壓縮。

如果你在第 6-12 題大量答「否」，你的主要缺口在品質判斷與系統維護。AI 可以讓你更快改動，也可以讓你更快引入未來問題。Mid-level 需要能判斷速度是不是正在換取隱性風險。

如果你在第 13-20 題大量答「否」，代表你還沒有成為 owner。owner 不只是把 ticket 做完，而是知道系統有哪些 invariant、哪些地方需要觀測、哪些債可以延後、哪些變更需要 rollback、哪些 AI 產出只能當草稿。

對 Mid-level 來說，下一步應該是主動接一塊可持續負責的範圍。它可以是一個模組、一條資料流、一個 service、一組測試策略或一類 production 問題。你需要累積的是長期 ownership，而不是更多短期產碼量。

## Senior 自測：你是否仍然擁有系統，而不只是擁有年資

Senior 在 AI 時代不會自動安全。年資不是護城河，真正的護城河是複雜度控制、事故判斷、系統簡化、review 品質、可選擇性設計，以及帶領團隊用 AI 而不讓品質失控的能力。

Senior 的核心問題是：當 AI 讓更多人能更快改 code，你是否能讓系統仍然可理解、可驗證、可回滾、可演進。

請回答：

1. 你能在高壓 incident 中快速縮小搜尋空間嗎？
2. 你能定義什麼叫「足夠可靠」嗎？
3. 你能用標準化流程，而不是個人英雄主義，帶團隊使用 AI 嗎？
4. 你能看出 AI code 哪裡「方向對但做法差」嗎？
5. 你能判斷某個 refactor 會不會破壞未來 optionality 嗎？
6. 你能讓別人接手你的系統而不失速嗎？
7. 你能把問題簡化，而不是只把複雜度藏起來嗎？
8. 你會拒絕高風險 vibe coding 嗎？
9. 你能分辨工具升級和工作方法升級的差異嗎？
10. 你能設計人機協作的 approval gate 嗎？
11. 你能判斷現階段該用單 agent 還是多 agent 嗎？
12. 你會要求 eval，而不是只看 demo 成功嗎？
13. 你能指出 agent failure 是模型、上下文、工具還是流程造成的嗎？
14. 你會把 AI 當成不可靠但有力的 subsystem，而不是全能同事嗎？
15. 你能把複雜需求拆成可平行處理的任務，但仍維持一致性嗎？
16. 你知道何時應該人工起草，而不是讓 AI 先寫嗎？
17. 你是否仍保有親手 trace、profiling、讀 source 的能力？
18. 你有沒有建立量測 AI 真的帶來何種改善，而非只靠感覺？
19. 你是否能把 AI 導入後的品質成本算進來？
20. 你是否真正擁有 codebase，而不是只有影響力？

### Senior 的解讀

如果你在第 1-7 題大量答「否」，代表你的 seniority 可能還停在經驗累積，而不是系統判斷。真正的 Senior 需要能在混亂中找出關鍵路徑，並把複雜問題變得可處理。

如果你在第 8-14 題大量答「否」，你對 AI workflow 的風險控制不足。Senior 不能只鼓勵大家使用工具；你必須能設計 gate、辨識 agent failure、要求 eval，並知道何時不該讓 AI 先寫。

如果你在第 15-20 題大量答「否」，代表你可能在 AI 導入後失去對 codebase 的真實掌握。這很危險。當產出速度上升，Senior 的責任不是跟著產出更多 patch，而是確保系統沒有在更高速度下累積不可見的複雜度。

對 Senior 來說，下一步不是把自己變成最會下 prompt 的人，而是把團隊的 AI 使用變成可審核、可量測、可回滾的工程流程。

## Tech Lead / Architect 自測：你是否能把判斷變成治理

Tech Lead 和 Architect 的責任在 AI-assisted development 中會變得更重。因為團隊變快時，系統風險不會自動下降；很多時候，風險只是更快、更分散、更難追蹤。

這一層的核心問題是：你是否能把架構判斷、風險分級、ownership、review、rollback、observability 與 escalation path 變成團隊可執行的 guardrail。

請回答：

1. 你能明確定義哪些系統不允許 agent 直接改嗎？
2. 你能為 AI-assisted development 設計風險分級嗎？
3. 你能說明團隊目前最大的交付瓶頸是不是寫 code 嗎？
4. 你知道哪些流程應該先自動化，哪些應該先治理嗎？
5. 你能讓設計、需求、測試、觀測形成閉環嗎？
6. 你能用一張圖講清楚系統資料流、控制流與責任邊界嗎？
7. 你能把架構判斷變成可執行的 guardrail 嗎？
8. 你會要求每個高風險變更都有 rollback 與 owner 嗎？
9. 你能檢查 agent workflow 是否創造了新的單點故障嗎？
10. 你能處理「團隊變快但系統更不穩」這種矛盾嗎？
11. 你能讓 review 標準從「看 style」升級成「看風險」嗎？
12. 你明白平台工程、產品工程與可靠性責任如何分界嗎？
13. 你能把 vendor demo 拆成可驗證的導入假設嗎？
14. 你能拒絕速度看似更快但長期不可維護的方案嗎？
15. 你有為 AI workflow 設 exit condition 與 escalation path 嗎？
16. 你能用數據而不是熱情推動工具導入嗎？
17. 你知道團隊的 review 容量是否跟得上 agent 產量嗎？
18. 你能讓 Junior 在 AI 時代仍然有可成長的責任嗎？
19. 你能把責任上移，而不是把壓力亂丟給工程師嗎？
20. 你已能定義什麼叫值得用 AI、自動化或人工保留嗎？

### Tech Lead / Architect 的解讀

如果你在第 1-8 題大量答「否」，代表團隊缺少 AI-assisted development 的基本治理。這不是工具採購問題，而是風險邊界、系統責任與交付流程沒有被重新設計。

如果你在第 9-15 題大量答「否」，代表你的 agent workflow 可能正在創造新的不透明性。自動化不是只要能跑就好；它必須有停止條件、升級路徑、審計軌跡與人類負責人。

如果你在第 16-20 題大量答「否」，代表你可能正在用情緒或流行趨勢推動 AI 導入，而不是用工程管理方式推動。Lead 的責任不是讓所有人都用 AI，而是定義哪些事情該用、怎麼用、誰負責、失敗時怎麼退。

對 Tech Lead / Architect 來說，最重要的下一步是把隱性判斷制度化。不要只在 review 時靠資深者直覺擋問題；要把風險分級、approval gate、rollback、observability、ownership 寫進 workflow。

## AI-native Engineer / Agent Builder 自測：你是在打造能力，還是在製造新複雜度

AI-native Engineer 或 Agent Builder 的位置會升值，但前提是你做的不是展示型鏈條，而是可驗證、可維護、可治理的 workflow。把幾個工具串起來不等於建立能力；把人工步驟包成花哨流程也不等於工程進步。

這一層的核心問題是：你是否能把 agent 當成需要設計、測試、觀測、限制與治理的軟體系統。

請回答：

1. 你清楚知道自己的 agent 真正成功率，而不是只記得 demo 嗎？
2. 你有 evaluation baseline 嗎？
3. 你有 failure taxonomy 嗎？
4. 你能區分模型問題、prompt 問題、工具問題、資料問題與流程問題嗎？
5. 你是否先把單 agent 做穩，再考慮多 agent？
6. 你能量測成本、延遲、成功率與人工返工時間嗎？
7. 你知道 agent 什麼時候應該停下來找人嗎？
8. 你知道自己的 tool schema 是否造成 tool confusion 嗎？
9. 你有設計 end-state evaluation 嗎？
10. 你能重現 agent 某次失敗，而不是只說「偶爾會錯」嗎？
11. 你知道哪些資料與權限不能暴露給 agent 嗎？
12. 你有考慮 prompt injection 與資料外洩嗎？
13. 你已建立 source quality 或 groundedness 檢查嗎？
14. 你做的是 workflow，還是只是把人工步驟包成鏈條？
15. 你把人類審核看成核心能力，而不是低效阻礙嗎？
16. 你能證明多 agent 比單 agent 更好，而不是只是更複雜嗎？
17. 你有為 agent 保留可觀測性與審計軌跡嗎？
18. 你知道哪部分能力會很快被平台吃掉嗎？
19. 你具備足夠軟體工程能力來判斷 agent 寫出的東西好不好嗎？
20. 你是在打造能力，還是在製造新的一層不可維護複雜度？

### AI-native Engineer / Agent Builder 的解讀

如果你在第 1-6 題大量答「否」，你缺少評估基線。沒有 baseline、failure taxonomy、成本、延遲、成功率與返工時間，就很難知道 agent 是否真的改善 workflow。

如果你在第 7-13 題大量答「否」，你的風險控制不足。Agent 不只是會呼叫工具的模型；它會接觸資料、權限、上下文與外部系統。停機條件、資料邊界、prompt injection、groundedness、失敗重現，都是必要工程要求。

如果你在第 14-20 題大量答「否」，你可能在製造複雜度，而不是建立能力。多 agent、不透明鏈條、缺乏審計、缺乏人類審核，都會讓系統更難維護。AI-native 的價值不在於把流程包得更炫，而在於讓人機協作更可靠、更可驗證、更可治理。

對 Agent Builder 來說，下一步是把「demo 成功」換成「可重現、可量測、可審核」。這是工程產品和技術表演的分界。

## 從分數到行動

完成自測後，不要只看總分。請把所有「否」分成五類：

| 類別 | 代表問題 | 典型題目 |
|---|---|---|
| 理解 | 你講不清楚 code path、資料流、狀態生命週期 | Junior 1-4、Senior 17 |
| 驗證 | 你不知道怎麼證明結果正確 | Junior 5-7、Mid 7、AI-native 1-3 |
| 風險 | 你看不出 blast radius、failure mode、security / privacy 邊界 | Mid 3-5、Tech Lead 1-9、AI-native 11-13 |
| Ownership | 你只擁有 ticket，不擁有模組、系統或 workflow | Junior 20、Mid 18-20、Senior 20 |
| 治理 | 你無法把判斷變成團隊流程 | Senior 10-13、Tech Lead 7-17 |

接著選出你最多「否」的兩類，安排下一季訓練。

如果最多的是「理解」，請減少直接讓 AI 先寫整段 code，改成先自己畫資料流、列狀態、trace 一次主路徑，再讓 AI 協助補洞。

如果最多的是「驗證」，請把測試、反例、assertion、eval、manual walkthrough 放到呼叫 AI 前。不要等 AI 產出後才問「要怎麼測」。

如果最多的是「風險」，請練習每個 PR 都寫 blast radius、rollback、security / privacy 影響、observability。這會讓你的工程判斷從「能不能做」升級到「能不能安全地上 production」。

如果最多的是「ownership」，請爭取可持續負責的範圍。不要只接散票。你需要一塊會隨時間累積上下文、債務、事故與決策歷史的系統責任。

如果最多的是「治理」，請把個人直覺變成流程。定義風險分級、approval gate、AI code review checklist、rollback 標準、agent 停止條件與 escalation path。

## 對讀者的職涯含義

這份清單真正要檢查的，不是你會不會使用 AI，而是你在 AI 壓縮任務後還剩下什麼工程責任。

如果你大量回答「否」，不要把它解讀成單純的工具落後。更準確的解讀是：你目前的位置可能太接近可被加速、商品化、切碎與外包的工作層。你需要往上移動到問題定義、驗證、風險控制、系統 ownership、團隊治理與事故承擔。

未來工程師的安全感，不來自「我比 AI 更會打字」，而來自「AI 產出的東西必須經過我的定義、約束、驗證與承擔，才有資格進入真實系統」。


---

# 第 8 章：工程師的 AI 使用守則

AI 可以加速工程工作，但不能替你承擔 production、security、privacy、rollback、observability 與 ownership 的責任。

這一章的目的不是教你寫更漂亮的 prompt，而是建立一套可執行的 AI 使用守則。工程師真正需要避免的，不是「用了 AI」，而是把 AI 的輸出誤認為已經完成工程工作。

在 agentic coding 時代，任務被壓縮，責任會上移。你可以讓 AI 協助產生草稿、拆解問題、補測試、整理文件、搜尋 codebase、提出方案比較；但你不能把需求判斷、風險控制、驗證責任、production 後果與 human ownership 一起交出去。

## 一個基本原則

使用 AI 前，先問一句話：

> 如果這段輸出錯了，誰會發現、怎麼發現、多久發現、如何回滾、誰負責？

如果你答不出來，這個任務就不應該直接交給 AI 產出可 merge 的結果。

AI 的價值在於壓縮低風險、邊界清楚、可驗證的工作。AI 的風險在於它也會壓縮你思考的時間，讓模糊需求、隱性假設、未驗證推論、更大的 blast radius，以更快速度進入 codebase。

所以本章的守則可以濃縮成三句：

1. AI 可以先做草稿，但不能替你定義責任。
2. AI 可以幫你加速驗證材料，但不能替你完成驗證責任。
3. AI 可以擴大產出量，但不能成為降低 review、security、privacy、rollback、observability 門檻的理由。

## 什麼可以先交給 AI

可以優先交給 AI 的工作，通常同時符合四個條件：

- 任務邊界清楚。
- 失敗成本低。
- 可以快速自動驗證。
- 不涉及深層隱含規則、敏感資料或高風險 production 行為。

符合這些條件的任務，可以讓 AI 先做，然後由人類 review、修正與整合。

| 任務類型 | 可以交給 AI 的形式 | 人類仍要做的事 |
|---|---|---|
| 測試骨架 | 根據既有功能產生 unit test、integration test 草稿 | 確認 assertion 是否對準需求，補反例與邊界案例 |
| 文件初稿 | 產生 README、API 說明、變更摘要、操作步驟 | 驗證內容是否符合實際系統，不讓文件描述不存在的行為 |
| 重複性 refactor | 依既有模式改名、搬移、抽函式、更新呼叫點 | 控制 diff 範圍，跑測試，確認沒有改變語意 |
| 簡單 migration script 草稿 | 產生資料轉換、欄位補值、格式整理的初稿 | 檢查資料量、交易、鎖、回滾、重跑安全性 |
| 觀測 query 草稿 | 產生 log query、metric query、dashboard 初稿 | 確認指標定義、維度、誤報與漏報風險 |
| 低風險 internal tool | 產生小型輔助工具、腳本、一次性分析 | 限制權限與輸入輸出範圍，避免接觸敏感資料 |
| 小型 prototype | 快速探索 UI、API 形狀或方案可行性 | 不把 prototype 當 production code，重新審視架構與品質 |
| Repo 問答 | 摘要 code path、找相關檔案、解釋既有模式 | 回到 source 驗證，不把摘要當事實 |
| 任務拆解 | 把 issue 拆成子任務、驗收點、風險清單 | 由工程師決定範圍、順序、風險與責任人 |
| Review checklist | 根據 diff 產生可能檢查項目 | 由 reviewer 判斷真正風險，不把清單當審核完成 |

這些任務的共同特徵是：AI 的輸出即使不完美，也容易被人類檢查，且錯誤通常不會直接造成嚴重 production 後果。即便如此，它們仍然只是草稿或輔助材料，不是自動合格的工程交付物。

## 什麼不應直接交給 AI

不應直接整包交給 AI 的工作，通常具備以下特徵：需求模糊、風險高、錯誤代價大、牽涉安全與隱私、缺少測試、缺少 rollback、影響公開介面，或需要深層系統上下文。

| 高風險工作 | 為什麼不能直接交給 AI |
|---|---|
| 模糊需求本身 | AI 會把模糊包裝成看似完整的方案，但不會替產品或工程負責 |
| 資料模型變更 | 錯誤 schema、migration、backfill 可能造成資料不一致或難以回復 |
| 權限與認證設計 | 小錯可能變成越權、資料外洩或合規問題 |
| 公開 API 邊界 | 一旦外部依賴形成，錯誤設計會變成長期相容性成本 |
| 金流、資安、隱私邏輯 | 錯一次的成本可能遠高於開發速度收益 |
| 核心性能優化 | AI 可能給出局部看似合理、整體反而更差的修改 |
| 分散式一致性問題 | 需要明確理解 failure mode、重試、順序、冪等與資料修復 |
| Incident 中的關鍵決策 | AI 可協助整理資訊，但不能主導止血、回滾、溝通與取捨 |
| 沒有可靠測試的高風險改動 | 沒有驗證基礎時，AI 只會更快產生不可判斷的 patch |
| 沒有 rollback 的 production 變更 | 不能安全撤回的改動，不應由不可靠輸出直接推進 |

這些工作不是完全不能使用 AI，而是不能讓 AI 主導。比較合理的方式是讓 AI 協助列方案、列 failure mode、列 review checklist、找相似 code、產生測試構想、整理 incident timeline。真正的決策、實作範圍、驗證標準與上線責任仍必須由人類工程師承擔。

## 呼叫 AI 前必須先想清楚的五件事

在你把需求丟給 AI 之前，至少先寫下五件事。這五件事不是形式文件，而是防止 blind coding 的基本約束。

### 1. 成功條件是什麼

不要只寫「修好 bug」或「新增功能」。請寫清楚什麼情況代表成功：

- 哪個使用者行為會被改變？
- 哪個 API、頁面、任務或流程應該產生什麼結果？
- 哪些測試、資料、監控或人工驗收可以證明它成立？

如果成功條件不清楚，AI 很容易產生形式完整但方向錯誤的 code。

### 2. 不能破壞的 invariants 是什麼

每個系統都有不能被破壞的條件，例如：

- 使用者只能看見自己有權限看的資料。
- 一筆付款不能被重複扣款。
- 某個狀態轉移只能單向發生。
- 某個資料欄位一旦公開就必須保持相容。
- 某個任務可以重跑，但不能重複產生副作用。

AI 不一定知道這些 invariants。就算 codebase 裡有線索，它也可能錯過、誤解或過度概括。呼叫 AI 前，你要先把不可破壞的條件說出來。

### 3. 最大的 failure modes 是什麼

請至少列三個最重要的失敗模式：

- 正常資料可以跑，但邊界資料壞掉。
- 權限檢查漏掉某條路徑。
- migration 可以跑一次，但不能安全重跑。
- 錯誤被吞掉，production 無法觀測。
- retry 造成重複副作用。
- 新增依賴讓部署、版本或安全風險上升。

AI 可以幫你補充 failure mode，但不應該由 AI 第一個定義 failure mode。因為這正是工程師的核心價值之一。

### 4. 要如何驗證

驗證不等於「跑了測試」。你需要先定義驗證層次：

- 單元測試驗證哪個純邏輯？
- 整合測試驗證哪條外部邊界？
- E2E 或手動 walkthrough 驗證哪個使用者流程？
- 反例測試覆蓋哪個 failure mode？
- security / privacy / permission 檢查在哪裡做？
- 上線後用哪些 log、metric、trace 觀測？

如果你不能說出驗證方式，就不應該要求 AI 直接產生 final patch。

### 5. 如果方向錯了，誰接手與如何回滾

每個 AI-assisted 變更都需要 human owner。owner 不是「按下 merge 的人」而已，而是能在出問題時解釋 code path、判斷影響範圍、執行 rollback、通知相關人、補上修復的人。

同時，你要知道回滾方式：

- 是否有 feature flag？
- 是否能 revert commit？
- 是否有資料 migration 需要反向修復？
- 是否有外部 API 或 client 已經依賴新行為？
- 是否有監控能告訴你應該回滾？

沒有 owner 與 rollback 的 AI code，不應進 production。

## Review AI code 的方法

Review AI code 時，不要只問「看起來對不對」。AI 產出的 code 常常在風格、命名、表面結構上很像正確答案。你要 review 的是控制流、資料流、狀態、錯誤邊界、隱性假設、長期維護與 production 行為。

請用下面這份清單：

1. 我能否不用 AI 解釋這段 code 的控制流、資料流與狀態流？
2. 這段 code 引入了哪些新依賴、隱性假設或耦合？
3. 它改變了哪些 public contract、資料格式、權限邊界或錯誤語意？
4. 它的 failure modes 在哪裡？錯誤會被丟出、吞掉、重試，還是靜默失敗？
5. 它如何被測？主路徑、邊界案例與反例是否都被覆蓋？
6. 它是否假設不存在的 API、過期的套件行為或不符合 repo 的慣例？
7. 如果 production 出錯，我要去哪裡看 log、metric、trace 或 audit trail？
8. 這段寫法六個月後別人看得懂嗎？會不會把複雜度藏在抽象後面？
9. 若需求改變，這裡保留 optionality，還是把未來鎖死？
10. 這段 code 的 human owner 是誰？他能不能承擔事故處理？

有一個實用標準：如果你無法口頭解釋 AI 產出的 code path，就不應該 approve。你可以讓 AI 幫你理解，但最後必須由你自己理解。

## 驗證 AI output 的方法

最低要求不是「編譯能過」，也不是「AI 說測試會通過」。最低要求是你能用足夠證據說明：這個變更滿足需求，沒有破壞關鍵 invariant，主要 failure mode 有被覆蓋，production 出事時有人能觀測與回滾。

AI output 的驗證至少包含七層：

### 1. 跑測試，而且看懂測試

跑 unit test、integration test、E2E test 或專案對應的驗證命令。不要只看綠燈，也要看測試到底驗證什麼。AI 很容易產生「看似有測，實際只測 mock」的測試。

### 2. 檢查 assertion 是否對準需求

每個 assertion 都要能回答：它防止哪個錯誤？它對應哪個 acceptance criteria？如果 assertion 只是在確認 mock 被呼叫，卻沒有驗證行為結果，價值很低。

### 3. 做至少一次反例測試

每個重要變更至少要有一個反例：無權限、空資料、重複請求、錯誤格式、逾時、部分失敗、重跑、競態條件。反例能暴露 AI code 最容易藏住的假設。

### 4. 檢查 security、privacy、permission

不要讓 AI 自行決定敏感資料、權限邊界、log 內容或 token 處理方式。檢查是否有資料外洩、越權、過度 logging、把 secrets 放進 code 或 prompt、把不該送出的資料送給外部服務。

### 5. 確認 observability

production 上必須看得到行為。高風險變更至少要知道：

- 成功與失敗的 metric 是什麼？
- 錯誤 log 是否包含足夠上下文但不洩漏敏感資料？
- trace 是否能串起跨服務路徑？
- dashboard 或 alert 是否能在合理時間內暴露異常？

### 6. 做人工 walkthrough

人工 walkthrough 是由 owner 從入口走到出口，說明資料如何進入、狀態如何變化、錯誤如何處理、結果如何被觀測。這一步不能由 AI 摘要取代。

### 7. 高風險變更加 rollback 與 feature flag

對高風險變更，測試通過仍不夠。需要 feature flag、分階段 rollout、可撤回策略、資料修復方案，或至少明確的 revert 路徑。不能回滾的改動要提高審核等級。

驗證責任不能外包。AI 可以幫你產生驗證材料，但最後要由工程師決定這些證據是否足夠。

## 避免 blind coding / vibe coding 的流程

Blind coding 是你沒有明確理解問題、風險與驗證，就開始接受 AI 產出的 code。Vibe coding 在 prototype 階段可以有用，因為它能快速探索形狀；但 production 不能 vibe。Production 需要可理解、可驗證、可觀測、可回滾、有人負責。

比較穩定的 AI-assisted workflow 應該是：

1. 先拆問題，不先叫 AI 寫大段 code。
2. 先定成功條件、invariants、failure modes、驗證方式與 owner。
3. 讓 AI 產生成熟度適合當下階段的產物，例如方案比較、prototype、測試草稿、patch draft、review checklist。
4. 要求 AI 列出假設、未知、風險與需要人類確認的地方。
5. 先在小範圍跑通，再擴大 diff。
6. 人工 review、自動化測試、security / privacy 檢查、observability 檢查都過，才考慮 merge。
7. 高風險改動保留人工主導，AI 只能輔助。

這套流程的重點是把 AI 放在工程流程裡，而不是讓工程流程跟著 AI 輸出跑。你可以讓 AI 快速產生候選答案，但不能讓候選答案自動變成方向。

## 避免 skill atrophy

AI 使用過度最隱性的風險，是能力退化。你可能每天都完成更多任務，但逐漸失去拆解、debug、建模、讀 source、推理 failure mode 的能力。這種退化短期不明顯，直到遇到 AI 解不出、production 出事、需求模糊、系統邊界複雜時才會暴露。

最低限度，請保留以下手動訓練：

| 頻率 | 訓練 | 目的 |
|---|---|---|
| 每週一次 | 不用 AI 做 root-cause analysis | 保留追問題本質的能力 |
| 每週一次 | 手動畫系統資料流或錯誤邊界 | 保留系統建模能力 |
| 每週一次 | 手動 trace 一條重要 code path | 保留讀 source 與控制流理解能力 |
| 每月一次 | 從 log、trace、DB 查詢下手處理真實 bug | 保留 production debugging 能力 |
| 每月一次 | 反駁一個 AI 方案 | 練習辨識隱性假設與長期維護成本 |
| 每季一次 | 回顧自己負責模組的 invariants、風險與 observability | 確認 ownership 沒有空洞化 |

這不是反 AI。相反地，越依賴 AI，越需要保留手動能力。因為你必須有能力判斷 AI 何時錯、錯在哪裡、怎麼修、是否能上線。

## Merge AI code 前的最低檢查標準

團隊應該把以下內容寫成強制 checklist。這不是 bureaucratic overhead，而是 AI-assisted development 的最低安全帶。

| 檢查項 | 最低標準 |
|---|---|
| Human owner | 有明確人類 owner，且 owner 能解釋 code path 與承擔事故處理 |
| 風險等級 | 已標記 low / medium / high risk，並依風險套用不同 review 門檻 |
| 需求對齊 | 有明確 acceptance criteria，不只是「AI 完成了需求描述」 |
| Code path 理解 | 至少一位 reviewer 能口頭說明入口、出口、資料流、狀態變化 |
| 測試覆蓋 | 主路徑、關鍵邊界與至少一個反例有測試或人工驗證 |
| Security / privacy / permission | 權限、敏感資料、secret、外部服務、logging 已檢查 |
| Observability | 有必要的 log、metric、trace、dashboard 或 alert 計畫 |
| Rollback | 有 revert、feature flag、分階段 rollout 或資料修復方案 |
| 新依賴 | 新套件、API、服務、版本與授權風險已被檢查 |
| Technical debt | 若留下債務，已記錄原因、範圍、後續處理條件 |
| AI 來源標記 | 如果主要 patch 由 AI 產生，review 責任與人工修改範圍要清楚 |
| 文件與交接 | 高風險或共享模組變更有必要文件或交接資訊 |

如果團隊 review 容量跟不上 agent 產量，解法不是降低 review 標準，而是降低 agent 進入可 merge 狀態的速度，或提高自動化驗證與風險分級。AI 讓產出變多時，review 和 ownership 也必須升級。

## 團隊層級的 code ownership 規範

AI-assisted development 中，最危險的情況不是 AI 寫錯，而是沒有人真正擁有它寫的東西。團隊至少需要四條規範：

1. AI 產出永遠必須有 human owner。
2. Ownership 是 codebase 或 module ownership，不只是 ticket ownership。
3. 每個 agent workflow 都要有 exit condition 與 escalation path。
4. Review 標準看風險與長期維護，不只看 style。

Human owner 要能回答：

- 這段 code 為什麼存在？
- 它保護了哪些 invariant？
- 它失敗時會怎麼表現？
- 它在 production 上怎麼觀測？
- 它出事時誰會收到訊號？
- 它如何 rollback？
- 它的長期維護成本在哪裡？

如果沒有人能回答，這段 code 不應該因為「AI 產生得很快」而進入主線。

## 不同風險等級的使用方式

不是所有 AI code 都需要同樣嚴格的流程。合理做法是分級。

| 等級 | 例子 | AI 可做什麼 | Gate |
|---|---|---|---|
| Low | 文件、測試骨架、內部小工具、非關鍵重複修改 | 可產生完整草稿 | 一般 review、測試、人工抽查 |
| Medium | 既有功能延伸、一般 bugfix、有限範圍 refactor | 可產生 patch draft | Owner walkthrough、測試、反例、observability 檢查 |
| High | 權限、資料模型、金流、隱私、核心 API、分散式行為、重大 migration | 只作為輔助分析與草稿，不主導 | 設計審查、資深 review、rollback、feature flag、security / privacy 檢查 |
| Critical | Incident 關鍵決策、不可逆資料操作、重大安全修復、會影響大量用戶的 production 變更 | 協助整理資訊、列選項、找相關 code | 人類主導，明確指揮鏈、審計、溝通與回滾策略 |

這個分級的目的不是降低效率，而是把 AI 的使用方式對齊風險。低風險任務可以讓 AI 多做；高風險任務要讓 AI 多輔助，但少主導。

## 對讀者的職涯含義

AI 使用守則表面上是流程問題，實際上是職涯定位問題。

如果你只會讓 AI 寫 code，卻不能定義成功條件、識別 invariant、設計驗證、檢查 security / privacy、建立 observability、準備 rollback、承擔 human ownership，你的位置仍然停留在被壓縮的任務層。你可能短期更快，但長期更容易被更便宜、更自動化的 workflow 取代。

未來更有價值的工程師，不是拒絕 AI 的人，也不是盲目相信 AI 的人，而是能把 AI 放進嚴格工程流程的人。你要能讓 AI 加速低風險工作，同時把高風險責任牢牢握在人類工程師、owner、review gate 與 production governance 手上。


---

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


---

# 結語：從會寫，升級到會定義、會驗證、會治理、會承擔、會簡化

未來五到十年的工程師主路線，不是從「會寫 code」變成「不用寫 code」，而是從會寫，升級到會定義、會驗證、會治理、會承擔、會簡化。

這本書反覆討論的，不是 AI 會不會取代工程師。這個問法太粗。比較準確的說法是：AI coding 正在壓縮一大批 implementation 任務，讓原本靠打字速度、樣板熟練度、局部修補能力建立的價值變薄；同時，它把更多責任推到問題定義、驗證、系統理解、風險控制與 production ownership 上。

所以，真正的分化不在於誰用不用 AI，而在於誰能在 AI 放大速度之後，仍然掌握方向與後果。

## 從會寫，到會定義

會寫 code 仍然必要。看不懂程式的人，很難可靠地審核 AI 產出的程式；沒有 implementation 經驗的人，也很難知道一個需求會在系統裡撞到哪些邊界。

但只會寫已經不夠。

未來工程師的第一個升級，是會定義問題。這包括把模糊需求拆成 acceptance criteria，把產品語言轉成技術邊界，把「做一個功能」轉成可測、可部署、可回復的變更。

AI 可以幫你填滿很多 implementation 細節，但它不會自動知道組織真正要的是什麼，也不會自動知道某個需求背後的商業限制、法規限制、使用者脈絡與技術債。你定義得越差，AI 只會越快產生錯的東西。

會定義的人，會問：

- 這個需求解決的真問題是什麼？
- 哪些情境算成功，哪些情境算失敗？
- 這次變更會碰到哪些系統邊界？
- 什麼可以延後，什麼不能模糊？
- 如果只能做最小可行版本，範圍應該切在哪裡？

這些問題不華麗，但它們決定了 AI 的產出是槓桿，還是噪音。

## 從會寫，到會驗證

AI 時代最危險的習慣之一，是把「看起來合理」當成「已經正確」。Agent 產出的 code 可能命名合理、格式一致、測試也像樣，但仍然誤解需求、漏掉 failure mode、破壞權限邊界，或在 production 資料下失效。

因此，未來工程師的第二個升級，是會驗證。

會驗證不是只會跑測試。它至少包含：

- 知道應該測什麼，而不是只接受 AI 產生的測試。
- 能區分 happy path、edge case、regression 與 production risk。
- 能讀懂測試失敗背後的 root cause。
- 能判斷 coverage 數字是否有意義。
- 能設計 manual check、log、metric、alert 與 rollback 驗證。

AI 可以幫忙產生測試，但測試策略仍然需要人。更重要的是，當測試綠燈但直覺不對時，工程師要有能力停下來。未來有價值的人，不是永遠能讓 CI 變綠的人，而是知道綠燈不代表風險歸零的人。

## 從會寫，到會治理

當 agent 能產出更多 code，團隊問題會變成治理問題。誰可以讓 agent 改哪些模組？哪些 PR 需要 module owner approval？高風險變更如何 gate？review queue 怎麼管理？Junior 如何學習？誰對 incident 負責？

這些都不是單一工程師在本機 prompt 裡能解決的事。

會治理的工程師，不一定是主管。Mid-level 可以治理一個模組，Senior 可以治理一條 delivery path，Tech Lead 可以治理一套 AI-assisted SDLC。治理的核心，是讓速度、品質與責任能共存。

會治理的人，會建立清楚的規則：

- AI 產出永遠有 human owner。
- Ownership 以 codebase/module 為單位，不只以 ticket 為單位。
- Review 依風險分層，不把所有注意力浪費在 style。
- Agent workflow 有 exit condition 與 escalation path。
- 中高風險變更在 merge 前就要有 rollback plan。

這些規則聽起來像流程，但本質是工程判斷的外化。當 code volume 上升，只有靠個人小心是不夠的。團隊需要制度把小心變成可重複的工作方式。

## 從會寫，到會承擔

工程工作最後不是停在 PR merge。真正的責任在 production。

未來最危險的工程師，常常不是完全不會使用 AI 的人，而是很會用 AI 快速完成 ticket，卻不願承擔後果的人。他能產出 diff，卻說不清楚為什麼這樣改；能讓測試綠燈，卻不知道失敗時怎麼回復；能關票，卻不理解這段 code 未來誰要維護。

這種人短期看起來很有效率，長期會把成本轉嫁給 reviewer、SRE、下一個接手的人，以及 production 事故。

會承擔的人則相反。他不一定每次都寫最多 code，但他能回答：

- 這個變更為什麼必要？
- 主要風險在哪裡？
- 我怎麼知道它真的有效？
- 出錯時誰會被影響？
- 怎麼 rollback？
- 三個月後有人讀這段 code，會不會理解我當初的取捨？

這就是 ownership。AI 不會讓 ownership 過時，只會讓缺乏 ownership 的代價更快暴露。

## 從會寫，到會簡化

最後一個升級，是會簡化。

AI 很擅長增加東西。增加一層 abstraction、增加一個 helper、增加更多測試、增加文件、增加設定、增加流程。這些東西有時候是必要的，但 codebase 的長期健康，常常取決於有人願意刪除、收斂、合併、拒絕與簡化。

未來工程師不能只把 AI 當成產出機，也要把它當成複雜度放大器來管理。

會簡化的人，會看見：

- 這個功能是否真的需要新 abstraction？
- 這段 agent 產出的 code 是否只是把簡單問題包得更複雜？
- 能不能用既有模式解決，而不是引入新風格？
- 哪些測試是有價值的，哪些只是鎖死 implementation detail？
- 哪些流程是必要 gate，哪些只是因為不信任而堆出的摩擦？

工程師的價值不只在於把不存在的東西做出來，也在於阻止系統變得不可理解。當 AI 讓新增變容易，簡化會變得更稀缺。

## 最危險的工程師

未來最危險的工程師，不是 Junior，也不是某個特定年資的人，而是把自己留在低責任、低理解、低驗證位置的人。

他的輪廓大致如下：

- 只會把 ticket 改寫成 prompt，無法澄清需求。
- 依賴 AI 產生 implementation，卻不讀懂關鍵路徑。
- 把測試綠燈當成唯一驗證。
- 遇到不熟悉模組仍然硬推 PR。
- 不知道 rollback、monitoring、incident ownership。
- 把 review 當成別人替自己負責。
- 長期不累積 domain、system、debug、reliability 或 security 能力。

這種工程師不一定立刻失業。很多組織在工具導入初期，甚至可能短暫獎勵看似高產出的行為。但當系統變大、事故變多、review capacity 被壓爆，真正能留下價值的人會是能承擔複雜度的人，而不是只會製造更多 diff 的人。

## 最有價值的工程師

未來最有價值的工程師，也不是單純「最會 prompt」的人。Prompt 技巧會變，工具介面會變，模型能力會變，很多今天看起來稀缺的操作技巧會被產品吸收。

更穩定的價值，是能把 AI 放進可靠工程流程裡的人。

他的輪廓大致如下：

- 能把模糊需求定義成可驗證的技術方案。
- 能看懂系統，而不是只看單一檔案。
- 能設計測試、eval、manual check 與 production monitoring。
- 能審 AI code 的風險，而不是只看 style。
- 能擁有一個模組、一條流程或一類問題。
- 能在速度上升時維持可靠性、可維護性與安全。
- 能使用 AI 簡化工作，而不是把系統堆得更複雜。

這種工程師會升值，原因不是 AI 讓他自動變強，而是 AI 放大了他原本就該具備的 ownership、判斷力與系統能力。

## 最後的行動路線

如果你讀完整本書，只帶走一條路線，那就是：

**從會寫，升級到會定義、會驗證、會治理、會承擔、會簡化。**

接下來三到十二個月，可以把行動壓成五件事。

第一，選一個你能真正擁有的範圍。它可以是一個模組、一條資料流程、一組 API、一個 internal tool，或一類常見事故。不要只追更多 ticket，開始累積 ownership。

第二，訓練 verification。每次使用 AI 產 code，都要求自己寫下 acceptance criteria、failure cases、測試策略與 rollback 想法。把「我覺得可以」改成「我如何知道可以」。

第三，補上系統理解。讀依賴、讀 log、讀 incident、讀 migration、讀部署設定。未來的差距不只在寫法，而在誰知道系統為什麼長成這樣。

第四，把 review 從挑錯升級成風險判斷。看需求是否被解對，看測試是否有意義，看邊界是否被破壞，看 production 出錯時怎麼辦。

第五，練習簡化。每次 agent 產出更多 code，都問自己能不能少一點、清楚一點、靠既有模式一點、未來好刪一點。

未來工程師不是 AI 的打字員，也不是站在旁邊喊口號的 AI evangelist。未來工程師是能把 AI 的速度接進真實系統，並對結果負責的人。

## 對讀者的職涯含義

你的職涯風險，不在於 AI 會不會寫 code；它已經會寫很多 code，而且會越寫越多。你的風險在於，你是否仍把自己的價值定義在最容易被壓縮的那一層。

如果你把自己訓練成只會接 ticket、叫 agent、送 PR，你會被工具進步與組織重分工夾在中間。如果你把自己訓練成能定義問題、驗證結果、治理流程、承擔 production 後果、簡化系統的人，AI 不是你的替代品，而是你放大責任範圍的工具。

這不是保證每個人都會升值。這只是指出一條比較務實的路：不要追逐「AI 取代誰」的粗糙答案，去成為那個在任務被壓縮後，仍然能接住責任的人。


---

# 附錄：研究來源與不確定性

本書的結論建立在多種證據交叉判讀上，而不是單一 benchmark、單一公司報告或單一專家觀點；但 2023 到 2026 年的 AI coding 變化太快，所有外推都必須保留不確定性。

這個附錄的目的不是把全書變成研究報告，而是讓讀者知道：哪些判斷比較穩，哪些判斷仍需要保守看待。主文已經把結論轉成職涯與團隊行動指南；附錄只保留必要的來源脈絡與限制。

## 證據類型

本書使用的來源大致分成七類。每一類證據能回答的問題不同，也各自有偏誤。

| 證據類型 | 代表來源 | 比較能支持的結論 | 主要限制 |
|---|---|---|---|
| 開發者調查 | Stack Overflow Developer Survey、JetBrains State of Developer Ecosystem | AI 工具採用率、開發者信任、公司政策、使用者主觀感受 | self-report 偏誤，樣本可能偏向特定社群或工具使用者 |
| 控制實驗與 field experiment | GitHub Copilot 實驗、Google 企業內研究、Microsoft / GitHub Next 研究、MIT / SSRN 工作論文 | 在特定任務與情境下的速度提升、任務配置改變 | 任務範圍有限，外部效度不一定能推到所有團隊 |
| DevOps 與組織研究 | DORA 2024、DORA 2025、DORA AI ROI 相關報告 | AI 對 delivery、documentation、quality、stability 與組織能力的關係 | 多為組織層面資料，不能直接等同個人能力因果 |
| Benchmark 與能力評測 | SWE-bench Verified、SWE-bench Live、METR long-task horizon、METR Frontier Risk Report | 模型與 agent 在 repo-level coding、長任務能力上的變化趨勢 | benchmark 污染、測試設計、任務選樣與快速過時問題 |
| 官方產品與工程案例 | OpenAI agents guide、GitHub Copilot coding agent、Anthropic multi-agent research system、OpenAI harness engineering | agent workflow、eval、tool use、guardrail、產品化方向 | 供應商有產品利益，案例常是特定高成熟團隊 |
| 實務專家文章 | Simon Willison、Martin Fowler、Charity Majors、Kent Beck、Thoughtworks 實驗 | context、測試、human-in-the-loop、ownership、workflow 差異與工程判斷 | 觀點與經驗型證據，不能當成普遍量化結論 |
| 安全與品質研究 | Copilot 早期安全研究、package hallucination、LLM-generated code security/quality、secure coding with AI | AI 產碼的安全、供應鏈、品質與多輪修補風險 | 部分研究針對特定模型、語言或漏洞類型 |

這些來源彼此並不完全一致。某些研究看到明顯速度提升，某些研究在熟悉 repo 的資深開發者身上看到速度下降或收益有限。這不是矛盾到無法判斷，而是提醒我們：AI 的效果高度依賴任務、工具、工作流、codebase 熟悉度、測試品質與團隊治理。

因此，本書沒有採用「AI 一定讓所有工程師變快」或「AI 一定讓工程師失業」這種說法，而是採用更穩健的主線：任務被壓縮，責任上移。

## 主要來源說明

### 開發者調查：採用率高，但不等於信任與成熟

Stack Overflow 與 JetBrains 的開發者調查顯示，AI 工具已經進入主流開發者日常，許多團隊與個人都在使用或試用。但同類資料也顯示，開發者對 AI 的信任並非無條件；在部署、監控、資安、系統責任等高風險工作上，很多人仍然保守。

這類來源支持本書對「AI coding 已經不是邊緣現象」的判斷，也支持「工具普及不等於責任消失」。但調查資料主要來自自陳，不能直接證明實際 productivity，也不能完整描述長期職涯影響。

### Productivity 研究：速度提升存在，但有條件

GitHub、Microsoft、Google 與經濟學研究者的實驗與 field study，提供了 AI coding 在特定任務上提升完成速度、PR throughput 或工作效率的證據。這些研究讓我們不能簡單否認 AI 對 implementation 的壓縮效果。

但這些研究通常有範圍限制：任務可能較受控，工具與組織環境特定，或需要假設使用者已經穩定導入。它們能支持「部分任務被加速」，不能直接支持「所有工程工作會等比例被取代」。

本書因此把 AI 視為 amplifier：它能放大已有能力、流程與測試，也能放大模糊需求、薄弱 review 與不清楚的 ownership。

### DORA 與組織研究：AI 效益取決於系統能力

DORA 相關研究對本書很重要，因為它把問題從個人打字速度拉回 delivery system。資料顯示，AI 可能提升文件、個人生產力感受或某些品質面向，但也可能對 delivery stability 等組織結果產生負面關聯。後續 DORA 對 AI ROI 的討論也強調，效益取決於組織能力與流程成熟度。

這支持本書第 9 章的重點：團隊不能只導入工具，還要重設 ownership、review、gate、rollback、escalation 與 apprenticeship。

### Benchmark：能力進步很快，但評測本身不穩

SWE-bench Verified、SWE-bench Live 與 METR 的長任務能力研究，提供了模型與 agent 能力快速進步的參考。它們讓我們看到 repo-level coding、長時間任務與 tool use 正在變得更實用。

但 benchmark 也是本書最謹慎使用的來源之一。OpenAI 與其他研究者都指出，SWE-bench Verified 之類 benchmark 可能受到污染、測試設計與記憶問題影響。SWE-bench Live 是對污染問題的回應，但新 benchmark 仍需要時間驗證。

因此，本書沒有把任何單一 benchmark 分數當成未來職涯的直接預測。比較可靠的用法，是把 benchmark 當成趨勢信號：agent 能處理的任務範圍正在擴大，但真實工程責任仍不能由分數替代。

### 官方產品與工程案例：看方向，不直接外推

OpenAI、GitHub、Anthropic 等官方文件與案例，清楚顯示 agent workflow 正在產品化：tool use、orchestration、eval、guardrails、background agent、PR review、multi-agent research system，都已經從概念進入實務工具鏈。

這些來源支持「agentic coding 會進入工程流程」的方向判斷。但官方來源有明顯產品利益，工程案例也常來自高成熟團隊或極端場景。它們適合用來理解工具方向與 workflow 設計，不適合直接推論所有公司都能得到同樣收益。

### 實務專家文章：補足工作流與判斷力

Simon Willison、Martin Fowler、Charity Majors、Kent Beck、Thoughtworks 等實務文章與實驗，雖然不都是量化研究，但對本書的工程判斷很有價值。它們共同強調幾件事：context 很重要，測試與人工接手很重要，不能盲信 AI 宣稱，語言與樣板知識的價值可能下降，vision、breakdown、feedback、ownership 與 delivery lifecycle 會更重要。

這類來源支持本書對「未來工程師不是 prompt 操作者，而是系統責任承擔者」的定位。不過它們仍屬觀點與經驗證據，不能單獨當成市場預測。

### 安全與品質研究：AI 不會自動帶著安全意識

安全相關研究提醒我們，LLM-generated code 可能引入漏洞、錯誤依賴、package hallucination、供應鏈風險，且多輪互動不保證產出更安全。這些研究雖然涵蓋的模型與場景不同，但方向一致：AI code 需要流程化治理，而不是只靠開發者感覺。

這支持本書在 review、approval gate、rollback、security 與 reliability 上的保守立場。速度提升不能抵消安全與 production 後果。

## 四個主要不確定性

### 1. 工具進展太快

2023 到 2026 年，AI coding 工具從 autocomplete 快速進到 repo-level agent、background task、tool use、multi-agent workflow。任何對 2031 或 2036 的外推都可能錯估速度、方向或商業模式。

因此，本書更重視相對穩定的能力：定義問題、驗證結果、治理風險、承擔後果、簡化系統。工具會變，但這些能力不太可能因工具變強而失去重要性。

### 2. Benchmark 不穩

Benchmark 是必要信號，但不是穩固地基。污染、測試設計、file path memorization、資料洩漏、任務選樣，都會影響分數。當 frontier model 進步很快時，benchmark 也會更快過時。

所以，本書使用 benchmark 的方式是看趨勢，不把分數直接翻譯成職缺消失比例、薪資變化或某個年資層的命運。

### 3. Survey 與 self-report 有偏誤

開發者常常會高估或低估自己的 productivity。METR 等研究也指出，主觀感覺與實際時間變化可能不同。公司內部調查、開發者平台問卷與工具商報告，都可能受到樣本、期待與產品利益影響。

因此，本書不把「大家覺得更快」當成充分證據，而是把它與實驗、組織研究、benchmark、案例與安全研究一起交叉判讀。

### 4. Junior 招募長期資料不足

AI 對 Junior 的影響是本書最需要保留不確定性的部分之一。現在可以合理推斷：入門 implementation 任務會被壓縮，傳統練功路徑會受影響，團隊需要重設 apprenticeship。但長期招聘數量、薪資、晉升速度、不同產業差異，仍缺乏足夠嚴格的一手長期資料。

因此，本書沒有宣稱「Junior 會消失」。更準確的說法是：舊的 Junior 成長路徑正在變窄，新的路徑必須更早納入 code reading、verification、debug、ownership 與 supervised production responsibility。

## 如何閱讀本書的結論

本書的判斷可以分成三個信心水準。

高信心：

- AI coding 已經能壓縮許多明確、局部、低模糊度的 implementation 任務。
- 單純會寫樣板與完成小 ticket 的價值會下降。
- Verification、debug、system understanding、ownership、reliability、security 與 requirements clarification 會更重要。
- 團隊需要 human owner、risk-based review、approval gate、rollback 與 escalation path。

中信心：

- Mid-level 中只靠一般 implementation 的人會承受較大壓力。
- Senior 與 Tech Lead 的價值會更偏向治理、複雜度控制與 delivery system 設計。
- Junior apprenticeship 會從「多做小任務」轉向「受控地學會驗證與承擔」。

低到中信心：

- 未來五到十年不同地區、產業與公司規模的職缺數量變化。
- Junior 招募是否會大幅下降，以及下降幅度。
- 哪些 AI coding agent 產品會成為長期標準。
- Benchmark 分數與真實團隊 productivity 的穩定對應關係。

讀者應該把本書當成職涯與工程判斷框架，而不是精準預測報告。它的價值不在於猜中某一年某種職缺會少幾成，而在於幫你避開最脆弱的位置，往更能承擔責任的位置移動。

## 推薦延伸閱讀方向

如果你想繼續追蹤，可以優先看五類資料，而不是只看社群上的工具展示：

- DORA 與其他 delivery / DevOps 研究，理解 AI 對組織結果的影響。
- METR、SWE-bench Live 等能力評測，理解長任務與 repo-level coding 能力變化。
- Stack Overflow、JetBrains 等開發者調查，理解採用率、信任與工作流變化。
- 安全與軟體工程研究，理解 AI-generated code 的風險。
- Martin Fowler、Simon Willison、Charity Majors、Kent Beck、Thoughtworks 等實務文章，理解成熟工程師如何把 AI 放進工作流。

追來源時要特別留意三件事：來源是否有產品利益、資料是自陳還是行為紀錄、任務是否接近真實 codebase 與 production 責任。這三件事通常比標題裡的百分比更重要。

## 對讀者的職涯含義

附錄對職涯的含義是：不要把自己的未來押在單一報告、單一 benchmark 或單一工具展示上。AI coding 的方向已經足夠清楚，細節仍然高度不確定。

比較穩健的策略，是投資那些跨工具、跨模型、跨公司都仍然有價值的能力：定義、驗證、治理、承擔與簡化。即使工具進步速度超出預期，這些能力也更可能讓你站在責任上移後的位置，而不是被壓縮在 implementation 的最薄一層。


---

