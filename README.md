# Codex Sample Game

GitHub Pages にデプロイするための最小構成の Web ゲームです。現在は 15 パズルを題材としたスライドパズルとなっており、リポジトリの `Settings > Pages` で `main` ブランチのルートを公開すればそのままホスティングできます。

## 開発

```bash
npm install # 依存はありませんが lockfile の更新に利用します
npm test    # Node.js の組み込みテスティングフレームワークで実行
```

開発時は任意の HTTP サーバーでルートを配信してください。例: `npx serve .`。
CI では GitHub Actions が `npm test` を自動実行し、ゲームロジックのユニットテストを検証します。

## 仕組み

- `index.html` – 盤面や HUD、解説セクションなどのマークアップ。
- `style.css` – タッチ操作とデスクトップ操作の両方に対応したレスポンシブなスタイル。
- `engine.js` – スライドパズル用のボード生成／シャッフル／勝利判定ヘルパー。
- `engine.test.js` – ボードロジックのユニットテスト。
- `game.js` – DOM を介した 15 パズルの実装。HUD、ベスト手数の保存、キーボード操作にも対応しています。

## デプロイ手順

1. main ブランチにプッシュ。
2. GitHub の `Settings > Pages` で Branch を `main`, Folder を `/ (root)` に設定。
3. 数分待つと `https://<your-account>.github.io/<repo-name>/` でアクセスできます。
