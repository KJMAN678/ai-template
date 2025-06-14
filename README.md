### claude code
- [公式サイト](https://docs.anthropic.com/ja/docs/claude-code/overview)
- ローカル実行を想定

```sh
--- .claude
 |-- settings.local.json
--- .claudeignore
```

### Cursor
- [BugBot](https://docs.cursor.com/bugbot)
  - AI code review for pull requests
  - GitHub のコメントに、`bugbot run` or `bugbot run verbose=true` と入力
- [Cursor Ignore Files](https://docs.cursor.com/context/ignore-files#default-ignore-list)
- [書き捨てではなく継続開発可能なコードを Cursor Agent で書くために意識していること](https://dev.classmethod.jp/articles/cursor-agent-maintainable-coding-tips/)
- [kinopeee/cursorrules]()https://github.com/kinopeee/cursorrules/tree/main 
  - [directorystructure.md](https://raw.githubusercontent.com/kinopeee/cursorrules/refs/heads/main/directorystructure.md) ... ディレクトリ構成をCursorに伝えるためのファイル. claude code 等でディレクトリ構成を作成すると楽。
  - [technologystack.md](https://raw.githubusercontent.com/kinopeee/cursorrules/refs/heads/main/technologystack.md) ... 技術スタックをCursorに伝えるためのファイル
```sh
--- .cursor
 |- rules/
         |-- global.mdc
--- .cusorignore
--- .cusorindexingignore
--- directorystructure.md
--- technologystack.md
```

### OPENAI-API で PR-Review
- [Qodo Merge](https://qodo-merge-docs.qodo.ai/installation/github/)
  - GPT-4.1利用
  - 日本語の回答をするようプロンプト設定
- GitHub の Repository >> Settings >> Secretes and variables >> Actions の Repository secrets の New repository secret を登録
  - OPENAI_KEY という名称で OPENAI API keys の SECRET KEY を登録
    - [OPENAI API keys](https://platform.openai.com/settings/organization/api-keys) 
```sh
--- .github/
           |- workflows/
                        |-- pr_agent.yml
```
