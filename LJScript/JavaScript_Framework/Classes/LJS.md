# Class [LJS]

This class is designed to combine all parts of the control structure `LJScript`. 
Before you begin, you need to understand what kind created variables and for what they.

Access:
```javascript
$js;
```
Constructor code:
```javascript
constructor (globals = {}, macros = {}, onlodas = {}) {  
    this.globals = globals; //This var is a collection for the global components of this package.
    this.macros = macros; //This var is a collection for the global macroses of this package. 
    this._configs = {}; //This var is a collection for application configs.
    ...
    this.isLocal = this._configs["lar-env"] === "local"; //Local status
    this.token = this._configs["lar-token"]; //Laravel CSRF-Token
	...  
    this._declars = {}; //Collection of declared data for the application.
    this._onloads = onlodas; //A collection of methods to perform.
    this._executors = {}; //Collection of performers for remote control.
    this._events = {}; //Collection of events to the application.
    this._doc = $(document); //Document link
	...
}
```

# Methods

## apply
The method is called from the class constructor.
```javascript
this.apply();
```
It is applied for:
 * Getting headers with application settings.
 * Challenge the global application of events.
 * Initializes the execution of methods that are intended to be executed immediately after the application is loaded.

> This method is performed automatically once, a repeated call will result in a fatal error.

## applyEvents

The method is automatically called from the `apply` method.
```javascript
this.applyEvents();
```
It is applied for:
 * Initialization of global macroses.
 * Initialization of global classes.

> This method is performed automatically once, a repeated call will result in a fatal error.

## applyGlobal
The method is intended to add global classes to the application.
```javascript
/**
 * @param (string) name
 * @param (function|class) closure
 */
this.applyGlobal(name, closure);
```
### Example
```javascript
const Navigator = require("./src/classes/Navigator");
$js.applyGlobal("nav", Navigator);
```

## applyMacro
The method is intended to add global macros to the application.
```javascript
/**
 * @param (string) name
 * @param (function|class) closure
 */
this.applyMacro(name, closure);
```
### Example
```javascript
const Toastr = require("toastr");
$js.applyGlobal("toast", Toastr);
```

