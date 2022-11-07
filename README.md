# codespaces-cloudfrare-nextjs-sample

Cloudfrare に Next.js をデプロイするサンプル

## frontend setup

```
mkdir frontend && cd frontend/
npx create-next-app@12.3.2 nextapp --ts --use-npm
```

### 一応バージョンダウンの方法

```
cd frontend/nextapp/
npm remove next
npm install next@12.3.2
```

### ここまでを frontend@next12 にリネーム

```
mv frontend frontend@next12
# cloudfrareのNODE_VERSIONを17.6.0に変更したらデプロイできた。
```

## Nextjs13 でテスト

```
mkdir frontend && cd frontend/
npx create-next-app nextapp --ts --use-npm
mv frontend frontend@next13error
# やっぱりNext.js 13ではエラーでcloudfrareにデプロイできない。
```

### 動くバージョンに戻る

```
mv frontend@next12 frontend
```

### .node_version ファイルで NODE のバージョンを指定する

```
echo 17.6.0 >> frontend/nextapp/.node_version
```
