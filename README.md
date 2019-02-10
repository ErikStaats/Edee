# Erik's DEvelopment Environment (Edee)

* [Building](#building)
* [Installing](#installing)

## Building

To build Edee, start by cloning the repository.

```
Edee$ git clone https://github.com/ErikStaats/Edee.git
Cloning into 'Edee'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
Edee$
```

Then, use "`dpkg-deb --build`" to build the Edee package.

```
Edee$ dpkg-deb --build Edee/pkg/edee edee.deb
dpkg-deb: building package 'edee' in 'edee.deb'.
Edee$ ls -l edee.deb
-rw-r--r-- 1 erikstaats erikstaats 684 Feb 10 11:40 edee.deb
Edee$
```


## Installing

To install Edee, use "`dpkg -i`" and "`apg-get install -f`". The Edee package
uses dependencies to install other packages. These introduce package dependency
errors when using "`dpkg -i`", and these are resolved and the additional
packages are installed using "`apg-get install -f`".

```
Edee$ which make
Edee$ sudo dpkg -i edee.deb
.
.
.
Errors were encountered while processing:
 edee
Edee$ sudo apt-get install -f
.
.
.
Setting up edee (1) ...
Edee$ which make
/usr/bin/make
Edee$
```

