<div align="center">

# 🌊 win10-gitbash

**A record of using Windows 10 like Linux — after getting tired of PowerShell's awkwardness and the endless PATH juggling**

<sub>**English** · [中文](README.zh-CN.md)</sub>

<sub>Git + Anaconda, pieced together so that "writing Python comfortably" actually works ( ¯꒳¯ )</sub>

</div>

---

## 📑 Contents

- [Install Git for Windows](#install-git-for-windows)
- [Install Anaconda](#install-anaconda)
- [Add Anaconda to the Windows PATH](#add-anaconda-to-the-windows-path)
- [Make Git Bash recognise conda](#make-git-bash-recognise-conda)
- [Make Git Bash VS Code's default terminal](#make-git-bash-vs-codes-default-terminal)
- [One last note](#one-last-note)

---

## Install Git for Windows

Download and install from [git-scm.com](https://git-scm.com/).

Two options worth paying attention to during setup:

- **Editor**: choose `Visual Studio Code`
- **PATH environment**: choose `Git from the command line and also from 3rd-party software`

After that you'll have this Bash terminal available:

![GitBash](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/GitBash.png?raw=true)

## Install Anaconda

Download the installer from the [Anaconda website](https://www.anaconda.com/products/individual); you can skip through the options during setup.

Then open Anaconda Navigator:

![Navigator](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/Navi.png?raw=true)

Install VS Code from there too, and you'll have everything you need.

## Add Anaconda to the Windows PATH

Once this is set up, not just Git Bash but PowerShell and cmd can use everything in conda directly.

> **Setting PATH on the Windows side**

1. Open Control Panel, click "System and Security"
   ![1](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/1.png?raw=true)
2. On the next screen, click "System"
   ![2](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/2.png?raw=true)
3. Click "Advanced system settings" on the left of the "System" screen
   ![3](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/3.png?raw=true)
4. Click "Environment Variables"
   ![4](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/4.png?raw=true)
5. Under "System variables", find `Path` and click "Edit"
   ![5](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/5.png?raw=true)
6. Add `Anaconda3` and `Anaconda3/Scripts`, and move them to the top
   ![6](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/6.png?raw=true)

That's the Windows PATH done.

## Make Git Bash recognise conda

Next, edit `bash.bashrc`. If you didn't change the install location when installing Git, it's usually at `C:\Program Files\Git\etc`.

Add this at the bottom:

```shell
#Anaconda PATH
export PATH=$PATH:"/d/Users/ユーザー名/Anaconda3"
export PATH=$PATH:"/d/Users/ユーザー名/Anaconda3/Scripts"
```

Save it. (Replace the path inside the quotes with your own Anaconda location.)

## Make Git Bash VS Code's default terminal

Last step ✨

On Windows, VS Code's default terminal is PowerShell. Now we switch it to the Git Bash we just installed.

First open Settings from the bottom-left of VS Code:

![VSCode1](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/VSCode1.png?raw=true)

Click the top-right corner of the settings screen to open the JSON settings file:

![VSCode2](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/VSCode2.png?raw=true)

Add this inside:

```json
{
  "terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe"
}
```

(Replace the path with your own Git Bash location.)

And that's everything — nice work (´-ω-`)

## One last note

> In practice, thanks to the old PATH problems, getting every library in Anaconda to load cleanly is still hard.
> **WSL2, which can reach the GPU, is the better recommendation now** — this road basically ends there ( ˘•ω•˘ )

---

<div align="center">
<sub>An environment-setup memo written for myself, hoping it helps you too while you wrestle with Windows</sub>
</div>
