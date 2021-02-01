# A,B,CでのGit練習
## 1. Aの作業
   * GitHub上にリモートリボジトリを用意
   ![スクリーンショット 2021-01-29 14 37 48](https://user-images.githubusercontent.com/78012223/106419912-e5528b80-649c-11eb-9071-867958ed4902.png)
   * 画面右上にある+ボタンをクリックし、[New repository]を選択する
   * ファイルをリボジトリ上にアップ
   ※ 今回は、Windows [GitBash]、mac[ターミナル]で行った
   * フォルダを作成したいディレクトリに移動し、mkdirコマンドで新規フォルダを作成<br>
     $ cd ディレクトリ名<br>
     $ mkdir フォルダ名<br>
   * 作成したフォルダに移動し、git initコマンドでgitを使用する準備をする<br>
     $ cd 作成したフォルダ名<br>
     $ git init<br>
   * リモートを追加
     $ git remote add origin [URL]<br>
     ※URLはCodeボタンをクリックすると表示されるURL[`https://github.com/ユーザー名/リポジトリ名.git`]を入力する。
![gitURL](https://user-images.githubusercontent.com/78012223/106419964-04511d80-649d-11eb-99a6-7a5b623d0289.png)
   * touchコマンドHTMLファイルを作成<br>
     $ touch index.html<br>
   * viコマンドでindex.htmlの中身を編集<br>
     ↓viエディターの使用方法は以下のサイトを参考<br>
https://www.i-ryo.com/entry/2018/11/27/010415#%E4%BD%9C%E6%88%90%E3%81%97%E3%81%9F%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%AE%E4%B8%AD%E8%BA%AB%E3%81%AF%E3%81%BE%E3%81%A0%E3%81%AA%E3%81%84<br>
   * HTMLファイル編集後、git addコマンドでindex.htmlをステージングエリアに上げる(どのファイルをpushするか選択)<br>
     $ git add index.html<br>
   * コミットする<br>
     $ git commit -m "メッセージ内容"<br>
   * pushコマンドでリモートブランチにデータを送る<br>
     $ git push origin master<br><br>
## 2. Bの作業
   * リモートリボジトリをローカルPCに取り込み、Aのリモートリボジトリに移動してフォークする。<br>
   ![fork](https://user-images.githubusercontent.com/78012223/106416815-a836cb00-6495-11eb-95fb-ec59fbd01a91.png)←フォークボタン<br>
   (これにより、自分のリボジトリにフォークしたリボジトリが入る。)
   * 次に、フォークしたリボジトリからクローンする
   * クローンするディレクトリへ移動、git cloneコマンドクローン<br>
     $ cd クローンするディレクトリ名<br>
     $ git clone[URL]<br>
     ※URLはCodeボタンをクリックすると表示されるURL[`https://github.com/クローン元ユーザー名/リポジトリ名.git`]を入力する。
   * クローンしてきたフォルダのディレクトリに移動<br>
     $ cd クローンしてきたフォルダ<br>
   * ブランチを作成し作業ブランチに変更する<br>
     $ git checkout -b develop<br>
   * ファイルの編集(1のファイル作成と同じ流れでコミットまで行う)<br>
   * pushコマンドでリモートブランチにデータを送る<br>
     $ git push origin develop<br>
   * Aにプルリクエストを行う<br><br>
## 3. AはBのプルリクエストを承認しマージする<br><br>
## 4. 
   
