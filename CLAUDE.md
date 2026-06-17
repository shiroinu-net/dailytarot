# Daily Tarot — ルーティン指示

## タスク

毎日、その日の日付（YYYY-MM-DD）でタロットリーディングを行い、HTMLファイルを生成してリポジトリにコミット・プッシュする。

## 生成するファイル

**ファイルパス：`tarot/index.html`（固定）**

日付ごとのファイル名（`tarot/YYYY-MM-DD.html`）は使用しない。
`tarot/index.html` を毎回上書きすることで、最新のリーディングが `https://shiroinu-net.github.io/dailytarot/tarot/` に常に表示される状態を維持する。

## 生成条件

- カード：3枚をランダムに選ぶ
  - Position I：状況（POSITION I / SITUATION）
  - Position II：課題（POSITION II / CHALLENGE）
  - Position III：アドバイス（POSITION III / ADVICE）
- テーマ別リーディング：仕事・創作活動 / 体調・メンタル / 人間関係 / 金運・生活
- カードはSVGで描画する（各カード固有のビジュアルデザイン）
- デザイン：ライト背景（#f9f7f4）、Noto Sans JP、14px、余白多め
- 言語：日本語

## コミット

ブランチ `main` にコミット・プッシュする。
コミットメッセージ例：`Update daily tarot reading for YYYY-MM-DD`
