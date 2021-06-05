## Информация о проекте
[Скачать BridgeJS](https://nullsoftdev.github.io/bridgejs/bridge.js)

BridgeJS был создан для удобного объеденения нескольких проектов  

BridgeJS использует [socket.io и socket.io-client](http://socket.io/)

### API
## createServer
```javascript
let customName = 'myServer',
    port = 5125
let bridge = new bridgejs.createServer(port,customName)
```
## createClient
```javascript
let customName = 'myClient'
let bridge = new bridgejs.createClient(port,customName)
```

**Примечание: Функции ниже есть и в server и в client!**

## getClient
```javascript
let clientName = 'myClient'
let client = bridge.getClient(clientName) // Получить клиента или сервер.
```
С помощью данной функции можно получить клиента/сервер и выполнять функции ниже без указания имени клиента
(Просто используйте bridge на client)
Пример:
```javascript
let clientName = 'myClient'
let client = bridge.getClient(clientName)
bridge.eval(clientName,'console.log("Bridge $ Hello world")')
client.eval('console.log("Client $ Hello world")')
```

## eval
```
console.log(`result1:`,client.eval('2+2')) // sync eval
console.log(`result2:`,client.eval('callback(2+2)')) // sync eval
client.eval(`4+4`,result3>console.log(`result3:`,result3) // async eval
client.eval(`callback(4+4)`,result4=>console.log(`result4:`,result4) // async eval
```
