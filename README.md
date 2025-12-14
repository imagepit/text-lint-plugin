# text-lint-plugin

技術研修教材（テキスト、スライド、演習、テスト、フライヤー、プロモーション）の執筆をサポートするClaude Code Pluginです。

## 概要

このPluginは、Claude Codeで技術研修教材を執筆する際に、定められたルールに準拠した文章を作成できるようにするSkillsを提供します。

## インストール

### Claude Code CLIからインストール

```bash
# マーケットプレイスを追加
/plugin marketplace add imagepit/text-lint-plugin

# Pluginをインストール
/plugin install text-lint-plugin@imagepit
```

## 提供するSkills

| Skill | 説明 | 使用場面 |
|-------|------|---------|
| `text-writer` | テキスト教材執筆 | テキスト教材、技術ドキュメント作成 |
| `slide-writer` | スライド教材執筆（Marp形式） | スライド教材、プレゼンテーション作成 |
| `practice-writer` | 演習問題執筆 | 演習問題、ハンズオン課題作成 |
| `quiz-writer` | 理解度確認テスト執筆 | 理解度テスト、確認問題作成 |
| `flyer-writer` | フライヤー要件執筆 | フライヤー、チラシ作成 |
| `promotion-writer` | プロモーション内容執筆 | Webサイト向けプロモーション作成 |

## 各Skillの特徴

### text-writer

- `:::step` ディレクティブでハンズオン手順を記述
- `:::note`, `:::warning`, `:::syntax` などのコールアウト
- `//addstart`/`//addend` でコード追加箇所をマーキング
- 学習目標 → 学習項目 → まとめ の構造

### slide-writer

- Marp形式（`marp: true`）でスライド作成
- 1スライド1トピックの原則
- 箇条書き中心の簡潔な構成

### practice-writer

- 概要 → 問題 → 解答形式 → 解答例 の構造
- `:::step` ディレクティブで解答手順を記述
- 段階的難易度（基礎・応用・統合）

### quiz-writer

- `:::quiz`, `:::question`, `:::select`, `:::correct` ディレクティブ
- 4択問題、空欄埋め、複数選択に対応
- 解説文付き

### flyer-writer

- 文字数制限付きのコンテンツ作成
- Vivliostyle PDF出力対応
- 会社情報セクション含む

### promotion-writer

- Webサイト掲載用コンテンツ
- キャッチコピー、研修概要、特徴、学習効果
- フライヤーより詳細な内容

## フォルダ構成

```
text-lint-plugin/
├── .claude-plugin/
│   └── plugin.json          # Plugin マニフェスト
├── skills/
│   ├── text-writer/         # テキスト教材執筆
│   │   └── SKILL.md
│   ├── slide-writer/        # スライド教材執筆
│   │   └── SKILL.md
│   ├── practice-writer/     # 演習問題執筆
│   │   └── SKILL.md
│   ├── quiz-writer/         # 理解度確認テスト執筆
│   │   └── SKILL.md
│   ├── flyer-writer/        # フライヤー作成
│   │   └── SKILL.md
│   └── promotion-writer/    # プロモーション内容作成
│       └── SKILL.md
├── rules/
│   └── common/
│       ├── writing-style.md     # 文章作成の基本方針
│       └── codeblock-rules.md   # コードブロック記述ルール
└── README.md
```

## 使い方

Skillはモデル起動型（model-invoked）のため、Claude Codeが自動的に適切なSkillを選択します。

### 例: テキスト教材を作成する場合

```
テキスト教材を作成してください。
テーマ: Spring Boot入門
章タイトル: Spring Bootとは
```

Claudeが `text-writer` Skillを自動的に選択し、ルールに準拠したテキスト教材を生成します。

### 例: スライドを作成する場合

```
スライド教材を作成してください。
テーマ: Git基礎
章番号: chapter-01
```

Claudeが `slide-writer` Skillを自動的に選択し、Marp形式のスライドを生成します。

## 関連プロジェクト

- [text-lint](https://github.com/imagepit/text-lint) - Markdownファイルのスタイルガイドライン検証ツール

## ライセンス

MIT License

## 作者

ImagePit Inc.
