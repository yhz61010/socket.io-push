#### node 依赖

```
npm install socket.io-push-client --save
```

#### js sdk
[source](../../static/js/push-client-1.0.js)

[minified](../../static/js/push-client-1.0.min.js)


#### 初始化

```javascript
var pushClient = PushClient('https://spush.yy.com', {
            transports: ['websocket'], //使用的tranport, proxy如果是多进程模式, 不支持polling
            useNotification: true //是否接收notification
        });
```

#### 获取pushId
```javascript
var pushId = pushClient.pushId
```

#### subscribe topic

```javascript
var topic = 'topic';
pushClient.subscribeTopic(topic);
pushClient.unsubscribeTopic(topic);
```

#### push callback

```javascript
pushClient.on('push',function(data){

});
```

#### notification callback

```javascript
pushClient.on('notification',function(notification){
  console.log('',notification.title,notification.message,notification.payload);
});
```

#### connect callback

```javascript
pushClient.on('connect',function(data){
  console.log('',data.uid);
});

pushClient.on('disconnect',function(){

});
```
