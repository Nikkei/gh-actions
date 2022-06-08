# aws-eb

DockerベースのアプリケーションをAWS Elastic Beanstalkへデプロイするためのカスタムアクション

## Description
### build-image

- dockerのカスタムアクションを利用しイメージをビルドするアクション
- cacheも自動的に行う

### init-eb

- EB環境を作成するアクション
  - 環境を作成するためにコンフィグの作成やLifecycleの設定も行う
- すでに目的の環境が作成済みの場合、特になにも行わない

### install-deploy-tools

- デプロイに必要なツール類をインストールする

### login-aws

- AWSのカスタムアクションを利用してAWSへの認証を行うアクション
- 上記だけだとEBのコマンドが動かないので、別途credentialファイルの作成も行う

### pre-deploy

- EBへデプロイするための前準備を行う
  - 設定ファイルの更新、拡張機能の追加等

### push-image

- ECRへdockerイメージをプッシュするアクション
  - ECRの作成及び設定の投入も行う
