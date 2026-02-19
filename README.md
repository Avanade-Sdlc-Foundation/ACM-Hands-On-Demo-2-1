# TravelApp - Next.js トラベルアプリケーション

Next.js、TypeScript、Tailwind CSS で構築された包括的な旅行アプリケーションです。ユーザーが旅行の検索、予約の管理、旅行ガイドの閲覧、ロイヤルティポイントの追跡を行うことができます。

## 機能

- **旅行検索＆予約**: 高度なフィルタリング機能でキュレーションされた旅行体験を閲覧・検索
- **旅行ガイド**: 目的地のエキスパートアドバイスとローカルな洞察
- **予約管理**: 旅行予約の表示と管理
- **ロイヤルティポイントシステム**: 予約ごとにポイントを獲得・追跡
- **レスポンシブデザイン**: すべてのデバイスで動作するモバイルファーストデザイン
- **モダンUI**: Tailwind CSS で構築されたクリーンでアクセシブルなインターフェース

## 技術スタック

- **フレームワーク**: Next.js 14 with App Router
- **言語**: TypeScript
- **スタイリング**: Tailwind CSS
- **テスト**: Jest + React Testing Library
- **リント**: ESLint with Next.js configuration

## 使い始め方

### 前提条件

- Node.js 18+ 
- npm または yarn パッケージマネージャー

### インストール

1. リポジトリをクローン:
```bash
git clone <repository-url>
cd copilot-agent-demo
```

2. 依存関係をインストール:
```bash
npm install
```

3. 開発サーバーを起動:
```bash
npm run dev
```

4. ブラウザで [http://localhost:3000](http://localhost:3000) を開く

## Docker サポート

### Docker でのクイックスタート

Docker Compose を使用してアプリケーションを実行:

```bash
# 本番バージョンをビルドして実行
docker-compose up --build

# ホットリロード機能付きの開発バージョンを実行
docker-compose --profile dev up --build travel-app-dev
```

### 手動 Docker コマンド

```bash
# Docker イメージをビルド
docker build -t travel-app .

# コンテナを実行
docker run -p 3000:3000 travel-app

# ホットリロード機能付きの開発用
docker build -f Dockerfile.dev -t travel-app-dev .
docker run -p 3000:3000 -v $(pwd):/app -v /app/node_modules travel-app-dev
```

### GitHub Package Registry

アプリケーションは以下の場合に自動的にビルドされ、GitHub Package Registry にプッシュされます:
- `main` または `develop` ブランチへのプッシュ
- タグ付きリリース
- `main` へのプルリクエスト

最新のイメージを取得:
```bash
docker pull ghcr.io/ravi-cheetiralaav/copilot-agent-demo:main
```

## 開発スクリプト

- `npm run dev` - 開発サーバーを起動
- `npm run build` - 本番用ビルド
- `npm run start` - 本番サーバーを起動
- `npm run lint` - ESLint を実行
- `npm run test` - テストを実行
- `npm run test:watch` - ウォッチモードでテストを実行

## プロジェクト構造

```
app/                    # Next.js App Router ページとレイアウト
├── layout.tsx         # ルートレイアウトコンポーネント
├── page.tsx           # ホームページ
├── trips/             # 旅行関連ページ
├── guides/            # 旅行ガイドページ
├── bookings/          # 予約管理ページ
├── points/            # ロイヤルティポイントページ
└── globals.css        # グローバルスタイル

components/             # 再利用可能なReactコンポーネント
├── ui/                # 基本UIコンポーネント（ボタン、入力など）
├── layout/            # レイアウトコンポーネント（ヘッダー、フッター）
├── trips/             # 旅行固有のコンポーネント
├── guides/            # ガイド固有のコンポーネント
├── bookings/          # 予約固有のコンポーネント
└── __tests__/         # コンポーネントテスト

lib/                   # コアロジックとサービス
├── types/             # TypeScript 型定義
├── data/              # モックデータとデータモデル
├── services/          # データサービス関数
└── utils.ts           # ユーティリティ関数

public/                # 静的アセット
tests/                 # テストファイルとテストユーティリティ
```

## 機能概要

### 旅行検索
- 目的地、カテゴリー、価格、期間、評価による高度フィルタリング
- 詳細情報付きのインタラクティブな旅行カード
- 予約インターフェース付きの個別旅行詳細ページ

### 旅行ガイド
- エキスパートが執筆した目的地ガイド
- タグベースの分類
- 画像と読了時間見積もり付きのリッチコンテンツ

### 予約管理
- ステータストラッキング付きの全予約表示
- 確認付き予約キャンセル
- 特別リクエストを含む詳細予約情報

### ロイヤルティポイントシステム
- 予約金額に基づくポイント獲得（1ドルにつき1ポイント）
- メンバーシップティア: ブロンズ、シルバー、ゴールド、プラチナ
- 進捗追跡と特典概要
- ボーナスポイント機会

## コード標準

### TypeScript
- 厳密な型指定を有効化
- すべての props とデータ構造にインターフェース使用
- 適切な型のエクスポートとインポート

### React パターン
- フック付き関数コンポーネント
- データフェッチング用サーバーコンポーネント
- 'use client' ディレクティブでマークされたクライアントコンポーネント
- 適切な関心の分離

### スタイリングガイドライン
- Tailwind CSS クラスを優先
- 一貫したスペーシングと色スキーム
- レスポンシブデザインパターン
- アクセシビリティの考慮

### テスト
- Next.js 用 Jest 設定
- コンポーネントテスト用 React Testing Library
- サービス層ユニットテスト
- 重要なパスのテストカバレッジ

## 開発ガイドライン

### 各コミット前に
1. `npm run lint` を実行してコード標準を確認
2. `npm run test` を実行してすべてのテストが通ることを確認
3. コンポーネントが Next.js App Router パターンに従っていることを確認
4. 新機能を追加する場合はドキュメントを更新

### コンポーネント開発
- すべての props に TypeScript インターフェースを使用
- 単一責任原則に従う
- 適切なエラーハンドリングとローディング状態を実装
- 画像に意味のある alt テキストを含める
- パフォーマンスを最適化

### 新機能追加
1. `lib/types/` で型を作成
2. `lib/data/` でモックデータを追加
3. `lib/services/` でサービス関数を実装
4. `components/` で再利用可能なコンポーネントを作成
5. `app/` ディレクトリでページを構築
6. 新機能のテストを追加
7. この README を更新

## API 構造

アプリケーションはバックエンド API をシミュレートするためにモックデータとサービス関数を使用します。主要サービス:

- **TripService**: 旅行検索、旅行詳細取得、注目の旅行
- **GuideService**: 旅行ガイドの取得、目的地によるフィルタリング
- **BookingService**: 予約作成、ユーザー予約管理

## コントリビューション

1. 確立されたコードパターンに従う
2. TypeScript strict モードの準拠を維持
3. 新しいコンポーネントと関数にテストを追加
4. 新機能のドキュメントを更新
5. レスポンシブデザインの実装を確保

## ライセンス

このプロジェクトは、Next.js とモダンな Web 開発プラクティスを紹介するデモアプリケーションの一部です。
