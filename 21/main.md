# 區塊儲存相關服務

區塊儲存與物件儲存一樣是一種資料儲存的技術，它把資料分割成一樣大小的區塊並儲存在硬體。這樣的技術讓資料能夠快速被存取。

## Elastic Block Storage (EBS)

![img](https://github.com/mhsiungw/2024-ithome/blob/main/21/ec2-ebs-setting.jpg?raw=true)
EBS 是為 EC2 設計的區塊儲存服務，儲存在裡面的資料不會因為 EC2 停止而遺失。

EBS 主要分為兩個磁碟區類型

### Solid State Drive (SSD)

SSD 適合經常處理取用、更改小型資料的場景（transational workload），像是銀行資料。

### Hard Disk Drive (HDD)

HDD 適合需要同時處理大量資料的場景（throughput intensive workload），像是資料倉儲。

### EBS 相關計價項目

#### Amazon EBS Volume Types

兩個磁碟區類型可以再細分不同的類型，EBS 會依照你選擇磁碟區類型計價。

#### Amazon EBS Snapshots

你可以為 EBS 建立快照當作備份，會依照儲存的大小以每 GB 每月計費。還原備份時也會依照 GB 計費。

#### Recycle Bin for EBS Snapshots

為了防止誤刪 Snapshot 導致不可逆的結果，你可以為 Snapshot 設定 Retention Rule，設定 Snapshot 刪除的保留時間。

![img](https://github.com/mhsiungw/2024-ithome/blob/main/21/ebs-recycle.jpg?raw=true)

#### Amazon EBS Fast Snapshot Restore (FSR)

從 Snapshot 創建 EBS Volume 時，對於第一次的取用會有延遲的問題，你可以透過設定 FSR 降低延遲問題。FSR 依照小時計費。

#### Amazon EBS direct APIs for Snapshots

你可以使用 API 取得和創建 SnapShots，這會依照請求數量計費。

## Instance Store

![img](https://github.com/mhsiungw/2024-ithome/blob/main/21/ec2-instance-store-setting.jpg?raw=true)

每個 EC2 Instance 類型都支援以 EBS 的方式儲存資料，但有一些 EC2 Instance 類型也支援 Instance Store，但使用 Instance Store 儲存的資料會在 Instance 停止時消失，所以不適合儲存重要的資料。

使用 Instance Store 不需額外的費用。
