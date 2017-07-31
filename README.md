go-sqlcipher
==========

SQLCipher driver conforming to the built-in database/sql interface and using the latest sqlcipher code.


It's wrapper with
 * [go-sqlite3](https://github.com/mattn/go-sqlite3) sqlite3 driver for go that using database/sql.
 * [SQLCipher](https://github.com/sqlcipher/sqlcipher) SQLCipher is an SQLite extension that provides 256 bit AES encryption of database files.
 * Using [openssl](https://github.com/openssl/openssl) as the 256 bit AES encryption.


Installation
------------

This package can be installed with the go get command:

    go get github.com/muyuballs/go-sqlcipher

_go-sqlcipher_ is *cgo* package.
If you want to build your app using go-sqlcipher, you need gcc.
However, if you install _go-sqlcipher_ with `go install github.com/muyuballs/go-sqlcipher`, you don't need gcc to build your app anymore.
    
Documentation
-------------

API documentation can be found here: http://godoc.org/github.com/xeodou/go-sqlcipher

Examples can be found under the `./_example` directory

FAQ
---

The golang code is copy from [go-sqlite3](https://github.com/mattn/go-sqlite3)
If you have some issue, maybe you can find from https://github.com/mattn/go-sqlite3/issues

Here is some help from go-sqlite3 project.

* Want to build go-sqlite3 with libsqlite3 on my linux.

    Use `go build --tags "libsqlite3 linux"`

* Want to build go-sqlite3 with libsqlite3 on OS X.

    Install sqlite3 from homebrew: `brew install sqlite3`

    Use `go build --tags "libsqlite3 darwin"`

* Want to build go-sqlite3 with icu extension.

   Use `go build --tags "icu"`

* Can't build go-sqlite3 on windows 64bit.

    > Probably, you are using go 1.0, go1.0 has a problem when it comes to compiling/linking on windows 64bit.
    > See: https://github.com/mattn/go-sqlite3/issues/27

* Getting insert error while query is opened.

    > You can pass some arguments into the connection string, for example, a URI.
    > See: https://github.com/mattn/go-sqlite3/issues/39

* Do you want to cross compile? mingw on Linux or Mac?

    > See: https://github.com/mattn/go-sqlite3/issues/106
    > See also: http://www.limitlessfx.com/cross-compile-golang-app-for-windows-from-linux.html

* Want to get time.Time with current locale

    Use `loc=auto` in SQLite3 filename schema like `file:foo.db?loc=auto`.

* Want to open with readonly

   Use `readonly=true` in SQLite3 filename schema like `file:foo.db?readonly=true`.


License
-------

MIT:

sqlite3-binding.c, sqlite3-binding.h, sqlite3ext.h

The -binding suffix was added to avoid build failures under gccgo.

In this repository, those files are amalgamation code that copied from SQLCipher. The license of those codes are depend on the license of SQLCipher.

In this repository, those files are an amalgamation of code that was copied from SQLite3. The license of that code is the same as the license of SQLite3.

Original repository https://github.com/mattn/go-sqlite3 is under MIT.

