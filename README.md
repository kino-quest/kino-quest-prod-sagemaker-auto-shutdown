# Sagemaker Studio AutoShutDownのセットアップ方法

## 前提

次のバージョンで動作確認をしています。

- sagemaker_studio_autoshutdown
  - 0.1.5
- JupyterLab
  - 3.3.4

## ターミナルを起動

`File -> New -> Terminal` からターミナルを起動します。

## conda を起動

以下のコマンドをコピペして実行します。

```bash
conda activate studio
```

## JupyterLabのバージョンを確認

以下のコマンドをコピペして実行します。

```bash
jupyter lab --version
```

バージョンが`3.3.4`であることを確認します。

## GitHub からリポジトリを取得

```bash
git clone https://github.com/kino-quest/kino-quest-prod-sagemaker-auto-shutdown.git
```

カレントディレクトリを変更します。

```bash
cd kino-quest-prod-sagemaker-auto-shutdown
```

## auto-shutdownのextensionをセットアップ - シェルスクリプトを実行

以下のコマンドをコピペして実行します。

```bash
cp ./on-jupyter-server-start.sh ../
cd ..
./on-jupyter-server-start.sh
```

実行が終わると現在利用しているターミナルが閉じます。

## ターミナルを起動

`File -> New -> Terminal` からターミナルを起動します。

## タイムアウト時間を設定 - シェルスクリプトを実行

以下のコマンドをコピペして実行します。

```bash
conda activate studio
./.auto-shutdown/set-time-interval.sh
```

なお、タイムアウト時間は60分に設定していますが、このスクリプトを修正して再度このコマンドを実行することで
タイムアウト時間の再設定が可能です。
