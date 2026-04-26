# GitHubの使い方

## 1. 概要
GitHubはソースコードのバージョン管理およびチーム開発を支援するプラットフォームである。  
単なるコード保存ではなく、「開発プロセス全体」を管理するツールとして利用される。

---

## 2. 基本フロー（最重要）

```text
ブランチ作成
↓
作業
↓
commit
↓
push
↓
Pull Request
↓
CI実行
↓
merge
3. 基本操作（初級）
ブランチ作成
git checkout main
git pull
git checkout -b feature/xxx
commit / push
git add .
git commit -m "docs: xxxを追加"
git push -u origin feature/xxx
4. Pull Request

Pull Request（PR）は、変更内容をレビューし、mainブランチへ統合するための仕組みである。

目的
コードレビュー
CIによる自動チェック
品質担保
5. 実務フロー（中級）
ブランチ戦略
main      安定版
feature/  機能開発
fix/      バグ修正
ci/       CI関連
docs/     ドキュメント
開発フロー
Issue作成
↓
ブランチ作成
↓
開発
↓
PR作成
↓
CIチェック
↓
merge
6. Issue駆動開発

Issueをタスク・疑問・課題として管理する。

フロー
Issue作成
↓
調査・開発
↓
docsに整理
↓
close
7. 上級テクニック
rebase（履歴を整理）
git rebase -i HEAD~3
revert（安全な取り消し）
git revert <commit-id>
reflog（履歴の復元）
git reflog
8. コンフリクト解決
同じ箇所を複数人が変更
↓
merge時に衝突
↓
手動で修正
9. CI/CD（GitHub Actions）

GitHub Actionsを用いて以下を自動化する。

PR時の自動チェック
テストの実行
デプロイ
10. よくあるミス
mainに直接pushしてしまう
コミット粒度が大きい
PRを出さない
ブランチ名が適当
11. 自分の運用ルール
必ずブランチを切る
PRベースで開発する
コミットは1目的ごとに分ける
Issueでタスク管理する
CIを通してからmergeする
12. 開発フロー図
13. 画像の追加方法

リポジトリ内に以下のように配置する。

assets/
 └── git-flow.png

Markdownでは以下のように記述する。

![Git Flow](../../assets/git-flow.png)