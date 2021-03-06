**Application**

[CLion](https://www.jetbrains.com/clion/)

**Description**

JetBrains CLion is a cross-platform .NET IDE based on the IntelliJ platform and ReSharper. CLion supports .NET Framework, the new cross-platform .NET Core, and Mono based projects. This lets you develop a wide range of applications including .NET desktop applications, services and libraries, Unity games, Xamarin apps, ASP.NET and ASP.NET Core web applications.

**Build notes**

Latest stable CLion release from Arch Linux.

Note:- This application requires a license, otherwise it will run in Evaluation Mode for 30 days.

**Usage**
```
docker run -d \
    -p 5900:5900 \
    -p 6080:6080 \
    --name=<container name> \
    -v <path for config files>:/config \
    -v <path for data files>:/data \
    -v /etc/localtime:/etc/localtime:ro \
    -e CLION_PROPERTIES=<optional path to idea.properties file> \
    -e CLION_VM_OPTIONS=<optional additional jvm options > \
    -e WEBPAGE_TITLE=<name shown in browser tab> \
    -e VNC_PASSWORD=<password for web ui> \
    -e UMASK=<umask for created files> \
    -e PUID=<uid for user> \
    -e PGID=<gid for user> \
    allergicduck/arch-clion
```

Please replace all user variables in the above command defined by <> with the correct values.

**Example**
```
docker run -d \
    -p 5900:5900 \
    -p 6080:6080 \
    --name=clion \
    -v /apps/docker/clion:/config \
    -v /apps/docker/clion/projects:/data \
    -v /etc/localtime:/etc/localtime:ro \
    -e WEBPAGE_TITLE=CLion \
    -e VNC_PASSWORD=mypassword \
    -e UMASK=000 \
    -e PUID=0 \
    -e PGID=0 \
    allergicduck/arch-clion
```

**Access via web interface (noVNC)**

`http://<host ip>:<host port>/vnc.html?resize=remote&host=<host ip>&port=<host port>&&autoconnect=1`

e.g.:-

`http://192.168.1.10:6080/vnc.html?resize=remote&host=192.168.1.10&port=6080&&autoconnect=1`

**Access via VNC client**

`<host ip>::<host port>`

e.g.:-

`192.168.1.10::5900`

**Notes**

User ID (PUID) and Group ID (PGID) can be found by issuing the following command for the user you want to run the container as:-

```
id <username>
```
___
If you appreciate my work, then please consider buying me a beer  :D

[![PayPal donation](https://www.paypal.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=MM5E27UX6AUU4)

[Documentation](https://github.com/binhex/documentation) | [Support forum](https://forums.unraid.net/topic/76727-support-binhex-clion/)
