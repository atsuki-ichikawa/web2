
ローカルのディレクトリをGitHubに公開する手順

---

### **事前準備**
1. **Gitをインストール**
   - まだインストールしていない場合は、[Git公式サイト](https://git-scm.com/)からインストール

2. **GitHubアカウント作成**
   - [GitHub](https://github.com/)でアカウントを作成し、サインイン

3. **GitHubリポジトリを作成**
   - GitHubで新しいリポジトリを作成
     1. サイト右上の「＋」アイコン → 「New repository」をクリック。
     2. リポジトリ名を入力（例: `my-project`）。
     3. 必要に応じて説明を追加し、PublicかPrivateを選択。
     4. 「Create repository」をクリック。

---

### **ローカルディレクトリをGitHubに公開する手順**

1. **ローカルディレクトリに移動**
   ```bash
   cd /path/to/your/local/directory
   ```

2. **Gitリポジトリを初期化**
   ```bash
   git init
   ```

3. **GitHubリポジトリをローカルに登録**
   - GitHubリポジトリの「Quick setup」で表示されるURLをコピー
   - 例: `https://github.com/username/my-project.git`
   ```bash
   git remote add origin https://github.com/username/my-project.git
   ```

4. **ファイルをステージング**
   - 全てのファイルをステージに追加する場合:
     ```bash
     git add .
     ```
   - 特定のファイルだけを追加する場合:
     ```bash
     git add ファイル名
     ```

5. **コミット**
   - 変更内容を記録します:
     ```bash
     git commit -m "初回コミットメッセージ"
     ```

6. **ファイルをGitHubにプッシュ**
   - 初回プッシュ時はブランチ名を指定:
     ```bash
     git branch -M main
     git push -u origin main
     ```

---

### **成功確認**
- GitHubのリポジトリページを開き、ローカルディレクトリ内のファイルが表示

---

### **今後の更新手順**
1. **変更をステージング**
   ```bash
   git add .
   ```

2. **変更をコミット**
   ```bash
   git commit -m "更新内容の説明"
   ```

3. **変更をプッシュ**
   ```bash
   git push
   ```

---

### **注意点**
- **.gitignore** ファイルを利用して、公開したくないファイルやディレクトリを除外
  例: `.gitignore` ファイルに以下を記載すると `node_modules` フォルダが無視
  ```
  node_modules/
  ```






GitHubリポジトリをローカルにクローンする方法は以下の通り

---

### **GitHubリポジトリをローカルにクローンする手順**

#### **1. リポジトリのURLを取得**
1. GitHubで対象のリポジトリを開
2. 「Code」ボタンをクリック
3. 表示されるURL（HTTPSかSSHのどちらか）をコピー
   - HTTPSの場合の例: `https://github.com/atsuki-ichikawa/web2.git`
   - SSHの場合の例: `git@github.com:atsuki-ichikawa/web2.git`

---

#### **2. ローカルでクローン先のディレクトリに移動**
1. ターミナル（コマンドプロンプトやPowerShellでも可）を開
2. クローンしたい場所に移動
   ```bash
   cd /path/to/desired/directory
   ```

---

#### **3. リポジトリをクローン**
1. クローンコマンドを実行
   - HTTPSを使う場合:
     ```bash
     git clone https://github.com/atsuki-ichikawa/web2.git.git
     ```
   - SSHを使う場合:
     ```bash
     git clone git@github.com:atsuki-ichikawa/web2.git
     ```

2. クローンが成功すると、指定したディレクトリ内にリポジトリの内容がダウンロード

---

#### **4. クローン先のディレクトリに移動**
```bash
cd repository-name
```

---

#### **5. クローンが成功したか確認**
1. ディレクトリの内容を確認
   ```bash
   ls   # macOS/Linux
   dir  # Windows
   ```

2. `.git`ディレクトリがあればクローンは成功

---

### **補足情報**
- **SSHを使いたい場合の準備**
  - GitHubにSSHキーを設定していない場合は、以下の手順を参考にSSHキーを設定
    1. ローカルでSSHキーを生成:
       ```bash
       ssh-keygen -t ed25519 -C "your-email@example.com"
       ```
    2. 公開鍵をGitHubに追加:
       - GitHubの「Settings」 → 「SSH and GPG keys」 → 「New SSH key」で公開鍵を登録。

- **複数のブランチがある場合**
  - クローンした後、別のブランチを使いたい場合は以下を実行:
    ```bash
    git checkout branch-name
    ```

---

