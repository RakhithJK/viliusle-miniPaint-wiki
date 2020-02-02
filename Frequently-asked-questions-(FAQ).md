## Can i ask you to add new features?
Yes, submit new issue. New features can be added, if its not too much complicated and if feature is really useful to all users.

## I liked old version of miniPaint more than current one. Can i still use it?
Yes, go to https://github.com/viliusle/miniPaint > Releases>  v3.3 > Assets > Download and open index.html file (also add it to bookmarks for quick access for next time).
Direct link for souce code: https://github.com/viliusle/miniPaint/archive/v3.3.zip

## Old miniPaint was different, what was changed and why?
There was many changes from v3 (old vesion) to v4 (new version), but bigest diffrences are these:
* v3 - **Destructive editing:** everything was saved on canvas, rotating object 999 times means loosing probably 90% quality, all actions was done on canvas, that was already edited before. **Memory problems:** old version was using too much memory, it was not possible to open big images at all. Also it was **hard to extend** app, add new features.
* v4 - App **engine was updated**. Everything is saved in memory (config.layers). And rendered from memory to screen. **Non destructive editing**, rotating object 999 times means loosing ... 0% quality, because most actions are done on original object. (exceptions are some effect, since they are slow). v4 use **less memory** and its is faster. It was build using **webpack**, which allows to have clean and fast code.

Full change log: https://github.com/viliusle/miniPaint/releases