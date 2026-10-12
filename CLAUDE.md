# CLAUDE.md — 2027 台東・花東縱谷・東海岸 5 天 4 夜（四位長輩）

> 使用者以繁體中文溝通，回覆請一律使用繁體中文。新對話開始先讀完這份。

## 這個 repo 是什麼
從 `trip-template` 開出來的旅遊懶人包：單一 `index.html`（桌機版＋手機 App 版＋PWA），發布在 GitHub Pages
`https://jerry940080.github.io/2027-taiwan/`。做法、資料格式、踩雷筆記都在 `.claude/skills/trip-guide/`
（`SKILL.md`、`references/architecture.md`、`references/pitfalls.md`），改資料前先讀。
**直接 commit 到 `main`**（使用者 2026-10-12 指定），Pages 設 Settings → Pages → Deploy from a branch → main / root。

## 行程表（2026-10-12 初版，日期暫定）
| Day | 日期 | 內容 | 交通 | 過夜 |
|---|---|---|---|---|
| 1 | 5/24（一） | 台北 → 台東；下午台東森林公園（琵琶湖）、海濱公園（國際地標）；晚餐米巴奈山地美食坊；鐵花新聚落看燈籠 | 台鐵普悠瑪／新自強（約 07:30 → 11:10，推算）＋計程車 | 台東市飯店（待訂） |
| 2 | 5/25（二） | 包車縱谷：鹿野高台 → 關山米國學校 → 悟饕池上飯包午餐 → 伯朗大道（電動代步車）→ 大坡池 →（選項 福原豆腐店）→ 回台東 | 8 人座包車 08:30–17:10 | 續住 |
| 3 | 5/26（三） | 包車海線：小野柳 → 加路蘭 → 都蘭新東糖廠 → 東河包子 → 成功漁港海鮮午餐 → 三仙台（看景不過橋）→ 回台東 | 8 人座包車 08:30–16:30 | 續住 |
| 4 | 5/27（四） | 史前文化博物館 → 卑南遺址公園 → 區間車到知本 → 知本老爺午餐＋泡湯（選項 東遊季）→ 回台東 | 計程車＋台鐵區間車＋計程車 | 續住 |
| 5 | 5/28（五） | 台東糖廠文創園區 → 台東美術館 → 午餐、買伴手禮 → 台東 → 台北 | 計程車＋台鐵（約 14:40 → 18:30，推算） | 回家 |

## 重要決策（別再改回去）
- **使用者需求**（2026-10-12 問答）：4 位長輩、5 天 4 夜、5 月底、全程大眾運輸（台灣好行為主、部分包車）、台北出發台鐵直達台東、
  **台東市住 4 晚每天放射狀出遊**、行走正常但**避免爬坡與長步道**、重心花東縱谷＋台東市區周邊、**必去海線一日（三仙台、都蘭、加路蘭）**、
  **不要夜市與人擠的網紅景點**、餐飲沒特別需求、日期暫定 5/24–5/28（確定後改 `DAYS`、`BOOK`、`wxFetch`、`dayDiff`、`trip.json`）。
- 使用者原本給了兩個 share.google 連結與一支 YouTube 影片當參考，雲端環境連不到，使用者說「不重要，自行規劃」。
- 「繼承之前的紀錄」＝沿用熱海・伊豆懶人包的版面與功能（trip-guide 範本），不是沿用舊行程內容。
- 縱谷、海線兩天雖然台灣好行 8168A／8101 都到，但班次少、長輩等車久，**改成包車**；其餘天計程車＋區間車。交通頁有寫替代的好行路線。
- 三仙台**不過橋**、鹿野高台**不走滑草場**、小野柳**只到第一個觀景台**、伯朗大道**租電動代步車**：都是為了長輩不走坡與長步道。
- 鐵花村 2023 年底熄燈，現在叫**鐵花新聚落**（燈籠、波浪屋仍在），是夜間散步不是夜市。
- 知本老爺 2026/9 整修重開，泡湯方案與票價**未查證**，`BOOK` 有「出發前兩週電話確認」；備案東遊季（大眾池 08:00–22:00）。
- 5 月底是梅雨季：Day 2、Day 3 可對調（`DAYS[].rain`、`BOOK` 的 wx 項有寫）。
- 花費頁同行人數預設 4（`PPL` 預設值改成 4），包車、飯店、計程車用 `car` 旗標分攤。

