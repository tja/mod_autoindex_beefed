Beefed Up `mod_autoindex` Listing
=================================

This software package beefs up the default `mod_autoindex` directory listings by using jQuery. See [this blog post](http://www.my-ride-home.com/2010/12/mod_autoindex/) for more information.

Installation
------------

Copy all files of this folder into a folder called `.index` in the root of your server (e.g. a DAV server).

Also, add the following configuration to you `<Directory>` entry in Apache's config file:

    <Directory "/path/to/folder">
      Options Indexes ...
      ...
      <IfModule mod_autoindex.c>
        IndexOptions FancyIndexing
        IndexOptions VersionSort
        IndexOptions HTMLTable
        IndexOptions FoldersFirst
        IndexOptions IconsAreLinks
        IndexOptions IgnoreCase
        IndexOptions SuppressDescription
        IndexOptions SuppressHTMLPreamble
        IndexOptions XHTML
        IndexOptions IconWidth=16
        IndexOptions IconHeight=16
        IndexOptions NameWidth=*
        IndexOrderDefault Ascending Name
        HeaderName /.index/header.htm
        ReadmeName /.index/footer.htm
      </ifModule>
    </Directory>

And you're all set.
