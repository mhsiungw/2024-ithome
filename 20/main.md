# 其他 S3 其他計價項目和服務

## Security Access & Control

### Dual-layer server-side encryption

S3 自 2023 起預設會以 SSE-S3 對物件進行加密，你也可以選擇以雙層加密的方式儲存物件。

### S3 Access Grants

S3 Access Grant 讓你可以根據用戶的企業身份授予 S3 訪問權限

## Management & Insights

### S3 Inventory

S3 Inventory 幫助你管理 S3 儲存空間，並定期生成儲存物件的清單。你可以使用它來生成報告，如 Replication 或加密狀態 的檢查，便於監控和管理儲存資料。

![img](https://github.com/mhsiungw/2024-ithome/blob/main/20/s3-inventory.jpg?raw=true)

### S3 Object Tagging

你可以替 S3 物件新增標籤（Tagging），這樣在使用監控服務（如 CloudWatch）時，可以根據這些標籤過濾和識別特定的資料，幫助更有效地管理資源。

![img](https://github.com/mhsiungw/2024-ithome/blob/main/20/s3-tags.jpg?raw=true)

### S3 Batch Operations

S3 Batch Operations 允許你對大量 S3 物件執行批次操作，如複製物件、修改標籤、設定存儲類別等。這功能適合需要大規模管理和操作物件的場景。

### S3 Storage Lens

S3 Storage Lens 幫助用戶監測 S3 存儲空間的使用狀況，並提供詳細的可視化數據報告。除了監控，Storage Lens 也會提供成本優化的建議，幫助用戶更有效率地管理和優化其存儲資源。

### S3 Analytics Storage Class Analysis

S3 Analytics Storage Class Analysis 用來監控物件的存取模式，並幫助使用者識別可以轉移到更具成本效益的存儲類別（Storage Class）的物件，例如將不常取用的物件轉移到 S3 Standard-IA 或 S3 Glacier。

## Transform & Query

### S3 Object Lambda

S3 Object Lambda 允許你將 Lambda 函數 與 S3 整合，對於 `GetObject`、`HeadObject` 和 `ListObjects` 請求進行動態處理。這樣可以在返回物件之前，根據需要對其進行轉換或過濾，無需將資料移動到其他服務進行處理。

![img](https://github.com/mhsiungw/2024-ithome/blob/main/20/s3-object-lambda.jpg?raw=true)
