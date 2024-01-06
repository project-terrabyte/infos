## 目次
- [必要ソフトウェアのセットアップ](#必要ソフトウェアのセットアップ)
- [リポジトリのセットアップ](#リポジトリのセットアップ)
- [Unityのテンプレートスクリプトのセットアップ](#unityのテンプレートスクリプトのセットアップ)

#

<br>

# 必要ソフトウェアのセットアップ
本プロジェクトでは以下のソフトウェアまたはサービスを使用します。
- Unity 2022.3.1f1
- VisualStudio Code
- GitHub
- Miro
- GoogleDrive
- Microsoft 365 ( の一部 )

### アカウントの作成
- [Unity](https://id.unity.com/ja/)
- [GitHub](https://github.com/login) (アカウントを作成した後に、KaRU3まであなたのユーザーネームを知らせてください。組織に追加します。)
- [Miro](https://miro.com/ja/login/)
- [Google](https://takeout.google.com/?hl=ja)
- [Microsoft](https://account.microsoft.com/account?lang=ja-jp)

### Unity2022.3.1f1のインストール
1. [Unity Hubインストーラー](https://unity.com/ja/download)をダウンロードし、インストールしてください。
2. [Unityのバージョンアーカイブ](https://unity.com/releases/editor/archive#download-archive-2022)に移動してください。
3. Unity 2022.X系統のバージョンが表示されているので、その中から `Unity 2022.3.1f1`を見つけ、UnityHubボタンをクリックしてください。
4. UnityHubが起動し、ダウンロードが始められるようになります。
5. Add Modulesの画面で以下の項目にチェックを入れます。<br>
    - Linux Build Support (IL2CPP)<br>
    - Linux Build Support (Mono)<br>
    - Mac Build Support (Mono)<br>
    - Universal Windows Platform Build Support<br>
    - Windows Build Support (IL2CPP)
6. 規約の同意を求められるので、全て同意してインストールを開始してください。

### VisualStudio Codeのインストール
1. [VScodeのインストーラー](https://code.visualstudio.com/download)をダウンロードしてください。
2. インストーラーを起動し、インストーラーの指示に従ってインストールしてください。
3. インストールが出来たら、VScodeを起動し以下の[拡張機能](https://code.visualstudio.com/docs/editor/extension-marketplace)をインストールします。<br>
    - C#
    - C# Dev Kit
    - IntelliCode for C# Dev Kit
    - Git Lens
    - Code Spell Checker
    - Unity
    - 後は必要に応じて各自でインストールしてください。

### Git/GitHub Desktopのインストール
1. [Git (Bash)](https://git-scm.com/downloads)をインストールしてください。
2. [GitHub Desktop](https://desktop.github.com/)をインストールしてください。

#

# リポジトリのセットアップ
本プロジェクトでは、Gitによるバージョンコントロールを使用します。

### ワークフォルダーの作成
1. 任意の場所に作業用のフォルダーを作成します。
2. そのフォルダーの中にテキストファイルを作成します。
3. 2で作成したファイルの中に以下のコードをコピペします。
    ```bat
    @echo off

    echo Enter your GitHub username
    set /p githubUsername=^> 
    cls

    echo Enter your GitHub email (see in: https://github.com/settings/emails )
    set /p githubEmail=^> 
    cls

    echo Enter target repository URL
    set /p repository=^> 

    echo What directory name do you want?
    set /p dirName=^> 
    cls

    echo.
    echo -----------------------------------------------------
    echo Git configuration script for Windows
    echo -----------------------------------------------------

    echo Downloading github repository...
    git clone %repository% %dirName%

    echo Configure your account...

    rem Configure Git with your GitHub account
    cd %dirName%
    git config --local user.name %githubUsername%
    git config --local user.email %githubEmail%

    echo Your account config is...
    git config --local user.name
    git config --local user.email

    cd ..
    echo Success!!
    pause
    ```
4. 保存してファイルを閉じて、[テキストファイルの拡張子](https://support.hp.com/jp-ja/document/c01967336)を`.txt`から`.bat`に変更します。
5. .batファイルをダブルクリックして実行してください。
7. 色々聞かれるので順番に以下の内容を入力してください。
    - Enter your GitHub username: あなたのGitHubのユーザーネームを入力してください。
    - Enter your GitHub email: あなたのGitHubの[メールアドレス](https://github.com/settings/emails)を入力してください。
    - Enter target repository URL: https://github.com/project-terrabyte/Game.git を入力してください。
    - What directory name do you want?: 好きなフォルダ名を入力してください。<br>
    以下のようになればエンターを押して下さい。
    ```cmd
    Enter your GitHub username
    > Username

    Enter your GitHub email (see in: https://github.com/settings/emails )
    > 123456789+Username@users.noreply.github.com

    Enter target repository URL
    > https://github.com/project-terrabyte/Game.git

    What directory name do you want?
    > ExampleFolderName
    ```

### バージョン追跡を開始
1. GitHub Desktopを開き、左上の`File`を押し、`Add local repository`を押して下さい。
2. `Local path`の欄の横にある`Choose...`ボタンを押して先ほどbatファイルで作成したフォルダーを選んでください。
3. `Add repository`ボタンを押してください。
4. 左下の`Summary`と書かれている入力欄の横のアイコンをクリックして、batファイルで設定したユーザーネームとメールアドレスになっていればセットアップは完了です！

#

# Unityのテンプレートスクリプトのセットアップ
コーディング規約により、テンプレートの変更が必要です。
1. UnityHubを開き、`installs`タブの`2022.3.1f1`のインストール先フォルダーをコピーします。<br>
    ex) C:\Unity_releases\2022.3.1f1\Editor\
2. `Win + E`を押してエクスプローラーを開き、パス入力欄に先ほどコピーしたパスをペーストし、エンターを押して移動してください。
3. そこから `Data\Resources\ScriptTemplates\`に移動してください。
4. その中にある、`81-C# Script-NewBehaviourScript.cs.txt`を複製して、元あったファイルの末尾を`~.cs.txt.old`としてください。
5. 複製してできたファイルを開き、以下のコードに置き換えてください。
    ```csharp
    // Description: 
    // Author: https://github.com/
    using System.Collections;
    using System.Collections.Generic;
    using UnityEditor;
    using UnityEngine;

        #ROOTNAMESPACEBEGIN#
    public class #SCRIPTNAME# : MonoBehaviour {

        private void Start() {
            #NOTRIM#
        }
        private void Update() {
            #NOTRIM#
        }
    }
    #ROOTNAMESPACEEND#
    ```
6. 保存して、ファイル名を`81-C# Script-NewBehaviourScript.cs.txt`に変更してください。

#

## お疲れ様でした！
