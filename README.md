# .irssi

a quick bootstrap to get running with irssi. aimed at use with one server mainly. 

## install 

if you have an irssi setup, either delete it or back it up: 

```
cd ~ && rm -rf .irssi 
```

```
cd ~ && mv .irssi .old-irssi
```

clone this repo to your home directory, or wherever `irssi` looks for the config:

```
cd ~
git clone https://github.com/jeromescuggs/.irssi 
```

almost there! now you'll want to configure the `.irssi/config` file with your info. the important stuff is at the top, here you define the network name, server address, your nickname, and the channel you'd like to automatically enter after (automatically) connecting to the server when you start `irssi`.

when setting the channel to autojoin, you can omit the '#' e.g. entering `foobar` will be equal to having typed `/join #foobar`.

```
servers = (

  {
    address = "irc.server.net";
    chatnet = "SERVERNAME";
    port = "6667";
    use_tls = "no";
    tls_verify = "no";
    autoconnect = "yes";
  }
);

chatnets = {
  SERVERNAME = {
    type = "IRC";
    nick = "USER_NICK";
    realname = "USER_REAL";
  }
};

channels = (
  { name = "CHATROOM_NAME"; chatnet = "SERVERNAME"; autojoin = "yes"; }
);
```
