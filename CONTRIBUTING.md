# Contributing / 参加のしかた

Default guide for all `larai-w` repositories. A repository may override this with its own
`CONTRIBUTING.md` — if one exists there, follow that instead.

`larai-w` の全リポジトリ共通のガイドです。各リポジトリに独自の `CONTRIBUTING.md` が
ある場合は、そちらが優先されます。

---

## コードを書かない参加のしかた / Without writing code

VEAI LAB. のプロダクトは介護・在宅ケアの現場を想定しています。
**実際に使った人の声がいちばん役に立ちます。** 開発環境は必要ありません。

| こんなとき | どうぞ |
|---|---|
| 動きがおかしい | Issue（バグ報告） |
| こうだったらいいのに | Issue（改善提案） |
| 使ってみた感想、現場で気づいたこと | Issue |
| 脆弱性を見つけた | [SECURITY.md](SECURITY.md) の手順で**非公開**に |

うまく言葉にならなくても構いません。断片でも歓迎します。

These are care and independent-living tools. **Feedback from people who actually used
them matters most** — no development environment needed. Half-formed thoughts are welcome.
Vulnerabilities go through [SECURITY.md](SECURITY.md), never a public Issue.

---

## コードで参加する場合 / Contributing code

### 1. 公開リポジトリに入れてはいけないもの

これらは公開リポジトリに置きません。private な作業スペースで扱います。

- 戦略・成長計画・価格・売上・営業やパイロットの生データ
- 施設名・個人名など、施設や人を特定できる情報
- 服薬内容・健康記録などの個人の健康情報
- 認証情報、APIキー、トークン、アクセスコード
- 内部の作業ログ、引き継ぎメモ、未公開の下書き

Never commit strategy, pricing, sales or pilot raw data, facility- or person-identifying
information, personal health data, credentials, or internal working notes.

### 2. pre-commit ガードを迂回しない

多くのリポジトリに公開境界チェックとシークレット走査の pre-commit フックがあります。
**検証を飛ばすオプションで回避しないでください。** 引っかかった場合は、迂回ではなく
中身を直します。

新しく clone したときは一度だけ有効化が要ります。

```bash
git config core.hooksPath .githooks
```

Do not skip the pre-commit guards. If a guard fires, fix the content instead.

### 3. 健康・介護に関する文言

VEAI のプロダクトは**医療機器ではありません**。UI・ドキュメント・README を問わず、
次を主張しないでください。

- 診断・治療・予防の効果（「〜が治る」「〜を防ぐ」「症状を改善する」）
- 100%・完全・確実といった絶対的な表現

書けるのは「**記録する・整理する・共有する**」という行為までです。判断は利用者と
専門職に委ねます。

These are not medical devices. Do not claim diagnosis, treatment, or prevention, and do
not use absolute guarantees. Describe the activity — recording, organising, sharing — and
leave the judgement to the user and their professional.

### 4. AI 支援開発について

このラボは AI 支援でコードを書いています。それ自体は歓迎しますが、**生成物をそのまま
信用しない**という前提で運用しています。

- PR に AI 生成のコードが含まれる場合は、その旨を書いてください
- 生成されたコードも、人間が書いたコードと同じ検証を通してください
- テストが通ることと、意図どおり動くことは別です

We build with AI assistance. Please say so in the PR when a change contains AI-generated
code, and hold it to the same verification as hand-written code.

### 5. 検証してから出す

リポジトリごとに検証コマンドが違います。`README.md` / `AGENTS.md` / `CONTRIBUTING.md`
を確認し、**通してから** PR を出してください。何を確認したかは PR に書きます。

---

## 行き詰まったら / If you are stuck

Issue で聞いてください。「これは Issue にしていいことですか」も含めて構いません。

Open an Issue — including "is this even worth an Issue?"
