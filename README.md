# Fuu — 說不出口的累，畫下來

**中文** ｜ English（準備中）

Fuu 是一個情緒表達 App，給累到沒力氣照顧自己的上班族。
選一個顏色，把心情畫成一隻 Moodie。想更懂自己的時候，再慢慢替它命名。

> 這是產品設計作品集的一部分。設計、研究和這個可以操作的版本，都是同一個人做的。

## 線上試玩

👉 https://tracyyunn.github.io/fuu.design/

用手機打開最接近真實體驗；用電腦打開會出現一支手機框，左邊是說明。

## 可以試試看

| 功能 | 做什麼 |
| --- | --- |
| Check-in | 選一個感受 → 畫畫（或用現成的）→ 留一句話 |
| My Moodies | 每天的小人、每個情緒的紀錄、日曆 |
| Body Reset | 跟著做的伸展練習，做完回饋有沒有比較好 |
| Mind Space | 不知道從哪說起時，聊一聊，會帶你到適合的工具 |
| Brain Dump | 睡前把腦袋裡的事寫下來、放掉，配一段助眠聲音 |

**第一次打開是空的。** 到 **Me 分頁最下面的「Demo 工具」**，可以一鍵加入過去 3 週的示範資料、解鎖子情緒、重看 Onboarding、讓 Body Reset 快轉。

## 幾個設計上的決定

- **不施壓**：沒有連續天數、沒有 check-in 提醒、沒有分數。
- **顏色＝情緒**：情緒色只用在 Moodies；介面只用紫色和灰色。
- **測試後改的地方**：例如測試者不知道顏色代表情緒、看不出筆刷、以為點了感受就會跳頁，所以加了說明、把筆刷改成線條、拿掉 Next。

完整的思考過程放在作品集頁面。

## 技術

- 一個 HTML 檔，不用框架、不用安裝，直接打開 `index.html` 就能用
- 資料存在瀏覽器的 localStorage，**不會上傳到任何地方**；換一台裝置或瀏覽器就看不到
- 首頁 Moodie 的動畫用 [lottie-web](https://github.com/airbnb/lottie-web)
- 沒有任何金鑰或後端

### Mind Space 的 AI

在 claude.ai 上打開時，Mind Space 會用 Claude 回覆（第一次會詢問同意）。
在 GitHub Pages 或直接打開檔案時沒有 AI，會用預先寫好的回覆。要接真的 AI 需要自己的後端，金鑰不能放在前端。

## 檔案

```
template.html   App 本體（畫面、樣式、互動）
arts.json       六個情緒小人的向量圖
lottie.json     首頁 Moodie 動畫
build.py        把 arts.json、lottie.json 塞進 template.html，產生 index.html
index.html      產生出來的檔案，直接打開或放上 GitHub Pages
```

改完 `template.html` 後執行：

```
python3 build.py
```

## 注意

Fuu 不是醫療或心理治療工具。如果你正處在危機中，請聯絡當地的緊急服務或心理支持專線（App 裡的 Me → Need help now；示範版放的是美國的 988 專線）。
