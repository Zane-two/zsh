# zsh

## 一、 安装zsh\z4h

### 1. zsh

​	(1). Debian系 ： sudo apt install zsh

​	(2). Arch系 ： yay -S zsh \ sudo pacman -S zsh

### 2.z4h

#### (1). 修改hosts来确保基本的github访问：

```text
# GitHub Host Start

185.199.108.154              github.githubassets.com
140.82.113.21                central.github.com
185.199.108.133              desktop.githubusercontent.com
185.199.108.153              assets-cdn.github.com
185.199.108.133              camo.githubusercontent.com
185.199.108.133              github.map.fastly.net
199.232.69.194               github.global.ssl.fastly.net
140.82.112.3                 gist.github.com
185.199.108.153              github.io
140.82.114.3                 github.com
140.82.114.6                 api.github.com
185.199.108.133              raw.githubusercontent.com
185.199.108.133              user-images.githubusercontent.com
185.199.108.133              favicons.githubusercontent.com
185.199.108.133              avatars5.githubusercontent.com
185.199.108.133              avatars4.githubusercontent.com
185.199.108.133              avatars3.githubusercontent.com
185.199.108.133              avatars2.githubusercontent.com
185.199.108.133              avatars1.githubusercontent.com
185.199.108.133              avatars0.githubusercontent.com
185.199.108.133              avatars.githubusercontent.com
140.82.114.10                codeload.github.com
52.216.114.235               github-cloud.s3.amazonaws.com
52.216.107.20                github-com.s3.amazonaws.com
52.217.94.236                github-production-release-asset-2e65be.s3.amazonaws.com
52.217.133.241               github-production-user-asset-6210df.s3.amazonaws.com
52.216.244.140               github-production-repository-file-5c1aeb.s3.amazonaws.com
185.199.108.153              githubstatus.com
64.71.144.202                github.community
185.199.108.133              media.githubusercontent.com

# Please Star : https://github.com/ineo6/hosts
# Mirror Repo : https://gitee.com/ineo6/hosts
# Update at: 2021-12-06 14:14:14

# GitHub Host End
```

 如果还是不行那你可能需要先完成科学上网的设置

#### (2). 执行命令安装z4h

```
if command -v curl >/dev/null 2>&1; then
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/romkatv/zsh4humans/v5/install)"
else
  sh -c "$(wget -O- https://raw.githubusercontent.com/romkatv/zsh4humans/v5/install)"
fi
```

整个安装过程完全交互式，根据自己需要安装即可

#### (3). 设置成默认

```bash
chsh -s /usr/bin/zsh
```

## 二、 安装oh-my-zsh

<a src="https://ohmyz.sh/">官网</a>

<a src="https://github.com/ohmyzsh/ohmyzsh/">github</a>

#### 1. curl

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

#### 2. wget

```
sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

#### 3. git

```bash
git clone https://gitee.com/mirrors/oh-my-zsh ~/.oh-my-zsh

cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc

chsh -s /bin/zsh
```

#### 4. Gitee ( 国内镜像 )

```bash
sh -c "$(wget -O- https://gitee.com/pocmon/mirrors/raw/master/tools/install.sh)"
```

## 三、 oh-my-zsh插件安装

#### 1. zsh自带的插件

##### extract

提供一个 extract 命令，以及它的别名 x。功能是：一！键！解！压！你知道tar的四种写法吗？我也不知道，所以我装了这个。从今以后 tar, gz, zip, rar 全部使用 extract 命令解压，再也不用天天查 cheatsheet 啦！

##### rand-quote

提供一条 quote 命令，显示随机名言。和fortune的作用差不多，但是我感觉fortune上面大多是冷笑话，还是quote的内容比较有意思。

当然这种东西很少有人会主动去按的。所以你可以在你的zshrc里面的最后一行加上quote，实现每次打开shell显示一条名言的效果～

再进一步，安装一个cowsay，把quote | cowsay放到zshrc的最后一行。于是每次打开终端你就可以看到一头牛对你说：

![img](https://pic3.zhimg.com/50/v2-adfbc44c98d3a6b1137efa8a7abfda6c_720w.jpg?source=1940ef5c)![img](https://pic3.zhimg.com/80/v2-adfbc44c98d3a6b1137efa8a7abfda6c_720w.jpg?source=1940ef5c)

##### themes

提供一条 theme 命令，用来随时手动切换主题。在想要尝试各种主题的时候很实用，不需要一直改 zshrc 然后重载。

##### gitignore

提供一条 gi 命令，用来查询 gitignore 模板。比如你新建了一个 python 项目，就可以用

```text
 gi python > .gitignore 