## 資料來源與未查證
- **台鐵班次與時刻全部是推算**（搜尋只找到舊年度車次：樹林 06:41 → 台東 11:35 的 22 次等），2027 年時刻表出來後要改 `STOPS[1][0]`、`STOPS[5]` 末兩站、hero `.flights`、手機 `mh-flt`、交通頁 Day 1／5。
  票價「約 NT 1,040」是 2025/6 調價後依台北–花蓮 583 推算，未查證。訂票規則：乘車日前 28 天 00:00 開賣（2020 年起的規定，2026 未見變動）。
- 查到的：台灣好行 8168A 縱谷鹿野線每日 2 班、現金全票 117（旅遊網站，未標年份）；8101 東部海岸線 2026/7 起只能在興東客運官網購票劃位；
  史前館週二至日 09:00–17:00、16:30 停售（第三方目錄）；東遊季大眾池 08:00–22:00（旅遊網站）；鐵花村 2023/12/31 熄燈（新聞）；知本老爺 2026/9 整修重開（新聞）。
- **未查證**（畫面標「約」「待確認」）：各景點營業時間與票價（史前館全票 100、卑南展示廳 30 來自舊資料）、包車價格（搜到 NT 2,700–4,060 的套裝頁，8 人座未明）、計程車車資、
  米巴奈與各餐廳的營業時間與公休、悟饕營業時間（兩個來源 10:30–19:00／08:00–20:00）、池上穀倉藝術館週一二休、台東美術館免費、電動代步車租金。
- **座標**全部依地址／地圖估（±100–300 m），`check.js` 落海檢查通過；最不確定的是 mibanai、tofu、granary、plants、chenggong、dongyouji。
- 天氣平年值（台東 29／24、池上 28／22、成功 28／24、知本 29／23）是 5 月約略值，未逐筆查證。
- 官方網址只填到首頁（連不到外網，沒實際點開）。
- 候選飯店（桂田喜來登、娜路彎、康橋）與餐廳（米巴奈、老東台米苔目、卑南豬血湯、寶桑湯圓、福原豆腐店、東河包子）是常見在地店家，地址與電話未逐一查證。

## 底圖
- `LAND`：g0v `twgeojson/twCounty2010.geo.json`（內政部縣市界）用 shapely 聯集後裁 bbox 120.75,22.45,121.75,23.75、簡化 0.0004°，2 個多邊形 579 點（含綠島）。
  產生腳本在對話 scratchpad（`tools/land_tw.py`），要重做：下載該檔 → `unary_union` → `intersection(box)` → `simplify` → 寫回 `const LAND=`。
  Natural Earth 10m 太粗（整段東海岸只有 61 點），GADM 被網路政策擋。
- `LINES`：Natural Earth 10m railroads（`make_geo.py --rails world`，2 段、無路線名），只當背景鐵道與區間車路徑。`RAIL_OK` 比對 `/鐵道/`。
- `CAR_ROUTES`：台9線縱谷、台11線海線、台9線知本三條**示意走廊**（手填座標，非道路圖資），footer 有註明。

