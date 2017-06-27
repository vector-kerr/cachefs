# CacheFS

Cache Filesystem for PHP.

This package is made from code included in
[Ron Shpasser's GAE Support for Lumen Library](https://github.com/shpasser/GaeSupportLumen)
(Released under the [MIT License](https://github.com/shpasser/GaeSupportLumen/blob/master/LICENSE)).



# Installation

`composer require vector88/cachefs`



# Usage

1. Register the `cachefs` stream handler.
   ```php
   <?php

   \Vector88\CacheFS\CacheFS::register();
   ```

2. Use the `cachefs` stream handler.
   ```php
   <?php

   $fh = fopen( 'cachefs://some/file', 'w' );
   fwrite( $fh, 'file content' );
   fclose( $fh );

   // ...

   $fh = fopen( 'cachefs://some/file', 'r' );
   $content = fread( $fh, filesize( 'cachefs://some/file' ) );
   fclose( $fh );
   ```
