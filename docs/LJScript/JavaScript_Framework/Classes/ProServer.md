# Class (ProServer)
The class is designed to communicate with the client `WS` server.

Access:
```javascript
$js.serve;
```
Constructor code:
```javascript
constructor(ljs) {
    this.ljs = ljs; //LJS object
    this.link = this.ljs.cfg("server"); //Link to connect to LarServer.
    ...
}
```

# Methods

## connect
The method is intended to connect to `LarServer`.
```javascript
this.connect();
```
> It is not advisable to call this method yourself. This method is executed when the application is initialized and when the `resetConnect` method is called.

## disconnect
Closes connection with `LarServer`.
```javascript
this.disconnect();
```
> It is not advisable to call this method yourself. This method is executed when the application is initialized and when the `resetConnect` method is called.

## onMessage
Method to populate connection event on receiving data from `LarServer`
```javascript
this.onMessage();
```
> It is not advisable to call this method yourself. This method is executed when the application is initialized and when the `resetConnect` method is called.

## reConnect
Method for full reconnection to `LarServer`.
```javascript
this.reConnect();
```

## resetConnect
The method resets the current connection and opens a new one.
```javascript
this.resetConnect();
```

## send
A method for sending commands to the `LarServer` server.
```javascript
/**
 * @param (string) execute
 * @param (object|array|string) data
 */
this.send(execute, data);
```
### Example
```javascript
$js.serve.send("console.users@get", {ID: "07b30fee10576dc9914f524145d50c31"});
```
This example sends data for execution to the class `Lar\Developer\ServerExecutors\ConsoleUsers::get()`
which is registered with `Lar\Developer\ServiceProvider::boot()`

