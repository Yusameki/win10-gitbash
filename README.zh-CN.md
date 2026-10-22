<div align="center">

# 🌊 win10-gitbash

**受不了 PowerShell 的别扭和 PATH 的来回折腾，于是像用 Linux 那样用 Win10 的记录**

<sub>[English](README.md) · [日本語](README.ja.md) · **中文**</sub>

<sub>用 Git + Anaconda，把「能舒服地写 Python」这件事拼起来 ( ¯꒳¯ )</sub>

</div>

---

## 📑 目录

- [安装 Win10 版 Git](#安装-win10-版-git)
- [安装 Anaconda](#安装-anaconda)
- [把 Anaconda 的 PATH 加进 Windows](#把-anaconda-的-path-加进-windows)
- [让 Git Bash 认出 conda](#让-git-bash-认出-conda)
- [把 VS Code 的默认终端换成 Git Bash](#把-vs-code-的默认终端换成-git-bash)
- [最后的小提醒](#最后的小提醒)

---

## 安装 Win10 版 Git

从 [git-scm.com](https://git-scm.com/) 下载安装。

安装时这两个选项请留意：

- **Editor**：选 `Visual Studio Code`
- **PATH environment**：选 `Git from the command line and also from 3rd-party software`

装好后就能用下面这个 Bash 终端了：

![GitBash](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/GitBash.png?raw=true)

## 安装 Anaconda

从 [Anaconda 官网](https://www.anaconda.com/products/individual) 下载安装包，安装过程中的选项可以一路跳过。

装完之后打开 Anaconda Navigator：

![Navigator](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/Navi.png?raw=true)

顺手在里面把 VS Code 也装上，这样要用的软件就齐了。

## 把 Anaconda 的 PATH 加进 Windows

设置好之后，不只是 Git Bash，连 PowerShell 和命令提示符都能直接用 conda 里的东西。

> **Windows 侧的 PATH 设置**

1. 打开「控制面板」，点击「系统和安全」
   ![1](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/1.png?raw=true)
2. 在下一个画面点击「系统」
   ![2](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/2.png?raw=true)
3. 点击「系统」画面左侧的「高级系统设置」
   ![3](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/3.png?raw=true)
4. 点击「环境变量」
   ![4](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/4.png?raw=true)
5. 在「系统变量」里找到 `Path`，点「编辑」
   ![5](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/5.png?raw=true)
6. 把 `Anaconda3` 和 `Anaconda3/Scripts` 加进去，并且挪到最上面
   ![6](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/6.png?raw=true)

到这里 Windows 上的 PATH 就加完了。

## 让 Git Bash 认出 conda

接着改 `bash.bashrc`。如果安装 Git 时没改过安装位置，它一般在 `C:\Program Files\Git\etc`。

在最下面加上：

```shell
#Anaconda PATH
export PATH=$PATH:"/d/Users/ユーザー名/Anaconda3"
export PATH=$PATH:"/d/Users/ユーザー名/Anaconda3/Scripts"
```

保存即可（引号里记得换成自己的 Anaconda 位置哦）。

## 把 VS Code 的默认终端换成 Git Bash

最后一步了 ✨

Windows 上 VS Code 的默认终端是 PowerShell，现在我们把它换成刚装好的 Git Bash。

先从 VS Code 左下角打开设置：

![VSCode1](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/VSCode1.png?raw=true)

点击设置画面右上角，打开设置用的 json 文件：

![VSCode2](https://github.com/Yusameki/win10-gitbash/blob/master/Pic/VSCode2.png?raw=true)

在里面加上：

```json
{
  "terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe"
}
```

（引号里换成自己 Git Bash 程序的路径）

这样就全部完成啦，辛苦啦 (´-ω-`)

## 最后的小提醒

> 实际用下来，因为 PATH 的老问题，Anaconda 里所有库都能顺利调用还是挺难的。
> **能吃到 GPU 的 WSL2 现在更推荐** —— 这条路的尽头差不多就是那里 ( ˘•ω•˘ )

---

<div align="center">
<sub>一份写给自己的环境搭建备忘，也希望能帮到正在折腾 Windows 的你</sub>
</div>
