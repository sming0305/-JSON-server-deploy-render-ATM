# JSON-server 部屬至 render

## 關於 server.js

### 引用必要的套件：
json-server：用來建立 API 伺服器。  
json-server-auth：提供身份驗證功能，可以限制存取 API 的權限。

### 建立伺服器：
jsonServer.create()：建立一個 JSON Server 的實例。  
jsonServer.router('db.json')：建立一個路由器，並且將 db.json 檔案作為資料來源。  
server.db = router.db：將資料庫對象儲存在伺服器上，方便在後面的中間件中存取。  
jsonServer.defaults()：建立一個預設的中間件陣列，包括 CORS、日誌、GZIP 壓縮等功能。

### 加入中間件：
server.use(middlewares)：加入預設的中間件。  
server.use(auth)：加入身份驗證中間件。  
server.use(router)：加入路由器中間件，用來處理 API 的請求。

### 啟動伺服器：
server.listen(port)：啟動伺服器，監聽特定的 port。


以上建立一個使用 JSON Server 的 API 伺服器，並且提供身份驗證的功能。透過這個伺服器，可以存取 db.json 檔案中的資料，並且對這些資料進行 CRUD 操作。