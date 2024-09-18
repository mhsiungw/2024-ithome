# AWS Regions, Availability Zones

今天我們學習 Region 與 Availability Zones，Region 與 Availability Zones 是組成 Amazon Gloabal Infrastructure 中重要的概念與設施。

## AWS Region

Region 是一個地理位置，由一個以上的 Availability Zones 組成，目前 AWS 擁有 34 個 Regions，每一個 Region 都是獨立不受其他 Region 影響，舉例來說，Asia Pacific (Tokyo) (ap-southeast-1) Region 的服務停擺不會影響到 US East (N. Virginia)(us-east-1)。

每個 Region 會有一個代碼，像 us-east-1 是 N. Virginia Region 的代碼。

## Availability Zones

Availability Zone 由一個以上的獨立資料中心組成。每一個 AZ 距離彼此數公里到 100 公里遠，並透過高頻寬、低延遲的線路彼此連接。每個 AZ 會以 Region code 加上一個英文字母作為代號，像是 US East Region 的 us-east-1a。

當我們需要部署服務時，我們需要先創建一個 subnet 並指定給 AZ 後，才能透過 subnet 把服務部署在該 AZ。

關於 Subnet，我們會在下一章介紹。

## Multiple Availability Zones

透過把服務部署在不同的 AZ 上，可以提高服務的可用性。舉例來說，透過把 RDS Instances 部署在 us-east-1a 和 us-east-1b 上，當 us-east-1a 因自然災害或意外停止服務時， 我們的服務仍然能夠透過 us-east-1b 正常運行。

## Multiple Regions

隨著服務的使用者群擴大，我們需要考慮到其他國家的使用者，這時候我們可以考慮把服務部署在不同的 Region 達到低延遲性。

除了達到低延遲的目的，我們可能也會因為當地法規而把服務部署在不同 Region。舉例來說，為了符合 GDPR 特定資料只能儲存在 EU 內的資料中心，這時候，我們就需要把服務部署在不同的 Region 內。

## AWS Local Zones and AWS Wavelength Zones

除了 Region 內的 Availability Zone，AWS 也有提供其他類別的 Zones。

Local Zone 與 Wavelength 和 AZ 一樣，讓你可以透過 subnet 在上面部署服務。

但 Local Zone 讓你夠能夠以更近的距離服務終端使用者，而 Wavelength Zone 讓你可以更快地服務使用 5G 裝置的使用者，
