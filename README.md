golang-gin-example
===

## Install Go

`Go`をインストールする。

```sh
$ brew update
$ brew install go --cross-compile-all
```

`launchctl`に登録する。

```
# /etc/launchd.conf
setenv GOROOT /usr/local/Cellar/go/1.3.1/libexec
setenv GOPATH $HOME/.go
```

```
$ launchctl < /etc/launchd.conf
```

## Run golang-gin-example

パッケージマネージャに[goop](https://github.com/nitrous-io/goop)を使用しているので、インストールする。

```
$ go get github.com/nitrous-io/goop
```

対象のリポジトリをクローンする。

```
$ git clone git@github.com:osamingo/golang-gin-example.git
```

ディレクトリを移動して、依存関係を解決する。  
`goop`コマンドが見つからない場合は、`$GOPATH/bin/goop`とかに存在するので`PATH`を通す。

```
$ cd golang-gin-example
$ goop install
```

`go run`で動かす。

```
$ goop go run src/main.go
```

起動後、`http://localhost:8080/ping`に繋がるか確認できればOKです。

## Install IntelliJ IDEA & Golang plugin

### IntelliJ IDEA

DL site: [IntelliJ IDEA - The Best Java and Polyglot IDE](http://www.jetbrains.com/idea/)

上記のサイトから、通常通りインストールする。

### Install Golang plugin

EAP DL site: [@dlsniper's dropbox](https://www.dropbox.com/sh/kzcmavr2cmqqdqw/j8wjp8SdNH) (@via/  [go-lang-plugin-org/go-lang-idea-plugin](https://github.com/go-lang-plugin-org/go-lang-idea-plugin))

最新版のプラグインを使用したいので、作者のDropboxからEAPの`jar`をDLする。

![install-plugin-from-jar](https://raw.githubusercontent.com/osamingo/golang-gin-example/master/img/install-plugin-from-jar.png)

上記のハイライトしているボタンを押下してインストールする。

## Start IntelliJ IDEA

コマンドラインから起動しないと、何故か`GOROOT`を見てくれないので、`open`コマンドで起動する。

```
$ open /Applications/IntelliJ\ IDEA\ 13\ CE.app
```

起動後、`Import Project...`からプロジェクトをインポートする。

![import-project-one](https://raw.githubusercontent.com/osamingo/golang-gin-example/master/img/import-project-one.png)

![import-project-two](https://raw.githubusercontent.com/osamingo/golang-gin-example/master/img/import-project-two.png)

![import-project-three](https://raw.githubusercontent.com/osamingo/golang-gin-example/master/img/import-project-three.png)

インポート後、`Shift + Command + A`で、`Find Action`を起動させる。

![edit-configurations](https://raw.githubusercontent.com/osamingo/golang-gin-example/master/img/edit-configurations.png)

`.vendor`に`GOPATH`を通す。

![edit-configurations-detail](https://raw.githubusercontent.com/osamingo/golang-gin-example/master/img/edit-configuration-detail.png)

`main.go`を右クリックし、起動させる。

![run-main](https://raw.githubusercontent.com/osamingo/golang-gin-example/master/img/run-main.png)

起動後、`http://localhost:8080/ping`に繋がるか確認できればOKです。
