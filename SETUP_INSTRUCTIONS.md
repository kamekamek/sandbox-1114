# 焼き鳥ランディングページ - セットアップ指示書

このリポジトリでは、2つの異なる焼き鳥ランディングページを管理し、GitHub Pagesで公開します。

## 📁 ディレクトリ構成

```
sandbox-1114/
├── rpg/                    # RPG風ランディングページ
│   └── index.html
├── shop/                   # 通常版ランディングページ
│   ├── index.html
│   ├── script.js
│   └── styles.css
├── SETUP_INSTRUCTIONS.md   # この指示書
└── README.md
```

## 🎯 ブランチごとの役割

- **`claude/yakitori-rpg-landing-01Lp14Njq6HJS7tK8WudoXzC`**: RPG版を管理
- **`claude/yakitori-shop-landing-page-01Bw1S6suTsXL9hkhDoc4ga3`**: 通常版を管理
- **`main`** (推奨): 両方をマージして公開用に使用

---

## 📝 通常版ブランチの方への指示

### ステップ1: ブランチを切り替える

```bash
git checkout claude/yakitori-shop-landing-page-01Bw1S6suTsXL9hkhDoc4ga3
git pull origin claude/yakitori-shop-landing-page-01Bw1S6suTsXL9hkhDoc4ga3
```

### ステップ2: shop/ディレクトリを作成

```bash
mkdir -p shop
```

### ステップ3: ファイルをshop/ディレクトリに移動

```bash
git mv index.html shop/index.html
git mv script.js shop/script.js
git mv styles.css shop/styles.css
```

### ステップ4: 変更をコミット

```bash
git add .
git commit -m "Reorganize files into shop/ directory for GitHub Pages compatibility"
```

### ステップ5: プッシュ

```bash
git push origin claude/yakitori-shop-landing-page-01Bw1S6suTsXL9hkhDoc4ga3
```

---

## 🔄 mainブランチへのマージ（両方の担当者が実施後）

両方のブランチでディレクトリ構成を変更した後、以下の手順でmainブランチにマージします。

### オプションA: RPG版担当者が実施する場合

```bash
# mainブランチを作成（まだない場合）
git checkout -b main

# RPG版をマージ
git merge claude/yakitori-rpg-landing-01Lp14Njq6HJS7tK8WudoXzC --no-ff

# 通常版をマージ
git fetch origin claude/yakitori-shop-landing-page-01Bw1S6suTsXL9hkhDoc4ga3
git merge origin/claude/yakitori-shop-landing-page-01Bw1S6suTsXL9hkhDoc4ga3 --no-ff

# プッシュ
git push -u origin main
```

### オプションB: 通常版担当者が実施する場合

```bash
# mainブランチを作成（まだない場合）
git checkout -b main

# 通常版をマージ
git merge claude/yakitori-shop-landing-page-01Bw1S6suTsXL9hkhDoc4ga3 --no-ff

# RPG版をマージ
git fetch origin claude/yakitori-rpg-landing-01Lp14Njq6HJS7tK8WudoXzC
git merge origin/claude/yakitori-rpg-landing-01Lp14Njq6HJS7tK8WudoXzC --no-ff

# プッシュ
git push -u origin main
```

---

## 🌐 GitHub Pagesの設定

### 1. GitHubリポジトリのSettings画面へ移動

`https://github.com/kamekamek/sandbox-1114/settings/pages`

### 2. Source設定

- **Branch**: `main` を選択
- **Folder**: `/ (root)` を選択
- **Save**をクリック

### 3. 公開URL

設定後、以下のURLで各ページにアクセスできます：

- **RPG版**: `https://kamekamek.github.io/sandbox-1114/rpg/`
- **通常版**: `https://kamekamek.github.io/sandbox-1114/shop/`

📌 GitHub Pagesの反映には数分かかる場合があります。

---

## 🚨 注意事項

### ファイル競合を避けるために

- RPG版は必ず `rpg/` ディレクトリ内で作業
- 通常版は必ず `shop/` ディレクトリ内で作業
- ルートディレクトリには共通ファイル（README.md等）のみ配置

### マージ時の競合が発生した場合

```bash
# 競合を確認
git status

# 競合ファイルを手動で編集
# <<<<<<<, =======, >>>>>>> マーカーを削除して正しい内容に修正

# 競合解決後
git add .
git commit -m "Resolve merge conflict"
```

---

## 📞 サポート

質問や問題が発生した場合は、このリポジトリのIssuesで報告してください。

---

## ✅ チェックリスト

### RPG版担当者
- [x] rpg/ディレクトリにindex.htmlを配置
- [x] 変更をコミット＆プッシュ

### 通常版担当者
- [ ] shop/ディレクトリを作成
- [ ] index.html, script.js, styles.cssをshop/に移動
- [ ] 変更をコミット＆プッシュ

### どちらか一方（または両方で相談）
- [ ] mainブランチを作成
- [ ] 両方のブランチをmainにマージ
- [ ] GitHub Pagesを設定
- [ ] 公開URLで動作確認

---

**最終更新**: 2025-11-14
