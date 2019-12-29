## やれること
- S3で静的コンテンツ配信を行う一連の流れをAWSに構築する
- GitHub上のリポジトリからソースを取得してデプロイする

## 実行手順
1. GitHubのデプロイ対象に[buildspec.yaml](https://docs.aws.amazon.com/ja_jp/codebuild/latest/userguide/build-spec-ref.html)を作成する
2. template.yamlのParametersを任意の値に設定する
3. 以下どちらかの方法でCFnを実行する
  - CFnコンソール上で実行
  - Cloud9などのターミナル上で以下のコマンドを実行

```sh
aws cloudformation deploy --template template.yaml --stack codepipeline-s3-cfn --capabilities CAPABILITY_IAM
```

## TODO
- 特定リポジトリへマージが発生した時に自動でデプロイを走らせる