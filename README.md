# Handoff: ママアフィリ × AI分析講座 LP

## Overview
ママ向けアフィリエイター（楽天アフィリ実践者）を対象とした、AI分析講座のランディングページ（LP）デザイン。
「感覚発信から、データ発信へ」をメインメッセージに、楽天アフィリの成果CSVをAIに読み込ませて分析するワークフローを提供する3ヶ月伴走型講座の集客ページ。

## About the Design Files
このバンドルの `ママアフィリLP.html` および `styles.css` は、**HTMLで作成されたデザインリファレンス**です。
本番コードとしてそのままコピーするものではなく、**見た目と挙動の意図を示すプロトタイプ**として扱ってください。
対象コードベース（React/Vue/Next.js/WordPress等）の既存パターン・ライブラリを用いて、このデザインを再現することが目標です。
新規構築する場合は、LP用途に最適なフレームワーク（Next.js 等）を選定してください。

## Fidelity
**High-fidelity (hifi)**。配色・タイポ・余白・インタラクションすべて最終想定値で作られています。
developer は既存の UI ライブラリを用いつつ、**ピクセル精度で再現**してください。

## Design Tokens

### Colors (女性向けコスメLP調)
```
--bg:         #FFF8F5   /* ベース：ピュアホワイト〜クリーム */
--bg-2:       #FCEDE6   /* 二次背景：薄ピンクベージュ */
--bg-3:       #FFFFFF
--cream:      #FFF3EC

--pink:       #F5A3A8   /* メインピンク（CTA背景） */
--pink-deep:  #E57A8A   /* 強調コーラル */
--rose:       #C94763   /* 文字強調（ローズレッド） */
--pink-soft:  #FFE4E1   /* 背景淡ピンク */
--pink-baby:  #FFD4D7

--gold:       #C9A96E
--gold-deep:  #A78547

--choco:      #604437   /* メインテキスト：チョコブラウン */
--choco-2:    #7A5D4F   /* 本文サブ */
--choco-3:    #A68B7D   /* キャプション */
--line:       #F0DFD6

--mint:       #B9D8C5   /* OKカラー */
--yellow:     #FFEAA0   /* マーカーハイライト */
--yellow-deep:#E8C466
```

### Typography
- **見出し**：Zen Old Mincho（明朝体、weight 600-700、letter-spacing 0.04em）
- **本文**：Noto Sans JP（weight 400-600、line-height 1.85-2.1、letter-spacing 0.03em）
- **数字・装飾英字**：Playfair Display Italic（weight 700、大きな数値表現に使用）
- **等幅**：JetBrains Mono（コード風ステップ図解のみ）

### Spacing
- Section vertical padding: **96px**
- Container max-width: **860px**（標準）、**1080px**（wide）
- Container padding: 24px
- Card padding: 28-44px
- Card border-radius: **16-24px**（やわらかい丸み）
- Pill border-radius: **100px**

### Shadows
```
--shadow-pink:    0 4px 16px rgba(229,122,138,0.15)
--shadow-pink-lg: 0 10px 30px rgba(229,122,138,0.20)
--shadow-soft:    0 2px 10px rgba(96,68,55,0.08)
```

## Screens / Sections
LPは縦1枚構成。上から順に：

### 1. Top Ticker（お知らせバー）
- 背景：`linear-gradient(90deg, --pink-deep, --pink)`、白文字
- 40秒で左スクロールするループアニメーション
- 5種のメッセージ＋ドット区切り

### 2. Hero
- 背景：クリームベースに radial-gradient でピンク玉ボケ
- 中央揃え。装飾要素：
  - 右上に円形「限定 10名 先着」スタンプ（150×150、rose背景、白ダッシュボーダー、rotate(-10deg)）
  - 花型SVGスパーク3つ（ピンク・コーラル・イエロー）
- Headline：明朝体 clamp(34px, 5.8vw, 62px)、line-height 1.5
  - 上部に破線ピルで小見出し（"AI時代のアフィリ競争は、もう始まっている"）
  - 「感覚発信」に黄色マーカーハイライト、「データ発信」を rose色
- Sub：max-width 640px、line-height 2.15
- 3カラム Stats カード（現場20h/週、分析0h、目標3倍）
- CTA行：primary（ピンクグラデ、100px radius）＋ secondary outline ＋ 残席メーター（blink dot）

### 3. Problem セクション
- 背景：cream→bg-2 グラデ、top中央にローズ円形「?」装飾
- チェックリスト：2×3、角丸16pxカード、各項目に薄ピンク丸チェックマーク
- 下部に大きな rose→pink-deep グラデの warning callout（黄色⚠アイコン）

### 4. Before / After
- 白背景、3カラム（BEFOREカード / 矢印 / AFTERカード）
- AFTERカードは pink-soft グラデ＋ pink ボーダー
- 大数字：Playfair Display Italic 60px
  - BEFORE: ¥52,400/月
  - AFTER: ¥163,800/月
