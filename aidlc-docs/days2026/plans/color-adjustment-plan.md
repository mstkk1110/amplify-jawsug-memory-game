# JAWS DAYS 2026 色味調整計画

## 作成日
2026-02-16

## 目的
現在の神経衰弱ゲームの色味を、JAWS DAYS 2026公式サイト（https://jawsdays2026.jaws-ug.jp/）のデザインに合わせて調整する。

## 現状分析

### 現在の色味
- **背景**: ベージュ系グラデーション（#d2c9a4 → #b4ae8d）
- **ヘッダー**: 白背景（rgba(255, 255, 255, 0.9)）
- **タイトル**: グレー系（#4a5568）
- **スタートボタン**: 赤系グラデーション（#ff6b6b → #ee5a24）
- **カード表面**: ベージュ系グラデーション（#cbcda4 → #a9a16c）
- **ランキング**: 青系アクセント（#74b9ff）

### JAWS DAYS 2026サイトの色味分析（スクリーンショットより）

**主要カラー:**
- **オレンジ/イエロー系**: #FFA500, #FFB800, #F5A623（ロゴの"DAYS"部分、キャラクター）
- **ブルー系**: #4A90E2, #5B9BD5, #3B82F6（装飾的な円形要素）
- **ピンク/コーラル系**: #FF6B9D, #FF8FA3（装飾的な円形要素）
- **シアン/ターコイズ系**: #00CED1, #40E0D0（装飾的な円形要素）
- **背景**: ライトグレー/オフホワイト #F5F5F5, #FAFAFA
- **テキスト**: ブラック #000000, ダークグレー #333333

**デザインの特徴:**
- カラフルで明るい雰囲気
- 円形の装飾要素が多用されている
- オレンジがアクセントカラーとして強調
- ポップで親しみやすいデザイン

## 具体的な変更内容

### 1. 背景色
**現在:** ベージュ系グラデーション（#d2c9a4 → #b4ae8d）  
**変更後:** ライトグレー/オフホワイト系  
### 1. 背景色
**現在:** ベージュ系グラデーション（#d2c9a4 → #b4ae8d）  

**変更後:** 極淡いオフホワイト（JAWS DAYS 2026サイトに合わせる）

```css
body {
  /* 基本背景色 */
  background-color: #FAFAFA;
  
  /* 微妙なグラデーション（オプション） */
  background: linear-gradient(135deg, #FAFAFA 0%, #F5F5F5 100%);
  
  /* 背景画像を使用する場合 */
  background-image: url('./images/background-image.v1.png');
  background-repeat: repeat;
  background-size: 512px 512px;
  background-color: #FAFAFA; /* フォールバック */
}
```

**デザイン判断:**
- **極淡いオフホワイト（#FAFAFA）を採用**
- JAWS DAYS 2026のカラフルな要素（オレンジ、ブルー、ピンク）を引き立てる
- 視認性が最も高く、アクセシビリティに優れる
- 長時間見ても目が疲れにくい
- カラフルな前景要素で華やかさを表現

**背景画像について:**
- 既存の背景画像を使用する場合は、極淡いオフホワイト（#FAFAFA）に調整
- または背景画像なしで、単色またはグラデーションのみでもOK
- テクスチャを追加する場合は、微細なノイズや淡い幾何学模様を推奨

### 2. ヘッダー
**現在:** 白背景、グレーテキスト（#4a5568）  
**変更後:** 
- 背景: 白を維持（rgba(255, 255, 255, 0.95)）
- タイトル: ダークグレー/ブラック（#333333）

### 3. スタートボタン
**現在:** 赤系グラデーション（#ff6b6b → #ee5a24）  
**変更後:** オレンジ系グラデーション
```css
background: linear-gradient(45deg, #FFA500, #FF8C00);
box-shadow: 0 4px 15px rgba(255, 165, 0, 0.4);
```

### 4. カード表面・裏面
**現在:** ベージュ系グラデーション（#cbcda4 → #a9a16c）  
**変更:** 専用画像を使用しているため、CSS変更は不要

```css
/* カード表面 */
.card-front {
  background-image: url('images/front-face.v1.png');
  /* グラデーションは画像のフォールバック用として維持 */
  background: linear-gradient(135deg, #cbcda4, #a9a16c);
}

/* カード裏面 */
.card-back {
  background: white;
  /* 画像が表示される */
}
```

**デザイン判断:**
- 専用画像を使用しているため、背景色の変更は不要
- 画像が読み込めない場合のフォールバック用グラデーションは維持
- カードの枠線は視認性向上のため追加（後述）

