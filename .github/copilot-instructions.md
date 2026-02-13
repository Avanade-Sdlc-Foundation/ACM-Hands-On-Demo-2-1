これは、ユーザーが旅行を検索し、予約を管理し、旅行ガイドを表示し、ポイントを追跡するのに役立つ TypeScript を使用した Next.js ベースの旅行アプリケーションです。アプリケーションは、Next.js App Router アーキテクチャの一部として React コンポーネント、サーバーコンポーネント、クライアントコンポーネントを使用しています。コントリビュートする際は、以下のガイドラインに従ってください：

## コード標準

### 各コミット前に必須
- プロジェクト標準に従ってコードを確認するため `npm run lint` を実行する
- すべてのコンポーネントが Next.js App Router パターンに従っていることを確認する
- クライアントコンポーネントは、ブラウザ API や React フックを使用する場合、'use client' でマークする必要がある
- 新しい機能を追加する場合、README を更新する
- Copilot Instructions ファイル内のリポジトリ構造ドキュメントが正確であることを確認する
- ターミナルで `npm run test` を実行してすべてのテストが合格することを確認する

### TypeScript と React のパターン
- すべてのプロパティとデータ構造に TypeScript インターフェース/タイプを使用する
- React のベストプラクティスに従う（フック、関数コンポーネント）
- 適切な状態管理テクニックを使用する
- コンポーネントはモジュール化され、単一責任原則に従う必要がある

### スタイリング
- できるだけ Tailwind CSS クラスを優先して使用する必要があります。必要に応じて、カスタム Tailwind クラス/スタイルを定義できます。カスタム CSS の作成は最後のアプローチにする必要があります。

## 開発フロー
- 依存関係のインストール: `npm install`
- 開発サーバー: `npm run dev`
- ビルド: `npm run build`
- テスト: `npm run test`
- Lint: `npm run lint`

## リポジトリ構造
- `app/`: ルートごとに整理された Next.js App Router ページとレイアウト
- `components/`: 再利用可能な React コンポーネント
  - `components/ui/`: UI コンポーネント（ボタン、入力など）
  - `components/__tests__/`: コンポーネントテスト
- `lib/`: コアロジックとサービス
  - `lib/data/`: データモデルとモックデータ
  - `lib/types/`: TypeScript 型定義
- `public/`: 静的アセット
- `tests/`: テストファイルとテストユーティリティ
- `README.md`: プロジェクトドキュメント

## 主要なガイドライン
1. 作成しているコンポーネントと、'use client' が必要かどうかを評価してください
2. 画像には、純粋に装飾用でない限り、意味のある alt テキストを含める必要があります。純粋に装飾用の場合は、スクリーンリーダーによって無視されるように、null（空）の alt テキストを提供する必要があります（alt=""）。
3. データフェッチ、ルーティング、レンダリングについては Next.js のベストプラクティスに従う
4. 適切なエラーハンドリングとローディング状態を使用する
5. パフォーマンスのためにコンポーネントとページを最適化する
6. カスタム情報: https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions,https://code.visualstudio.com/docs/copilot/copilot-customization#_reusable-prompt-files-experimental