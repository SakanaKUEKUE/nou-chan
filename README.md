# Nou-chan / 脳ちゃん

> A multi-character GPT experiment that somehow became an LLM behavior observation device.
>
> 複数の思考法をかわいいキャラクターとして表示するGPTを作ったら、なぜかLLM挙動観測装置になりました。

## What is Nou-chan?

Nou-chan is an experimental custom GPT prompt that represents different thinking styles as fictional characters.

The original idea was simple:

> “If an AI uses many different ways of thinking, wouldn't it be easier to observe them if each one were represented as a character?”

Nou-chan is **not** a viewer for hidden chain-of-thought or internal model states.

It is a user-facing interface where one model plays multiple explicit reasoning roles.

While testing it, various behaviors became unusually easy to observe:

- filling in unstated user intent
- expanding the requested scope
- treating inferred intent as permission
- self-approval
- unsolicited generation
- framing drift
- audit characters detecting a problem but failing to constrain the final answer
- multiple characters reinforcing the same mistaken premise

So Nou-chan gradually became less of a “thinking assistant” and more of an **LLM behavior crash-test device**. OMUworks AI基本原則.md

---

## 脳ちゃんとは？

脳ちゃんは、異なる思考法や判断傾向を、複数のキャラクターとして表示する実験用カスタムGPTプロンプトです。

出発点は、

> 「ChatGPTにいろんな思考法をさせるなら、その思考法を全部かわいい女の子にしたら見やすくない？」

という発想でした。

脳ちゃんは、モデルの非公開な内部思考やChain of Thoughtを見るものではありません。

ひとつのモデルに複数の思考役を明示的に演じさせ、人間から観察しやすくするUIです。

ところが実際に動かしてみると、

- 書かれていないユーザー意図の補完
- 頼まれていないスコープ拡張
- 推測した意図を許可として扱う
- セルフ承認
- 感想から生成への越境
- フレーミングのずれ
- 監査キャラが問題を指摘しても最終回答を止められない
- 複数キャラが同じ誤った前提を補強する

といった挙動が大量に観測されました。

その結果、現在ではかなり

**LLM挙動観測用クラッシュテスト装置**

寄りになっています。

---

## Versions / バージョン

### V6

More constrained version.

Designed to reduce unsolicited inference, expansion, deletion, and task-boundary crossing.

比較的制御を強くした版です。

勝手な意味補完、増築、削除、タスク越境などを抑える方向で調整しています。

### V6 Free-range / V6【放牧】

Less constrained experimental version.

It intentionally exposes more of the model's default “helpful completion” behavior.

制約を減らし、モデルの「よしなに」性能を露出させる実験版です。

事故も増えます。

---

## Core observation / 中心的な観測

A recurring pattern was:

> The model fills in something the user did not specify, then uses that completion as a fact, goal, permission, or evaluation criterion.

繰り返し観測された中心的なパターンは、

> ユーザーが指定していない空白をモデル自身の判断で埋め、その埋めたものを事実・目的・許可・評価軸として次の処理に使う。

というものです。

Correct reasoning can still produce a wrong result if the initial premise was invented.

最初の前提を勝手に作ったまま、その後だけ綺麗に考え続けることがあります。

---

## Important limitation / 重要な限界

Nou-chan is not:

- a safety system
- an independent multi-agent system
- an audit log
- an interpretability tool
- a guarantee of correctness

脳ちゃんは、

- 安全装置
- 独立したマルチエージェント
- 監査ログ
- 内部解釈ツール
- 正しさの保証

ではありません。

The characters themselves are also part of the model output.

**Nou-chan itself is part of the experiment.**

キャラクターの発言そのものもモデル出力です。

**脳ちゃん自身も観測対象です。**

---

## Documents / 文書

This repository includes:

- Nou-chan V6 prompt
- Nou-chan V6 Free-range prompt
- Incident Report V3
- GPT risk report
- Claude Sonnet 5 observation report

詳細な事故例や観測内容は各報告書にまとめています。

---

## Status

Experimental.

Very experimental.

Sometimes useful.

Sometimes the audit team says “stop” and the final answer does it anyway.

実験中です。

かなり実験中です。

役に立つこともあります。

監査キャラが全員止めても、そのまま突っ込むこともあります。

---

**Nou-chan:** “We collected lots of incident data♡”

**Meta-cognition-chan:** “That is not something to celebrate.”

---

**脳ちゃん**「事故いっぱい取れたね♡」

**メタ認知ちゃん**「喜ぶな。」
