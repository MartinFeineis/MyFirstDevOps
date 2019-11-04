# Lesson 2
Learning about Software Installation and Package Manager.

## Yum Package Manager for Fedora
To search for new Packages use, where the Packagename is _<packagename>_
`yum search <packagename>`

## Installing a package
To install a package with _<packagename>_ run
`sudo yum install <packagename>`  You need to confirm this with `Y` or run the command like
`sudo yum -y install <packagename>`

## Uninstalling/removing a package
To uninstall a package run `sudo yum remove <packagename>`

## Showing package information
```bash
yum show <package>
```


## Lesson Tests
1. Install the package `bsdgames`.
2. Show the content of the `bsdgames` package.
3. Get the version of the `bsdgames` package.
4. Play one of the games.
