# Global Accelerator

AWS Global Accelerator give you a static ip as an entry point to your application and will then route traffic to the nearest application endpoint in a endpoint group.

AWS Global Accelerator 透過 AWS 的全球網路改善應用程式的效能與可用性。它提供靜態 IP 位置當作應用程式流量的單一入口，並把流量導到距離最近的端點群組（Endpoint Group）中的端點（Endpoint）。

## Endpoint Group

設定 Global Accelerator 時，每個 Region 可以設定一個 Endpoint Group，裡面包含多個 Endpoints。

## Endpoint

Endpoint 是指 AWS 上的運算資源，像是 EC2 或 ELB，Global Accelerator 會把流量導到這些 Endpoint 上。

## 權重 Weight

每個 Endpoint 可以有 0 到 255 的數字作為權重，Global Accelerator 會依照 Endpoint 在 Endpoint Group 所佔據的權重決定流量的分配。

## Global Accelerator 和 CloudFront 的差別

依照我的理解，兩者都是透過 AWS Global Network 改善應用程式的效能，但 Global Accelerator 著重在利用 Global Network 讓流量快速地到達你的應用程式所在的區域，而 CloudFront 則是著重在透過快取的行為改善效能。
