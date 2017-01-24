# Listbox
💬 listbox element for bash

![demo](https://github.com/gko/listbox/raw/master/demo.gif)

Simple bash listbox to choose from options

## Installation

### Manually
```bash
git clone https://github.com/gko/listbox
```
then in .bashrc or .zshrc:
```bash
source ./listbox/listbox.sh
```
### With [antigen](https://github.com/zsh-users/antigen)

In your .zshrc
```sh
antigen bundle gko/listbox
```

## Usage
```
Usage: listbox [options]
Example:
  listbox -t title -o "option 1|option 2|option 3" -r resultVariable -a '>'
Options:
  -h, --help                         help
  -t, --title                        list title
  -o, --options "option 1|option 2"  listbox options
  -r, --result <var>                 result variable
  -a, --arrow <symbol>               selected option symbol
```
### General usage
```bash
source ./listbox.sh
listbox -t Title -o "option 1|option 2|option 3" -r result
echo "user chose: $result"
```

output:
```bash
  Title
  -----
  option 1
> option 2
  option 3
  
user chose: option 2
```

### Specify arrow symbol
```bash
listbox -t Title -o "option 1|option 2|option 3" -a '→'
```

output:
```bash
  Title
  ---
→ option 1
  option 2
  option 3
  
option 1
```

### Pipe directly to variable
```bash
result=$(listbox -t Title -o "option 1|option 2|option 3" | tee /dev/tty | tail -n 1)
echo "user chose: $result"
```

output:
```bash
  Title
  ---
  option 1
> option 2
  option 3
  
user chose: option 2
```

## What about zsh

It supports zsh as well. Same usage as for bash.

## Like it?

:star: this repo

## License

[MIT](http://opensource.org/licenses/MIT)

Copyright (c) 2012-2016 Konstantin Gorodinskiy
