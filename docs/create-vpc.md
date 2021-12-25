# AWS における VPC の作成

AWSにおいて、インスタンスを動作させるために必要なネットワークの作成を行います。

自動化スクリプトを用意していますので、そちらを利用します。動作環境は次のとおりですので、事前に準備が必要となります。

- Git
- Make
- Node.js
- Yarn または NPM


## スクリプトの実行

- Git リポジトリをクローンします。

```sh
git clone https://github.com/latonaio/sap-s4hana-on-premise-installation-on-aws-create-vpc.git
```

- Yarn または NPM にてクローンしたディレクトリにパッケージをインストールします。

```sh
yarn
```

- スクリプトを実行します。`example-vpc` という名前の VPC が作成されます。

```sh
make deploy target="vpc"
```
