# Formbuilder

For use the formbuilder you need to just use renderForm function.
Indeed renderForm function need a config as parameter, this function build a form corresponding to the config and return the html.

### Config exemple

```js
var config = {
        elements: {
            name: {
                type: 'text',
                label: 'My name',
                value: 'Foo'
            },
            country: {
                type: 'select',
                label: 'Country',
                options: {
                    'fr': 'France',
                    'en': 'England',
                    'br': 'Brazil',
                selected: 'fr'
            }
        }
    };
```
Here is a basical config for build a form with a text input and select input.

For use this config you need to require the Formbuilder component like this:

```js
var FormBuilder = require('component!formbuilder');
```

And for get the html:
```js
FormBuilder.renderForm(config).done(function (html) {
    //Do treatment with html
});
```
The renderForm function use a javascript promise you need to use done at the end of the function.

### Retrieve data submitted by form

For retrieve the data submitted by form you can add the callback into the config like this:

```js
config.onSubmit = function (data) {
    //Do treatment with data
};
```
Indeed the callback have a data parameter, you can use the data and send to the server or something else.

### Validate data before submit

If you want validate data, you can add the callback onValidate into the config like this:

```js
config.onValidate = function (form, data) {
    if (!data.hasOwnProperty('title') || data.title.trim().length === 0) {
        form.addError('title', 'Title is required');
    }
}
```

Form object have addError function, you just need to set the key of element and the error to be throwed.

###Elements

Here is the list of available elements.

* ####**Text**
* ####**Textarea**
* ####**Checkbox**
* ####**Password**
* ####**Select**
* ####**Radio**
* ####**Hidden**
* ####**Datetimepicker**

All elements have a default settings which be overloaded.

Default settings:

```
- placeholder
- value
- label
- disabled
```

####**Text**

Config:

```js
config: {
    type: 'text',
    label: 'My name',
    value: 'Foo'
}
```

####**Textarea**####

Config:

```js
config = {
    type: 'textarea',
    rows: 10,
    label: 'My Textarea'
    value: 'textarea...'
}
```

####**Checkbox**####

Config:

```js
config = {
    type: 'checkbox',
    options: {foo: 'FOO', bar: 'BAR', foobar: 'FOOBAR'},
    checked: ['foo', 'bar'],
    inline: true,
    label: 'My checkbox'
}
```

####**Password**####

Config:

```js
config = {
    type: 'password',
    label: 'My password'
}
```

####**Select**####

Config:

```js
config = {
    type: 'select',
    options: {foo: 'FOO', bar: 'BAR', foobar: 'FOOBAR'},
    selected: ['foo', 'bar'],
    multiple: true,
    label: 'My select'
}
```

####**Radio**####

```js
config = {
    type: 'radio',
    options: {foo: 'FOO', bar: 'BAR', foobar: 'FOOBAR'},
    checked: ['foo', 'bar'],
    inline: true,
    label: 'My radio'
}
```

####**Hidden**####

```js
config: {
    type: 'hidden',
    value: 'Foo'
}
```

####**Datetimepicker**####

```js
config: {
    label: 'Datetime',
    type: 'datetimepicker',
},
```





