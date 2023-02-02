![[螢幕快照 2023-02-02 下午12.28.38.png]]

* 上圖為一個完整的 Git Flow 要有的流程。

### Master（主分支）
主要呈現給客戶的產品版本，確保每個版本都要可以執行，這個分支的來源只能從別的分支合併過來，**開發者不會直接commit到這個分支**，因為是穩定版，通常會在這分支上有版本編號。

### hotfix（Bug）
當master有Bug時，會**緊急產生hotfix的分支修復**，修完後再合併回master，也同時會合併到develop分支，為何要合併到Develop呢?因為不這樣做，當develop就會有此bug。

### release
當認為 Develop 分支夠成熟了，就可以把 Develop 分支合併到 Release分支，在這邊進行算是上線前的最後測試。測試完成後，Release 分支將會同時合併到 Master 以及 Develop這兩個分支上。Master 分支是上線版本，而合併回 Develop 分支的目的，是因為可能在 Release，分支上還會測到並修正一些問題，所以需要跟 Develop 分支同步，免得之後的版本又再度出現同樣的問題。

### develop
這個分支 是**所有開發的基礎分支**，當要新增功能時，會新增feature分支，開發完後再合併回Develop。

### feature
當要開始新增功能的時候，就是使用 Feature 分支的時候了。Feature 分支都是從 Develop 分支來的，完成之後會再併回 Develop 分支。
容易遭遇的問題：多個feature合併時容易遇到衝突，故features branch的**功能最好切越小越好**，並且縮短開發時程，降低衝突機率。
