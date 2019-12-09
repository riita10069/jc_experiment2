プログラミング言語：Python3
コンパイル方法：スクリプト言語なので不要。 cythonとかも特に使っていない
実行方法：jupyter notebookを起動してセルごとに Shift+Enter

## jupyter notebookの起動の方法(jupyterの環境がある場合は読み飛ばしていただいて構いません。)
### localのMacやWinを想定した場合

- Anaconda
- docker
- minikube
- Cookiecutter

とか色々方法はあります。

dockerを用いた方法が一番楽だと思うので、紹介しておきます。

https://www.docker.com/
からdockerをインストールします。

`docker pull jupyter/scipy-notebook`
で公式のイメージがあるので、Dockerfileを書く必要はありません。

`docker run -v `pwd`:/home/jovyan/work -p 8888:8888 --name jupyter jupyter/scipy-notebook`
とすれば、jupyterが立ち上がります。

コンソールの下の方に
```
Copy/paste this URL into your browser when you connect for the first time,
to login with a token:
http://7dae9a493ca7:8888/?token=<トークン>
```

というのが流れてくるはずなので、言われた通りのURLにアクセスすることで、jupyterがひらけます。
終わりです。


### どうしてもうまくいかない場合
https://34.84.172.63:8888/notebooks/18B15997_RyotaYamada/
に提出した課題と取り組んでいる課題があるので提出期限が過ぎているものからアクセスしてください。

こちらは、Kubernetesのクラスター上にPodとしてDockerのコンテナを配置しています。
Podとしてjupyterを配置しています。
HTTPSとWebSocketでコネクトが取れるようになってます。
DNSの設定はしていないので、IPアドレスに直接HTTPS飛ばしてください。
TLSによって提供される暗号化通信上でHTTP通信を行うように設定しているので、安全ですが、
認証局によって署名されたサーバ証明書とその秘密鍵には、OpenSSLを使用していて、中間 CA 証明書を発行していないです。
なので、接続はプライベートではありません。みたいなの出てくると思いますが、このWebサイトを閲覧ってしていただいて大丈夫です。
パスワードを要求されると思いますが、パスワードは、`titech5`なので、それでアクセスしてください。