```

来生成一份 gitignore 文件。

##### cp

提供一个 cpv 命令，这个命令使用 rsync 实现带进度条的复制功能。

##### zsh_reload

提供一个 src 命令，重载 zsh。对于经常折腾 zshrc 的我，这条命令非常实用。

##### git-open

提供一个 git-open 命令，在浏览器中打开当前所在 git 项目的远程仓库地址。

##### z

提供一个 z 命令，在常用目录之间跳转。类似 autojump，但是不需要额外安装软件。

##### vi-mode

vim输入模式，非常强大，不用多说。

##### per-directory-history

开启之后在一个目录下只能查询到这个目录下的历史命令。按 Ctrl+g 开启/关闭。对我来说很实用，但是不一定所有人都喜欢，可以考虑一下自己是否真的需要。

##### command-not-found

当你输入一条不存在的命令时，会自动查询这条命令可以如何获得。

##### safe-paste

像我这样的懒人，经常会从网上复制各种脚本。但是复制的命令有可能并不就是我要的，可能还需要改一改。但是往往我复制了几行脚本，粘贴到 zsh 里，就发现它直接运行了。这真是非常危险。

这个插件的功能就是：当你往 zsh 粘贴脚本时，它不会被立刻运行。给了我这种懒人修改别人脚本的机会。

##### [colored-man-pages](https://www.zhihu.com/search?q=colored-man-pages&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A617215298})

给你带颜色的 man 命令。

##### sudo

apt 忘了加 sudo？开启这个插件，双击 Esc，zsh 会把上一条命令加上 sudo 给你。

##### history-substring-search

一般人会在 zsh 中绑定 history-search-backward 与 histor-search-forward 两个功能。

```text
bindkey '^P' history-search-backward
bindkey '^N' history-search-forward
```

这样子，就可以在输入一个命令，比如 git 之后，按 Ctrl-P 与 Ctrl-N 在以 git为前缀的历史记录中浏览，非常方便。

但是这个做法有一个问题，就是这个功能只考虑输入的第一个单词。也就是说，如果之前输入了 git status, git commit, git push 等等命令，那么我输入 "git s" 再 Ctrl-P，并不会锁定到 "git status", 而是会在所有以 git 开头的历史命令中循环。

这个插件的功能就是实现了一对更好用的 history-search-backward 与 histor-search-forward ，解决了上面所说的问题。开启之后，需要绑定按键：

```text
bindkey '^P' history-substring-search-up
bindkey '^N' history-substring-search-down
```

这样子就可以以自己输入的所有内容为前缀，进行历史查找了。

#### 2. 单独安装的插件

##### zsh-autosuggestions

```text
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

##### zsh-syntax-highlighting

```text
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

 不属于自带插件，需要写入~/.zshrc中：

```
source "$ZSH_CUSTOM/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh"
```

## 四、 powerlevel10k主题

#### 1.Powerlevel10k 安装

- 手动安装

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

- 国内用户可以使用 [http://gitee.com](https://link.zhihu.com/?target=http%3A//gitee.com) 上的官方镜像加速下载.

```bash
git clone --depth=1 https://gitee.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

#### 2. Powerlevel10k 配置

- 编辑 .zshrc 文件， 文件路径 ~/.zshrc

```rb
open ~/.zshrc

ZSH_THEME="powerlevel10k/powerlevel10k"
```

- ```
    source .zshrc
    ```

#### 3. 设置Nerd-Font字体	(否则图标会乱码)

##### (1). 首先下载文件

```ruby
wget -c https://github.com/ryanoasis/nerd-fonts/releases/download/v2.0.0/SourceCodePro.zip
```

##### (2). 然后解压到文件夹:

```bash
sudo unzip SourceCodePro -d /usr/share/fonts/SourceCodePro
```

##### (3). 转到/usr/share/fonts/SourceCodePro目录，并安装

```bash
cd /usr/share/fonts/SourceCodePro
sudo mkfontscale # 生成核心字体信息
sudo mkfontdir # 生成字体文件夹
sudo fc-cache -fv # 刷新系统字体缓存
```

Source Code Pro fot Powerline, Jetbrains Mono Nerd Fonts

#### 4. 配色方案

##### (1). 第一步

```
git clone git://github.com/seebi/dircolors-solarized.git
```

```
cp ~/dircolors-solarized/dircolors.256dark ~/.dircolors
```

```
eval 'dircolors .dircolors'
```

##### (2). 第二步 (先检查 echo $TERM)

```
vim .barshrc
```

```
export TERM=xterm-256color
```

##### (3). 第三步

```
git clone git://github.com/sigurdga/gnome-terminal-colors-solarized.git
```

```
cd gnome-terminal-colors-solarized
```

```
./set_dark.sh  or  ./set_light.sh
```
