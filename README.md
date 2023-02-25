# npid
Get name of process by pid

Bash script for Linux to print name of the processes by one or more space
separated PIDs. Such a PID must be an integer number and can be obtained
through `pidof` command in example.

## Examples:
        
    $ npid 1074208
    firefox
    
    $ npid -c 1074208
    firefox: /usr/lib/firefox/firefox
    
    $ npid -p 1074208 787
    1074208 firefox
    787 python
    
    $ npid -p -c $(pidof python)
    787 python: /usr/bin/python /usr/bin/qtile start --no-spawn --with-state=/tmp/qtile-state 
    601 firewalld: /usr/bin/python /usr/bin/firewalld --nofork --nopid 
