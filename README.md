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
     ※URLはCodeボタンをクリックすると表示されるURL[`https://github.com/ユーザー名/リポジトリ名.git`]を入力する。
   * クローンしてきたフォルダのディレクトリに移動<br>
     $ cd クローンしてきたフォルダ<br>
   * ブランチを作成し作業ブランチに変更する<br>
     $ git checkout -b develop<br>
   * ファイルの編集(1のファイル作成と同じ流れでコミットまで行う)<br>
   * pushコマンドでリモートブランチにデータを送る<br>
     $ git push origin develop<br>
   * Aにプルリクエストを行う
   * GitHubの画面に戻ると、developのブランチに[Compare&pull request]ボタンが表示されているので、クリックする<br>
   ![画像pullリクエスト1](https://user-images.githubusercontent.com/78012223/106544448-e641f680-654a-11eb-8a70-c15fd17837f9.png)
   * リクエスト先が正しいことを確認し、[Create pull request]のボタンをクリックする
   ![画像pullリクエスト2](https://user-images.githubusercontent.com/78012223/106544659-45a00680-654b-11eb-858b-5dcc13a4967e.png)<br><br>
## 3. AはBのプルリクエストを承認しマージする
   * pull requestsタブをクリック
   ![pull-requests](https://user-images.githubusercontent.com/78012223/106425669-9100d900-64a7-11eb-8123-3dcc47781fd2.png)
   * マージしたいプルリクエストを選び、[Merge pull request] ボタンをクリック
   ![merge-button](https://user-images.githubusercontent.com/78012223/106425730-ad9d1100-64a7-11eb-9a04-4f07cec44a8b.png)
   * [Confirm merge] ボタンをクリック
   ![pullrequest-confirm](https://user-images.githubusercontent.com/78012223/106425607-729add80-64a7-11eb-8729-299439fab3ae.png)
   * マージの確認
   ![画像pullリクエスト3 ](https://user-images.githubusercontent.com/78012223/106545243-61f07300-654c-11eb-9659-c59c2cd01f6f.png)<br><br>

## 4. Aの作業
   * ローカルリモートに変更内容を反映（更新）する<br>
     $ git pull origin master<br>
   * index.htmlの内容を編集
   * 1のpushまでの流れを行う<br><br>
## 5. C (or B) の作業
   **<二人で作業する場合(Bの作業)><br>**
   * プッシュするための作業環境の準備<br>
   * 新しいリモートを追加する(URLにはクローン元のを使用)<br>
     $ git remote add upstream (URL)<br>
   * 作業ブランチをmasterに変更<br>
     $ git checkout master<br>
   * upsteramからpullしてmasterの最新状態を取得<br>
     $ git pull upstream master<br>
   * ローカルのmasterをoriginにpush<br>
     $ git push origin master<br>
   * 2の作業で作成したブランチへ移動<br>
     $ git checkout develop<br>
   * cssファイルの作成<br>
   * touchコマンドでcssファイル作成<br>
     $ touch style.css<br>
   * viコマンドでcssの編集<br>
   * 1のファイル作成と同じ流れでcssをコミットする<br>
     $ git add style.css<br>
     $ git commit -m "メッセージ内容"<br>
   * pushコマンドでリモートブランチにデータを送る<br>
     $ git push origin develop<br>
   * Aにプルリクエストを送る<br><br>
   **<三人の場合>**<br>
   * 2の作業で行った行ったことをcssとしてCが行う。<br<br>
## 6.AはCのプルリクエストを承認しマージする
   * pull requestsタブをクリック
   ![pull-requests](https://user-images.githubusercontent.com/78012223/106425669-9100d900-64a7-11eb-8123-3dcc47781fd2.png)
   * マージしたいプルリクエストを選び、[Merge pull request] ボタンをクリック
   ![merge-button](https://user-images.githubusercontent.com/78012223/106425730-ad9d1100-64a7-11eb-9a04-4f07cec44a8b.png)
   * [Confirm merge] ボタンをクリック
   ![pullrequest-confirm](https://user-images.githubusercontent.com/78012223/106425607-729add80-64a7-11eb-8729-299439fab3ae.png)
   * マージの確認
   ![画像pullリクエスト3 ](https://user-images.githubusercontent.com/78012223/106545243-61f07300-654c-11eb-9659-c59c2cd01f6f.png)<br><br>
↓参考にした記事一覧
・初心者向けGithubへのPullRequest方法 - Qiita 
https://qiita.com/samurai_runner/items/7442521bce2d6ac9330b
・Github で Fork してから Pull Request をするまでの流れ | けーこ in サンフランシスコ
http://kik.xii.jp/archives/179
