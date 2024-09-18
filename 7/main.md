# Elastic Compute Cloud (EC2)

## EC2 是什麼？

EC2 是一個在雲端上提供運算資源的 Web Service，運算資源是如電腦或手機設備中負責處理運算或儲存資料的資源，像是記憶體或核心。

## Instance Types

EC2 依照使用目的分為不一樣的 Instance Type，我們也可以從命名中知道 Instance 的目的。

Instance 的名字以逗點隔開分為兩個部分，前半部 Instance Family 與後半部 Instance Size，
Instance Family 分為 Series、Generation 與 Size，以 T3a.nano 來說，T 屬於 Burstable Performance Instances 系列，3 代表第三代，a 則代表處理器是 AMD，在同一個 Instance Family 中，還會以 Instance Size 區分出運算資源配比的不同，nano 就是 T3a Family 的其中一種 Instance Size。

https://docs.aws.amazon.com/ec2/latest/instancetypes/instance-type-names.html#:~:text=Instance%20types%20are%20named%20based,the%20options%2C%20for%20example%20gn%20.

AWS 依照不同的 Instance Family 分為不同的 Instance Types

### General Purpose

General Purpose，顧名思義，適合絕大部分的使用場景，像是網路應用程式、運算服務 ⋯⋯ 等等。

T (Burstable performance)、M (General Purpose) 和 Mac (macOS) 都屬於這個類別。

### Compute Optimised

Compute Optimised 適合影面轉碼、高效能運算 ⋯⋯ 等等的使用場景，Instance Series 為 C (Compute optimised) 的都屬於這個類別。

### Memory Optimised

Memory Optimised 適合需要在記憶體處理大量資料的場景，屬於這個類別的 Instance Family 有 R (Memory optimized)、U (High memory)、X (Memory intensive) 與 Instance Option z (High Performance)。

### Accelerated Computing

Accelerated Computing 透過硬體加速器或輔助處理器加速運算，以提供僅依賴 CPU 處理更高效的計算能力。
P (GPU accelerated) G (Graphics intensive) Trn (AWS Trainium) Inf (AWS Inferentia) DL F (FPGA) 與 VT (Video transcoding) 都屬於這個類別。

### Storage Optimised

Storage Optimised 適合高效率且需要順序讀取（Sequential read and write）的使用場景，順序讀取代表的是資料是依照順序被讀取的，像是影片串流或讀取一份檔案都是順序讀取，與其相對的是隨機讀取。

l (Storage Optimised)、lm (Storage optimized-1 to 4 ratio of vCPU to memory)、D (Dense Storage) 和 H 都屬於這個類別。

### HPC Optimised

HPC Optimised 是專為高效能計算工作設計，並提供最好的性價比。這一類別的 Instance Family 是 HPC (High performance computing)。
