# Load Balancer

## 什麼是 Load Balancer ?

> 網路負載平衡器 元件

**當你在網路上架設Server時，後來因用戶暴增導致server traffic 負載過大停機。這時候你會如何處理 ?**

A\) 買更好的 Server，每個月多 1000元的成本

B\) 使用負載平衡器 load balancer

-------------------------------------------------------------------------------------------------------------------------

### From AWS official document

> 負載平衡器會將傳入的流量分散到多個目標

網路負載平衡器 是在開放系統互相連線 \(OSI\) 模型的第四層運作。每秒可以處理數百萬個請求。負載平衡器接收到連線請求後，將依預設規則從目標群組中選取一個目標。負載平衡器會嘗試開啟接聽程式設定中指定之連接埠上所選目標的 TCP 連線。

### General的兩個概念

* **Listener**：通常用來定義 forwards 請求的規則。
  * Load Balancer 進來端點的**Protocol、port** Listener 負責這邊要怎麼對應到 EC2 Group的 **Protocol、port**
* **Health Check**：用來確認 **EC2** 還活著，Load Balancer 才知道可以送請求過去。
  * 當health 一直 response 一直是 404 時，會主動關閉主機。

[https://docs.aws.amazon.com/zh\_tw/elasticloadbalancing/latest/network/introduction.html](https://docs.aws.amazon.com/zh_tw/elasticloadbalancing/latest/network/introduction.html)