### 5. ランキングセクション
**現在:** 青系アクセント（#74b9ff）  
**変更後:** 
- 通常アイテム: オレンジ系（#FFA500）
- 1位: ゴールド維持（#FFD700）
- 2位: シルバー維持（#C0C0C0）
- 3位: ブロンズ維持（#CD7F32）

### 6. もう一度プレイボタン
**現在:** 緑系グラデーション（#00b894 → #00a085）  
**変更後:** ブルー系グラデーション
```css
background: linear-gradient(45deg, #4A90E2, #3B82F6);
box-shadow: 0 4px 15px rgba(74, 144, 226, 0.4);
```

### 7. その他のUI要素
- **input フォーカス**: オレンジ系（#FFA500）
- **timer/score 背景**: 薄いブルー系（rgba(74, 144, 226, 0.1)）
- **カードグリッド背景**: 薄い白（rgba(255, 255, 255, 0.2)）

## フォント設定

### 現在のフォント構成
```css
/* 基本フォント */
body {
  font-family: 'Arial', 'Hiragino Sans', 'Yu Gothic', sans-serif;
}

/* タイトル（h1） */
.game-header h1 {
  font-family: "Dela Gothic One", sans-serif;
}

/* カウントダウン */
.countdown {
  font-family: "Bungee", sans-serif;
}

/* モバイル時の本文 */
@media (max-width: 768px) {
  .game-controls {
    font-family: "Noto Sans JP", sans-serif;
  }
}
```

### JAWS DAYS 2026サイトとの比較
- **タイトルフォント**: Dela Gothic One ✓ 適切（太字ゴシック体）
- **本文フォント**: Noto Sans JP ✓ 適切（読みやすいゴシック体）
- **カウントダウン**: Bungee ✓ 適切（インパクトのある英字フォント）

### 推奨変更
**全体的に統一感を持たせるため、Noto Sans JPを基本フォントに設定**

```css
/* 基本フォント - Noto Sans JPに統一 */
body {
  font-family: 'Noto Sans JP', 'Hiragino Sans', 'Yu Gothic', sans-serif;
  font-weight: 400;
}

/* タイトル - 太字ゴシックを維持 */
.game-header h1 {
  font-family: "Dela Gothic One", sans-serif;
  font-weight: 400;
}

/* ボタン - 太字で強調 */
.start-button, .play-again-button {
  font-family: 'Noto Sans JP', sans-serif;
  font-weight: 700;
}

/* ランキング見出し - 太字 */
.ranking-section h2 {
  font-family: 'Noto Sans JP', sans-serif;
  font-weight: 700;
}

/* カウントダウン - インパクト重視 */
.countdown {
  font-family: "Bungee", sans-serif;
  font-weight: 400;
}
```

## アクセシビリティ・ユニバーサルデザイン対応

### 老眼対策・視認性向上

#### 1. フォントサイズの拡大
**現在の問題点:**
- タイマー・スコア表示: 1.1rem（約17.6px）
- ランキング: 標準サイズ
- ボタンテキスト: 1.2rem（約19.2px）

**改善案:**
```css
/* タイマー・スコア */
.timer, .score {
  font-size: 1.3rem;  /* 20.8px → より大きく */
  font-weight: 700;   /* より太く */
}

/* ランキング */
.ranking-item {
  font-size: 1.1rem;  /* 17.6px */
  line-height: 1.6;   /* 行間を広く */
}

/* ボタン */
.start-button, .play-again-button {
  font-size: 1.4rem;  /* 22.4px → より大きく */
  padding: 18px 40px; /* パディングも拡大 */
}

/* 名前入力欄 */
.player-name-input label {
  font-size: 1.2rem;  /* 19.2px */
}

.player-name-input input {
  font-size: 1.1rem;  /* 17.6px */
  padding: 12px 18px; /* より大きなタップ領域 */
}
```

#### 2. コントラスト比の向上
**WCAG 2.1 AA基準（4.5:1以上）を目指す**

```css
/* ヘッダータイトル */
.game-header h1 {
  color: #1a1a1a;  /* より濃い黒（現在: #333333） */
}

/* タイマー・スコア */
.timer, .score {
  color: #1a1a1a;  /* より濃い黒 */
  background: rgba(74, 144, 226, 0.15);  /* 背景を少し濃く */
}

/* ランキングテキスト */
.ranking-item {
  color: #1a1a1a;  /* より濃い黒 */
}

/* ボタンテキスト */
/* 白背景に対して十分なコントラストを確保 */
```

#### 3. 視覚的な区別の強化

