+++
date = '2017-04-17T10:23:05+02:00'
draft = false
title = 'Remove old node_modules directories'
tags = [ 'Snippets', 'Tips',  ]
+++

The node_modules directories can grow quite large,
if you need to free up some disk space with a simple bash command:

```shell
find . -type d -name 'node_modules' -prune -print0 | xargs -0 rm -rf
```

Here is a writeup what this one-liner actually does:

```shell
find .
  -type d              # Filter directories
  -name 'node_modules' # Find node_modules
  -prune               # Dont recurse in directories,
                       # this way find wont search inside the 'node_modules' dir
  -print0              # Print output in a format that is understandable for the pipe
  | xargs -0 rm -rf    # Remove directories
```



