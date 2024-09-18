# Route 53

Route 53 是一個 DNS 服務，負責把 Domain Name 轉換成電腦能夠讀懂的 IP 位址。
DNS 還分為 Authoritative 與 Recursive，Route 53 屬於 Authoritative DNS。

## Authoritative 與 Recursive 的差別是什麼呢？

電腦為了取得 IP 位址，需要向 DNS 發送請求，但我們不會直接發送請求到 Authoritative DNS，而是會發送到由網路供應商管理的 DNS，經由 DNS Lookup 後，最終才會由 Authoritative DNS 返回正確的 IP 位址。因此，Authoritative DNS 是對於某個 Domain 的 IP 位址有最終解釋權的 DNS，而關於 Recursive，我的理解是因為其需要來回地與 DNS Root Server、Top-Level Domain Server 與 Name Server 溝通，因此有了 Recursive 這個名字。

對於自己設備的網路供應商感興趣的話，可以到 https://www.whatismyisp.com/ 查詢。

## Hosted Zone 與 Record

設定 Route 53 時，有兩個名詞需要了解，Hosted Zone 與 Record。

### Hosted Zone

每一個 Hosted Zone 代表一個 domain name 的轉換規則，Hosted Zone 分為 Public Hosted Zone 和 Private Hosted Zone。

Public Zone 負責轉換來自外部網路的 DNS Queries 至正確的 IP 位址，而 Private Hosted Zone 是用來轉換來自相關連的 VPC 的 DNS Queries。

舉例來說，你使用 EC2 架設了一台資料庫，並在 Route 53 創建了一個 Private Hosted Zone 並把 db.example.com 與資料庫的 IP 位址綁定在一起，這時候，VPC 內其他服務發送解析 db.example.com 的 DNS Queries 時，Route 53 就會返回對應的 IP 位址。（範例來自：https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zones-private.html）

另外，Private Hosted Zone 是私人 DNS 服務，你不需要申請 Domain Name 才能使用。

那如果另一個 VPC 的 Private Hosted Zone 也擁有相同的 Domain Name 呢？
Route 53 會依照 DNS Queries 的來源 VPC 決定回覆的 IP 位址

那有沒有可能同一個 VPC 創建兩個相同 Domain Name 的 Private Hosted Zone 呢？
答案是不行！創建的時候，AWS 會回傳 400 Bad Request。

那兩個 Public Hosted Zone 可不可以擁有相同的 Domain Name 呢？答案是可以的。
Public Hosted Zone 在創建時會被分配到四個 Name Servers，透過更換你註冊的域名的 Name Servers，DNS Queries 會打到相對應的 Hosted Zone。

### Record

創建 Hosted Zone 後，你需要在 Hosted Zone 創建 Record 告訴 Route 53 要如何轉換你的 Domain Name。
創建 Record 時，你需要設定 Record Name、Record Type 和 Value，Record Name 可以設定你的 Subdomain，Record Type 是告訴 Route 53 要如何轉換你的 Domain Name，舉例來說，A Record 是轉換成 IPv4 位址，而 MX 是轉換成 mail server 位址。
