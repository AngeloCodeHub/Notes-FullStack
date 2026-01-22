
## GitHub Desktop reset限制條件

- 限制條件：你只能把分支重設到「最多到已經推送（pushed）到遠端的那個 commit」。如果你選的歷史 commit 在遠端已經有更新（也就是比最近一次已推送的 commit 更舊／不在可重設範圍），Reset 就會被停用（灰色）。
    - 如果你想還原已經推送的 commit，不要使用 Reset，改用「Revert changes in commit」（會產生一個反向的 commit），以免破壞其他人可能已基於該歷史做的工作。
- 受保護分支：如果目前分支是受保護分支，GitHub Desktop 也會提示或限制某些會變更歷史的操作；遇到限制時請切換到非受保護的分支再操作，或使用 Revert。
- 本地未推送的最近 commit：若你只是想回復最近未推送的 commit，可以用左側 Changes 頁面的「Undo」按鈕（撤銷最後一次 commit）。
