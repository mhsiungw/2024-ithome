# Amazon Elastic File System（EFS）、FSx 和 Storage Gateway

## Amazon Elastic File System (EFS)

Amazon Elastic File System (EFS) 是 AWS 提供的可擴展雲端檔案儲存服務，根據實際使用的存儲量和存取次數進行計價。它可以自動擴展和縮減以符合應用程式需求，適合多個 EC2 實例同時存取。

## AWS FSx

Amazon FSx 和 EFS 都是 AWS 的雲端檔案系統服務，但 FSx 提供了四種不同的檔案系統選項，分別是 FSx for Windows File Server、FSx for Lustre、FSx for NetApp ONTAP 和 FSx for OpenZFS，以滿足不同的工作負載需求。相比之下，EFS 主要針對 Linux 環境，專為簡單擴展的 NFS 文件存儲而設計。
![img](./fsx.jpg)

## AWS Storage Gateway

AWS Storage Gateway 提供一個混合式儲存解決方案的介面，讓本地應用程式能夠無縫地存取 AWS 雲端儲存空間。你可以使用 Amazon S3 File Gateway，讓本地檔案系統透過此介面存取和儲存資料到 S3。計費項目包括儲存的資料大小、存取請求數量，以及從 AWS 傳出的數據流量。
