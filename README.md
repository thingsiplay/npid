# npid
Get name of process by pid

Bash script for Linux to print name of the processes by one or more space
separated PIDs. Such a process identification number can be obtained by `pidof`
command in example. Alternatively a process name can be given instead a PID
number, in which case the script will run `pidof` internally to get the ID.

## Examples:

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
