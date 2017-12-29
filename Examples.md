### 1. Open, edit images, save using miniPaint on iframe

[open-edit-save.html](/viliusle/miniPaint/blob/master/examples/open-edit-save.html)

### 2. Add miniPaint in page as iframe

`<iframe style="width:100%; height:1000px;" id="miniPaint" src="https://viliusle.github.io/miniPaint/"></iframe>`

***

**Note:** You can access layers class globally: `window.Layers` or `document.getElementById('miniPaint').contentWindow.Layers` if outside of iframe.