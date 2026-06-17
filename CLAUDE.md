# Daily Tarot — Claude Code 自動実行仕様

## このリポジトリの目的

毎日、タロットリーディングのHTMLを自動生成し、GitHub Pages で公開する。

公開URL: **https://shiroinu-net.github.io/dailytarot/tarot/**

---

## 毎回実行するタスク

**今日の日付（YYYY-MM-DD）でタロットリーディングを行い、`tarot/index.html` を更新して main にマージする。**

### 手順

1. 今日の日付を取得する（`date +%Y-%m-%d` または環境変数から）
2. 大アルカナ22枚からランダムに3枚選ぶ（状況・課題・アドバイス）
3. `tarot/index.html` を以下の仕様でHTMLごと上書き生成する
4. コミット → フィーチャーブランチにプッシュ → PR作成 → squash merge で main にマージ

### HTML仕様

- **ファイル**: `tarot/index.html` のみ。日付ファイル（`tarot/YYYY-MM-DD.html`）は作らない
- **カード**: 3枚（状況 / 課題 / アドバイス）をランダムに選択
- **テーマ別リーディング**: 仕事・創作活動、体調・メンタル、人間関係、金運・生活 の4テーマ、各テーマで3ポジション分のテキストを書く
- **カード描画**: SVGで描画（各カードを160×260pxのSVGで）
- **デザイン**: ライト背景（`#f9f7f4`）、Noto Sans JP、14px、余白多め
- **既存ファイルを参考に**: `tarot/index.html` の現在のスタイル・構造を踏襲する

### Git フロー

```
# フィーチャーブランチで作業
git add tarot/index.html
git commit -m "Daily tarot reading YYYY-MM-DD (カード名1・カード名2・カード名3)"
git push -u origin <branch>

# PR作成 → squash merge → main に反映
```

### 完了条件

- `tarot/index.html` が今日の日付・カードの内容になっている
- main ブランチにマージされている
- https://shiroinu-net.github.io/dailytarot/tarot/ に反映される状態

---

## 大アルカナ一覧

| 番号 | 英語 | 日本語 |
|------|------|--------|
| 0 | The Fool | 愚者 |
| I | The Magician | 魔術師 |
| II | The High Priestess | 女教皇 |
| III | The Empress | 女帝 |
| IV | The Emperor | 皇帝 |
| V | The Hierophant | 教皇 |
| VI | The Lovers | 恋人 |
| VII | The Chariot | 戦車 |
| VIII | Strength | 力 |
| IX | The Hermit | 隠者 |
| X | Wheel of Fortune | 運命の輪 |
| XI | Justice | 正義 |
| XII | The Hanged Man | 吊るされた男 |
| XIII | Death | 死神 |
| XIV | Temperance | 節制 |
| XV | The Devil | 悪魔 |
| XVI | The Tower | 塔 |
| XVII | The Star | 星 |
| XVIII | The Moon | 月 |
| XIX | The Sun | 太陽 |
| XX | Judgement | 審判 |
| XXI | The World | 世界 |

前回使ったカードは `tarot/index.html` のフッターや本文から読み取り、なるべく重複を避ける。
