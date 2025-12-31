# レンタカー予約システム フロントエンド

株式会社ビップオート様向けレンタカー予約サイトのフロントエンド（HTML/CSS/JavaScript）

## 📁 ファイル構成

```
rental-car-frontend/
├── index.html              # トップページ
├── reservation.html        # 予約フォーム
├── mypage.html            # マイページ
├── custom.css             # 共通カスタムCSS（黄色テーマ）
├── reservation.css        # 予約フォーム用CSS
├── mypage.css             # マイページ用CSS
├── custom.js              # 共通JavaScript
├── reservation.js         # 予約フォーム用JavaScript
├── mypage.js              # マイページ用JavaScript
└── README.md              # このファイル
```

## 🎨 デザイン仕様

- **ブランドカラー**: 黄色（#FFD700）
- **サブカラー**: オレンジ（#FFA500）
- **参考サイト**: https://kobaccaribou-iwade.com/
- **レスポンシブ対応**: PC/タブレット/スマートフォン

## ✨ 実装済み機能

### 1. トップページ（index.html）
- ヘッダーナビゲーション（ログイン・マイページボタン追加）
- メインビジュアル
- 車両クラス紹介・料金表
- 免責保証プラン（アコーディオン形式）
- ご利用の流れ
- よくある質問
- 店舗情報
- フローティング予約ボタン

### 2. 予約フォーム（reservation.html）
**5ステップの予約フロー**:
- ステップ1: 車両選択（軽自動車/商用車）
- ステップ2: 日程・期間選択、免責保証選択
- ステップ3: お客様情報入力
- ステップ4: 予約内容確認、支払い方法選択
- ステップ5: 予約完了

**機能**:
- 進捗バー表示
- リアルタイム料金計算
- フォームバリデーション
- レスポンシブ対応

### 3. マイページ（mypage.html）
**予約履歴**:
- 予約一覧表示
- 予約詳細モーダル
- キャンセル機能（キャンセルポリシー表示）
- ステータス表示（予約確定/利用完了/キャンセル済み）

**登録情報編集**:
- 個人情報の編集
- パスワード変更
- アカウント削除

## 🔧 セットアップ手順

### 1. 必要なファイルの準備

参考サイトから以下のファイルを取得してください:
```
css/
  ├── all.css
  ├── all_min.css
  ├── style.css
  ├── style_min.css
  ├── style_1__min.css
  └── add.css

js/
  ├── jquery-3_4_1_min.js
  ├── app_min.js
  └── add.js

images/
  ├── logo.png              # ロゴ（制作予定）
  ├── main-visual.jpg       # メインビジュアル
  ├── car-kei.jpg           # 軽自動車画像
  ├── car-van.jpg           # 商用車画像
  ├── price-title.png       # 料金表タイトル
  ├── insurance-title.png   # 保険タイトル
  ├── flow-title.png        # 流れタイトル
  ├── faq-title.png         # FAQタイトル
  ├── shop-title.png        # 店舗情報タイトル
  ├── check-icon.png        # 完了アイコン
  ├── reserve-btn.png       # 予約ボタン
  └── tel-btn.png           # 電話ボタン
```

### 2. ディレクトリ構成

```
your-project/
├── index.html
├── reservation.html
├── mypage.html
├── login.html              # ログイン画面（未実装）
├── css/
│   ├── all.css
│   ├── style.css
│   ├── add.css
│   ├── custom.css         # 今回作成
│   ├── reservation.css    # 今回作成
│   └── mypage.css         # 今回作成
├── js/
│   ├── jquery-3_4_1_min.js
│   ├── app_min.js
│   ├── add.js
│   ├── custom.js          # 今回作成
│   ├── reservation.js     # 今回作成
│   └── mypage.js          # 今回作成
└── images/
    └── (上記の画像ファイル)
```

### 3. HTMLファイルの配置

1. 本リポジトリの HTML/CSS/JS ファイルをプロジェクトルートにコピー
2. 参考サイトの css/, js/, images/ フォルダを配置
3. ブラウザで index.html を開いて動作確認

