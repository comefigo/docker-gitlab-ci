# 概要

gitlabとgitlab-runnerをローカルで気軽に試すための環境をDockerで実現する

# 起動方法

1. 以下のコマンドで起動する
    ```
    > docker-compose up -d
    ```
2. 起動後、http://localhost にアクセス
3. パスワードの設定
4. ユーザ名：root / パスワード：3で設定したパスワードでログイン

# GitlabとRunnerの連携

CI/CDしたいプロジェクトとRunnerの連携設定

https://docs.gitlab.com/runner/register/index.html

1. Runnerの登録
```
> docker exec -it gitlab-runner gitlab-runner register
```
2. Gitlab URLの入力

URLはgitlabのリンク名(docker-composeで定義されているlinks)を使用する

```
Please enter the gitlab-ci coordinator URL (e.g. https://gitlab.com )
> http://gitlab/
```
3. プロジェクトの「Settings」-「CI/CD」-「General piplines」-「Runner token」で新規Tokenの発行し、プロンプトに入力
4. タグ付け  
    特定のタグがついたrunnerを実行することができる
5. 実行モードを選択

# .gitlab-ci.yml

gitlab-runnerはリポジトリルートにある`.gitlab-ci.yml`を参照し、タスクを実行する

※.gitlab-ci.yml
- http://cwfdev/gitlab/help/ci/quick_start/README
- http://cwfdev/gitlab/help/ci/yaml/README.md