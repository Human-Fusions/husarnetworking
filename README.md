# husarnetworking
some customized instructions for connecting to our husarnet network

## can't connect?
### try...
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
**and** I have to run these again every time I open a new terminal
