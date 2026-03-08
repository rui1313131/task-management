# タスク管理システム

チームで共有できるタスク管理システムです。
GitHub Issues と Projects を使って、誰でも簡単にタスクを作成・管理できます。

---

## 目次

1. [全体の流れ](#全体の流れ)
2. [タスクを作る](#1-タスクを作るissue作成)
3. [Projectsボードとは](#2-projectsボードとは)
4. [Projectsボードの作り方](#3-projectsボードの作り方)
5. [タスクの状態を変える](#4-タスクの状態を変える)
6. [進捗コメントを書く](#5-進捗コメントを書く)
7. [メンバーを招待する](#6-メンバーを招待する--管理者権限を与える)
8. [ラベル一覧](#ラベル一覧)

---

## 全体の流れ

```
① タスクを作る（Issue 作成）
        ↓
② 担当者・優先度を設定
        ↓
③ Projectsボードに表示される
        ↓
④ ボードでステータスを動かしながら作業
   Backlog → Todo → In Progress → Review → Done
        ↓
⑤ 完了したら Issue を Close
```

---

## 1. タスクを作る（Issue作成）

**[Issues] タブ → [New Issue] をクリック**

![Issueタブの場所](docs/images/issues-tab.png)
> ※ 上部ナビゲーションの「Issues」タブをクリックします

**テンプレートを選ぶ**

![テンプレート選択画面](docs/images/template-select.png)

| テンプレート | 使いどき |
|---|---|
| タスク | 通常の作業 |
| バグ報告 | 不具合・エラーの報告 |
| 機能提案 | 新しい機能のリクエスト |

**フォームを記入する（タスクの場合）**

| 項目 | 説明 | 例 |
|---|---|---|
| タイトル | 一言で内容がわかるように | `[Task] ログイン画面のUI修正` |
| タスクの内容 | 何をするか具体的に | ボタンの色を統一する |
| 優先度 | high / medium / low | medium |
| 期限 | 任意 | `2026-03-31` |
| 完了条件 | チェックリスト形式で | `- [ ] ボタン色を統一` |

記入後 **[Submit new issue]** で作成完了。

---

## 2. Projectsボードとは

Issueを**カード**として視覚的に管理できるカンバンボードです。
Trello・Notionのボード機能と同じイメージです。

```
┌──────────┬──────────┬─────────────┬──────────┬──────────┐
│ Backlog  │   Todo   │ In Progress │  Review  │   Done   │
├──────────┼──────────┼─────────────┼──────────┼──────────┤
│ タスクC  │ タスクB  │  タスクA    │          │ タスクX  │
│ タスクD  │          │             │          │ タスクY  │
└──────────┴──────────┴─────────────┴──────────┴──────────┘
```

| ステータス | 意味 |
|---|---|
| **Backlog** | いつかやる・保留中 |
| **Todo** | 次にやる予定 |
| **In Progress** | 現在作業中 |
| **Review** | レビュー・確認中 |
| **Done** | 完了 |

---

## 3. Projectsボードの作り方

> ※ Projectsボードは GitHub上で手動で1回だけ作成が必要です

**手順：**

1. リポジトリの **[Projects]** タブをクリック
2. **[Link a project]** → **[New project]** をクリック

   ![Projectsタブ](docs/images/projects-tab.png)

3. **[Board]** テンプレートを選択

   ![Boardテンプレート選択](docs/images/project-board-template.png)

4. プロジェクト名を `タスクボード` と入力 → **[Create project]**

5. デフォルトで `Todo / In Progress / Done` の列が作成される

6. 列を追加：**[+ Add column]** で `Backlog` と `Review` を追加

7. リポジトリと連携：プロジェクト設定 → **[Add repository]** でこのリポジトリを追加

---

## 4. タスクの状態を変える

### 方法A：Projectsボードで変える（推奨）

ボードを開き、カードを**ドラッグ＆ドロップ**で列間を移動するだけ。

![カードをドラッグ](docs/images/drag-card.png)

### 方法B：Issueのラベルで変える

Issue を開いて右サイドバーの **[Labels]** をクリック：

```
作業開始時   → "status: in progress" を付ける
レビュー待ち → "status: review" を付ける
ブロック中   → "status: blocked" を付ける
完了時       → Issue 下部の [Close issue] をクリック
```

---

## 5. 進捗コメントを書く

Issue を開いて、下部のコメント欄に記入 → **[Comment]** で投稿。

![コメント欄](docs/images/comment-box.png)

**進捗報告のテンプレート例：**

```markdown
## 進捗報告 2026-03-08

### 完了したこと
- [x] ボタンの色を統一
- [x] スマホ表示を確認

### 残り作業
- [ ] レビュー依頼

### 詰まっている点
特になし
```

---

## 6. メンバーを招待する / 管理者権限を与える

**Settings → Collaborators → [Add people]**

![Collaborators設定画面](docs/images/collaborators.png)

ユーザー名またはメールアドレスで招待できます。
相手が承認するとアクセスできるようになります。

### 権限の種類

| ロール | できること |
|---|---|
| **Admin（管理者）** | 設定変更・メンバー管理・リポジトリ削除 |
| **Maintain** | ほぼ全操作（設定・削除以外） |
| **Write** | Issue・PRの作成・編集・クローズ |
| **Read** | 閲覧のみ |

> 管理者権限を与えるには招待後、相手の名前の横のロールを **Admin** に変更してください。

---

## ラベル一覧

| ラベル | 意味 |
|---|---|
| `priority: high` | 優先度：高 |
| `priority: medium` | 優先度：中 |
| `priority: low` | 優先度：低 |
| `type: bug` | バグ修正 |
| `type: feature` | 新機能追加 |
| `type: task` | 一般タスク |
| `type: question` | 質問・相談 |
| `status: in progress` | 作業中 |
| `status: blocked` | ブロック中 |
| `status: review` | レビュー待ち |

---

## スクリーンショットの追加方法

> ドキュメント内の画像（`docs/images/`）は実際のスクリーンショットに差し替えてください

1. `docs/images/` フォルダを作成
2. スクリーンショットを撮影して保存
3. ファイルをフォルダにドラッグ＆ドロップ → コミット

または GitHub の Issue/PR のコメント欄に画像をドロップすると自動でURLが生成されるので、
それを README に貼り付ける方法も簡単です。

---

_Powered by GitHub Issues & Projects_
