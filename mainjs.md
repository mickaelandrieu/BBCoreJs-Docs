# main.js
Structure of your application entry point.
```js
require.config({
    paths: {
        'user': 'src/tb/apps/user'
    }
});

define('app.user', ['tb.core'], function (Core) {
    'use strict';

    /**
     * User application declaration
     */
    Core.ApplicationManager.registerApplication('user', {});

});
```

ApplicationManager registerApplication take two parameters :

* Application name
* object who can contains 4 event functions called by the core

```js
Core.ApplicationManager.registerApplication('user', {
        /**
         * occurs on initialization of content application
         */
        onInit: function () {
            return;
        },
        /**
         * occurs on start of content application
         */
        onStart: function () {
            return;
        },
        /**
         * occurs on stop of content application
         */
        onStop: function () {
            return;
        },
        /**
         * occurs on error of content application
         */
        onError: function () {
            return;
        }
    });
    ```
