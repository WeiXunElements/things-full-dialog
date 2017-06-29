# things-full-dialog

#### There is only one component in the application, and the screen is reconfigured and opened whenever the dialog is opened.
** Note : Since this dialog triggers events registered in the Document, it is recommended to use it only once in one system.

Example:
```html
      <things-full-dialog></things-full-dialog>
```

Open the Dialog by receiving `things-open-popup-view` and `things-close-popup-view`.
In `things-framework`, `things-dialog-manager` handles all popup events.
`event.detail` may contain the following information.

`view` mandatory
`modal` optional
`openCallback` optional
`closeCallback` optional

Example :
```js
  var upload = document.createElement('things-file-upload');
  upload.id = 'file-upload';
  upload.target = 'upload';
  upload.method = 'POST';
  upload.timeout = 300000;
  upload.hidden = false;

  var closeCallback = function() {
    this.refreshGridData();
  }.bind(this);

  var request = {
    view: upload,
    modal: true,
    closeCallback: closeCallback
  };

  this.fire('things-open-popup-view', request)
```

## Dependencies

Element dependencies are managed via [Bower](http://bower.io/). You can install that via:

    npm install -g bower

Then, go ahead and download the element's dependencies:

    bower install


## Playing With Your Element

If you wish to work on your element in isolation, we recommend that you use
[Polyserve](https://github.com/PolymerLabs/polyserve) to keep your element's
bower dependencies in line. You can install it via:

    npm install -g polymer-cli

And you can run it via:

    polymer serve

Once running, you can preview your element at
`http://localhost:8080/components/things-full-dialog/`, where `things-full-dialog` is the name of the directory containing it.
