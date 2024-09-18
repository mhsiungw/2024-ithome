# AWS Database Migration Service (DMS)

## AWS Database Migration Service 是什麼？

DMS 協助使用者把資料庫遷移到 AWS 的資料庫服務上，像是把 MySQL 遷移到 RDS For MySQL 或者 MongoDB 遷移到 AWS DocumentDB。

## 同質資料（Homogeneous）和異質資料（Heterogeneous）遷移

DMS 遷移分為同質資料遷移和異質資料遷移。同質資料遷移是指像 MySQL 遷移到 RDS For MySQL 這樣同種資料庫間的遷移，異質資料庫是指像從 Oracle 資料庫到開源資料庫的資料庫遷移。

## DMS 相關元件

![img](https://docs.aws.amazon.com/images/dms/latest/userguide/images/datarep-intro-rep-instance1.png)

### Replication Instance

Replication Instance 負責執行 Migration Task，是一個部署在 EC2 上的伺服器。

### Endpoints

DMS 使用 Endpoints 連接到你的 Target 和 Source 資料庫。

### Task

你需要透過創建 Migration Task 執行資料遷移。在 Task，你需要設定 Replication Instance 和 Endpoints，你也可以透過 Task 決定要遷移哪些資料。

## 執行 DMS 的大概步驟

1. 創建 Replication Instance
2. 創建連接 Target/Source 資料庫的 Endpoints
3. 創建 Migration Task
