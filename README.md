# lofree-frontend

ローカルフリーマーケットアプリ「lofree」のフロントエンドプロジェクト（Next.js 製）です。

---

## 前提（開発環境）

※wsl2Ubuntu 上に npx,npm のインストール済み

- OS：WSL2 + Ubuntu 22.04.3 LTS
- Node.js：v22.14.0
- npm：v10.9.2
- npx：v10.9.2

---

## 使用技術（バージョン）

- Next.js：v14.2.3（App Router 構成）
- React：v18.3.1
- TypeScript：v5.4.5
- ESLint：v8.57.0（eslint-config-next v15.3.1）
- Prettier：v3.5.3
- Tailwind CSS：バージョンの互換性で導入に失敗したため、今回はcss Modules
- Stylelint：v15.10.3
- Vercel：GitHub 連携で自動デプロイ
- eslint@8.57.0 \
- eslint-config-next@15.3.1 \
- @typescript-eslint/eslint-plugin@6.21.0 \
- @typescript-eslint/parser@6.21.0 \
- eslint-config-prettier@9.1.0 \
- eslint-plugin-prettier@5.1.3 \
- stylelint-config-standard@34.0.0 \
- husky@9.0.11 \
- lint-staged@15.2.2
- 互換性で手こずったぞ！！

---

## 構築手順

```bash
# 依存パッケージのインストール
npm install
# サーバ起動
npm run dev
```

プロジェクト直下に `.env.local` ファイルを作成してください：

```bash
cp .env.example .env.local
```

```.env.local
NEXT_PUBLIC_API_URL=http://localhost:8000/api
```

※ 本番環境では Vercel の GUI から Environment Variables に同様の値を登録

## 起動確認

ローカル開発 URL：http://localhost:3000
Laravel API との連携：http://localhost:8000/api

## 備考

```bash
# Lint/Formatチェック
npm run lint
# .env.local 設定例
NEXT_PUBLIC_API_URL=http://localhost:8000/api

# Stylelint によるCSS/SCSS ファイルの構文チェックと自動修正
npm run lint
# Prettier によるコード整形
npm run format
# ESLint によるTypeScript / JSX コードの静的解析と自動修正
npm run stylelint
```

## 🌐 デプロイ環境

- ホスティング：Vercel
- URL：https://lofree-frontend.vercel.app/
- 自動デプロイ：main ブランチへの push で自動反映（GitHub Actions不要）

## 🔐 環境変数（Vercel設定）

vercel GUI

- NEXT_PUBLIC_API_URL=https://api.lofree.app
  local
- NEXT_PUBLIC_API_URL=http://localhost:8000/api

## 現在（20250601）フロントエンド勉強不足

- 環境の切り分けについて理解が甘い。（githubとvercelやCircleCIの連携など、どの環境でデプロイしてるかの理解）
-

## 今後の手順（一旦ローカルで進めるぞ）

インフラ環境構築（Vercel設定やCircleCI、AWSなど）に時間かかりすぎてやる気なくなるから、
最小限（ローカル）開発できるようにしたら、早速開発に移る。
※AWS、CircleCI、Laravel APIレスポンス、マイグレーションは後回し。

6/1やること（機能追加前まで）
・CSSを適用
・ESLintなどの整備
・Laravel APIレスポンスポリシー作成
・Docker-Desktopインストール
