# AWS RDS 定價

RDS 依照資料庫引擎分為不同的定價項目，以下幾個是大部分引擎都有的項目：

## On-Demand Instance

On-Demand Instance 會依照小時計費，如果不滿一小時的話，會依照分鐘計費，但至少會計算十分鐘的費用。

## Reserved Instance

Reserved Instance 讓你可以透過預定 1 或 3 年的 Instance，獲得便宜於 On-Demand Instance 的折扣。

## Database Storage Cost

Database Storage Cost 是指 Instance 的硬碟容量

## Backup Storage cost

Backup Storage 是指資料庫的備份檔案，RDS 提供等同於資料庫本身硬碟容量的 Backup Storage 免費額度，舉例來說，假設你的 MySQL Instance 的硬碟容量是 700 GiB，當你的 Backup Storage 超過這個額度後才會被收費。

## Snaptshot Export

你可以手動為資料庫建立快照並傳輸到 S3 上備份

## Data Transfer Cost

依照資料傳輸的起始點與終結點，會有不一樣的傳輸費用，舉例來說，如果在同一個 Availability Zone，RDS 與 EC2 互相傳輸資料是不收費的，但如果是在 RDS 與外部網路的伺服器間傳輸資料，就會計算傳輸費用。

## RDS Extended Support

RDS 對每一種資料庫引擎的版本有制定一個 community end of life date 和 end of standard support date，使用者需要在 end of standard support date 之前更新資料庫版本，否則，會自動更新。這時候，使用者可以選擇購買 ES 延長舊版本的支援時間最長三年
