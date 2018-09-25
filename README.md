# core.loader.actions

loads actions from plugin definitions.

related to <a href="https://github.com/ido-ofir/core.type.action">core.type.action</a>

```js
let core = new require('core.constructor')();
 
core.plugin(
    require('core.loader.actions')
);

// plugins can now declare actions on the plugin definition object:
core.plugin({
    name: 'test',
    actions: [
        {
            name: 'someAction',
            get(){
                return (data, promise) => {
                    promise.resolve('ok');
                };
            }
        }
    ]
});

core.run('test.someAction', { some: 'data' }).then(ok => { ... })

```
