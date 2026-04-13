This is more of a personal note than a manual, but nevertheless, it might help someone.

```ONLY WORKS WITH PULSEAUDIO!!! and maybe pipewire through the compatibility layer?```

Add keybinds in dwm:

/* commands */
```
#include <X11/XF86keysym.h>
static const char *upvol[]      = { "/usr/bin/pactl",   "set-sink-volume", "0",      "+5%",      NULL };
static const char *downvol[]    = { "/usr/bin/pactl",   "set-sink-volume", "0",      "-5%",      NULL };
static const char *mutevol[]    = { "/usr/bin/pactl",   "set-sink-mute",   "0",      "toggle",   NULL };
```
/* keys */

	{ 0,         XF86XK_AudioRaiseVolume,      spawn,          {.v = upvol   } },
	{ 0,         XF86XK_AudioLowerVolume,      spawn,          {.v = downvol } },
	{ 0,                XF86XK_AudioMute,      spawn,          {.v = mutevol } },

Dependencies for keybinds:
1. ```pulseaudio-utils```

Add to slstatus:
```
{ run_command, "  %s ", "pamixer --get-volume-human" },
```

Sample:
<img width="1920" height="1080" alt="sample" src="https://github.com/user-attachments/assets/f6ca84e1-49cd-463d-9bc8-d8d10beecb49" />

Dependencies for slstatus:
1. ```pamixer```

Have a good day!
