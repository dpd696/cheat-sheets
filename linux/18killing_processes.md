# Killing processes (kill, pkill, killall)

## Listing All Signals

```
kill -l
```

## Sending A Signal (default SIGTERM - 15) To A Process By Pid
``` 
kill pid        # => Ex: kill 12547
```

## Sending A Signal To More Processes

```
kill -SIGNAL pid1 pid2 pid3 ...
```

## Sending A Specific Signal (SIGHUP - 2) To A Process By Pid

```
kill -2 pid
kill -HUP pid
kill -SIGHUP pid
```

## Sending A Signal (default SIGTERM - 15) To Process By Process Name

```
pkill process_name          # => Ex: pkill sleep
killall process_name
kill $(pidof process_name)  # => Ex: kill -HUP $(pidof sshd)
```

## Running A Process In The Background

```
command &   # => Ex: sleep 100 &
```

## Showing Running Jobs

```
jobs
```

## Stopping (Pausing) The Running Process

```
Ctrl + Z
```

## Resuming And Bringing To The Foreground A Process By job_d

```
fg %job_id
```

## Resuming In The Background A Process By job_d

```
bg %job_id
```

## Starting A Process Immune To SIGHUP

```
nohup command &     # => Ex: nohup wget http://site.com &
```