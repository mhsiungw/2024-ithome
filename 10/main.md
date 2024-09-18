# Elastic Container Service

## Overview

ECS 讓管理容器化應用程式更容易，容器化的應用程式是指跑在獨立於機器本身且擁有應用程式所需資源的 Container 環境上的應用程式。Task 是 ECS 裡最小的運算單位，透過 Task Definition，你可以設定 Image、Task 預留的運算資源、 Task 裡每個 Container 需要的運算資源與 Container 的數量 ⋯⋯ 等等。

設定完 Task Definition 後，你需要有一個 Cluster 才能夠啟動 Task。設定 Cluster 時，你需要設定 Infrastructure 決定 Container 要跑在 EC2 還是 Fargate 上，如果是跑在 EC2 上，你需要手動設定機器的運算資源，像是 Instance Types、最少與最多的 Instance⋯⋯ 等等。如果是跑在 Fargate 上，你只需要在 Task Definition 時設定你的 Container 需要的資源，Fargate 會依照 Container 需要的資源分配運算資源。

使用 ECS，你只需要為運算資源付費，無論是設定 Cluster、Task 或 Service，只要服務沒有部署到 EC2 或 Fargate 上，你都不需要付費。

# Elastic Kubernetes Service

## Overview

EKS 與 ECS 一樣，提供一個讓你方便管理容器化應用程式的服務，但與 ECS 不一樣的是，EKS 讓你能夠透過 Kubernetes 管理容器化應用程式，你透過在 EKS Console 設定 Cluster 並透過 Cluster 管理 Node，Node 是運行你的容器化應用程式的機器。

使用 EKS 時，每個 Cluster 的費用是每小時 $0.10 美金，加上你使用的 EC2 或 Fargate 運算資源。
