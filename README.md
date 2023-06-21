# ubuntu-ssh-handler
Handler to open ssh:// links via any terminal application

Install the ssh-handler.desktop file in 

~/.local/share/applications

Make executable

chmod +x ~/.local/share/applications/ssh-handler.desktop

Add the following line to ~/.config/mimeapps.list

[Default Applications]
x-scheme-handler/ssh=ssh-handler.desktop

Install and point the ssh-handler.desktop to the following python

ssh-handler-script

Make executable

chmod +x ~/.local/share/applications/ssh-handler-script

Log Out to update. Then when you open uri handlers starting with ssh:// it will open a new tab in your terminal of choose.

Script Options for ssh-handler-script
```
usage: ssh_handler.py [-h] -s S -t T [-o O [O ...]]

Open a custom Terminal Session with or without Options

options:
  -h, --help    show this help message and exit
  -s S          the raw ssh handler link, ssh://hostname
  -t T          Absolute path to the terminal appication you want to use to open the ssh handler
  -o O [O ...]  Terminal CMD line options, space seperated options, any option that contains a space must be escaped with \, ex. -o /T /SSH2 /CREDENTIALS\ credName
```

Example 1 - Open ssh links using SecureCRT sending in SecureCRT Command line options

```
Exec=/home/tjones/.local/share/applications/ssh-handler-script -s %u -t /usr/bin/SecureCRT -o /T /SSH2 /CREDENTIALS\\ crt_cred_acct
```
