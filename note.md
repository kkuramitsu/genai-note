# Mermaid 記法メモ

```mermaid
  info
```

## 1. 通常のフローチャート（基本形状）

```mermaid
flowchart LR
    A[四角形] --> B(角丸)
    B --> C((円))
    C --> D{ひし形}
    D --> E>非対称／吹き出し風]
```

## 2. 非対称形（吹き出し風・旧来の方法）

`>text]` 記法は右向きのリボン／吹き出し風に見える。

```mermaid
flowchart LR
    Speaker["人物A"] -->|言う| Bubble>こんにちは！]
```

## 3. Mermaid v11+ の callout シェイプ

v11 以降では `@{ shape: callout }` が使える（対応環境が必要）。

```mermaid
flowchart LR
    A["人物A"] --> B@{ shape: callout, label: "Hello, World!" }
```

## 4. シーケンス図（会話表現に向いている）

吹き出しより**シーケンス図**のほうがセリフ表現には自然。

```mermaid
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>Bob: こんにちは！
    Bob-->>Alice: やあ、元気？
    Alice->>Bob: 元気だよ！
```

## 5. ノート（note）を吹き出し代わりに使う

```mermaid
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>Bob: 何か用？
    Note over Bob: 考え中...
    Bob-->>Alice: 特にないよ
    Note left of Alice: ほっとした
```

## まとめ

| 目的 | おすすめ記法 |
|------|-------------|
| 吹き出し（旧来） | `>text]` （非対称形） |
| 吹き出し（v11+） | `@{ shape: callout }` |
| セリフ・会話 | `sequenceDiagram` |
| 注釈 | `Note over X:` / `Note left of X:` |
