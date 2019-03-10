# mediadb.js

The mediadb.js lib used in Gaia, extracted from [mozilla-b2g/gaia](https://github.com/mozilla-b2g/gaia/blob/master/shared/js/mediadb.js). Please refer to comments in file, or check its usage in the [Gallery](https://github.com/mozilla-b2g/gaia/blob/v2.2/apps/gallery/js/gallery.js#L219) app.

 ## Permissions

 To use this lib, the app should be a privileged or certified app and have permission to use DeviceStorage API. The manifest may look like this,

 ```json
{
  "type": "privileged",
  "permissions": {
    "storage": {},
    "device-storage:sdcard": { "access": "readwrite" }
  }
}
 ```

Here "storage" permission is to enable unlimited indexedDB quota, and "device-storage:sdcard" is to use DeviceStorage API. For more details, check KaiOS's [developer portal](https://developer.kaiostech.com/first-app/manifest).
