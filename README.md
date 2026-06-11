# World Cup Draft

スマホで友達と使うワールドカップ・ドラフトゲームです。

## 公開方法

一番簡単なのは GitHub Pages です。

1. GitHubで新しいリポジトリを作る
2. `world-cup-draft.html` と `sample-results.json` をアップロードする
3. リポジトリの Settings から Pages を開く
4. Branch を `main`、Folder を `/root` にして公開する
5. 表示されたURLをLINEで共有する

NetlifyやVercelにドラッグアンドドロップしても同じように公開できます。

## 外部結果フィード

アプリの「ライブ」画面にJSONのURLを入れると、チームの進出ステージと試合結果を取り込みます。

```json
{
  "updatedAt": "2026-06-11T12:00:00+09:00",
  "stages": {
    "日本": "r16",
    "ブラジル": "qf",
    "アルゼンチン": "champion"
  },
  "matches": [
    {
      "home": "日本",
      "away": "ドイツ",
      "homeScore": 1,
      "awayScore": 1,
      "status": "終了"
    }
  ]
}
```

`stages` に使える値は `group`, `r32`, `r16`, `qf`, `sf`, `runner`, `champion` です。

## 実データAPIについて

サッカー結果APIはAPIキーが必要だったり、ブラウザから直接呼べないことがあります。その場合は、API結果をいったんこのJSON形式に変換してGitHub Pagesなどに置くと、このアプリから安定して読み込めます。
