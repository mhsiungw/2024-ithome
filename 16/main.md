# CloudFront

CloudFront 是一個讓你能夠透過其全球端點（Edge Locations）達到低延遲傳送內容目的的網路服務。

## CloudFront 如何傳送你的內容

當使用者請求內容時，DNS 會把請求導到可以最快速傳送內容的 CloudFront Edge Locations，CloudFront 會確認 Edge Locations 是否存有 Cache 的內容，如果沒有的話，會再向 Regional Cache 確認，如果仍然沒有，CloudFront 才會把請求導到 Origin Server。透過 CloudFront 的全球端點網路與 Cache 機制，使用者得以快速地收到內容。
[img](https://docs.aws.amazon.com/images/AmazonCloudFront/latest/DeveloperGuide/images/regional-edge-caches.png)

## Edge Locations

Edge Location，又稱作 Point of Presence，是負責傳送內容的伺服器。

## Regional Cache

Regional Cache 置於 Origin Server 與 Edge Location 之間，Cache 的時長比 Edge Location 更長。

## CloudFront 如何運送你的內容？

![](https://docs.aws.amazon.com/images/AmazonCloudFront/latest/DeveloperGuide/images/regional-edge-caches.png)

## Invalidation Request

Invalidation 是指告訴 CloudFront 把 Edge Location 與 Regional Cache 的快取檔案清掉。

## 計價方式

### Data Transfer

CloudFront 計價會以 Data Transfer 與 Request 數量計價，Data Transfer 部分，分為向網路傳輸內容與向 Origin 傳輸內容，這裡的向 Origin 傳輸內容是指 Post 或 Put 方式請求，而 Get 方式的請求是不計價的。Request 則是指使用者向 CloudFront 方送的請求次數。Data Transfer 與 Request 會依照 Region 有不同的計價方式。
