# PostgreSQL_practice

### Ubuntu dowload 不需要權限安裝:
* 點選這個網址: https://www.enterprisedb.com/download-postgresql-binaries
* 選擇適合你的作業系統版本
* 解壓縮並放到你要的目錄 : tar -xvaf postgresql-10.3-2-linux-x64-binaries.tar.gz
* 將bin目錄加到環境變數 export PATH="/home/nlplab/ting/pgsql/bin:$PATH"
* source ~/.zshrc   或 .bashrc 看你用的是bash or zsh
* 創建psql數據目錄 : mkdir pqsql_data
* 初始化這個數據目錄 : initdb -D pgsql_data/
* 啟動數據庫 : pg_ctl -D pqsql_data -l logfile start
* 可以看相關process進行 : ps -ef | grep postgres
* 不用時可以關掉數據庫 : pg_ctl -D pqsql_data -l logfile stop

### 命令介面操作:
* psql -h 127.0.0.1 -d postgres -U user -p 5432
* 設定密碼 : \password xxxxxx

### 創建新資料 :
* 先用命令介面登入進去後，CREATE DATABASE myexampledb OWNER user 或直接在shell中 createdb -T template0 mydb -p 5432
* 丟掉資料庫 : dropdb -h localhost -p 5432 -U user databases

### 數據庫操作 : 
* 創建新表 : CREATE TABLE user_tbl(name VARCHAR(20), signup_date DATE);
* 插入數據 : INSERT INTO user_tbl(name, signup_date) VALUES('ting', '2013-12-22');
* 選擇紀錄 : SELECT * FROM user_tbl;

### 用python3 連接 PostgreSQL
* 進去 pgsql_data/ 修改 pg_hba.conf 新增一條存去規則 : host all all 0.0.0.0/0 password
* 修改 postgresql.conf : listen_addresses = * 及 port = 5432
* 重新啟動資料庫
* pip install psycopg2 安裝模塊
* 如何用python3 連接資料請參考postgres_connect.ipynb


### 相關常見指令 : 
* \h：查看SQL命令的解釋，比如\h select。
* \?：查看psql命令列表。
* \l：列出所有數據庫。
* \c [database_name]：連接其他數據庫。
* \d：列出當前數據庫的所有表格。
* \d [table_name]：列出某一張表格結構。
* \du ：列出所有用戶
\conninfo：列出當前數據庫連接訊息



  

