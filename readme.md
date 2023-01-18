### linterと formatterの設定

#### 要件
- lint: pylint
- formatter: autopep8

#### 前提
vscodeをworkspaceを作成して保存する。

#### pylint

1. pip install pylint
2. ctrl + P でコマンドパレット表示
3. >python:select linter
4. pylint --generate-rcfile > .pylintrc
5. .pylintr の Messages Control に [disable=print-statement,]を追加


#### autopep8
1. pip install autopep8
2. ctrl + P でコマンドパレット表示
3. >python:select linter

修正コマンド
> $ autopep8 -i <対象ファイル>

#### vscode
1. .vscode/settings.jsonを開く

```json
{
    "python.linting.enabled": true, // Lintの有効化
    "python.linting.pylintEnabled": true, // pylint
    "python.linting.lintOnSave": true, // ファイル保存時のlint実行
    "python.formatting.provider": "autopep8", // フォーマッタにautopep8
    "[python]": {
        "editor.formatOnSave": true, // ファイル保存時にフォーマッタ実行
    },
}
```

#### omake
https://note.com/npaka/n/n6afc09f45126