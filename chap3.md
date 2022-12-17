# CHAP 3 (インストール)

---

## 2.10

<div align="center"><img src="#"></div> 

---
#### 3.1.3 a

<div align="left"><img src="https://user-images.githubusercontent.com/97021497/207203393-7f33ce34-13d5-4db5-964c-b93357e1cba6.png" width="650"></div> 

```
$ su - 
(if errors) --> sudo su -
# useradd -m -d /home/postgres postgres 
# passwd postgres 
# su - postgres
```

#### 3.1.3 b.download & unzip source code

https://ftp.postgresql.org/pub/source/v11.2/postgresql-11.2.tar.gz

```
$ sudo tar xzvf postgresql-11.2.tar.gz -C /home
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
【./configure --prefix =/home/postgresql-11.2】


(if errors) --> export PATH="$PATH:/home/postgresql-11.2/src/bin"
(if errors) --> sudo apt-get install postgresql-devel

(change to root) --> su -

(if errors) --> sudo apt-get install readline
(if errors) --> sudo apt-get install make
```

```
# make
# sudo make install 
 ```
 
#### 3.1.4 SETTINGS AFTER INSTALL
 
```
su - postgres
 $ vi ~/.bash_profile 
export PATH =/usr/local/pgsql/bin:$PATH <---インストール 先 の bin ディレクトリ を PATH に 追加
```
--> 追加　↓

```
export PATH =/usr/local/pgsql/bin:$PATH
export LD_LIBRARY_PATH=/usr/local/pgsql/lib:$LD_LIBRARY_PATH
``` 
↓
``` 
# source ~/.bash_profile
 ```
 
 #### 3.1.5 起動と停止
 
``` 
 $  createdb -D /home/postgresql-11.2/ --locale=C
 createdb -D /home/postgres/data --locale=C

福岡 博; 笠原 辰仁; 宇山 公隆. OSS教科書 OSS-DB Silver Ver2.0対応 (p.116). 株式会社 翔泳社. Kindle 版. 
 createdb -D /home/postgres/data --no-locale

福岡 博; 笠原 辰仁; 宇山 公隆. OSS教科書 OSS-DB Silver Ver2.0対応 (p.116). 株式会社 翔泳社. Kindle 版. 
```
 ↓
> Warning: No existing cluster is suitable as a default target. Please see man pg_wrapper(1) how to specify one.
> Error: You must install at least one postgresql-client-<version> package
 ↓
```
sudo apt install postgresql-client-common
echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" | sudo tee /etc/apt/sources.list.d/pgdg.list
sudo apt update
sudo apt -y install postgresql-client
```
 
``` 
 $  createdb -D /home/remi/postgresql-11.2/ --locale=C
```
 ↓
> createdb: error: connection to server on socket "/var/run/postgresql/.s.PGSQL.5432" failed: No such file or directory
 
```
```
