# CKEditor ExtJS 6.x

This is an example of how to use the CKEditor.pkg to create a Ext JS application with the CKEditor.

**Important note: I do not work for Sencha or ckeditor.com and this package is called CKEditor for clarity purposes only **

## Getting things working
This GIT project contains the example code to get it running, it can be run with and without Sencha Architect 3.5 (minimum), but would require Sencha cmd to rebuild after any changes.

## CKEditor.com
This repo does contain the current build of CKEditor.  If you want a newer version, simple go to [ckeditor.com](http://ckeditor.com/) and download a pre-compiled version with the settings that you so desire and update the code in ```resources/ckeditor/```
Once you have the ckeditor code this needs to be added to your app.json **before** your app.js. If you have a precompiled version then it is okay to x-compile it into your app.js file. Remember the ordering is important.
###### app.json
```javascript
   "js": [
      {
         "path": "${framework.dir}/build/ext-all-rtl-debug.js"
      },
      {
         "path": "resources/ckeditor/ckeditor.js",
         "x-compile": true
      },
      {
         "path": "app.js",
         "bundle": true
      }
   ],
``` 
## CKEditor package
Next you will need to add the CKEditor.pkg file the current version is included with the repo. I will be adding this to a CDN at some point depending on how well it is recieved.
Simply copy it accross to your current workspace and then you will need to add the package using the following sencha command: ```sencha package add CKEditor.pkg```

If the package has been added correctly your app.json file should now contain CKEditor within the existing requires.
```javascript
   "requires": [
      "CKEditor"
   ],
```

## Writing ExtJS
Now all you need to do is to add this xtype ```xtype: 'ckeditor'``` or ```Ext.ckeditor.CKeditor``` if you intend to create it on the fly.
Currently no errors are caught put there are plenty of things I can add to this xtype.

## Licence

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons Licence" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