**カードの視認性向上:**
```css
/* カード表面 */
.card-front {
  border: 3px solid #2c3e50;  /* 濃い枠線を追加 */
}

/* カード裏面 */
.card-back {
  border: 3px solid #2c3e50;  /* 濃い枠線を追加 */
}

/* マッチしたカード */
.card.matched {
  opacity: 0.6;
  border: 4px solid #27ae60;  /* 緑の太い枠線 */
}
```

**ボタンの視認性向上:**
```css
.start-button, .play-again-button {
  border: 2px solid rgba(0, 0, 0, 0.2);  /* 枠線を追加 */
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);  /* テキストに影 */
}
```

#### 4. インタラクション要素の拡大

**タップ/クリック領域の最小サイズ: 44x44px（WCAG推奨）**

```css
/* ボタン */
.start-button, .play-again-button {
  min-height: 48px;  /* 推奨より少し大きく */
  min-width: 120px;
}

/* 入力フィールド */
.player-name-input input {
  min-height: 48px;
}

/* カード */
/* 既に十分なサイズがあるため調整不要 */
```

#### 5. 色覚多様性への配慮

**色だけに依存しない情報伝達:**

```css
/* マッチしたカードにアイコンを追加 */
.card.matched::after {
  content: '✓';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 3rem;
  color: #27ae60;
  font-weight: bold;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
  z-index: 10;
}
```

**ランキングの順位を視覚的に強調:**

**デザイン問題の指摘:**
現在の実装では、1-3位にメダル絵文字が`::before`で追加されるだけで、4位以降は何もないため、視覚的な揃いが崩れます。

**解決策: すべての順位に統一デザイン（推奨）**

```css
/* すべての順位に円形バッジを表示 */
.ranking-item {
  display: flex;
  align-items: center;
  gap: 0.75em;
}

.ranking-item::before {
  content: attr(data-rank);
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 2.5em;
  height: 2.5em;
  border-radius: 50%;
  font-weight: 700;
  font-size: 0.9em;
  flex-shrink: 0; /* 幅を固定 */
}

/* 1位: ゴールドメダル */
.ranking-item:nth-child(1)::before {
  content: '🥇';
  background: rgba(255, 215, 0, 0.2);
  font-size: 1.2em;
}

/* 2位: シルバーメダル */
.ranking-item:nth-child(2)::before {
  content: '🥈';
  background: rgba(192, 192, 192, 0.2);
  font-size: 1.2em;
}

/* 3位: ブロンズメダル */
.ranking-item:nth-child(3)::before {
  content: '🥉';
  background: rgba(205, 127, 50, 0.2);
  font-size: 1.2em;
}

/* 4位以降: 数字バッジ */
.ranking-item:nth-child(4)::before {
  content: '4';
  background: rgba(255, 165, 0, 0.1);
  color: #1a1a1a;
}

.ranking-item:nth-child(5)::before {
  content: '5';
  background: rgba(255, 165, 0, 0.1);
  color: #1a1a1a;
}

.ranking-item:nth-child(6)::before {
  content: '6';
  background: rgba(255, 165, 0, 0.1);
  color: #1a1a1a;
}

.ranking-item:nth-child(7)::before {
  content: '7';
  background: rgba(255, 165, 0, 0.1);
  color: #1a1a1a;
}

.ranking-item:nth-child(8)::before {
  content: '8';
  background: rgba(255, 165, 0, 0.1);
  color: #1a1a1a;
}

.ranking-item:nth-child(9)::before {
  content: '9';
  background: rgba(255, 165, 0, 0.1);
  color: #1a1a1a;
}

.ranking-item:nth-child(10)::before {
  content: '10';
  background: rgba(255, 165, 0, 0.1);
  color: #1a1a1a;
}
```

**デザインの利点:**
- ✓ すべての順位が同じ構造で統一感がある
- ✓ 1-3位はメダルで特別感を出しつつ、4位以降も整然としている
- ✓ 円形バッジで視覚的に揃っている（すべて2.5em × 2.5em）
- ✓ アクセシビリティ的にも優れている（すべての順位が同じ構造）
- ✓ 老眼の方にも見やすい（大きな円形バッジ）

#### 6. フォーカス表示の強化

**キーボード操作時の視認性:**

```css
/* すべてのインタラクティブ要素 */
button:focus,
input:focus,
.card:focus {
  outline: 3px solid #FFA500;  /* オレンジの太い枠線 */
  outline-offset: 3px;
  box-shadow: 0 0 0 6px rgba(255, 165, 0, 0.3);
}
```

#### 7. アニメーション・動きの配慮

**カードめくりの反応速度:**

**現在の設定:**
```javascript
// game.js
CARD_FLIP_DELAY: 700,   // ミスマッチ時の裏返し待機(ms)
```

