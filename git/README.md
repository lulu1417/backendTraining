# 前言
版本控制系統大概是最基礎的工具，不管你是在前端、後端還是 APP。熟悉 Git 是基本技能。假設你現在是一個人開發 Web 專案，你至少需要熟悉以下流程。

# 推薦學習資源
中文書：[為你自己學Git](https://gitbook.tw/)

# 問題
- Q1: 請說明
    1. 什麼是版本控制系統？
        幫你紀錄檔案更動內容的好工具，分成集中式和分散式。集中式只能一次一個人在專案目錄下更改檔案，分散式可讓多人同時在同個專案目錄下更改檔案
    2. Git 版本控制中有哪幾種檔案狀態？
        共有四種檔案狀態。
        ![](https://i.imgur.com/XqHZ5xL.png)

        1. untracked，未被git追蹤：尚未git init的所有檔案，或新加入但未被git追蹤的檔案
        2. change not stage for commit，已在工作目錄下，但尚未加進暫存區(stage)的檔案
        3. changed to be commit，已經加進暫存區，但未commit，或commit之後內容又有更動的檔案
        4. commited，已經提交的檔案

![](https://i.imgur.com/hZoDAPf.png)
- Q2: 上圖 A-J 是 Git 中檔案狀態切換得流程，請查出 A-J 執行的指令。(重點是確保自己真的學到在什麼情況下使用該指令。)
    - A: 將一般目錄變成 git working folder
	    ```git init ``` 會在專案目錄下自動建立.git這個資料夾
	- B: 將 working folder 的異動狀態登錄到 stage
	    ```git add 檔案名稱```
	- C: 將 stage 的狀態放到 local repository
        ```git commit -m "commmit message"```
    - D: 將 local repository 的狀態放到 remote repository
        ```git push```
    - E: 將 remote repository 的狀態取回到 local repository
        ```git pull```
    - F: 將 local repository 的狀態退回到 stage 階段（是 C 的逆向）
        ```git reset HEAD^ --soft```
    - G: 將 stage 的狀態退回到 working folder 階段（是 B 的逆向）
        ```git rm --cached 檔案名稱``` 一定要加--cached，不然會變成直接刪除那個檔案
    - H: 將 local repository 的狀態一口氣退回到 working folder 階段（是 B+C 的逆向）
        ```git reset HEAD^```  git reset預設是--mixed，hard則是連程式碼一起回到前一個commit紀錄
        
    - I: 從 remote repository 取回建立成新的 working folder
        ```git clone```
    - J: 將 git working folder 變回一般目錄
        ```rm -rf .git```，-r是遞迴刪除資料夾下的檔案，-f是強制刪除，不加的話每個檔案都要手動確認是否確定刪除
- Q3. 做這個題目，你事前評估做了什麼、利用了哪些資源、排程為何、事後怎麼驗收、得到什麼經驗？
    有先上網查資料，自己再實驗一次，過程中透過git log、git status，和IDE的提示來檢視操作結果是否正確。
    之前沒用過```git rm --cached```，算是學到了受用的新知識，可以把忘記加到.gitignore的檔案從暫存區再取回。        4. commited，已經提交的檔案

![](https://i.imgur.com/hZoDAPf.png)
- Q2: 上圖 A-J 是 Git 中檔案狀態切換得流程，請查出 A-J 執行的指令。(重點是確保自己真的學到在什麼情況下使用該指令。)
    - A: 將一般目錄變成 git working folder
	    ```git init ``` 會在專案目錄下自動建立.git這個資料夾
	- B: 將 working folder 的異動狀態登錄到 stage
	    ```git add 檔案名稱```
	- C: 將 stage 的狀態放到 local repository
        ```git commit -m "commmit message"```
    - D: 將 local repository 的狀態放到 remote repository
        ```git push```
    - E: 將 remote repository 的狀態取回到 local repository
        ```git pull```
    - F: 將 local repository 的狀態退回到 stage 階段（是 C 的逆向）
        ```git reset```
    - G: 將 stage 的狀態退回到 working folder 階段（是 B 的逆向）
        ```git rm --cached 檔案名稱``` 一定要加--cached，不然會變成直接刪除那個檔案
    - H: 將 local repository 的狀態一口氣退回到 working folder 階段（是 B+C 的逆向）
        
    - I: 從 remote repository 取回建立成新的 working folder
        ```git clone```
    - J: 將 git working folder 變回一般目錄
        ```rm -rf .git```，-r是遞迴刪除資料夾下的檔案，-f是強制刪除，不加的話每個檔案都要手動確認是否確定刪除
- Q3. 做這個題目，你事前評估做了什麼、利用了哪些資源、排程為何、事後怎麼驗收、得到什麼經驗？
    有先上網查資料，自己再實驗一次，過程中透過git log、git status，和IDE的提示來檢視操作結果是否正確。
    之前沒用過```git rm --cached```，算是學到了受用的新知識，可以把忘記加到.gitignore的檔案從暫存區再取回。