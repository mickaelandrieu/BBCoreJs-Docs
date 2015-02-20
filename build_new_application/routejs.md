# route.js
Structure of your application routing.
```js
define(['tb.core'], function (Core) {
    'use strict';
    /**
     * Register every routes of bundle application into Core.routeManager
     */
    Core.RouteManager.registerRoute('user', {
        prefix: 'user',
        routes: {
            index: {
                url: '/index',
                action: 'MainController:index'
            }
        }
    });
});
```
registerRoute take two parameter:
* The first parameter is the application name where this routing is bind.
* The second parameter is a route mapping.

Route mapping structure:
```js
{
    prefix: 'user',
    routes: {
        index: {
            url: '/index',
            action: 'MainController:index'
        }
    }
}
```
url result of that routing is #/user/index that call the indexAction function in the MainController o route application.

the route mapping can take dynamical url to :

```js
{
    prefix: 'user',
    routes: {
        show: {
            url: '/show/:uid',
            action: 'MainController:show'
        }
    }
}
```
Dynamical params are define :varname.


