# 自動化設定の整理（CONFIG-20260909 v3）

2026-09-09、Fable事前相談後にCodexが実施。

- houshasen_autopush.shを呼ぶグローバルPostToolUse登録1件を除去。任意の編集でgit add -A→commit→pushする処理を停止した。スクリプトは復旧参照用に保持し、実行しない。
- 求人ページの更新は、差分を確認し明示パスでステージして、ユーザーの依頼・承認範囲でcommit/pushする。編集だけで自動公開されなくなる。
- 管制台のcommit_status.shは別リポジトリ用で、この自動pushに依存しない。変更なし。
- 権限・認証・他のClaudeフックは保持。全体autoMode環境説明は$defaultsを含め、古い全repoリモートなし・実行回数・一律の本番反映という前提を整理。project-yakuminpro固有ルールはGit除外したCLAUDE.local.mdへ分離。
- 変更前バックアップと前後SHA256はCodex作業フォルダwork/config-v3-backup/manifest.json。復元時は後続の変更を上書きしない。