## 變更紀錄
### 2026-10-12 變更（一）：從範本建立台東行程
使用者要求「我現在想要繼承之前的紀錄，但是在我想要排 2027 5月底的台灣東部旅遊，請你以提問的方式來詢問我旅遊的細節」。
用 AskUserQuestion 問了四輪（日期天數、交通、同行、區域、出發地、住宿、步調、預算、參考連結、必去不要、暗定日期、餐飲、分支），依答案擬五天骨幹獲同意後建立。
- **做了什麼**：複製 `reference-guide.html` → `index.html`，依 `new-trip-checklist.md` 逐項替換（scratchpad `tools/build_data.py`、`build_static.py`）：
  `P/NAMES/GQ` 31 點、`CARDS` 25 張、`DAYS` 5 天、`STOPS`、`RAIN_STOPS`（Day 1–3）、`COST`（全 NT）、`BOOK` 10 項、`WX_LOC/WX_DAY`、`PACK`（長輩版）、
  `RESTO` 16 列、`SPOT_TREE` 四區單層、`FOOD_TREE=[]`、`MAP_ZONES={}`、`AREAMAPS=[]` 並刪掉 `areaHTML`（靜岡總覽）與 strip 連結；
  靜態 HTML：head、hero、交通頁（路線圖 SVG、每日交通 5 張卡、「長輩出遊須知」取代自駕須知、票價一覽表）、美食與行李、花費導言、footer、手機首頁文字。
  `izu-` → `tte-`（19 處）、`Asia/Tokyo` → `Asia/Taipei`、`dayDiff` 2027-05-24、`wxFetch` 5/8–5/29、維基改 `zh.wikipedia.org`、`renderCost` 摘要改成全 NT。
  `sw.js` `V='tte-v1'`、manifest、icons（PIL 畫的海與山）、`trip.json`（`tentative:true`）。
- **踩雷**：WebFetch 連不到 share.google／youtube；`make_geo.py` 下載 40 MB 檔會被代理切斷（`IncompleteRead`），改 `curl -C -` 續傳；
  Natural Earth 太粗，改 g0v 縣界聯集；天氣徽章原本蓋住 Day 5 的糖廠標記，把台東的 `WX_LOC` 座標移到外海 (22.745,121.175)。
- 驗證：`node .claude/skills/trip-guide/scripts/check.js index.html <scratchpad>/shots` 全部通過、無落海；scratchpad `tools/shots.js` 等動畫跑完截手機每天地圖、景點子區、桌機每日區塊與交通頁，逐張看過。

## 待辦
- [ ] 日期確定後：改 `DAYS[].date/wd`、`STOPS`、`BOOK` 截止日、`wxFetch` 期間、`dayDiff`、hero／手機首頁日期、`trip.json`（`tentative:false`）。
- [ ] 2027 台鐵時刻表出來後填實際車次、時刻、票價（見上）。
- [ ] 訂好飯店：改 `CARDS.hotel`、`NAMES.hotel`、`P.hotel`（實際座標）、`COST` 住宿列、`STOPS` 裡「台東市飯店（待訂）」、`DAYS[].stay`。
- [ ] 訂好包車：補司機電話與價格到 `BOOK.car`、`COST`。
- [ ] 確認知本老爺泡湯方案，或改成東遊季（把 `STOPS[4]` 的 zhiben 兩站換成 dongyouji）。
- [ ] 使用者提供照片後用 `scripts/addphotos.py` 加進 `IMG`；影片連結加進 `CARDS[].video`。
- [ ] GitHub Pages 開啟後確認首頁 jerry940080.github.io 有列出這趟（靠 `trip.json`）。

## index.html 內部結構
見 `.claude/skills/trip-guide/references/architecture.md`。這份行程的 key 一覽：
`ttstn hotel tiehua forest seaside mibanai sugar artmuseum`（台東市區）、`luye guanshan bento brown kaneshiro(幾何點) dapo tofu granary plants`（縱谷）、
`xiaoyeliu jialulan dulan donghe chenggong sanxiantai`（海線）、`prehistory beinan zbstn zhiben dongyouji`（卑南・知本）。

## 修改慣例
- 改行程只改 `STOPS`（＋`RAIN_STOPS`）；`COST`、`BOOK`、交通頁每日卡、hero 路線字串是手寫的要一起看。
- 改座標後跑 `check.js`；改 `sw.js` 把 `V` 加一；改日期或主要地點一起改 `trip.json`。
- 新增景點：`P`＋`NAMES`＋`GQ`＋`CARDS`＋放進 `SPOT_TREE` 某區的 `keys`＋排進 `STOPS`。
- 大檔用 Python 以唯一錨點取代並 `assert count==1`；commit 訊息中文一句話標題＋條列；推 `main`。
