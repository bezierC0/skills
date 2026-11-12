# jp-legal-assistant

日本法の法律問題を、弁護士に相談する前に自己チェックするための AI スキル。
契約書レビュー／労働／不動産／内容証明・訴訟対応／答弁書・準備書面・法廷での主張整理に対応。

> 本スキルの出力は一般的な法的情報です。個別の法律相談に代わるものではありません。

## 構成

```
jp-legal-assistant/
├── SKILL.md                 # 基本方針・ワークフロー・出力形式
└── references/
    ├── contract-review.md   # 契約書レビュー
    ├── labor.md             # 労働問題
    ├── real-estate.md       # 不動産
    ├── litigation.md        # 内容証明・訴訟・答弁書・法廷
    └── research.md          # 調べ方・改正分野・相談先
```

スクリプトや外部 API に依存しないため、どの AI でも使えます。

## 使い方

### Claude（claude.ai / Desktop）
Settings > Capabilities（Skills）で `jp-legal-assistant.zip` または `.skill` をアップロード。

### Claude Code
```
cp -r jp-legal-assistant ~/.claude/skills/
```

### ChatGPT（カスタム GPT / Projects）
- Instructions に `SKILL.md` の本文（`---` で囲まれた先頭部分を除く）を貼り付け
- Knowledge に `references/` の5ファイルをアップロード
- 本文中の「`references/xxx.md` を読む」は「ナレッジの xxx.md を参照」と読み替えられます

### Gemini（Gems）／ その他
- 指示欄に `SKILL.md` の本文を貼り付け、`references/` のファイルを知識として追加
- ファイル添付ができない場合は、関係する分野の reference を会話の最初に貼り付け

## 推奨の組み合わせ
条文の正確な取得には、e-Gov 法令 API を使う [jp-law-skill](https://github.com/HighBridgeDragon/jp-law-skill) の併用を推奨（コード実行と e-Gov へのネットワーク接続が必要）。
