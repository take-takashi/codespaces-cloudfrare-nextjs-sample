# codespaces-cloudfrare-nextjs-sample

Cloudfrare に Next.js をデプロイするサンプル

# 試した結果結論

- Next13 は 2022/11/08 現在、Cloudfrare pages にデプロイできない。

  なので Next12 にダウングレードする。

- api routes を Edge runtime 用に書き換える。
- node のバージョンを 17.6.0 にする。（node18 が 2022/11/08 時点デプロイエラーのため）

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

### .node-version ファイルで NODE のバージョンを指定する

```
# nextプロジェクトのルートに配置すること
echo 17.6.0 >> frontend/nextapp/.node-version
```

# 参考 URL

- [Cloudflare Pages で Next.js の Edge Runtime がサポートされました \| DevelopersIO](https://dev.classmethod.jp/articles/cloudflare-pages-support-nextjs-edge-runtime/)
