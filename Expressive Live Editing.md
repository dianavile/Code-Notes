## TEST: Expressive Live Editing(Lesson 17)

### Description
- Step up your environment for live editing.
- Live editing will cause any connected browser to automatically reload if you change any file.

### Different Approaches for Live Editing
- [Takana plugin on PackageControl](https://packagecontrol.io/packages/Takana)
- [Chrome Dev Workspaces](https://developers.google.com/web/tools/setup/setup-workflow)
- [Browser Sync](https://www.browsersync.io/)

### Using Browser-Sync
- 1. Install browser-sync.
- 2. Create a browser-sync object and initialize the server.

```
var browserSync = require('browser-sync').create();
 browserSync.init({
     server: "./"
 });
 browserSync.stream();
 ``` 
 
- 3. Run gulp in Terminal, see how browser opens with the page open.