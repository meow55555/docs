# Pull Request
為了避免 push 到共享或是別人的 repo 時發生衝突，你應該避免直接 push，發一個 Pull Request 是個更好的方式。  
To avoid push conflict when push to a shared or other's repo, please use pull request instead push it directly.

## 如何建立 PR How to Create a New PR
### fork
按下畫面右上方的「fork」按鈕  
Press the 'fork' button on the top right corner of the upstream repo.

### Clone
將上游 repo clone 到你的電腦  
Clone the repo from upstream to your local.

### 設定 push 目標 repo Set push remote
現在如果你執行 `git push`，會直接 push 到上游 repo，這不是我們想要的。所以你需要將 push 的目標 repo 更改成你上一步 fork 出去的 repo（你自己的）  
If you execute `git push` now, it will push commits to the upstream, which isn't what we want. So you need to change the push url to your own repo, which one you clone in the last step.  

執行 `git remote set-url --push origin <你自己的 repo>`。這會改變 push 的目標 repo，但是 fetch 還是原本的 upstream。  
Execute `git remote set-url --push origin <url to your own repo>`. This will change your push url, but you still can fetch from upstream.  

現在執行 `git remote -v`，結果應該要長的像下面這樣：  
Now execute `git remote -v`, the output should look like below:

```
origin  <url to upstream repo> (fetch)
origin  <url to your repo> (push)
```

如果兩個的位置反了，你可以修改 `.git/config` 檔直接調換他們。  
If the two are reverse, you can edit `.git/config` directly.

## 和上游同步 Sync with Upstream
在你開始編輯之前，記得要把你的 repo 和上游同步，這樣才能取得最新的版本。直接使用命令 `git pull` 就可以了，這非常簡單！
Before you open a PR, you need to sync your repo with upstream to catch up with the latest version. Just use command `git pull` to sync. It is very easy!  

> 注意：因為你取得所有的 commits，所以你的 commit tree 看起來會有點亂，但是別介意，直接 commit 就可以了。
> NOTE: You will get all commits from others, so the commit tree may look chaotic. Don't mind that. 

## Pull Request
當你完成修改後，按下你的 repo 的 GitHub 頁面上的「Contirbute」按鈕，跟著指示就可以提交一個 PR，記得寫下一些關於這次 PR 的描述。然後按下合併按鈕，你們都有權限。  
After you finish all changes, press the button 'Contirbute' button in your repo's github page. Follow the instructions, write some description about this PR. And then merge it, you all have the permission.

## Advance
如果可以的話，請在發 PR 前將你這次 PR 的所有 commits 壓縮成一個（用 `git rebase` 指令），這會讓 commit tree 看起來比較整齊。  
If you can, please squash all your commits into one(use `git rebase`). This helps the commit tree looks tidier. 
