config-electron
===============

Introduction
------------

This module is identical to [node-config](https://github.com/lorenwest/node-config) except that it works in the Electron environment.

Whenever your app gets packaged into an Electron executable, this module will still work as expected.

Even if you archive your app into app.asar, this module will still work as expected.

Installation
------------

```shell
$ npm install config-electron
$ mkdir config
$ vi config/default.json
```

Usage
-----

Assuming the following default.json:

```json
{
  "Customer": {
    "dbConfig": {
      "host": "prod-db-server"
    },
    "credit": {
      "initialDays": 30
    }
  }
}
```

Pull the config into your code:

```js
let config = require('config-electron');
let dbConfig = config.get('Customer.dbConfig');

console.log(config.Customer.credit.initialDays);
console.log(dbConfig.host);
```


License
-------

May be freely distributed under the [MIT license](https://raw.githubusercontent.com/djedi-knight/config-electron/master/LICENSE).
