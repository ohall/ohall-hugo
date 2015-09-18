+++
date = "2015-09-18T12:52:45-04:00"
tags = [
    "node",
    "tooling",
    "NPM",
    "development",
    "javascript",
    "DevOps"
]
categories = [
    "Node",
    "Tooling",
    "Development",
    "JavaScript",
    "DevOps"
]
title = "NPM Shrinkwrap is easy"

+++


In this hypothetical example, you're a programmer who has a project. In this project, you are using a bunch of dependecies, which you manage with NPM and are specified in the `package.json` file.

Whenever you build this app, you install all the things using `npm install`.  You continue to build the app and deploy it and your users use it
```.  Except one day you build the app and it breaks! WHY?! You haven't even touched the code!

Aha! A dependency has changed, or a dependency of a dependency and now our build is broken. Alas. 
    
So you're telling me that unless every package uses specific package version, my build could break at ANY time! 

Yes.

There must be a way to fix this.

There is!

## NPM Shrinkwrap

NPM Shrinkwrap locks your entire dependency tree to the current intalled version.  This is built into NPM and you can do it right now.

This command.

```
npm shinkwrap
```

will generate a file called `npm-shrinkwrap.json` that specified EXACTLY which version of each dependency will be installed when you `npm install`.

If you want to update a package, run `npm update <package_name>`. and then re-run `npm shinkwrap` to update your `npm-shrinkwrap.json`.

if you want to see which packages are out of date, you can use:

```
npm outdated
```

and you'll see something like this:

```
Package        Current  Wanted  Latest  Location
lodash           3.7.0  3.10.1  3.10.1  lodash
moment          2.10.2  2.10.6  2.10.6  moment
q                1.3.0   1.4.1   1.4.1  q
wreck            5.5.1   5.6.1   6.2.0  wreck
```

By default, shrinkwrap ignores your devDependencies you can include them by using the `--dev` flag.

```
npm shrinkwrap --dev
```

See how easy that is! So don't live with broken builds, use NPM shrinkwrap and keep your dependecies where they belong.