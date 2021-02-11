# Rem

Get some rapid-eye-movement sleep knowing your files are safe.

## What is Rem?

Rem is a CLI trash which makes it _ridiculously_ easy to recover them.

## Demo

[![asciicast](https://asciinema.org/a/390479.svg)](https://asciinema.org/a/390479)

Let's say we have the following file structure
```text
.
├── someDir
│   └── someFile
└── someFile
```

Next, we want to delete `someDir`. Simple!

```shell
rem someDir
```

Now it looks like this:
```text
.
└── someFile
```
Oh no! We actually needed that directory!
```shell
rem --undo someDir
```
Back to:
```text
.
├── someDir
│   └── someFile
└── someFile
```
It's really _that_ easy.

You can also delete files of the same name with no problem:
```shell
rem someDir/someFile someFile
```

## Installing
Build from source or use:
```shell
brew install quackduck/tap/rem
```
## Uninstalling
Simply remove the executable or use:
```shell
brew uninstall rem
```

Rem stores its trash by default at `~/.remTrash`.

## Usage

```text
Usage: rem [-t/--set-trash <dir>] [--permanent | -u/--undo] file
       rem [-d/--directory | --empty | -h/--help | -v/--version | -l/--list]
Options:
   -u/--undo              restore a file
   -l/--list              list files in trash
   --empty                empty the trash permanently
   --permanent            delete a file permanently
   -d/--directory         show path to trash
   -t/--set-trash <dir>   set trash to dir and continue
   -h/--help              print this help message
   -v/--version           print Rem version
```
