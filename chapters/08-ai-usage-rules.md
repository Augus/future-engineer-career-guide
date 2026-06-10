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
