# Google Maps For Fork CMS

An adaptation of the
[GoogleMapAPI V3](http://code.google.com/p/php-google-map-api/) to
allow geocodecaching through fork cms.


## Usage

For general usage: see http://code.google.com/p/php-google-map-api/

### Caching in fork:

    self::$map = new GoogleMapAPI();
    self::$map->_db_cache_table = 'geocodecache'; // cache results in this table
    self::$map->setCached(true); // turn caching on.

Make sure that either FrontendModel or BackendModel are loaded if you want the geocodes cached.

You can change the caching table name by setting the _db_cache_table
variable. The class expects to find a table which is constructed like
the following (if the _db_cache_table variable is not set, we default
to this tablename):

    CREATE TABLE GEOCODES (
      address varchar(255) NOT NULL default '',
      lon float default NULL,
      lat float default NULL,
      PRIMARY KEY  (address)
    );


# License

Released under the LGPL licence (see .php file for author info)