## 📝 次のステップ（未実装機能）

### 優先度：高

1. **ログイン画面（login.html）**
   - メールアドレス・パスワード入力
   - 会員登録リンク
   - パスワードリセット

2. **会員登録画面**
   - 新規アカウント作成フォーム
   - メール認証

3. **Stripe決済画面**
   - クレジットカード情報入力
   - 3Dセキュア対応

### 優先度：中

4. **管理画面（admin.html）**
   - 予約一覧（カレンダー/リスト表示）
   - 車両管理
   - 料金設定
   - FAQ・店舗情報編集
   - 会員管理

5. **パスワード変更画面**
   - 現在のパスワード確認
   - 新しいパスワード入力

6. **画像素材の差し替え**
   - ロゴ制作後の差し替え
   - 実際の車両画像への差し替え

## 🔌 バックエンド連携（未実装）

以下のAPIエンドポイントが必要です:

### 認証関連
- `POST /api/auth/register` - 会員登録
- `POST /api/auth/login` - ログイン
- `POST /api/auth/logout` - ログアウト
- `POST /api/auth/reset-password` - パスワードリセット

### 予約関連
- `GET /api/vehicles` - 車両一覧取得
- `GET /api/vehicles/:id/availability` - 在庫確認
- `POST /api/reservations` - 予約作成
- `GET /api/reservations/:id` - 予約詳細取得
- `GET /api/users/:id/reservations` - ユーザーの予約一覧
- `DELETE /api/reservations/:id` - 予約キャンセル

### ユーザー関連
- `GET /api/users/:id` - ユーザー情報取得
- `PUT /api/users/:id` - ユーザー情報更新
- `DELETE /api/users/:id` - アカウント削除

### 決済関連
- `POST /api/payments/stripe/session` - Stripe決済セッション作成
- `POST /api/payments/stripe/webhook` - Stripe Webhook

### 管理画面関連
- `GET /api/admin/reservations` - 予約一覧
- `PUT /api/admin/vehicles/:id` - 車両情報更新
- `PUT /api/admin/settings` - 設定更新

## 💡 カスタマイズポイント

### 色の変更
`custom.css` の `:root` 変数を編集:
```css
:root {
    --primary-color: #FFD700;    /* メインカラー */
    --primary-dark: #FFA500;     /* 濃いカラー */
    --secondary-color: #333333;  /* テキストカラー */
    --danger: #FF0210;           /* 警告カラー */
}
```

### 料金の変更
`reservation.js` の `vehiclePrices` オブジェクトを編集:
```javascript
const vehiclePrices = {
    'kei': {
        name: '軽自動車クラス',
        '10': 25000,  // 10日間料金
        '20': 45000,  // 20日間料金
        '30': 60000   // 30日間料金
    }
};
```

### 保険料金の変更
`reservation.js` の `insurancePrices` オブジェクトを編集:
```javascript
const insurancePrices = {
    'bronze': 1100,  // 1日あたり
    'silver': 2200,
    'gold': 3300
};
```

## 📱 レスポンシブ対応

- **PC**: 1200px以上
- **タブレット**: 768px〜1199px
- **スマートフォン**: 〜767px

各画面でブレークポイントを設定し、最適なレイアウトを実現。

## 🚀 デプロイ前のチェックリスト

- [ ] すべての画像ファイルを配置
- [ ] ロゴ画像を実際のものに差し替え
- [ ] 料金・車両情報を実際のものに更新
- [ ] 店舗情報（住所・電話番号・営業時間）を確認
- [ ] Google Map の埋め込みコードを正しい座標に更新
- [ ] FAQの内容を実際のものに差し替え
- [ ] SSL証明書の設定（HTTPS化）
- [ ] Xサーバーへのアップロード

## 📞 お問い合わせ

株式会社ビップオート  
住所: 和歌山県岩出市中島804-2  
電話: 0736-62-1122  
営業時間: 9:00〜18:00（水曜定休）

---

**作成日**: 2024年12月27日  
**バージョン**: 1.0.0  
**制作**: 千歳開発
