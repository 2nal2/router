# Nesting and Relative Links

Relative paths in the browser are a little different than on the file system and Reach Router has made an opinionated choice here. For many of us, the command line provides our intuition about relative paths

Imagine we're navigating up a directory.

```sh
$ cd /some/where
$ cd ../
$ pwd
/some
```

It works the same way with Reach Router:

```js
// if you're at /some/where
<Link to="../">Up</Link>
// this links to "/some"
```

If you are familiar with how path resolution works in the browser, you'll know that the trailing slash matters:

```js
// if we are at "/some/where/"
window.pushState("..")

// puts us at "/some/where"
// but a lot of people would expect to be at "/some"!

// now that we're at "/some/where"
window.pushState("..")

// puts us at "/some"
```

The difference from the command line here is that you can't be "at a file" in the command line. So any time you `cd` you're working relative to directories only. On the web you _can_ be "at a file", so the trailing slash indicates if you're "at a file" or "in a directory".

Reach Router made a choice to ignore trailing slashes completely, therefore eliminating any difference when navigating up the path. Therefore:

```js
// if we're at "/some/where" or "/some/where/"
<Link to="../">Up</Link>
// this links to "/some" in both cases
```

To sum it up, just imagine every url is a "directory" and you’ll do just fine.
