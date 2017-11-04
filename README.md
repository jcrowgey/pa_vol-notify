# pa_vol-notify
Bash script to provide desktop notifications of volume changes

Provides a wrapper to pactl's set-sink-volume and set-sink-mute commands
which provides notifications via dunstify <https://github.com/dunst-project/dunst>.  
Written for providing volume change notifications in i3-wm <https://i3wm.org>.

For example, in my `~/.config/i3/config`I have:  
```
bindsym XF86AudioRaiseVolume exec --no-startup-id ~/bin/pa_vol-notify set-sink-volume 0 +5%
bindsym XF86AudioLowerVolume exec --no-startup-id ~/bin/pa_vol-notify set-sink-volume 0 -5%
bindsym XF86AudioMute exec --no-startup-id ~/bin/pa_vol-notify set-sink-mute 0 toggle
```

Parses the text format of the output of `pactl list sinks` to output the correct info in the 
notification.
