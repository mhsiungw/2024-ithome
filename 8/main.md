# EC2 Tenancy Types 與 Payment Options

## Tenancy Types

EC2 依照 Instance 部署的機器分為三種不同的 Tenancy Types，分別是 Shared Tenancy、Dedicated Instance 與 Dedicated Host

### Shared Tenancy

Shared Tenancy 是預設的選項，代表你的 Instance 會與其他帳戶的 Instance 共用同一台機器。
在定價上，以 t3.nano 舉例，一小時是 $0.0052 美金。

### Dedicated Instance

Dedicated Instance 讓你可以獨自享有硬體，不必與其他帳戶共享，但當 Instance 重新啟動時，不保證會在同一台機器上。在定價上，以 t3.nano 舉例，一小時是 $0.0052 美金，但因為 Dedicated Instance 的關係，每個 Region 只要有跑 Dedicated Instance，就會再加收 $2 美金，但這個價錢是以 Region 為單位計價，而不是 Instance 的數量計價。

### Dedicated Host

Dedicatd Host 與 Dedicated Instance 一樣，讓你可以獨自享有硬體，且 Instance 重啟時，會在同一台機器上。
在定價上，因為使用者是向 AWS 租借一整台機器，會以 Instance 類型的方式計價，像是 t3 一個小時的費用就是 $11.489 美金，且最多可以跑 192 個 t3.nano Instances。

如果以 Shared Tenancy On-Demand Rate 計算，$11.489 美金一個小時可以跑 2209 台 Instances，這樣看來，
除非有必要，才需要選擇 Dedicated Host。

### Dedicated Host 或 Dedicated Instance？

Dedicated Ins ㄅ tance 與 Dedicated Host 都能夠讓你不必與其他帳戶共用硬體，那到底該選哪一種呢？
因為 Dedicated Host 可以讓你選擇你要在哪一台機器上部署 Instance，且也可以設定當 Instance 重啟時，是否要在同一台機器上重啟，如果這兩個特性是你需要的，就選擇 Dedicated Host 吧！

## Purchase Models

AWS EC2 提供不同的計價方式

### On-Demand

On-Demand 是預設且最彈性的計價方式，讓你能夠隨時取用運算資源。

### Savings Plans

你可以使用 Savings Plans 以承諾使用 EC2 一年或三年換取高達 72% 的折扣，折扣的基數會以 On-Demand 的價格計算。

Savings Plans 分為 Compute Savings Plans、EC2 Instance Savings Plans 與 Amazon SageMaker Savings Plans，Compute Savings Plans 適用於 EC2、Lambda 與 Fargate，EC2 Instance Savings Plans 只適用於 EC2，Amazon SageMaker Savings Plans，顧名思義適用於 SageMaker。

### Spot Instances

Spot Instance 讓你可以透過使用 AWS 目前未被使用的運算資源，節省高達 90% 的費用，但缺點是 AWS 可能會隨時停止你的 Instance 服務。

### Reserved Instances

Reserved Instances 與 Savings Plans 一樣提供高達 72% 的折扣，但不一樣的是，這邊需要綁定特定的 Instance 類型，所以提供比 Savings Plans 更少的彈性。
