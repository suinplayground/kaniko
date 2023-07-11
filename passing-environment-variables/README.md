# Kaniko: ビルド時に環境変数を渡すデモンストレーション

## つかいかた

### Docker Hubにレポジトリを作ろう

kanikoを完全に動かすには、イメージのプッシュ先リポジトリが要るので、Docker Hubにアカウントを作って、リポジトリを作ってください。

### config.jsonを作ろう

config.dist.jsonをコピーする。

```bash
cp config.dist.json config.json
```

config.jsonの`auth`の中身を埋める。

```bash
echo -n docker_hubのユーザ名:docker_hubのパスワード | base64
```

```json
{
  "auths": {
    "https://index.docker.io/v1/": {
      "auth": "ここ埋める"
    }
  }
}
```

### justfileの変数を自分のものに書き換えよう

`destination`を自分のDocker Hubのアカウント名・リポジトリ名に置き換える。

```bash
destination := "suin/test:tagname"
```

### Kanikoでビルドしてみよう

```bash
just build
```

### ビルドしたやつをpullしてrunしてみよう

```bash
just run
```
