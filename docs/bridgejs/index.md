## Информация о проекте
[Скачать BridgeJS](https://nullsoftdev.github.io/bridgejs/bridge.js)

BridgeJS был создан для удобного объеденения нескольких проектов  

BridgeJS использует [socket.io и socket.io-client](http://socket.io/)
### API
## Сервер
```javascript
let customName = 'myServer',
    port = 5125
let bridge = new bridgejs.server(port,customName)
```
## Клиент
```javascript
let customName = 'myClient'
let bridge = new bridgejs.client(port,customName)
```
## Общие функции
```javascript

```
