# CLAUDE.md — 28trip-site 共通ルール / Shared Rules

このリポジトリは、家族向けの旅行スケジュール共有サイトです（**GitHub Pages で無料公開**）。
将来は複数の旅ページを増やすハブに育てます。以下は**今後の全作業で必ず守る前提**です。

This is a family travel-itinerary site, **published for free via GitHub Pages**.
It will grow into a hub hosting multiple trip pages. The rules below are **mandatory for all future work**.

---

## 1. 言語 / Language

- すべて **日本語＋英語を併記**する。英語は**小さめ・控えめのグレー**で表示（例: `class="en"` = `color:#9aa6b1` 前後）。
- 併記の対象は漏れなく: **イベント名・店名・住所・営業時間・注意書き・メモ**まで全部。
- 固有名詞は**ローマ字併記**する。例: `八米 (Hachibei)`、`一翠窯 (Issui-gama)`。

> All text is bilingual (Japanese + English). English is smaller and a muted gray.
> Cover everything: event names, shop names, addresses, hours, warnings, notes.
> Add romaji to proper nouns, e.g. 八米 (Hachibei).

## 2. デザイン / Design

- **モバイルファースト**のレスポンシブ。
- 沖縄の夏らしい配色: **海のティール** ＋ **珊瑚色アクセント** ＋ **砂色背景**。
  - 現行トークン: `--sea:#0d8a9e` / `--deep:#0b6273` / `--coral:#ee6a4c` / `--sun:#f2b23e` / `--sand:#fbf7ef` / `--ink:#26323c` / `--muted:#71808d` / `--red:#d64545`
- 見出しは**丸みのあるフォント**（`M PLUS Rounded 1c`）、本文は `Noto Sans JP`。
- **凝りすぎず見やすく**。

## 3. 構成 / Structure

- 予定は**時系列（タイムライン）**で、各予定に**時刻を表示**。
- **日曜・祝日は赤系で強調**（例: `--red`、`.sun` クラス）。
- 場所カードには**写真を大きく見やすく**。
- 種類は**アイコン**で示す（例: 🍽 ランチ / 🚕 タクシー / 🏺 やちむん など）。

## 4. リンク / Links

- **店名 → 公式サイト**（`target="_blank" rel="noopener"` で新規タブ）。
- **住所 → Googleマップ検索URL**（`https://www.google.com/maps/search/?api=1&query=<URLエンコード済み住所>`）。
- **電話 → `tel:`**（タップで発信）。

## 5. プライバシー / Privacy（★重要：リポジトリは公開）

- このリポジトリは **GitHub で公開（public）** されている（GitHub Pages で無料公開するため）。
  → **コミットする内容はすべて全世界に見える**前提で扱う。
- **これらは絶対に載せない / コミットしない**:
  - ❌ 個人の**住所（番地）**・**個人の電話/携帯**・**名字（フルネーム）**・**子どもの名前**。
- **これらはオーナー判断で掲載可**:
  - ✅ 大人の**下の名前・ニックネーム**（例: `なおき` / `まーさ` / `ゆうま` / `かおり`）。
  - ✅ **店舗など既に公開されている情報**（店名・店の住所・店の固定/携帯電話）。
- 検索避けとして**各ページに必ず**入れる:
  ```html
  <meta name="robots" content="noindex, nofollow">
  ```
  ※ noindex は検索避けのみ。公開リポの中身自体は誰でも閲覧できる点に注意。

## 6. 画像 / Images

- 画像は **base64 埋め込みではなく `images/` フォルダ**に置き、HTMLからは**相対パス**で参照する（例: `images/hachibei1.jpg`）。
- 命名は**場所ベースで分かりやすく**（`<place><n>.jpg`）。
- 人物・自宅が写った写真は載せない（店舗・料理・風景のみ）。
- ※ 小さなインラインSVGアイコンはHTML内にインラインのまま可（UI装飾のため）。

## 7. デプロイ / Deploy

- 変更したら**必ず** `git add` → `git commit` → `git push`。**GitHub Pages が `main` から自動公開**。
- 公開URL: **https://28yu.github.io/28trip-site/**
- Jekyll 無効化のため `.nojekyll` を置いている（静的HTMLをそのまま配信）。
- コミットメッセージは**分かりやすく**。

---

## 沖縄 2026（お盆）の固定情報 / Okinawa 2026 fixed facts

- **日程**: 8/7(金)–8/16(日)、10日間。往路 JAL923 HND→OKA、復路 JAL906 OKA→HND。
- **なおき は 8/12–16 は静岡**にいる（同行なし）。該当日に**視覚的に分かるバッジ**を表示する（`.away`）。
  Naoki is in Shizuoka on 8/12–16 — show a clear badge on those days.
- **「仕事」= まーさ（妹）の勤務**で同行なし。**メモとして表示**する。
  "Work" = Maasa's shift, not joining. Show as a note.
- **定休注意 / Closures**:
  - **AONOKI = 火〜木 定休** → 8/13(木) は**赤字で注意喚起**。
  - **Oki Smash = 月〜木 定休** → 8/10(月) は**赤字で注意喚起**。
- **レンタカー**: 8/8 受取・**8/16 9:00 返却**（シーサイドレンタカー 那覇営業所）。
- **宿**: **宜野湾 (Ginowan)**（詳細な住所は公開しない）。
