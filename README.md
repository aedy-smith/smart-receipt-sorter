# 🧾 Smart Receipt Sorter (レシート自動整理ツール)

レシート画像・PDFから「日付・金額・取引先」を自動抽出し、  
フォルダ分け＆ファイル名リネームまで行うPythonツールです。

---

## 🚀 概要

このツールはOCR（Tesseract）とLLMを組み合わせて、  
レシートの情報を自動で整理します。

### 🔧 主な機能

- 📄 PDF / 画像（jpg, png）対応
- 🔍 OCRによる文字抽出
- 🧠 AIによる情報解析（取引日・金額・取引先）
- 📂 月ごとのフォルダ自動作成
- 🏷️ ファイル名の自動リネーム
- 🇯🇵 和暦 → 西暦変換対応

---

## 🧠 処理の流れ

1. PDF / 画像を読み込み
2. OCRでテキスト抽出
3. LLMで「日付・金額・取引先」を解析
4. ファイル名を生成
5. 月ごとのフォルダに整理

## 🖥️ 動作イメージ


input_box/
└─ receipt1.jpg

↓ 実行

archive/
└─ 2026-04/
└─ 2026-04-12_取引先_1200.pdf

---

## ⚙️ 使用技術

- Python
- pytesseract（OCR）
- pdf2image
- Pillow (PIL)
- LangChain
- Ollama（LLM）

---

## 🛠️ セットアップ

### ① 必要ライブラリ

bash
pip install pytesseract pdf2image pillow langchain langchain-ollama
② 外部ツールのインストール
■ Tesseract OCR

画像から文字を抽出するために使用します。

■ Poppler

PDFを画像に変換するために使用します。

③ パス設定
pytesseract.pytesseract.tesseract_cmd = r'YOUR_PATH'
POPPLER_PATH = r'YOUR_PATH'

※ パスは各自のインストール先に依存します

▶️ 実行方法
python main.py
📌 使い方
input_box フォルダにレシート（PDF / 画像）を入れる
スクリプトを実行
archive フォルダに自動整理される
💡 工夫したポイント
OCRだけでは不安定な情報抽出をLLMで補完
日本のレシートに対応（和暦処理）
実務を意識したファイル命名規則
OCR失敗時のフォールバック処理
🎯 想定ユーザー
個人事業主
経理担当者
レシート管理を自動化したい人

🔮 今後の改善
CSV出力（経費一覧）
GUI対応（クリック操作）
Webアプリ化（Flask）
精度向上（複数ページ対応など）
📄 ライセンス

MIT License

👤 作者

aedy-smith
