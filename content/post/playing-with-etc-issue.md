+++
date = "2017-05-23T13:27:28+05:00"
draft = false
title = "Playing with /etc/issue and /etc/motd"
image = "playing-with-etc-issue-and-etc-motd.png"
+++

This article covers the /etc/issue and /etc/motd files in an Arch Linux environment. It discusses what the files are for, what content can go inside of them, and recommendations for usage.



## What are they and why do I care?

Like most things in a Linux environment, we can start by looking at the man pages for both ```/etc/issue``` and ```/etc/motd```

{{< tabs "man-pages" >}}
    {{< tabs-title title="man issue" isActive="true" >}}
    {{< tabs-title title="man motd" >}}
{{< /tabs >}}

{{< tabs-content "man-pages" >}}

    {{% tabs-panel title="man issue" isActive="true" %}}
``` text
NAME
       issue - prelogin message and identification file

DESCRIPTION
       The file /etc/issue is a text file which contains a message or system identification to be printed before the login prompt.  It may contain various @char and \char sequences, if supported by the getty-type program employed on the system.

```
    {{% /tabs-panel %}}

    {{% tabs-panel title="man motd" %}}
```
NAME
       motd - message of the day

DESCRIPTION
       The contents of /etc/motd are displayed by login(1) after a successful login but just before it executes the login shell.

       The  abbreviation  "motd"  stands for "message of the day", and this file has been traditionally used for exactly that (it requires much less disk space than mail to all users).
```
    {{% /tabs-panel %}}

{{< /tabs-content >}}

So now we know that /etc/issue is used to display a message before the login prompt and may contain various character (escape) sequences.

We also found out that /etc/motd is used to display a message after a sucessful login but just before the login shell.


### What @char and \char sequences?

In the previous section, we saw in the man page for issue that it mentioned 'It may contain various @char and \char sequences, if supported by the getty-type program employed on the system.'

On Arch Linux, we are working with agetty, so you can visit the man page to see if it supports char sequences.

``` zsh
man agetty
```

```
ISSUE ESCAPES
       The  issue-file (/etc/issue, or the file set with the -f option) may contain certain escape codes to display the system name, date,
       time etcetera.  All escape codes consist of a backslash (\) immediately followed by one of the characters listed below.

       4 or 4{interface}
              Insert the IPv4 address of the specified network interface (for example: \4{eth0}).  If the interface argument is not speci‐
              fied,  then  select  the  first fully configured (UP, non-LOCALBACK, RUNNING) interface.  If not any configured interface is
              found, fall back to the IP address of the machine's hostname.

       6 or 6{interface}
              The same as \4 but for IPv6.

       b      Insert the baudrate of the current line.

       d      Insert the current date.
```

For more information, look at the [Issue Escapes section](https://www.systutorials.com/docs/linux/man/8-agetty/#lbAI) you can see the available escape sequences.


## /etc/issue.net

Some people will want to display a different version of /etc/issue content to users connecting via SSH instead of the one shown at a terminal. This could even be a requirement depending on company policies or customer needs. I personally do not use a separate file, as I keep my banners extremely abstract and don't display any detailed information (more on this in a minute).

### Reasons for an /etc/issue.net file
* SSH connections won't render escapse sequences, and instead will show the codes in their raw format (e.g. instead of seeing the time, you would see ```\t```)
* SSH connections won't render the clear chararcters (used to clear the screen before displaying on a terminal)
* You may want to display a stricter banner to remote connections, such as removing compromising information that may display on a terminal version.

To enable this new banner for the SSH daemon, you will want to edit your /etc/ssh/sshd_config file and make sure the following line exists...add or edit as needed...

```
Banner /etc/issue.net
```


## What should go in there?

Now that you know you can put whatever you want in /etc/issue


# My personal /etc/issue and /etc/issue.net

``` text
^[[3J^[[H^[[J

#########################################################################
#                                                                       #
#       You are connected to a privately owned server.                  #
#                                                                       #
#       Disconnect IMMEDIATELY if you are not an authorized user.       #
#                                                                       #
#       All connections are monitored and recorded                      #
#                                                                       #
#########################################################################


```


# Resources

* https://www.systutorials.com/docs/linux/man/8-agetty/
