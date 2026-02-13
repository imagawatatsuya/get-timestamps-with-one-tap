# get-timestamps-with-one-tap
タイムスタンプ `2025/04/15(火) 18:28:09` をワンタップ（ワンクリック）でクリップボードにコピー＆ペーストするウェブアプリ

## クソでかボタン
特にスマートフォンでアクセスしたとき **ボタンが最大化** する。押しやすい。

## 最終校閲・校正専用の LLM API 設定
最終工程の校閲・校正だけを LLM に担当させるためのサンプル設定を追加しています。

- 設定ファイル: `llm-proofreading-config.example.json`
- 利用時は `.env` でプロバイダ・APIキー・モデル名を管理してください（例: `PROOFREADING_LLM_PROVIDER`, `PROOFREADING_LLM_MODEL`, `OPENAI_MODEL` など）。
- サンプル: `.env.example`（これをコピーして `.env` を作成）
- `purpose` を `final_proofreading_only` に固定し、用途の逸脱を防ぎます。
- `llm-proofreading-config.example.json` は、誤字脱字・文法・表記ゆれに加え、小説全体の時系列/設定整合性や「意味が重複する段落・ブロック」の検出/統合まで含む厳密な校閲向けです。
- 主要 LLM と OpenRouter に対応し、`providerEnv` と `providerProfiles` で接続先を切り替えできます（OpenAI / Anthropic / Google / xAI / OpenRouter / DeepSeek / Qwen）。
- 主要LLMごとにモデル名も `.env` で指定可能です（`OPENAI_MODEL`, `ANTHROPIC_MODEL`, `GOOGLE_MODEL`, `XAI_MODEL`）。
- 中国系 LLM は OpenRouter 経由だけでなく、`deepseek` / `qwen` の直接接続プロファイルも選択できます。

