# MacOS

## Wakeup and sleep check
pmset -g log|grep -e " Sleep  " -e " Wake  "

## Homebrew
Homebrew is a free and open-source software package management system that simplifies the installation of software on Apple's macOS operating system.

## Drain Battery Problem
The problem is the macOS continues to check for updates (including email, software, news, etc.) while your MacBook Pro is asleep. This means it's very quick to get up and running, but it also means your battery goes down.

To fix it, you can tell you MacBook Pro to disconnect from the Internet while it's a sleep.

To do this, you need to set the tcpkeepalive setting to 0.

Open up Terminal and type:

**sudo pmset -b tcpkeepalive 0**

After you enter your password for sudo it gives you a warning saying some features may not work properly. This is fine, it simply disables Internet access during sleep.

You can check it is set correctly by running:

**pmset -g**

Which should show "tcpkeepalive 0"

And you can of course reverse it at any time by running:

**sudo pmset -b tcpkeepalive 1**

Simple!

Note: You can also force your Mac not to connect to the Internet when it's asleep even when connected to a power supply, if you like: sudo pmset -a tcpkeepalive 0. (Personally I don't mind as long as it's not using my battery, so -b is fine for me.)

Also note: The results from pmset -g will vary depending on if you MacBook Pro is connected to power or not when you run the command. It will reflect the current tcpkeepalive setting, depending on its current power situation.

https://apple.stackexchange.com/questions/253776/macbook-pro-13-with-retina-display-consumes-10-battery-overnight-with-the-lid-c



## Change PATH environment on mac

>> open -e .bash_profile


export M2_HOME=/Applications/Projects/Systems/apache-maven-3.5.3
export PATH=$PATH:$M2_HOME/bin


>> source .bash_profile // reload command


## Aptana Studio
### Terminal issue
```
chmod 755 /Applications/AptanaStudio.app/Contents/Eclipse/plugins/com.aptana.terminal_3.0.0.201802081530/os/macosx/redtty
```





