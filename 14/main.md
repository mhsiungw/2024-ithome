# Other RDS Optional Services

## Amazon Neptune

Amazon Neptune 是一個圖形資料庫，比起 SQL Databse 以 Table 的儲存資料的方式，圖形資料庫以節點的方式儲存資料，並利用邊（Edge） 形容節點間的關係。

使用者可以使用 Gremlin、SPARQL 或 openCypher 查詢資料庫資料。

## Amazon DynamoDB

DynamoDB 是 Amazon 提供的非關聯式資料庫，支援以鍵值或 Document 的資料型態儲存資料。

## Amazon Redshift

Amazon Redshift 是雲端資料倉儲，我自己把它理解為資料的倉庫，資料會從資料庫或交易系統 ⋯⋯ 等等的來源送進倉庫，並組織成適合被分析的型態，協助商業分析。

## Amazon ElastiCache

ElastiCache 讓你能夠簡化在雲端部署、管理 Memcached 和 Redis OSS Cache 流程的網頁服務

## Amazon MemoryDB

MemoryDB 是一個與 Redis OSS 相容的記憶體資料庫（In-memory Database），記憶體資料庫以記憶體為主要的資料儲存空間，但與快取不同的是，記憶體資料庫儲存的資料具有耐用性。耐用性是指除非硬體損壞，資料不會遺失。

## Amazon DocumentDB

Amazon DocumentDB 是一個與 MongoDB 相容的文件式資料庫服務。文件式資料庫以 JSON 格式儲存資料成一個 Document，並以 Collection 統整分類 Documents。

## Amazon Timestream for LiveAnalytics

Timestream 是用來儲存時間序列資料的資料庫，時間序列由在一段時間內記錄的資料點組合而成，像是股市價格或溫度。
