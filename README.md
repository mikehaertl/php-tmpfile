php-tmpfile
===========

[![Build Status](https://secure.travis-ci.org/mikehaertl/php-tmpfile.png)](http://travis-ci.org/mikehaertl/php-tmpfile)

A convenience class for temporary files.

## Features

 * Create temporary file with arbitrary content
 * Delete file after use
 * Send file to client, either inline or with save dialog
 * Save file locally

## Examples

```php
<?php
use mikehaertl\tmp\File;

$file = new File('some content', '.html');

// send to client for download
$file->send('home.html');

// save to disk
$file->saveAs('/dir/test.html');

// Access file name and directory
echo $file->getFileName();
echo $file->getTempDir();
```
