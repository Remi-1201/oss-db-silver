# CHAP 3 (インストール)

---

## 2.10

<div align="center"><img src="#"></div> 

---
#### 3.1.3 a

<div align="left"><img src="https://user-images.githubusercontent.com/97021497/207203393-7f33ce34-13d5-4db5-964c-b93357e1cba6.png" width="650"></div> 

```
$ su - 
# useradd -m -d /home/ postgres postgres 
# passwd postgres 
# su - postgres
```

#### 3.1.3 b.download & unzip source code

ページ（ https:// www. postgresql. org/ download/） から

```
$ tar xzvf postgresql-11.2.tar.gz
$ cd postgresql-11.2
 ```
 
 #### 3.1.3 c.install

```
sudo add-apt-repository ppa:ubuntu-toolchain-r/test
sudo apt-get update
sudo apt-get install gcc-snapshot
sudo apt-get install gcc g++
$ 【./configure】 or 
【./configure --without-readline --without-zlib】 or 
【./configure --prefix =/home/postgres/pgsql】

(if errors) --> export PATH="$PATH:/C/Work/postgresql-11.2/src/bin"
(if errors) --> sudo apt-get install postgresql-devel

(change to root) --> su -
sudo apt-get install make
$ make

$ su 
# make install 
# exit
 ```
 
#### 3.1.4 SETTINGS AFTER INSTALL
 
```
 $ vi ~/.bash_profile 
export PATH =/usr/local/pgsql/bin:$PATH <---インストール 先 の bin ディレクトリ を PATH に 追加
```
--> 追加　↓
```
export PATH=/C/Work/postgresql-11.2/src/bin:$PATH
export LD_LIBRARY_PATH=/C/Work/postgresql-11.2/src/backend/lib:$LD_LIBRARY_PATH
``` 
↓
``` 
 $ source ~/.bash_profile
 ```
 
