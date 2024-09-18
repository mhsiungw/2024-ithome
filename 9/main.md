# AWS Fargate

AWS Fargate 是一個與 ECS 或 EKS 搭配使用的 Serverless 的服務，讓你可以不用手動設定需要提供給 ECS 與 EKS 的運算資源。在 AWS 中，一個 Serverless 的服務含有以下的特點，不用管理伺服器、按使用的資源付費、自動規模化，與 AWS Fargate Serverless 的特性對比，EC2 不是一個 AWS 定義的 Serverless 的服務，因為使用者仍需要管理伺服器，這裡的管理伺服器是指更新 EC2 Instance 上的 OS、處理安全性漏洞和手動在上面跑應用程式 ⋯⋯ 等等。

## Pricing

AWS Fargate 會依照你要求的運算資源計價，以 US East 為例，每個 vCPU 每小時費用為 $0.04048，每個 GB 的記憶體每小時費用是 $0.004445，除此之外，你也可以透過使用 Spot Fargate 運行可被中斷的服務，節省高達 70% 的費用。除了運算資源，Fargate 預設提供 20 GB 的暫時儲存空間，每多一個 GB，每小時會計價 $0.000111。
