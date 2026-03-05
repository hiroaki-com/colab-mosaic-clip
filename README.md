# Colab Mosaic Clip

[![Python](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Colab](https://img.shields.io/badge/platform-Google%20Colab-orange.svg)](https://colab.research.google.com/github/hiroaki-com/colab-mosaic-clip/blob/main/mosaic_clip_ja.ipynb)
[![FFmpeg](https://img.shields.io/badge/FFmpeg-compatible-blueviolet.svg)](https://ffmpeg.org/)

[English](./README_EN.md) | 日本語

https://github.com/user-attachments/assets/0c5b0ee4-e73c-4e62-8fac-a351ec8fb391

### 概要

Google Colab 環境で動画の任意の時間範囲・位置に、モザイクまたは単色マスクをかけて MP4 で出力するツールです。インストール不要・無料で使えます。

対応入力形式: `.mov` `.mp4` `.avi` `.mkv` `.webm`

#### 主な機能

- 動画プレイヤー上で開始・終了秒をボタン一発で記録
- フレーム画像をクリックしてモザイク位置を直感的に指定
- モザイクと単色マスク（任意色）の 2 種類のパターン
- 複数箇所への同時適用、追加・移動・リサイズ・取り消しに対応
- 仕上がりをその場でプレビュー確認
- ローカルダウンロードまたは Google Drive への保存

#### 対象ユーザー

- スクリーンショット・画面録画に映り込んだ個人情報を手軽に消したい開発者
- ffmpeg コマンドを書かずにモザイク処理を済ませたいエンジニア
- デモ動画や技術記事用の動画から機密情報を除去したいテクニカルライター
- アカウント情報・APIキーなどが写った動画を SNS に投稿したい方

---

### クイックスタート

#### 実行環境

```
https://colab.research.google.com/github/hiroaki-com/colab-mosaic-clip/blob/main/mosaic_clip_ja.ipynb
```

> CPU ランタイムで動作します。GPU は不要です。

#### 基本的な実行手順

1. Google Colab でノートブックを開きます
2. セットアップを実行します（初回のみ）
3. 動画ファイルをアップロードします
4. 動画を再生し、モザイクをかけたい開始・終了秒を記録します
5. フレーム画像をクリックしてモザイク位置を指定します
6. 出力横幅・保存先を設定して書き出しを実行します
7. プレビューで仕上がりを確認します
8. ローカルまたは Google Drive に保存します

---

### モザイク指定の操作

| 操作 | 動作 |
|---|---|
| ➕ ON 状態でクリック | モザイク枠を新規追加（追加後は自動で OFF） |
| 枠内ドラッグ | モザイク枠を移動 |
| 右下□ドラッグ | モザイク枠をリサイズ |
| ↩ 1つ戻す | 直前に追加した枠を削除 |
| 🗑 全消去 | すべての枠をリセット |
| 👁 配色を確認 | モザイク適用後の仕上がりをプレビュー |

複数箇所に枠を追加すれば、1 回の書き出しでまとめて処理できます。

---

### モザイクパターン

| パターン | 説明 | 向いている用途 |
|---|---|---|
| モザイク | 指定ブロックサイズでピクセル化 | 顔・文字など、ぼかしで隠したい場合 |
| 単色 | 任意の色で塗りつぶし | 完全に隠したい場合（黒塗り・グレーなど） |

#### 粒度（モザイクのみ）

| 粒度値 | 見た目 |
|:---:|---|
| 小（2〜8 付近） | 細かいモザイク |
| 大（20〜40 付近） | 粗いモザイク |

---

### 書き出し設定

| 項目 | 設定範囲 | 備考 |
|---|---|---|
| 出力形式 | MP4 (H.264) | 音声付きで出力（元動画に音声がある場合） |
| 出力横幅 | 240px 〜 1920px | 縦横比は自動維持 |
| モザイク適用範囲 | 開始秒 〜 終了秒 | 開始 = 終了のとき 1 フレームのみ処理 |

---

### 保存オプション

| 保存先 | 説明 |
|---|---|
| ローカルにダウンロード | ブラウザのダウンロードダイアログで保存 |
| Google Drive に保存 | 指定パスへ自動コピー（マウント込み） |
| 両方 | 上記を同時に実行 |

---

### 技術スタック

- Runtime: Google Colab (Python 3.10+)
- 変換エンジン: FFmpeg
- UI: ipywidgets
- 画像処理: Pillow
- Storage: Google Drive API / ローカルダウンロード

---

### ライセンス

MIT License. 詳細は [LICENSE](LICENSE) を参照してください。

### クレジット

- [FFmpeg](https://ffmpeg.org/) - 動画変換エンジン
- [Google Colab](https://colab.research.google.com/) - 無料実行環境
- [Pillow](https://python-pillow.org/) - 画像処理ライブラリ

### サポート

- バグ報告: [Issues](https://github.com/hiroaki-com/colab-mosaic-clip/issues)
- 質問・議論: [Discussions](https://github.com/hiroaki-com/colab-mosaic-clip/discussions)
