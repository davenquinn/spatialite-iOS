
# Spatialite

[![Build Status](https://api.travis-ci.org/Ryandev/spatialite-iOS.svg)](https://travis-ci.org/Ryandev/spatialite-iOS)
[![Carthage Compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)
[![License](https://img.shields.io/badge/license-MPL-blue.svg)](https://www.mozilla.org/en-US/MPL/1.1)

Spatialite is a plugin for SQLite that allows for geo-spatial queries


## Usage

* Include spatialite and sqlite header
```objc
#import <spatialite/spatialite.h>
#import <sqlite3/sqlite3.h>
```

* Initialize spatialite where ''mySQLite3Connection'' is your handle to a valid database instance

```objc
        int sqliteInitStatus = sqlite3_initialize();
        assert(sqliteInitStatus==SQLITE_OK);
        
        int sqliteInitOSStatus = sqlite3_os_init();
        assert(sqliteInitOSStatus==SQLITE_OK);
        
        sqlite3_enable_load_extension(mySQLite3Connection, 1);
        
        spatialite_initialize();

        _spatialiteConn = spatialite_alloc_connection();
        assert(_spatialiteConn);
        spatialite_init_ex(mySQLite3Connection, _spatialiteConn, 1);```
```

After the above you are able

## Notes
If you use the sqlite3 built provided by iOS/Mac ensure this version supports loading extension (Alternatively build sqlite3 with [extension support](https://www.github.com/Ryandev/SQLite-iOS))

## Project setup

### Carthage
```
github 'Ryandev/proj4' == 4.9.2
github 'Ryandev/geos' == 3.5.0
```


## License

SpatiaLite is licensed under the MPL tri-license terms; you are free to choose the best-fit license between:

1. [MPL 1.1](http://www.mozilla.org/MPL/MPL-1.1.html)
2. [GPL v2.0](http://www.gnu.org/licenses/gpl-2.0.html#TOC1) or any subsequent version
3. [LGPL v2.1](http://www.gnu.org/licenses/lgpl-2.1.html) or any subsequent version
