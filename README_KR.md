# things-full-dialog

#### 애플리케이션에 단 하나만 존재하고 다이얼로그가 오픈 될 때 마다 화면 구성을 다시하여 오픈한다.
** 주의 : 이 Dialog는 Document에 등록되는 Event를 Trigger하기에 한 시스템에 단 한번만 사용될 것을 권장한다.

Example:
```html
      <things-full-dialog></things-full-dialog>
```

`things-open-popup-view`, `things-close-popup-view`를 받아서 Dialog Open
`things-framework`에서는 `things-dialog-manger`로 모든 popup event를 처리한다.
`event.detail`에는 아래와 같은 내용이 포함될 수 있다.

`view` 필수
`modal` option
`openCallback` option
`closeCallback` option

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

Element dependencies are managed via [Bower](http://bower.io/). You can
install that via:

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


## Example 1. Things date picker
`<things-full-dialog>` 애플리케이션에 단 하나만 존재하고 다이얼로그가 오픈 될 때 마다 화면 구성을 다시하여 오픈한다.
** 주의 : 이 Dialog는 Document에 등록되는 Event를 Trigger하기에 한 시스템에 단 한번만 사용될 것을 권장한다.
