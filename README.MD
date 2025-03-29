# ドローン空撮画像から洪水を見つける（Cohere Multimodal Embed 3）

このプロジェクトは、Cohere 社のマルチモーダル埋め込みモデルの Cohere Embed を使って、FloodNet Datasetの画像を洪水とそうでないものに分類するものです。

## プロジェクト構成

- `100_generate_image_labels.ipynb`: 画像のラベル生成を行うノートブック
- `200_generate_image_embeddings.ipynb`: 画像の埋め込みベクトルを生成するノートブック
- `300_classify_image.ipynb`: 画像の分類を実行するノートブック
- `datasets/`: 画像データセットを格納するディレクトリ
- `with_output/`: （参考）出力結果を残したノートブックを格納したディレクトリ

## 必要な環境

- Python 3.11.9
- 仮想環境（.venv）の使用を推奨

## セットアップ

1. リポジトリをクローン
2. 仮想環境を作成し、アクティベート
3. 依存パッケージのインストール:
   ```bash
   pip install -r requirements.txt
   ```
4. `.env_sample`を`.env`にコピーし、必要な環境変数を設定
   - COHERE_API_KEY: Cohere APIのキー
   - COHERE_EMBED_MODEL_ID: 使用する埋め込みモデルのID

## データセットのダウンロード
- 下記で公開されているFloodNet Datasetをダウンロードします。
　https://github.com/BinaLab/FloodNet-Supervised_v1.0
　（Dataset Details の Dropbox のリンクからダウンロードします。）
- ダウンロードしたデータセットを`datasets/floodnet/`ディレクトリに格納します。

## 使用方法

1. `100_generate_image_labels.ipynb`を実行して画像のラベルを生成
2. `200_generate_image_embeddings.ipynb`を実行して画像の埋め込みベクトルを生成
3. `300_classify_image.ipynb`を実行して画像の分類を実行

## 出力ファイル

- `labels.csv`: 生成された画像ラベル
- `image_embeddings.csv`: 生成された画像の埋め込みベクトル

## 注意事項

- Cohere APIの利用には有効なAPIキーが必要です

