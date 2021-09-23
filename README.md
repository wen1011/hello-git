# git 心得

- 2021 中秋節快樂，大家上課辛苦了

![Happy Moon Festival](https://mir-s3-cdn-cf.behance.net/project_modules/disp/fec74e32654151.568e2bc66a28a.gif "Optional title")

- 出處https://www.behance.net/gallery/32654151/Happy-Moon-Festival

# 序. git<->github\gitlab

`git`

- 作業系統: Linux（Linux 嚴格來說是單指作業系統的核心，因作業系統中包含了許多使用者圖形介面和其他實用工具）
  Git 是一種分散式版本的版本控制系統（Version Control System） -解決：

* 「最新版本？」
* 「兩個版本之間的差異？」
* 「什麼功能是誰寫的？」
* 「什麼功能是在什麼時候寫的？」
* 「什麼功能是什麼時候拿掉的？誰拿掉的？」
* 「沒有負擔做很多功能測試」

`Github`

- 它取決於 Git 版本控制系統。 因此，可以對程序的源代碼進行操作並進行有序的開發。 而且，該平台是用 Ruby on Rails 編寫的。

`GitLab`

- GitHub 是另一個具有 Web 服務和版本控制系統的偽造站點，目的是使開發人員的生活更輕鬆。

`GitHub vs GitLab 的區別`

- GitHub

  `優點`

  - 免費服務，儘管它也提供付費服務。
  - 在回購結構中非常快速的搜索。
  - 社區很大，很容易找到幫助。
  - 它提供了與 Git 合作和良好集成的實用工具。
  - 易於與其他第三方服務集成。
  - 它還可以與 TFS，HG 和 SVN 一起使用。

  ` 缺點`

  - 它不是絕對開放的。
  - 它有空間限制，因為單個文件不能超過 100MB，而免費版本的存儲庫限制為 1GB。

- GitLab

  ` 優點`

  - 免費計劃無限制，儘管它有付款計劃。
  - 它是開源許可證。
  - 允許在任何計劃上進行自我託管。
  - 它與 Git 很好地集成在一起。

  ` 缺點`

  - 與競爭對手相比，它的界面可能會更慢。
  - 存儲庫存在一些常見問題。

# 1. 安裝 git

- 確認電腦裡是否有安裝過 git:
  > git --version

# 2. 設定環境變數

```markdown
$ git config --global user.name "''" "username"
$ git config --global user.email "useremail"

# 確認設定的內容

$ git config --list
```

# 3. 建立 repo

- repository (存儲庫) --> repo

* 在要被控管的專案底下，輸入這個指令
  > $ git init
* 直接把整個 .git 檔案夾刪掉

```markdown
rm -r .git
```

# 4. 在 repo 中新增、修改、刪除檔案

```markdown
# 查看 git 的狀態

$ git status

# 把檔案加入

$ git add test.txt

# 提交這次的修改

$ git commit -m "正確填寫這次 commit 的資訊"

# 檢視這次修改的差異

$ git diff

# 已經加入過的檔案，又有修改的話，一樣要再 add 一次，才可以 commit

$ git add test.txt
$ git commit -m "xxxx"

# 針對已經加入過的檔案，可以直接用以下指令提交

$ git commit -am "xxxxx"

# 可以「反悔」加入暫存區

$ git restore --staged login.html

# 反悔剛剛的修改

$ git restore login.html

# 讓檔案回到某個特定版本

$ git checkout <commit> test.txt

# 讓檔案回復到前兩個版本

$ git checkout HEAD~2 test.txt

# 回到現在版本

$ git checkout HEAD
```

```git log

```

相關指令

```markdown
# 查看提交紀錄

$ git log

# 查看特定檔案的紀錄

$ git log <file>

# 查看檔案修改細節

$ git log -p a.txt

# 可以搜尋關鍵字

$ git log --grep="delete"

# 查看內容是誰編寫的

$ git blame test.txt
```

# 5: 建立分支與合併

- 把 git 預設分支改成 main

```markdown
$ nano ~/.gitconfig  
[init]
defaultBranch = main
```

- hello-git 是 master 可以執行以下指令把主分支改成叫 main：

```$ git branch -m master main

```

- 分支指令：

```# 檢視分支
$ git branch

# * 是標注你所在的分支

# 建立分支
$ git branch <branch-name>

# 切換分支
$ git switch <branch-name>

```
