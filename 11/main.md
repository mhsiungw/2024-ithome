# Lambda

AWS Lambda 提供一個讓你執行函式的平台。使用 AWS Lambda 時，你需要先創建一個 Trigger，Trigger 會發送 Event，這個 Event 會觸發 AWS Lambda 執行你提供的函式，函式可以以同步或非同步的方式執行。函式也能夠與 AWS 上其他服務搭配，並組建成一個 Serverless 的應用程式。

## Trigger

Trigger 是指觸發 Lambda 執行函式的一個服務或資源，它可以是 AWS 外的服務，像是 MongoDB，或是 AWS 內的服務，像是 S3。

## Event

Trigger 透過發送 Event 觸發 Lambda 上的函式，Event 會以 JSON 格式傳給函式，JSON 內容會依照 Trigger 服務的不同而改變。舉例來說，S3 Put Event 的內容會包含 bucket name 和 object key，我們可以透過 Lambda 預設的 AWS SDK 取得對應的 S3 Object。

另外，因為 Lambda 會監測函式的執行次數、時長 ⋯⋯ 等等數據，你可以透過在 Lambda Console 創建 Test event 測試你的函式，避免讓測試結果影響你的監測數據。

## 同步或非同步

函式依照 Event 來源分為同步或非同步的觸發方式。

同步的觸發方式中，Service 會等待函式執行後的結果，舉例來說，被 API Gateway Trigger 的函式執行方式是同步，因此 API Gateway 會等待函式執行後的結果，那如果函式執行太久怎麼辦？每個 Service 會設定等待時間，像 API Gateway 最多等 29 秒，當超過時間後，函式執行的結果就無法送出了。

非同步的觸發方式中，Service 送出 Event 後會立刻收到 202 的訊息，代表請求已被收到，之後，Event 會被放在 Event Queue 裡等待被執行。函式執行完成後，你可以設定 Destination 接收函式執行後的結果。

## Event Source Mappings (事件源映射)

還有一些 Event 來源會利用 Event Source Mappings 批次儲存 Event Record 為 payload，並在達到 MaximumBatchingWindowInSeconds、BatchSize 或 6 MB payload size 其中之一的限制後，把 payload 送給函示執行。

MaximumBatchingWindowInSeconds 是指等待 Records 的最長時間，舉例來說，DynamoDB 預設為 0，因此只要一有 Record，函式就會被處發。

BatchSize 是指批次儲存 Records 的最大數量，而 payload size 是指這個 Batch 最大的容量，預設是 6 MB，且無法更改，因此只要儲存的 Records 超過 6MB，函式就會被執行。

## Lambda 計價

Lambda 會依照區域、處理器、函式的請求次數與執行時長計費，請求次數與函示執行時長都是從函式執行到結束去計算。

比較特別地是，函示執行時長會依照你分配給函式的記憶體資源而有不同的計價，單位會是 Gigabyte-seconds（GB-s），GB-s 的意思是每秒鐘使用某個特定大小的記憶體容量。

舉例來說，一個擁有 1536 MB 記憶體資源的函示這個月被執行了三百萬次，且每個函示的平均執行時長是 120 毫秒，處理器是 x86 Price，Region 是 Asia Pacific Hong Kong (ap-east-1)。

首先，我們先算出執行次數的費用，因為 Lambda 提供每月一百萬執行次數的免費額度，所以我們只需要計算其中兩百萬次請求，價格是每一百萬次請求為 $0.28，兩百萬個請求乘於二是 $0.56。

再來，我們計算執行時長的費用，我們先算出我們總共花了多少時間執行函式，3,000,000 乘 120 是 360,000 秒。接著我們算出我們花了多少的記憶體資源，360,000 乘 1536，這個數字再除以 1024 得出總 GB 量 540,000。這代表我們的函示這個月花了 540,000 GB-s 的執行時長。把扣掉 Lambda 每個月提供的執行時長免費額度 400,000 GB-s 後的數字乘以 0.00002292 得出 $3.2088，四捨五入後得出 $3.21。

所以以這個例子來說，這個月的 Lambda 費用會是 $3.21。
