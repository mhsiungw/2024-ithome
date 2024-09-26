# Amazon Relational Database Service (RDS)

RDS 是 Amazon 提供的資料庫服務，協助使用者更輕鬆的設定、管理與擴展資料庫。
設定 RDS 時，你需要設定 Database Engine，Database Engine 是 RDS DB Instance 裡實際在跑的資料庫，RDS 提供了七種不同的 Database Engine

## Database Engines

1.  Amazon Aurora
    Amazon Aurora 是 AWS 的 Data Engine，與 PostgreSQL 與 MySQL 相容，意思就是從 PostgreSQL 與 MySQL 遷移到 AUrora 是可行的。
2.  RDS For PostgreSQL
3.  RDS For MySQL
4.  RDS For MariaDB
5.  RDS For SQL Server
6.  RDS For Oracle
7.  RDS For Db2

## When to use EC2 hosted databases or AWS RDS?

既然我們也能夠自己在 EC2 上部署資料庫，那在什麼樣的情況才需要考慮使用 RDS 呢？
RDS 除了提供 DB Instance 讓使用者可以儲存與獲取資料外，還提供下列服務：

1. Managed automated backups
   RDS 每日依照 Region 會自動地在不同時間點執行資料庫備份，並儲存在 S3 一段設定的時間，你可以用這些「資料庫快照」重新創建資料庫，取回資料。
2. DB event notifications
   RDS 也能夠在特定 Event 發生時，透過郵件通知使用者
3. Built-in instance and database monitoring and metrics
   RDS 每一分鐘會發送資料庫的相關指標到 CloudWatch，像是 Instance 的 CPU 使用率或者 Database 相關的效能指標。
4. Automatic software patching
   每個 RDS Instance 創建時會設定一個維護時段（沒設定的話會由 RDS 依照 Region 挑選），RDS 會在維護時段執行一些安全性問題相關的軟體更新，像是資料庫引擎

所以如果你選擇在 EC2 上管理資料庫的話，這些都會變成你需要考慮的事情。
