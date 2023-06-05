# npid
Get name of process by pid

Bash script for Linux to print name of the processes by one or more space
separated PIDs. Such a process identification number can be obtained by `pidof`
command in example. Alternatively a process name can be given instead a PID
number, in which case the script will run `pidof` internally to get the ID.

# Installation

Download the project directly from Github:

```
$ git clone https://github.com/thingsiplay/npid
$ cd npid
```
    
Now make the main program `npid` executable and put the file into a folder in the
`$PATH` for easy access. Or run the script `suggested_install.sh` to automate
the installation process:

```
$ bash suggested_install.sh
```

# Usage
  
```
usage: npid [-h] [-p] [-c] [--] [POPT ...] [PID ...] [NAME ...]
```

## Examples:

```
$ npid 1074208
firefox

$ npid -c 1074208
firefox: /usr/lib/firefox/firefox

$ npid -p 1074208 787
1074208 firefox
787 python

$ npid -p -c python
787 python: /usr/bin/python /usr/bin/qtile start --no-spawn --with-state=/tmp/qtile-state 
601 firewalld: /usr/bin/python /usr/bin/firewalld --nofork --nopid 

$ npid -pc firefox | grep 'firefox:' | grep -oE '^[0-9]+'
1074208
```
