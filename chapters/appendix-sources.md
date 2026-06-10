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
