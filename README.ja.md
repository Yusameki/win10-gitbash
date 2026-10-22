<div align="center">

# 🌊 win10-gitbash

**PowerShell の使いにくさと PATH の行き来に疲れて、Windows 10 を Linux みたいに使う記録**

<sub>[English](README.md) · **日本語** · [中文](README.zh-CN.md)</sub>

<sub>Git + Anaconda で「気持ちよく Python を書く」を組み立てる ( ¯꒳¯ )</sub>

</div>

---

## 📑 目次

- [Windows 10 版 Git をインストール](#windows-10-版-git-をインストール)
- [Anaconda をインストール](#anaconda-をインストール)
- [Anaconda の PATH を Windows に追加](#anaconda-の-path-を-windows-に追加)
- [Git Bash に conda を認識させる](#git-bash-に-conda-を認識させる)
- [VS Code の既定ターミナルを Git Bash にする](#vs-code-の既定ターミナルを-git-bash-にする)
- [最後にひとこと](#最後にひとこと)

---

## Windows 10 版 Git をインストール

[git-scm.com](https://git-scm.com/) からダウンロードしてインストールします。

インストール時にこの 2 つの選択肢に注意してください：

- **Editor**：`Visual Studio Code` を選ぶ
- **PATH environment**：`Git from the command line and also from 3rd-party software` を選ぶ

インストールが終われば、下の Bash ターミナルが使えます：

![GitBash](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/GitBash.png?raw=true)

## Anaconda をインストール

[Anaconda 公式サイト](https://www.anaconda.com/products/individual) からインストーラをダウンロードします。インストール中のオプションは基本的にそのままで大丈夫です。

終わったら Anaconda Navigator を開きます：

![Navigator](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/Navi.png?raw=true)

ついでに中から VS Code も入れておくと、必要なものが揃います。

## Anaconda の PATH を Windows に追加

これを設定すると、Git Bash だけでなく PowerShell やコマンドプロンプトからも conda の中身が直接使えるようになります。

> **Windows 側の PATH 設定**

1. 「コントロールパネル」を開き、「システムとセキュリティ」をクリック
   ![1](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/1.png?raw=true)
2. 次の画面で「システム」をクリック
   ![2](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/2.png?raw=true)
3. 「システム」画面の左側にある「システムの詳細設定」をクリック
   ![3](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/3.png?raw=true)
4. 「環境変数」をクリック
   ![4](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/4.png?raw=true)
5. 「システム環境変数」の中の `Path` を見つけて「編集」をクリック
   ![5](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/5.png?raw=true)
6. `Anaconda3` と `Anaconda3/Scripts` を追加し、一番上に移動させる
   ![6](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/6.png?raw=true)

これで Windows 側の PATH は完了です。

## Git Bash に conda を認識させる

次に `bash.bashrc` を編集します。Git のインストール先を変えていなければ、ふつうは `C:\Program Files\Git\etc` にあります。

一番下にこれを追加します：

```shell
#Anaconda PATH
export PATH=$PATH:"/d/Users/ユーザー名/Anaconda3"
export PATH=$PATH:"/d/Users/ユーザー名/Anaconda3/Scripts"
```

保存すれば OK です（引用符の中は自分の Anaconda の場所に置き換えてください）。

## VS Code の既定ターミナルを Git Bash にする

最後の一歩です ✨

Windows での VS Code の既定ターミナルは PowerShell なので、これをさっき入れた Git Bash に変えます。

まず VS Code の左下から設定を開きます：

![VSCode1](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/VSCode1.png?raw=true)

設定画面の右上をクリックして、設定用の json ファイルを開きます：

![VSCode2](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/VSCode2.png?raw=true)

そこにこれを追加します：

```json
{
  "terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe"
}
```

（引用符の中は自分の Git Bash のパスに置き換えてください）

これで全部終わりです。おつかれさまでした (´-ω-`)

## 最後にひとこと

> 実際に使ってみると、PATH の昔からの問題で、Anaconda のライブラリを全部きちんと呼べるのはなかなか難しいです。
> **GPU を使える WSL2 のほうが今はおすすめ** —— この道の行き着く先はだいたいそこです ( ˘•ω•˘ )

---

<div align="center">
<sub>自分のための環境構築メモですが、Windows と格闘している誰かの役にも立てば嬉しいです</sub>
</div>
