# codespaces-cloudfrare-nextjs-sample

Cloudfrare に Next.js をデプロイするサンプル

## frontend setup

```
mkdir frontend && cd frontend/
npx create-next-app nextapp --ts --use-npm
cd nextapp/
npm i -D prettier eslint-config-prettier
```

## codespaces setup

```
互換性フラグに以下の設定を追加
streams_enable_constructors, transformstream_enable_standard_constructor
```
