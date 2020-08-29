# 作業環境を快適にしたい！
自分用の環境構築案です．

Power Shellの使いにくさとPATH設定の問題に耐えられず，

Linuxと同じような感覚でWin10を使うための記録です．

Git, Anacondaを使います．



## Win10版のGitをインストール

以下のサイトからgitをダウンロードしてインストールします．

[Git](https://git-scm.com/)

インストールする時，

- **Editor**: 

  Visual Studio Code

- **PATH environment**: 

  Git from the command line and also from 3rd-party software

にします．

インストールが成功すれば下のBash端末が使えるようになります．

![GitBash.png](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/GitBash.png?raw=true)



## Anacondaをインストール

以下のサイトからAnacondaのインストーラーをダウンロードします．

[Anaconda](https://www.anaconda.com/products/individual)

インストールする時は全部飛ばしても大丈夫です．



インストールが終わったら，Anaconda Navigatorを開きます．



VSCodeをインストールします．

これで使用するソフトが整えました！



## Win10にAnacondaのPATHを追加する

ここからPATHの設定を行う，

上手くいくと，Git Bashだけでなく，

Power ShellやコマンドプロンプトにもAnacondaのアプリが使えるようになります．



> Windows側のPATH設定

1. 「コントロールパネル」から「システムとセクシュアリティ」をクリックします．
2. 次にの画面で「システム」をクリックします．
3. 「システム」画面の左側にある「システムの詳細設定」をクリックします．
4. 「環境変数」をクリックします．
5. この画面で「システム環境変数」にある「Path」の項目を編集します．
6. ここに「Anaconda3」と「Anaconda3/Scripts」を追加して，一番上にします．

これでWindows上のPATH追加は完了です．



> Git BashにAnacondaのPATHを追加

bash.bashrcファイルにPATHを追加します，

Gitをインストールする際にインストール先を変えていない場合，

`C:\Program Files\Git\etc`にあると思います．

その一番下に

```shell
#Anaconda PATH
export PATH=$PATH:"/d/Users/yusam/Anaconda3"
export PATH=$PATH:"/d/Users/yusam/Anaconda3/Scripts"
```

を追加して保存します．



## VS CodeのデフォルトターミナルをGit Bashにする















