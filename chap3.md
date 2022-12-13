# CHAP 3 (インストール)

---

## 2.10

<div align="center"><img src="https://user-images.githubusercontent.com/97021497/206949032-90eb7bfc-e990-40db-a329-7dfbcf497b7f.png"></div> 

---

<div align="left"><img src="https://user-images.githubusercontent.com/97021497/207203393-7f33ce34-13d5-4db5-964c-b93357e1cba6.png" width="650"></div> 

```
$ su - 
# useradd -m -d /home/ postgres postgres 
# passwd postgres 
# su - postgres
```

#### download & unzip source code

ページ（ https:// www. postgresql. org/ download/） から

```
tar xzvf postgresql-11.2.tar.gz
cd postgresql-11.2
 ```
 
 #### install

```
sudo add-apt-repository ppa:ubuntu-toolchain-r/test
sudo apt-get update
sudo apt-get install gcc-snapshot
sudo apt-get install gcc g++
【./configure】 or 【./configure --without-readline --without-zlib】 or 【./configure --prefix =/home/postgres/pgsql】

(if errors) --> export PATH="$PATH:/C/Work/postgresql-11.2/src/bin"
(if errors) --> sudo apt-get install postgresql-devel

(change to root) --> su -
sudo apt-get install make
$ make
 ```
