# nextjs-sharing-code-monorepo

NextJS TypeScript プロジェクト間でコードを共有する方法を示すデモアプリケーションです。構築方法の詳細は[こちら](https://medium.com/weekly-webtips/sharing-code-between-nextjs-applications-2c0f3b415e1)をご覧ください。

## 仕組み

- [pnpm workspaces](https://pnpm.io/workspaces) を使用して、2 つの NextJS アプリケーションと共有パッケージを含む「モノレポ」を作成します
- Next.js バージョン 13 以降では、[`transpilePackages` オプション](https://beta.nextjs.org/docs/api-reference/next.config.js#transpilepackages) を使用できます。

## 始め

1. `pnpm i` で依存関係をインストールします
2. `pnpm dev:all` で両方のアプリケーションを起動します
3. `localhost:3001` と `localhost:3002` でアプリケーションを表示します

コード共有はフロントエンドとバックエンド（API）コードの両方で示されています：

- `app-1` のホームページは `app-1/pages/index.js` で定義されており、`app-2` の `openApp2` コンポーネントを使用しています。これは `localhost:3001` で動作しているのを見ることができます
- `app-1` の 'hello' API ルートは `app-1/pages/api/hello.tx` で定義されており、`app-2` の `sayHello` 関数を使用しています。これは `localhost:3001/api/hello` で動作しているのを見ることができます
