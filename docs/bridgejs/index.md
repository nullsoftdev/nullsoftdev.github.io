## Информация о проекте
[Скачать BridgeJS](https://nullsoftdev.github.io/bridgejs/bridge.js)

BridgeJS был создан для удобного объеденения нескольких проектов  

BridgeJS использует [socket.io и socket.io-client](http://socket.io/)

## API
### createServer
**createServer(port,name)**
```javascript
let customName = 'myServer',
    port = 5125
let bridge = new bridgejs.createServer(port,customName)
```
### createClient
**createClient(port,name)**
```javascript
let customName = 'myClient'
let bridge = new bridgejs.createClient(port,customName)
```

**Примечание: Функции ниже общие для server и client!**

### eval 
**bridge.eval(clientName,code,callback)**
```javascript
console.log(`result1:`,bridge.eval(clientName,'2+2')) // sync eval
console.log(`result2:`,bridge.eval(clientName,'callback(2+2)')) // sync eval
bridge.eval(clientName,`4+4`,result3>console.log(`result3:`,result3) // async eval
bridge.eval(clientName,`callback(4+4)`,result4=>console.log(`result4:`,result4) // async eval
```

### getClient
**getClient(clientOrServerName)**
**С помощью данной функции можно получить клиент и выполнять функции ниже**
```javascript
let clientName = 'myClient'
let client = bridge.getClient(clientName)

bridge.eval(clientName,'console.log("Bridge $ Hello world")')
client.eval('console.log("Client $ Hello world")')
```
#### [client.eval(code,callback)](#eval)
