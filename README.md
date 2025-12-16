# husarnetworking
some customized instructions for connecting to our husarnet network

## can't connect?
### The first time, try...
```
RELEASE="v1.3.6"
ARCH="amd64"
```
*Here the version is updated to the latest from 1.3.5- I think this was a problem!*

```
sudo curl -L https://github.com/husarnet/husarnet-dds/releases/download/$RELEASE/husarnet-dds-linux-$ARCH -o /usr/local/bin/husarnet-dds
sudo chmod 755 /usr/local/bin/husarnet-dds
```
*These commands pull the right release and make it so any computer user can read and execute*
```
export RMW_IMPLEMENTATION=rmw_fastrtps_cpp
export FASTRTPS_DEFAULT_PROFILES_FILE=/var/tmp/husarnet-fastdds-simple.xml
```
*This is re-exporting the settings to this new release*

```
husarnet-dds singleshot
```
*Don't forget the mysterious singleshot command that gives access permissions*

### The results I have had
are that after I run these commands I can connect to the talker/listener test script
**however** I still can't see the topic names

### After the first time, just run
```
export RMW_IMPLEMENTATION=rmw_fastrtps_cpp
export FASTRTPS_DEFAULT_PROFILES_FILE=/var/tmp/husarnet-fastdds-simple.xml
```
*I'm going to write a little bash script to take care of this so I don't have to do it every time*

## Still can't see the topic names?
After I logged out and in a few times I was able to see the topic names. Don't know what changed, will update if I work it out.
Notably I logged on as root user and ran the sequence, so it's possible that running it as root changed it somehow?
After doing it as root once I do not have to be root user to make it work for subsequent connections.


## Can't log in?
If you're getting 
```
ERROR: Authentication error occured
ERROR: Invalid character '<' looking for beginning of value
```
Try logging in to the dashboard and find the join code- it should look like this:
```
sudo husarnet join hfisoftware@case.edu/[JOIN CODE HERE]
```
but maybe be for sma258
