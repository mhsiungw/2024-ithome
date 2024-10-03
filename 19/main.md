# Amazon S3 Storage Classes

Amazon S3 依照效能、定價和資料存取頻率分為不同的物件存取類別（Storage Class）。

![img](https://github.com/mhsiungw/2024-ithome/blob/main/19/storage-class-setting.jpg?raw=true)

## Default

### S3 Standard

S3 Standard 是預設的存儲類別。它提供 99.99% 的可用性和跨三個可用區的存儲，確保資料的高耐久性（99.999999999%），代表存取一百個億個物件只有一個物件會丟失，代表丟失物件的可能性極低。

## Unknown or changing access

### S3 Intelligent - Tiering

S3 Intelligent-Tiering 會依據資料的存取頻率自動將資料分類至不同的存儲層，包括 Frequent Access（預設）、Infrequent Access（資料未取用三十天後） 和 Archive Instant Access（資料未取用九十天後）。可額外選擇啟用 Archive Access 和 Deep Archive Access 來進一步節省成本。不同的存儲層有不同的計價模式。

S3 Intelligent-Tiering 提供 99.999999999% 的耐久性和 99.9% 的可用性。

### S3 Express One Zone

S3 Express One Zone 提供比 S3 Standard 快 10 倍的資料取用速度和更低的成本，但資料僅存放在單一可用區（AZ）。因此，使用者需考量到當該 AZ 發生問題時，資料喪失的風險。

S3 Express One Zone 提供 99.999999999% 的耐久性和 99.95% 的可用性。

## Infrequent Access

### S3 Standard - Infrequent Access

S3 Standard-Infrequent Access (S3 Standard-IA) 提供比 S3 Standard 更低的存儲成本，適合不常取用但需要快速存取的資料。雖然存取性能與 S3 Standard 相同，但存取成本較高，因此適合資料取用頻率低但對效能有要求的使用情境。

S3 Standard - Infrequent Access 提供 99.999999999% 的耐久性和 99.9% 的可用性。

### S3 One Zone - Infrequent Access

S3 One Zone-Infrequent Access (S3 One Zone-IA) 提供比 S3 Standard-IA 更低的存儲成本，但資料僅存放於單一可用區（AZ），與 S3 Express One Zone 類似，這增加了因 AZ 故障導致資料喪失的風險。

S3 One Zone 提供 99.999999999% 的耐久性和 99.95% 的可用性。

## Archive

### S3 Glacier Instant Retrieval

S3 Glacier Instant Retrieval 讓使用者可以用便宜的價格儲存資料，但存取資料時會有額外的資料存取費用（Data Retrieval requests 與 Data retrievals）。

S3 Glacier Instant Retrieval 提供 99.999999999% 的耐久性和 99.9% 的可用性。

### S3 Glacier Flexible Retrieval

S3 Glacier Flexible Retrieval 提供低成本存儲，並允許彈性解封存。使用者可選擇幾分鐘內付費取回資料，或等 5 至 12 小時免費取回。

S3 Glacier Instant Retrieval 提供 99.999999999% 的耐久性和 99.99% 的可用性。

### S3 Glacier Deep Archive

S3 Glacier Deep Archive 提供最低的 Storage 費用，但解封存資料需要花上 12 - 48 小時。

S3 Glacier Instant Retrieval 提供 99.999999999% 的耐久性和 99.99% 的可用性。
