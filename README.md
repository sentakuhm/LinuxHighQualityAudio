# LinuxHighQualityAudio
Enabling linux high quality audio

1. move deamon.conf to ~/.config/pulse folder.<br/>
2. edit /etc/asound.conf<br/>
```
# Use PulseAudio by default
pcm.!default {
  type pulse
  fallback "sysdefault"
  hint {
    show on
    description "Default ALSA Output (currently PulseAudio Sound Server)"
  }
}
```

to looks like:<br/>
```
# Use PulseAudio plugin hw
pcm.!default {
   type plug
   slave.pcm hw
}
```
