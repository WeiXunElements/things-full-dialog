# things-full-dialog

#### 이 컴포넌트는 애플리케이션에 단 하나만 존재하고, 다이얼로그가 오픈될 때마다 화면 구성을 다시하여 오픈한다.
** 주의 : 이 Dialog는 Document에 등록되는 Event를 Trigger하기 때문에, 한 시스템에서 단 한번만 사용할 것을 권장한다.

Example:
```html
      <things-full-dialog></things-full-dialog>
```

`things-open-popup-view`, `things-close-popup-view`를 받아서 Dialog를 Open한다.
`things-framework`에서는 `things-dialog-manger`로 모든 popup event를 처리한다.
`event.detail`에는 아래와 같은 내용이 포함될 수 있다.

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

element의 종속성은 [Bower](http://bower.io/)를 통해 관리되며, 아래의 방법을 통해 설치할 수 있다.

    npm install -g bower

다음, element의 종속성을 다운로드한다.

    bower install

## Playing With Your Element

element를 독립적으로 처리하려면 [Polyserve](https://github.com/PolymerLabs/polyserve)를 사용하여 element의 bower 의존성을 유지하도록 하며, 이는 아래의 방법을 통해 설치할 수 있다.

    npm install -g polymer-cli

그리고, 아래의 방법을 통해 실행할 수 있다.

    polymer serve

element를 실행한 경우, `things-full-dialog`가 디렉토리 이름으로 포함되어 있는 `http://localhost:8080/components/things-full-dialog/`를 통해 이를 미리 확인할 수 있다. 
