# shuffle-background
Summary:
I built this after expirenting with bash introduction for my personal computer for fun and expirence. It shuffles images in a directory and sets the desktop background. It was built for Gnome-3 on Ubuntu. Should work on any OS with gnome-3 I think.

Process:
gsettings set org.gnome.desktop.background picture-uri-dark file:/usr/share/backgrounds/canvas_by_roytanck.jpg # setting to set background as image -dark for dark mode uri or light
ls |sort -R |tail -$] |while read file; do
    # command here
done
First process didn't work. It shuffled all of the images and changed it (8/n) times. Very resource demanding.
Replaced with ...$|head -n 1... to stop after one shuffle
Learned how to provide log files for diagnosis which helped with the previous issue.

Use:
I put the final in my /bin folder and gave it a short name so I coudld run it with "alt+F2" which brought up my 'run program' so I could quickly shuffle it. I also created a custom shortcut for Ubuntu, 'Ctrl+Shift+Alt+B' which was the .sh file in my /bin folder.

Final:
#!/bin/bash
file=$(ls "path to wallpapers" | sort -R | head -n 1)
gsettings set org.gnome.desktop.background picture-uri-dark /home/jonah/Pictures/Backgrounds/$file
#echo "Ran" >> ~/LOGFILE.log # uncomment to provide logfile for testing
