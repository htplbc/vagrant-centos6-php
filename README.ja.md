# Vagrant CentOS6 PHP 開発環境

このプロジェクトは、あなたのPHPプロジェクトを含むCentOS 6.5（64bit）仮想マシンをセットアップします。PHPプロジェクトのディレクトリを仮想マシンからマウントするため、ホスト側でお好みのエディタを使って作業できます。

## 必要なソフトウェア

* VirtualBox - フリーな仮想化ソフトウェア [ダウンロード](https://www.virtualbox.org/wiki/Downloads)
* Vagrant 1.5+ - VirtualBoxのイメージを操作するツール [ダウンロード](http://downloads.vagrantup.com/)
* Git - バージョン管理システム [ダウンロード](http://git-scm.com/downloads)

### テストされた環境

* Ubuntu 14.04     - VirtualBox 4.3.18 & Vagrant 1.6.5 & Git 1.9.1
* Mac OS X 10.10.1 - VirtualBox 4.3.18 & Vagrant 1.6.5 & Git 1.9.3

## この開発環境に含まれるもの

以下のいくつかは、Chef Opscodeリポジトリを使ってインストールされます。

* PHP 5.5
  * Xdebug
  * Zend OPcache
  * APCu
* Apache 2.2
  * FuelPHPプロジェクト用のバーチャルホスト設定
* MySQL 5.1
  * データベース **php_dev** および **php_test**
* phpMyAdmin 4.0
* PHPUnit 3.7
* Composer
* Git 1.7.1
* MongoDB 2.6
* Redis 2.4

(オプション)

* FuelPHP 1.x
* Phalcon 1.x / 2.x
* Beanstalkd

## 推奨されるセットアップ方法とディレクトリ構成

vagrant-centos6-phpをあなたのプロジェクトに追加します:

	$ git submodule add git@github.com:kenjis/vagrant-centos6-php.git vagrant
	$ cd vagrant
	$ vagrant up

ディレクトリ構成は以下のようになります:

	project/
	├── public/
	└── vagrant/

## PHPプロジェクトへのアクセス方法

* **ブラウザ(ポート転送)**: [http://localhost:8000](http://localhost:8000)
* **ブラウザ(IPアドレス直接)**: [http://192.168.33.33](http://192.168.33.33)
* **MySQL**: mysql:host=192.168.33.33;dbname=php_dev (rootユーザのpasswordはVagrantfileに設定されています)

### Vagrant

よく使うコマンド:

* `vagrant up` 仮想マシンを起動しプロビジョンします
* `vagrant suspend` 仮想マシンの状態を保存して停止します
* `vagrant halt` 仮想マシンを停止 (シャットダウン) します
* `vagrant ssh` 仮想マシンへのSSHアクセスを提供します
* `vagrant destroy` 仮想マシンを破棄します
* `vagrant status` 仮想マシンの状態を表示します
* `vagrant global-status` すべての仮想マシンの状態を表示します

もっと知りたい場合は、http://docs.vagrantup.com/v2/

## Thanks to

* https://github.com/iturgeon/vagrant-fuelphp