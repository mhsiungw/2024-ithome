# Amazon Global Infrastructure

## AWS 的 Global Infrastructure 是什麼？

AWS 的 Global Infrastructure 由 Regions 組成，Region 是實體的地理位置，像是日本的東京或美國的 Ohio，每個 Region 會有複數以上的 Availability Zone（AZ），每個 AZ 會由一個以上的 Data Centres 組成，這些 Data Centres 會用來運行我們的服務。

## 高可用性和低延遲

這樣的架構讓我們的服務具有高可用性和低延遲的特性。

可用性是指系統在一段時間的可運行時間，舉例來說，AWS S3 Standard storage class 被設計成提供 99.99 的可用性，這代表在一年的 99.99% 的時間中，它會是正常運行的，換句話說，它會有最多 52 分鐘的停機時間。

延遲是指電腦在交換資料時發生的延誤，瀏覽網頁就是一種與另一台電腦交換資料的過程，而低延遲的特性能夠讓我們更快速地交換資料，提供使用者更流暢的使用者體驗。

AWS 的 Global Infrastructure 讓我們可以透過部署服務在接近使用者的 Region 與多個 AZ 上，達到高可用性與低延遲的目的。

## 那它有什麼缺點嗎？

雖然這樣的架構帶來了許多優點，但也提升了部署系統的複雜性，除此之外，我們也必須了解 AWS 提供的服務和定價，以更好地利用這個架構，這無疑都帶給企業培育和招募人才的成本。

但是相較於以往在公司內部部署服務，雲端服務讓我們能夠用更彈性、快速的方式部署服務。
