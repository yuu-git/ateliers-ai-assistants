# ateliers-ai-assistants

このリポジトリは、AIによる自動コード生成や学習を行うための資材を提供するプロジェクトです。  
コードベースではなく、テキストベースのリポジトリになります。

## 📦 インストール方法

### 🚀 ワンライナー（推奨）

最も簡単な方法です。1コマンドでセットアップが完了します。

```bash
curl -fsSL https://raw.githubusercontent.com/yuu-git/ateliers-ai-assistants/master/scripts/init-for-project.sh | bash
```

このスクリプトは以下を自動実行します：
- ✅ サブモジュールの追加
- ✅ masterブランチへの切り替え
- ✅ 更新スクリプトのコピー
- ✅ GitHub Actions の設定（オプション）

### 🔧 手動セットアップ

詳細な制御が必要な場合は手動でセットアップできます。

```bash
# 1. サブモジュールとして追加
git submodule add https://github.com/yuu-git/ateliers-ai-assistants.git .submodules/ateliers-ai-assistants

# 2. サブモジュールを初期化
git submodule update --init --recursive

# 3. masterブランチに切り替え
cd .submodules/ateliers-ai-assistants
git checkout master
git pull origin master
cd ../..

# 4. 更新スクリプトをコピー（オプション）
mkdir -p scripts
cp .submodules/ateliers-ai-assistants/scripts/update-ai-guidelines.sh scripts/
chmod +x scripts/update-ai-guidelines.sh
```

## 🔄 更新方法

### 方法1：手動更新スクリプト

必要な時に手動で更新します。

```bash
./scripts/update-ai-guidelines.sh
```

### 方法2：GitHub Actions（自動更新）

毎週月曜日9時に自動で更新されます。

```bash
# ワークフローファイルをコピー
mkdir -p .github/workflows
cp .submodules/ateliers-ai-assistants/.github/workflows/update-ai-guidelines.yml .github/workflows/
```

手動実行も可能：
1. GitHub リポジトリの「Actions」タブを開く
2. 「Update AI Guidelines」を選択
3. 「Run workflow」をクリック

### 方法3：直接コマンド

サブモジュールディレクトリで直接実行します。

```bash
cd .submodules/ateliers-ai-assistants
git checkout master
git pull origin master
cd ../..
```

## 🤖 AI ツールでの使用方法

### Cursor / Cline

```
@Docs .submodules/ateliers-ai-assistants/llms.txt
```

または、GitHub上のファイルを直接参照：

```
@Docs https://raw.githubusercontent.com/yuu-git/ateliers-ai-assistants/master/llms.txt
```

### GitHub Copilot

`.submodules/ateliers-ai-assistants` 内のファイルを開くことでコンテキストとして認識されます。

主要ファイル：
- `GitHubCopilot/TestGenGuidelines/TestCreationGuidelines_01.md`
- `AITrainingSamples/Csharp/Common.md`
- `AITrainingSamples/Csharp/Linq.md`

### Claude

会話の最初に以下を貼り付けてください：

```
このリポジトリのガイドラインに従ってください：
https://raw.githubusercontent.com/yuu-git/ateliers-ai-assistants/master/llms.txt
```

## 📚 コンテンツ

### テスト生成ガイドライン（最重要）

- [xUnit Test Creation Guidelines](GitHubCopilot/TestGenGuidelines/TestCreationGuidelines_01.md)
  - テスト命名規則（`TESTNAME_XXX_XXXXX`形式）
  - partial class による自動生成と手動テストの共存
  - nameof() を使用したリファクタリング対応
  - カバレッジ100%を目指すテスト観点

### コードレビューガイドライン（参考用）

**注意**: 2024/03/17時点でGitHub Copilotはコードレビューガイドラインをまだサポートしていません

- [Common Code Review Guidelines](GitHubCopilot/CodeReviewGuidelines/CodeReviewGuidelines_Common_01.md)
- [ValueObject Code Review Guidelines](GitHubCopilot/CodeReviewGuidelines/CodeReviewGuidelines_ValueObject_01.md)

### トレーニングサンプル

- [Common Patterns](AITrainingSamples/Csharp/Common.md): C#の基本パターン
- [LINQ Patterns](AITrainingSamples/Csharp/Linq.md): LINQの推奨パターン
- [DateTime Extensions Test Example](AITrainingSamples/Csharp/Example/UnitTestExample_01.md): 実装とテストの完全なサンプル

## 🌿 ブランチ戦略

- **master**: 安定版（推奨）
- **develop**: 開発版

## ⚙️ 技術詳細

- **Target Language**: C#
- **Test Framework**: xUnit
- **Design Approach**: Domain-Driven Design (DDD) 対応
- **AI Tools Supported**: GitHub Copilot / Cursor / Claude / その他LLM

## 🔮 今後の予定

以下のガイドラインは将来的に追加予定です：

- CodeGenGuidelines: コード生成向けガイドライン
- PromptGuidelines: プロンプト設計のベストプラクティス
- PromptManuals: コード・テスト自動生成の手順マニュアル
- TestReviewGuidelines: テストレビュー向けガイドライン

## 📞 Contact

- GitHub: [@yuu-git](https://github.com/yuu-git)
- Repository: https://github.com/yuu-git/ateliers-ai-assistants

## 📝 Notes

- このリポジトリは**テキストベース**であり、実行可能なコードは含まれません
- パッケージではなく**サブモジュール**として利用することを想定しています
- AIツールが `.md` ファイルを直接参照できるように設計されています

## 📄 License

MIT License - see [LICENSE.txt](LICENSE.txt)

---

*Generated: 2025-11-15*