- リスト：BEFORE は "—"、AFTER は "♡"

### 5. Market Forecast
- 背景：白→bg-2 グラデ
- Chart card（上端にピンクグラデアクセント）
- 6本の縦棒グラフ（2022〜2029、過去→現在→予測）
- 2029年棒：rose→濃色グラデ＋黄色インナーアウトライン
- スクロール IntersectionObserver で height アニメーション（0.9s cubic-bezier）
- pink-soft 背景の注釈カラーアウト

### 6. How It Works（3ステップ）
- 白→cream グラデ背景
- 3カード（CSV→AI→分析）、カード上部に64px円ナンバーバッジ（ピンクグラデ）
- 中央に等幅フォントの"画面擬似図"（pink-soft背景）

### 7. Case Study
- 白→cream グラデ背景
- 左右2カラム大カード（講師自身の発見）
- 左：タイトル＋chip群＋pink-softクォートボックス
- 右：4 insights リスト（大きな italic 数字＋タイトル＋説明）
- カード左上に装飾的な """ の薄いクォートマーク

### 8. Curriculum
- 淡ピンク＋ゴールドの radial-gradient 背景
- 2×3グリッド、白カード
- 数字は Playfair 48px italic、CORE/OPTタグ付き
- hover で translateY(-4px)

### 9. Screening
- cream→白 グラデ背景
- 白大カード、内部は 2カラム（OK / NG）
- OK：mint ボーダー＋緑系グラデ、NG：line ボーダー＋ニュートラル
- h4 は中央配置＋両サイド破線

### 10. FAQ
- 白背景、cream のアコーディオンカード
- hover で pink-soft、open で白＋pink ボーダー
- Q.マークは Playfair italic 26px rose色
- toggle "+" は 45deg 回転で閉じる表現

### 11. Final CTA
- ピンク radial-gradient 背景
- カウントダウン行（white カード、border pink、DAYS/HOURS/MIN/SEC 4セル）※現状はフロントエンドのダミー
- 大見出し＋rose色ハイライト
- CTA行×2（Primary / Secondary）

### 12. Footer
- choco背景、白ブランド名＋グレー3リンク

## Interactions

| 要素 | 挙動 |
|---|---|
| Top ticker | CSS keyframes で無限左スクロール 40s |
| Hero 残席メーターdot | blink 1.5s ease-in-out |
| Market chart bars | IntersectionObserver 発火後、height 0→data-h% を 0.9s cubic-bezier |
| FAQ アコーディオン | click で `.open` トグル、+ は 45deg 回転 |
| Final CTA countdown | setInterval 1s で秒減算（14日08:42:17 ダミー、ゼロで リセット） |
| Primary button hover | translateY(-2px) + shadow 強化 |
| CUR item hover | translateY(-4px) + shadow 強化 |

## Tweaks（キャッチコピーバリエーション）
Hero headline は5案を切替できる状態で実装されています（`HERO_COPIES` 配列）：
1. 感覚発信から、データ発信へ
2. "感覚で勝てる時代"は、あと1年で終わる
3. あなたの勝ちパターン、言葉にできますか？
4. 同じ投稿時間・同じジャンル、収益だけ3倍
5. 見たことのない自分の数字、その中に未来がある

実装時は決定案を1つ選んで採用してください。

## 外部依存
- Google Fonts: Noto Sans JP / Zen Old Mincho / Playfair Display / JetBrains Mono / Bebas Neue
- アイコン・画像：なし（全てCSS/SVGインライン）
- JS：バニラのみ、外部ライブラリなし

## Files in this bundle
- `ママアフィリLP.html` ... 本LPのマークアップ＋インラインJS
- `styles.css` ... 全スタイル定義

## Implementation Notes（実装時の推奨）
- React/Next.jsの場合：セクションごとに Component 分割推奨（`Hero`, `Problem`, `BeforeAfter`, `MarketChart`, `HowItWorks`, `CaseStudy`, `Curriculum`, `Screening`, `FAQ`, `FinalCTA`）
- 成果CSV・AI連携の実在実績は**講師自身の想定値**であり、公開前に本人に文言確認してください
- 金額表記（¥52,400 / ¥163,800）は仮置き。実データに差し替え
- 「先着10名」「残席3」の数値もフロント側ダミー。バックエンド／管理画面からの動的供給を推奨
- カウントダウンは現在ダミー。本番は対象日時からの差分計算に置換
- 市場規模データ出典：サイバー・バズ／デジタルインファクト調べ（公開前に最新値を再確認推奨）

## Deliverables Next Step
1. 公開ドメイン・Vercel等の公開先を確定
2. フォーム（無料個別相談申込）の接続先（LINE／Formrun／Typeform等）を実装
3. プライバシーポリシー／特商法ページのコンテンツ作成
4. OG画像／メタタグの追加
