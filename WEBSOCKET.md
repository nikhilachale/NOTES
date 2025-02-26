

WebSockets provide a way to establish a persistent, full-duplex communication channel over a single TCP connection between the client (typically a web browser) and the server



### **Use Cases for WebSockets:**

- **Real-Time Applications**: Chat applications, live sports updates, real-time gaming, and any application requiring instant updates can benefit from WebSockets.
- **Live Feeds**: Financial tickers, news feeds, and social media updates are examples where WebSockets can be used to push live data to users.
- **Interactive Services**: Collaborative editing tools, live customer support chat, and interactive webinars can use WebSockets to enhance user interactio

Good example - [https://www.binance.com/en/trade/SOL_USDT?type=spot](https://www.binance.com/en/trade/SOL_USDT?type=spot)

### Why not use HTTP/REST? Why do you need ws?
1. Network Handshake happens for every request
2. No way to push server side events (You can use polling but not the best approach)