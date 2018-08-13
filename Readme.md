# 概要

gitlabとgitlab-runnerをローカルで気軽に試すための環境をDockerで実現する

# 起動方法

1. 以下のコマンドで起動する

```
> docker-compose up -d
```

# Runnerにジョブを登録

https://docs.gitlab.com/runner/register/index.html

1. Runnerにジョブを登録
```
> docker exec -it gitlab-runner gitlab-runner register
```
2. Gitlab URLの入力

URLはgitlabのリンク名(docker-composeで定義されているlinks)を使用する

```
Please enter the gitlab-ci coordinator URL (e.g. https://gitlab.com )
> http://gitlab/
```