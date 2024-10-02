# Shared Responsibility Model

Shared Responsibility Model 是一個區分客戶和 AWS 在雲端服務上責任歸屬的概念。

![img](https://d1.awsstatic.com/security-center/Shared_Responsibility_Model_V2.59d1eccec334b366627e9295b304202faf7b899b.jpg)

## 雲端的安全 Security of the Cloud

AWS 負責雲端的安全，像是雲端的硬體、軟體和設備設施。

## 雲端內的安全 Security in the Cloud

客戶則負責雲端服務內的安全，負責範圍依照雲端服務的不同而有差異。

以 EC2 舉例來說，客戶需要負責管理個體內使用的作業系統、安裝的套件和軟體、防火牆的設置 ⋯⋯ 等等。
但以 S3 來說，S3 的作業系統會由 AWS 維護管理，客戶需要負責上傳到 S3 的檔案權限管理和是否加密 ⋯⋯ 等等。
