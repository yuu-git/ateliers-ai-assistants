# ateliers-ai-assistants

このリポジトリは、AIによる自動コード生成や学習を行うための資材を提供するプロジェクトです。  
コードベースではなく、テキストベースのリポジトリになります。

そのため、開発環境や実行環境などの情報記載は、省略します。

## 利用手順

性質の都合、パッケージではなく、サブモジュールとして利用します。  
パッケージではテキストファイル (`*.md`) をAIが利用することができないためです。

## サブモジュール化の手順

### 1. コマンド

現在のプロジェクトディレクトリに `.submodules` というディレクトリを作成し  
その中に ateliers-ai-assistants  サブモジュールを追加したい場合：

```bash
git submodule add https://github.com/yuu-git/ateliers-ai-assistants.git .submodules/ateliers-ai-assistants
```

### 2. サブモジュールのブランチについて

基本的に master の使用を推奨します。  
開発中機能の使用は develop ブランチを使用し、試験的機能を試す場合は、新しくブランチを作ります。  
checkout および pull の手順は以下の通りです。

サブモジュールディレクトリに移動後：

```bash
git checkout master
git pull origin master
```

または

サブモジュールディレクトリに移動後：

```bash
git checkout develop
git pull origin develop
```
