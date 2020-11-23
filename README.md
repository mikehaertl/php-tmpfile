php-tmpfile
===========

[![GitHub Tests](https://github.com/mikehaertl/php-tmpfile/workflows/Tests/badge.svg)](https://github.com/mikehaertl/php-tmpfile/actions)
[![Packagist Version](https://img.shields.io/packagist/v/mikehaertl/php-tmpfile?label=version)](https://packagist.org/packages/mikehaertl/php-tmpfile)
[![Packagist Downloads](https://img.shields.io/packagist/dt/mikehaertl/php-tmpfile)](https://packagist.org/packages/mikehaertl/php-tmpfile)
[![GitHub license](https://img.shields.io/github/license/mikehaertl/php-tmpfile)](https://github.com/mikehaertl/php-tmpfile/blob/master/LICENSE)

A convenience class for temporary files.

## Features

 * Create temporary file with arbitrary content
 * Delete file after use (can be disabled)
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

If you want to keep the temporary file, e.g. for debugging, you can set the `$delete` property to false:

```php
<?php
use mikehaertl\tmp\File;

$file = new File('some content', '.html');
$file->delete = false;
```
