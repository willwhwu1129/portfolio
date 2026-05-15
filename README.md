# Will Wu — 作品集網站

## 檔案說明

```
index.html      → 前台網站（不需要動）
articles.json   → 所有作品的內容資料（你每次更新這個）
README.md       → 說明文件
```

---

## 第一次上架步驟

### 1. 建立 GitHub 帳號與 Repository

1. 去 [github.com](https://github.com) 註冊帳號
2. 點右上角 **+** → **New repository**
3. Repository name 填：`portfolio`
4. 選 **Public**
5. 點 **Create repository**

### 2. 上傳檔案

1. 進入剛建立的 repository
2. 點 **Add file** → **Upload files**
3. 把 `index.html`、`articles.json`、`README.md` 三個檔案全部拖進去
4. 點 **Commit changes**

### 3. 開啟 GitHub Pages

1. 進入 repository → 點上方 **Settings**
2. 左側選單找 **Pages**
3. Source 選 **Deploy from a branch**
4. Branch 選 **main**，資料夾選 **/ (root)**
5. 點 **Save**

等 2–3 分鐘，你的網址就是：
```
https://你的GitHub帳號.github.io/portfolio
```

### 4. 設定 articles.json 的正確路徑

GitHub Pages 部署後，`articles.json` 和 `index.html` 在同一個資料夾，
`index.html` 裡的 `ARTICLES_URL = './articles.json'` 這行**不需要改**，直接可用。

---

## 如何新增一篇文章

### 長文寫作範本

打開 `articles.json`，在最前面的 `[` 後面加入：

```json
{
  "id": "唯一英文id不能重複",
  "type": "long-form",
  "typeLabel": "長文寫作",
  "title": "你的文章標題",
  "summary": "列表頁顯示的摘要，一兩句話",
  "date": "2025-04",
  "client": "客戶名稱",
  "content": [
    { "type": "paragraph", "text": "第一段內容" },
    { "type": "heading", "number": "01", "text": "段落標題" },
    { "type": "paragraph", "text": "段落內文" },
    { "type": "callout", "text": "重點提示框內容" }
  ]
},
```

### 社群文案範本

```json
{
  "id": "唯一英文id",
  "type": "social",
  "typeLabel": "社群文案",
  "title": "系列貼文標題",
  "summary": "摘要",
  "date": "2025-04",
  "client": "客戶名稱",
  "posts": [
    {
      "number": "01",
      "tag": "心態 #1",
      "title": "貼文大標",
      "body": "貼文內文\n\n換行用 \\n\\n",
      "hashtags": "#標籤一 #標籤二"
    }
  ]
},
```

### 銷售文案範本

```json
{
  "id": "唯一英文id",
  "type": "copywriting",
  "typeLabel": "銷售文案",
  "title": "專案標題",
  "summary": "摘要",
  "date": "2025-04",
  "client": "客戶名稱",
  "salesPage": {
    "badge": "標籤文字",
    "headline": "主標題",
    "subheadline": "副標題說明",
    "painPoints": ["痛點一", "痛點二", "痛點三", "痛點四"],
    "plans": [
      {
        "name": "方案名稱",
        "perks": "方案內容 · 用點分隔",
        "price": "$1,800",
        "period": "每月",
        "featured": false
      }
    ],
    "cta": "按鈕文字",
    "ctaSub": "按鈕下方小字"
  }
},
```

---

## 每次更新流程

1. 在電腦用任何文字編輯器（記事本、VSCode 都可以）打開 `articles.json`
2. 照上面的範本加入新文章
3. 存檔
4. 去 GitHub 的 repository
5. 點 `articles.json` → 右上角鉛筆圖示 **Edit this file**
6. 把新內容貼進去
7. 點 **Commit changes**
8. 等 1 分鐘，網站自動更新

> 也可以直接在 GitHub 網頁上編輯，不需要下載任何軟體。

---

## 注意事項

- `id` 每篇文章必須唯一，建議用英文加數字，例如 `gym-article-2`
- JSON 格式要正確，每個 `{ }` 之間要有逗號，最後一筆**不加逗號**
- 不確定 JSON 格式對不對，可以貼到 [jsonlint.com](https://jsonlint.com) 檢查
