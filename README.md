# mediadb.js

The mediadb.js lib used in Gaia, extracted from [mozilla-b2g/gaia](https://github.com/mozilla-b2g/gaia/blob/master/shared/js/mediadb.js). Please refer to comments in file, or check its usage in the [Gallery](https://github.com/mozilla-b2g/gaia/blob/v2.2/apps/gallery/js/gallery.js#L219) app.

``` js
/*
 * MediaDB.js: a simple interface to DeviceStorage and IndexedDB that serves
 *             as a model of the filesystem and provides easy access to the
 *             user's media files and their metadata.
 *
 * Gaia's media apps (Gallery, Music, Videos) read media files from the phone
 * using the DeviceStorage API. They need to keep track of the complete list of
 * media files, as well as the metadata (image thumbnails, song titles, etc.)
 * they have extracted from those files. It would be much too slow to scan the
 * filesystem and read all the metadata from all files each time the apps starts
 * up, so the apps need to store the list of files and metadata in an IndexedDB
 * database. This library integrates both DeviceStorage and IndexedDB into a
 * single API. It keeps the database in sync with the filesystem and provides
 * notifications when files are added or deleted.
 * /
 ```

 ### Permissions

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
