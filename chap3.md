# CHAP 3 (インストール)

---　

## 練習問題　ここから～

## 3.5
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208793494-7b9e0491-c73b-4ede-97af-ec83871c0da8.png"></div> 
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208793546-c0ca25a8-c67d-41c8-bbab-d8c078defe65.png"></div> 

<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208794420-3f085314-3b25-45ae-897e-34b49b34041b.png"></div> 
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208794473-9d75dbfc-e02a-4654-912d-2fdba00f3c7d.png"></div> 

## 3.4
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208791854-79a981ba-add6-4454-ade5-13b009079cb5.png"></div> 
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208791919-529d4453-911b-436e-a99f-3d53bd7ca35e.png"></div> 

<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208793254-119c7da5-3098-4593-bc19-942ff9150d09.png"></div> 
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208793306-f790b245-ac09-4571-83eb-c651c4441d4c.png"></div> 

## 3.3
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208568692-c9ae2507-8c0b-4473-a9c5-842020939c26.png"></div> 
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208568755-737a1d80-d4a5-44a1-85d5-906b84212eaf.png"></div> 

<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208569357-d383d8e4-fb26-4ec5-89a6-558cb7c668f1.png"></div> 
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208569519-5a5526c7-eb87-4e61-9873-911ed6dc8991.png"></div> 

## 3.2

<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208561183-5b5e3901-0fb6-4108-a60e-587c0a72e397.png"></div> 
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208561246-d33ab87b-89a3-4e16-a49d-f8fa8916db3f.png"></div> 

<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208563857-5d26ef6a-a210-4929-814b-e38f1f154dad.png"></div> 
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208563910-2a92b132-39cb-45dc-aaa5-054982ec2f59.png"></div> 

## 3.1

<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208555794-6ad83e45-4dc5-4768-9854-ed21b5edee68.png"></div> 
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208557879-353a9c76-7a6f-4b18-b89f-0209724afff8.png"></div> 

<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208560077-e1ada24e-3ea8-4056-8a97-b79a40d5b663.png"></div> 
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208560141-379e5152-54e1-4b7f-90d8-2656dec410bf.png"></div>


## 練習問題　～ここまで

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
