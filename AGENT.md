# 尼克出版社網站規格書

## 專案概述

本專案為「尼克出版社」單頁式形象網站，依據 Canva 參考切版重製，使用 Bootstrap 5 作為主要前端框架。網站為純靜態頁面，可直接開啟 `index.html` 瀏覽，不需要後端或建置流程。

## 技術規格

- HTML 入口：`index.html`
- CSS 框架：Bootstrap 5，本機檔案引用
- JavaScript：Bootstrap Bundle，本機檔案引用
- 外部 CDN：不使用
- 圖片來源：已下載至本機 `images/` 資料夾
- 字型：使用系統字型與 CSS serif 備援字型

## 檔案結構

```text
website/
├── index.html
├── SPEC.md
├── css/
│   └── bootstrap.min.css
├── js/
│   └── bootstrap.bundle.min.js
└── images/
    ├── hero-reading.jpg
    ├── hero-bookshelf.png
    ├── hero-cafe.jpg
    ├── about-printing.jpg
    ├── book-novel.jpg
    ├── book-picture.jpg
    └── book-business.jpg
```

## 頁面區塊

### 1. 固定導覽列

- 顯示品牌名稱「尼克出版社」
- 深色半透明背景
- 桌機版顯示右側選單
- 手機版使用 Bootstrap navbar toggler
- 選單項目：
  - 關於我們
  - 書籍
  - 聯絡

### 2. 首頁輪播

- 使用 Bootstrap Carousel
- 共 3 張圖片
- 每張圖片有深色遮罩與標語文字
- 圖片高度約為 `70vh`

輪播文案：

- 用文字點亮每一個靈魂
- 嚴選好書 · 陪伴成長
- 閱讀，是最美的日常風景

### 3. 關於我們

- 左側圖片：`images/about-printing.jpg`
- 右側文字：介紹尼克出版社成立理念、出版領域與編輯流程
- 桌機版左右排列，手機版上下排列

### 4. 精選書籍

- 使用 Bootstrap grid 與 card
- 桌機版 4 欄
- 平板版 2 欄
- 手機版 1 欄

書籍資料：

| 書名 | 描述 | 價格 | 圖片 |
| --- | --- | --- | --- |
| 《霧中燈塔》長篇小說 | 年度文學獎入圍作品，探索孤獨與救贖的深刻故事 | NT$ 380 | `images/book-novel.jpg` |
| 《時間的形狀》散文集 | 暢銷作家最新力作，關於記憶與時光的溫柔書寫 | NT$ 320 | `images/hero-bookshelf.png` |
| 《小星星的冒險》繪本 | 溫馨親子共讀繪本，培養孩子勇氣與想像力 | NT$ 280 | `images/book-picture.jpg` |
| 《思維突破》商管書 | 職場必讀，教你建立高效思考模式與決策力 | NT$ 450 | `images/book-business.jpg` |

### 5. Footer

- 深色背景
- 三欄資訊：
  - 品牌與聯絡資訊
  - 服務時間
  - 社群連結
- 目前社群連結皆為 `#`，日後可替換為實際網址

聯絡資料：

- 地址：台北市中正區重慶南路一段88號3樓
- 電話：02-2381-6688
- 信箱：service@morninglight.com.tw
- 服務時間：週一至週五 09:00 - 18:00

## 樣式重點

主要色彩定義於 `index.html` 的 `:root`：

```css
--ink: #1e293b;
--navy: #1a1a2e;
--blue: #1e3a5f;
--paper: #fdfaf6;
--muted: #6b7280;
--sand: #c4b8a8;
```

主要自訂 class：

- `.heading-font`：標題 serif 字型
- `.hero-slide`：輪播圖片尺寸
- `.carousel-overlay`：輪播深色遮罩
- `.section-title`：區塊標題
- `.about-img`：關於區圖片比例
- `.products-section`：書籍區背景
- `.product-card`：商品卡 hover 效果
- `.product-img`：商品圖片固定高度
- `.price-badge`：價格標籤
- `.site-footer`：footer 背景與文字
- `.social-link`：社群按鈕

## 維護注意事項

- 若要更新 Bootstrap，請替換 `css/` 與 `js/` 內的本機 Bootstrap 檔案，並確認 `index.html` 引用路徑不變。
- 不要改回 CDN 引用；目前需求是本機 Bootstrap。
- 更換圖片時請放在 `images/` 資料夾，並同步更新 `alt` 文字。
- 商品卡數量可增減，但建議沿用 Bootstrap grid 結構：

```html
<div class="col-md-6 col-lg-3">
  <article class="card product-card h-100 shadow-sm">
    ...
  </article>
</div>
```

- 導覽列連結使用頁內錨點，新增區塊時需同步更新 `id` 與 nav link。
- Footer 社群連結目前為預留用 `#`，正式上線前需替換為實際網址。

## 驗收重點

- 可直接開啟 `index.html` 瀏覽。
- 頁面不依賴 CDN 或外部字型。
- 桌機、平板、手機版面皆可正常排列。
- Carousel 可正常切換。
- Navbar 手機版選單可正常展開與收合。
- 所有圖片路徑皆為本機相對路徑。
