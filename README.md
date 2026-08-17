# 公式サイト（Website/）

『流転のジェミニ』公式サイトの原本。ビルドツールなしの静的HTML/CSS（歌帳・ハブHPと同じ運用感）。

**作成・公開**: 2026-08-16 ／ **公開URL**: https://gemini.yomolog.net

## 公開・更新手順

- **配信リポ**: kanae-yomo-dev/gemini-rpg-site（ブランチ main / root・GitHub Pages・リポ直下にCNAMEファイルあり）。配信リポにこのREADME.mdは置かない
- **更新の流れ**: ここ（原本）を編集 → 主さんのターミナルで `cp -R ~/LifeLog/GeminiRPG/Website/ ~/gemini-rpg-site/` → push（アカウントは `gh auth switch -u kanae-yomo-dev`）
- **DNS**（お名前.com）: `gemini` のCNAMEレコード（→ kanae-yomo-dev.github.io）＋GitHub Pagesドメイン検証用TXTレコード（`_github-pages-challenge-kanae-yomo-dev`）。**TXTは消さずに維持**

## 構成

| ファイル | 内容 |
|---|---|
| `index.html` | ホーム（キャッチコピー・特徴3つ・最新情報・リンク集・Steam導線） |
| `characters.html` | キャラクター（主人公・パートナー・仲間） |
| `world.html` | 世界とシステム（世界観・感情/慧眼/装備・序盤ダンジョン) |
| `news.html` | ニュース一覧（新記事はコメント位置に新しい順で追加） |
| `about.html` | 開発について（開発者紹介・開発動機・連絡先。ヘッダー・フッター両メニューに掲載） |
| `en/*.html` | 英語版5ページ（日本語版と1対1対応。ヘッダーのJA⇄ENで相互リンク） |
| `css/style.css` | 共通スタイル（全ページで共有） |
| `assets/main-visual.jpg` | ヒーロー用キービジュアル（1920w・タイトル無しクリーン版） |
| `assets/og-image.jpg` | OGP用（1200×630 中央クロップ） |
| `assets/chara-*.jpg` | キャラ肖像5枚（ミズキ・ナギ・ルイ・カイリ・ペチ。600×600・透過は白合成） |

画像の原本は `Docs/デザインシステム/assets/main-visual.png`（3696×2118）。Web用はPILで縮小したJPEG（8.4MB→260KB）。タイトルはHTML側で重ねる方式（英語版流用とSEOのため。文字入り版 `main-visual-title-ja.png` はサイトでは未使用）。

デザインは `Docs/05_アート/アート方針ブレスト_2026-08-16.md` を直輸入（紺×金の星図・幾何学枠・静謐・色数抑制）。色は `style.css` 冒頭の `:root` 変数に集約。フォントはGoogle Fonts「Shippori Mincho」（ゲーム側のフォント検討が確定したら追随を検討）。

## 書いてよい内容（ネタバレ規律）

正本は `Docs/01_計画文書/12_広報戦略.md` §4「ネタバレ三層」。

- **載せてよい**: 第1層のみ（死後の世界・記憶喪失・パートナーとの暮らし・かけら集め・感情システム・慧眼・仲間・「4つの結末」の存在）
- **気配まで**: 第2層は雰囲気テキスト1行程度に留める（現在は world.html の「その優しさの意味を、あなたはまだ知らない。」のみ）
- **書かない**: 第3層（黒幕・真相・個々のエンディング内容・レフレクトス等）。エンディング表記は必ず「選んだ主人公ごとに4つの結末」

## 英語版の運用

- 対訳の正本は `Docs/08_ローカライズ/英語対訳資料.md`（タイトル=Gemini in Flux・Afterworld・Mirror of Samsara・Sharp Eye・Pechiの", nya"等）。サイト独自の新訳を作らない
- キャッチコピー・ショート説明は `12_広報戦略.md` §1の確定英文をそのまま使用
- **日本語ページを更新したら英語ページも同時に更新する**（特にニュース記事の追加）
- 表記順序ルール厳守: Mizuki→Nagi ／ Rui→Kairi
- 英語ページのSteamリンクは `utm_content=en` を付けて日本語版と区別

## Steamリンクの規律

固定リンクを使い回さない（広報戦略§13）。ページ×位置ごとにUTMを分けてある：

- `utm_source=official_site` 固定 ／ `utm_medium=hero_button|footer_link` ／ `utm_campaign=site_top|site_characters|site_world|site_news`
- **`Docs/07_広報/Steam/Steam_UTM計測リンク集.md` への登録が未了**（公開時に追記すること）

## 未了・今後

- [ ] カグヤ・ハヤテのビジュアル差し込み（絵が未作成＝実行計画C1・C2の顔グラ整備と連動。現在は幾何学メダリオンで代替）
- [ ] ロゴ画像の活用検討（`Docs/デザインシステム/assets/logo-ja/en.png` あり。現在タイトルはHTML文字）
- [x] デプロイ先の決定 → 2026-08-16公開（上記「公開・更新手順」参照）
- [x] OGPの絶対URL化 → 2026-08-16（全8ページに og:url / og:image を設定）
- [x] UTMリンク集への登録 → 2026-08-16（`Docs/07_広報/Steam/Steam_UTM計測リンク集.md` の公式サイト節）
- [x] 広報戦略マスター文書へ「公式サイト」の節を追加 → 2026-08-16（§10媒体運用）
