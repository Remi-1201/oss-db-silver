# CHAP 4 (標準付属ツール)

## 練習問題　ここから～

## 3.5
<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208793494-7b9e0491-c73b-4ede-97af-ec83871c0da8.png"></div> 

## 練習問題　～ここまで

# CHAP 4 (メモ)

## 4-1 　 共通 的 な オプション 

<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208795413-6ade4a4f-7731-418e-bb0e-ef7007317f9c.png"></div> 

## 4-2-1 　 pg_ctl initdb

<div align="center"><img src="https://user-images.githubusercontent.com/97021497/208795736-22aebb94-963f-4719-b282-7f1d67ba6a84.png"></div> 

>次 の 例 では、 UTF 8 の エン コーディング、 ロ ケール なし で、/ pgdata ディレクトリ に データベース クラスタ を 作成 し て い ます。 

```
$
pg_ctl initdb -D /pgdata -o "--encoding=UTF8 --no-locale" 
```

## 4-2-2 　 pg_ctl start
