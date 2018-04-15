# PostgreSQL_practice

### Ubuntu dowload 不需要權限安裝:
1.點選這個網址: https://www.enterprisedb.com/download-postgresql-binaries
2.選擇適合你的作業系統版本
3.解壓縮並放到你要的目錄 : tar -xvaf postgresql-10.3-2-linux-x64-binaries.tar.gz
4.將bin目錄加到環境變數 export PATH="/home/nlplab/ting/pgsql/bin:$PATH"
5.source ~/.zshrc   或 .bashrc 看你用的是bash or zsh
6.創建psql數據目錄 : mkdir pqsql_data
7.初始化這個數據目錄 : initdb -D pgsql_data/
8.啟動數據庫 : pg_ctl -D pqsql_data -l logfile start
9.可以看相關process進行 : ps -ef | grep postgres
10.不用時可以關掉數據庫 : pg_ctl -D pqsql_data -l logfile stop

### 命令介面操作:
1.psql -h 127.0.0.1 -d postgres -U user -p 5432
2.設定密碼 : \password xxxxxx

### 創建新資料 :
先用命令介面登入進去後，CREATE DATABASE myexampledb OWNER user




  

