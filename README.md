# rssreader

使用 GitHub Pages + GitHub Actions + osmosfeed 建立的個人 RSS 閱讀器。[1][2]

## 網站網址

- 閱讀器首頁：<https://rucifa.github.io/rssreader/> [2]
- 設定檔：`osmosfeed.yaml` [1]

## 使用方式

這個專案會透過 GitHub Actions 定期抓取 `osmosfeed.yaml` 中設定的 RSS 來源，並將產生的靜態頁面部署到 GitHub Pages，因此不需要自架伺服器也能閱讀 RSS 內容。[1]

平常使用時，直接打開 GitHub Pages 網址即可查看最新內容；如果想新增或刪除訂閱來源，只要編輯 `osmosfeed.yaml` 的 `sources` 區塊並提交變更即可。[1]

## 更新 RSS 來源

1. 打開 repo 根目錄的 `osmosfeed.yaml`。[1]
2. 修改 `cacheUrl`，格式如下：[1]

```yaml
cacheUrl: https://rucifa.github.io/rssreader/cache.json
```

3. 在 `sources` 底下加入或刪除 RSS 來源，一行一個 `- href:`。[1]

```yaml
sources:
  - href: https://news.ycombinator.com/rss
  - href: https://www.theverge.com/rss/index.xml
  - href: https://ivonblog.com/index.xml
```

4. 按下 `Commit changes` 後，GitHub Actions 會重新建置網站；完成後再打開閱讀器首頁查看更新結果。[1]

## 查看成果

- 直接開啟：<https://rucifa.github.io/rssreader/> [2]
- 如果剛提交完還沒看到新內容，先到 repo 的 `Actions` 頁面確認 workflow 是否成功，再等幾分鐘重新整理 GitHub Pages 網站。[1][3]

## GitHub Pages 設定

此專案的 GitHub Pages 發布來源應設為：

- Source：`Deploy from a branch` [4]
- Branch：`gh-pages` [1]
- Folder：`/(root)` [4]

## 備註

如果網站未更新，最常見原因通常是 GitHub Actions workflow 尚未完成，或 `osmosfeed.yaml` 中的 RSS 網址不是有效 feed。[1]