```css
/* styles.css */
.card-inner {
  transition: transform 0.6s ease-in-out;
}
```

**ユニバーサルデザイン視点での見直し:**

1. **カードめくりアニメーション（0.6秒）**
   - **現在**: 0.6秒（600ms）
   - **評価**: ✓ 適切
   - **理由**: 
     - 速すぎず遅すぎず、視認しやすい
     - 高齢者や視力の弱い方でも追いやすい
     - WCAG 2.1推奨の範囲内（0.5〜1.0秒）

2. **ミスマッチ時の待機時間（0.7秒）**
   - **現在**: 700ms
   - **推奨**: 1000ms（1秒）に延長
   - **理由**:
     - 高齢者や認知機能に配慮
     - カードの内容を確認する時間を確保
     - 焦らずゲームを楽しめる

**推奨変更:**
```javascript
// game.js
const GAME_CONFIG = {
  CARD_FLIP_DELAY: 1000,   // ミスマッチ時の裏返し待機(ms) - 700ms → 1000ms（推奨）
};
```

**実装判断:**
- 現在の700msで動作確認後、必要に応じて調整
- ユーザーテスト後に最適な値を決定

```css
/* styles.css - アニメーション速度は維持 */
.card-inner {
  transition: transform 0.6s ease-in-out; /* 適切な速度 */
}
```

**motion-reduce対応:**

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
  
  .card-inner {
    transition: none;
  }
}
```

**デザイン判断:**
- カードめくりアニメーション（0.6秒）は維持 ✓
- ミスマッチ時の待機時間を1秒に延長 ← 推奨
- motion-reduce対応でアクセシビリティ向上 ✓

### ユニバーサルデザインチェックリスト

- [x] フォントサイズの拡大（最小1.1rem以上）
- [x] コントラスト比の向上（4.5:1以上）
- [x] タップ領域の拡大（最小44x44px）
- [x] 色だけに依存しない情報伝達
- [x] フォーカス表示の強化
- [x] アニメーション削減オプション
- [x] 視覚的な区別の強化（枠線・影）

## 実装の優先順位

### Phase 1: 主要な色味変更（必須）
1. 背景色の変更
2. スタートボタンの色変更（オレンジ系）
3. ヘッダータイトルの色調整

### Phase 2: UI要素の調整（推奨）
4. ~~カード表面の色変更~~（専用画像使用のため不要）
5. ランキングのアクセントカラー変更
6. もう一度プレイボタンの色変更

### Phase 3: アクセシビリティ対応（重要）
7. フォントサイズの拡大
8. コントラスト比の向上
9. タップ領域の拡大
10. 視覚的な区別の強化
11. ~~カードめくり速度の調整~~（動作確認後に判断）

### Phase 4: 細部の調整（オプション）
12. input フォーカスカラー
13. timer/score の背景色
14. アニメーション削減対応
15. カードめくり速度の調整（必要に応じて）
16. その他の微調整

## 実装方法

1. `styles.css` の該当箇所を順次変更
2. 各変更後にブラウザで確認
3. 必要に応じて色の微調整

## 期待される効果

### 老眼・視力低下のある方への配慮
- フォントサイズ拡大により、文字が読みやすくなる
- コントラスト比向上により、要素の区別がしやすくなる
- タップ領域拡大により、誤操作が減る

### 色覚多様性のある方への配慮
- 色だけでなく、アイコンや枠線で情報を伝達
- マッチしたカードに✓マークを表示
- ランキングにメダル絵文字を追加

### すべてのユーザーへの利点
- より見やすく、使いやすいUI
- 疲れにくいデザイン
- 幅広い年齢層が楽しめる

## 承認待ち

この計画書をご確認いただき、以下をお知らせください：

1. **実装範囲の承認**
   - Phase 1のみ / Phase 1-2 / Phase 1-3（アクセシビリティ含む） / 全Phase実装

2. **色味の調整希望**
   - 提案した色コードで問題ないか
   - 特定の色を変更したい場合はご指示ください

3. **アクセシビリティ対応の優先度**
   - すべて実装 / 一部のみ / 後回し

4. **その他の要望**
   - 追加で変更したい箇所
   - 避けたい色や雰囲気
   - 特に重視したいアクセシビリティ機能

---

**ステータス**: 承認待ち  
**次のアクション**: ユーザーの承認を得て実装開始

**推奨**: Phase 1-3（色味変更 + アクセシビリティ対応）の実装を推奨します。JAWS DAYSのような技術イベントでは、インクルーシブなデザインが高く評価されます。
