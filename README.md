# Generic Bash Functions

## Purpose
Set of bash functions useful at all times.

## Functions list
Default log level is "info". Can be changed by setting $LOG\_LEVEL.  

### log
Log messages with severity ([d]ebug|[i]nfo|[w]arning|[e]rror) to stdout or $LOG\_FILE if set.  
```sh
log <severity> <message>
```
```
EXAMPLE
log i "This is a log message with severity info"

LOG_FILE will contain:
2019-04-02 14:02:53 CEST | ESC[0;32m[i]ESC[0m This is a log message with severity info

stdout will contain (while the [i] will be green):
2019-04-02 14:02:53 CEST | [i] This is a log message with severity info
```
### sys\_log
Log message with severity prefix (debug|info|warning|error) to /var/log/local6.  
```sh
sys_log <severity> <message>
```
```
EXAMPLE
sys_log info "This is a log message with severity prefix info"

/var/log/local6 will contain:
2019-04-02T12:07:23.199934+00:00 rnd-vm-10-198 -bash[12662]: [info] This is a log message with severity prefix info
```
### progress\_bar
Display waiting pattern until a process finishes  
```sh
progress_bar <$PID>
```
```
EXAMPLE
progress_bar 37458

# Below lines are displayed in one line, here multiple lines are used to articulate what is shown.
[processing of 37550] \
[processing of 37550] |
[processing of 37550] /
[processing of 37550] -

# Below line is displayed once the $PID has stopped, this line overwrites the above.
# Once the processing of the $PID stopped, only below lines remains in the terminal scroll view.
[processing of 37550] has finished
```

## Usage
```sh
pushd /opt
git clone https://github.com/lanthean/gbf.git
ln -snf ./gbf generic_bash_functions
popd
source /opt/gbf/generic_bash_functions
```

## Contact me
e	lanthean@protonmail.com  
g https://github.com/lanthean  
