# ubuntu-ssh-handler
Handler to open SecureCRT or any terminal via ssh:// urls 

Specifically for setting up a custom handler to open ssh:// links via browser to SecureCRT.

Install the secureCrt-ssh.desktop file in 

~/.local/share/applications

Make executable

chmod +x ~/.local/share/applications/secureCrt-ssh.desktop

Add the following line to ~/.config/mimeapps.list

[Default Applications]
x-scheme-handler/ssh=secureCrt-ssh.desktop

Install and point the secureCrt-ssh.desktop to the following python

secureCrt-script

Make executable

chmod +x ~/.local/share/applications/secureCrt-script

Log Out to update. Then when you open uri handlers starting with ssh:// it will open a new tab in SecureCrt
