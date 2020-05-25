# Denomon

Simple watcher file for build an application using deno

[![asciicast](https://asciinema.org/a/kkoeCdKB5bKgCLY7XzHsmbFZy.png)](https://asciinema.org/a/kkoeCdKB5bKgCLY7XzHsmbFZy)

> Note : The pointer printed only on asciinema, but not on the bash / zsh

### Installation

Download using Wget

```bash
$ wget -O denomon https://raw.githubusercontent.com/muhibbudins/denomon/master/install.sh | sh
```

or, CURL
```bash
$ curl -LJO https://raw.githubusercontent.com/muhibbudins/denomon/master/install.sh | sh
```

Move the denomon binary into **/usr/bin** or **/usr/local/bin**

```bash
$ sudo mv denomon /usr/local/bin
```

Make it executable

```bash
$ sudo chmod +x /usr/local/bin/denomon
```

### Usage

```bash
$ denomon <options> <file>
```

Example:

- Showing help message

```bash
denomon --help
```

- Single command to spawn current folder (but not recursively [see limitation](https://github.com/muhibbudins/denomon#limitations).)

```bash
$ denomon
```

- Spawn file with permission [see note below]

```bash
$ denomon --allow net,read server.ts
```

- Spawn file with specific folder and permission [see note below]

```bash
$ denomon --dir fixtures --allow net,read server.ts
```

- Spawn specific folder with permission

```bash
$ denomon --dir fixtures --allow net,read
```

> Note : If you set denomon to spawn single file, all changes at root folder will trigger reload on main file.


### Options

#### --version

Showing denomon version

#### --help

Print this help message

#### --dir

Assign directory to watch

#### --allow

Assign permission for the files

### Features

- Auto build for single file
- Watching all files in folder
- Auto reload build for child process (ie. net)

### Limitations

#### --dir

Refer to this [issue](https://github.com/fsnotify/fsnotify/issues/18), currently this tools only can watch file in one folder. But not recursively.

### License

This project is under MIT License

### Stargazers over time

[![Stargazers over time](https://starchart.cc/muhibbudins/denomon.svg)](https://starchart.cc/muhibbudins/denomon)
      