# AI 不必失控，也會把世界駭壞：Bruce Schneier 在 DEF CON 34 談 Hacking AI

Bruce Schneier 在 DEF CON 34 主軌演講〈Hacking AI〉（2026-08-07，拉斯維加斯；DEFCONConference 頻道 2026-09-04 上傳，44:34）的深度導讀。內容涵蓋他對 hack 的廣義定義（任何一套規則都能被駭）、獎勵駭取與「精靈問題」、今天的 coding agent 與 Hugging Face 事件、AI 駭客行為的速度、規模、範圍、精密度、軟體與法律修補速度的落差、信任與完整性，以及他把問題拉回資本主義與民主的現場問答；講者說法與公開資料的落差集中在〈對照公開資料〉一節。

## 製作聲明

本導讀的分析與撰稿由 AI 模型完成，不是人類分析，也沒有經過人工逐句校稿。分工（以主文〈製作說明〉為準）：逐句中文翻譯由 agy 的 gemini-3.8-flash-medium 完成，再由 Claude Opus 5.5 一次讀完全部 536 句中英對照、修正其中 49 句；存疑句的聽音校對用 agy 的 gemini-3.8-flash-high，約 145 句，其中 7 句的中文依聆聽結果改寫，另統一了精靈兩型的譯名，其餘 390 句沒有對照原音；研究、查證帳本與撰稿由 Claude Opus 5.5 完成；Claude Opus 5.5 依審稿 A、B 的意見修稿，並由審稿 C 終審；之後由 Claude Opus 5.5 依總編輯準則潤稿並標示重點，其後又經兩輪總編輯審查與潤稿（共三輪，皆為 AI 模型執行）。整體流程由 Claude Sonnet 5.5 統籌派工與合併審稿意見。獨立審稿三路：事實審稿與終審用 Claude Opus 5.5（事實審稿另就 14 條已確認與部分確認的主張回官方原頁做了第二方核對），編輯審稿用 Claude Sonnet。圖由 Claude Opus 5.5 以 SVG 與動態 SVG 繪製，未使用 AI 生圖；封面是抽象示意圖，另兩張圖是本文對講者論點的示意，都不是影片畫面。修補速度那張圖的動態效果只播一次，播完停在完整圖面；封面的光點動畫緩慢循環；系統開啟減少動態效果設定時，兩張圖都只顯示靜態圖面；`images/og-hero.jpg` 是封面 `hero-zh.svg` 的靜態畫面以瀏覽器截圖轉成的 1200×630 分享圖，不是另外生成的圖。

字幕是 YouTube 機器字幕，沒有說話者標記；開頭是主持人介紹，33:35 起是現場問答。引言的中文是翻譯，不是講者原話，可能有誤。

## 檔案

| 檔案 | 說明 |
|---|---|
| `schneier-defcon34-hacking-ai.md` | 正式導讀 Markdown |
| `index.html` | 導讀網頁（可直接用瀏覽器開啟，圖片為相對路徑，不依賴外部函式庫） |
| `player.html` | 中英雙語字幕同步播放器（YouTube 嵌入，536 句、9 章；章節為依內容自訂，非原影片章節） |
| `translation-zh.html` | 全文繁中譯本（非官方，依 YouTube 機器字幕，AI 翻譯） |
| `images/` | 封面 `hero-zh.svg`（抽象示意，光點緩慢循環；手機版 `hero-zh-mobile.svg` 為 1:1）與兩組示意圖 SVG（三個面向、修補的速度；後者的動態只播一次，播完停在完整圖面），各有桌面版與 `-mobile` 版；`og-hero.jpg` 分享用封面（封面靜態畫面截圖） |

## 原始來源

- 影片：DEF CON 34 - Hacking AI - Bruce Schneier，DEFCONConference 頻道，https://www.youtube.com/watch?v=eEBv0STiYhI
- 逐字稿：YouTube 機器字幕（en-orig），原檔不另外公開；播放器與譯文頁顯示的是逐句定稿

## 重要來源

- Bruce Schneier〈AI Doesn't Have to Go Rogue to Break the World〉（本場演講的書面改寫版，CyberScoop 2026-11-09 刊出，schneier.com 轉載）
- DEF CON 34 議程與講者介紹（defcon.org）
- Hugging Face〈Security incident disclosure — July 2026〉（2026-07-16）、OpenAI〈OpenAI and Hugging Face partner to address security incident during model evaluation〉（2026-07-21）
- Simon Willison〈Claude Fable is relentlessly proactive〉（2026-06-11）
- Schneier 相關文章：The Coming AI Hackers（2021）、Autonomous AI Hacking and the Future of Cybersecurity（2025-10）、AI and Trust、The Age of Integrity、The AI Agents of Tomorrow Need Data Integrity、Cybersecurity in the Age of Instant Software
- Harvard Kennedy School Misinformation Review：LLMs grooming or data voids?（2025-10）
- 完整清單與可信度見導讀文末〈來源清單〉

## 已知存疑

- cue 426（36:46–36:57）英文機器字幕是 "don't let AI code is too expensive"，播放器與譯文頁中文為「別讓 AI 寫程式，成本太貴了」，講者原意可能是 AI 或 human，未能確認；導讀主文不依賴這句。2026-11-22 起，播放器與譯文頁在這句後面加註〔存疑：聽音確認講者字面說的是 AI，語意上也可能是 human 的口誤〕。
- cue 457（39:07–39:22）字幕與中文照講者發音寫 "Kami K3"；Hugging Face 官方頁上有 Kimi K3，講者可能指它，但沒有一手確認，導讀主文不指名。播放器與譯文頁在這句後面加註〔存疑：聽音確認講者念作 Kami K3，是否指 Kimi K3 未確認〕。
- 這兩句經 AI 多次聽音仍得出不同結果（426 兩次機器轉寫都是 AI，457 三次聽音分別為 Kami、Llama、Kami），建議由人工只聽 36:46–36:57 與 39:07–39:22，約 30 秒，聽得出來再把標記改成確定版。

## 狀態

已發布（2026-11-22）：https://lushinshang.github.io/schneier-defcon34-hacking-ai/ ；repo `lushinshang/schneier-defcon34-hacking-ai`（公開，GitHub Pages，main／根目錄）。公開 repo 只含 `index.html`、`player.html`、`translation-zh.html`、`schneier-defcon34-hacking-ai.md`、`README.md`、`share_post.md`、`images/`；研究與 QA 紀錄不公開。
