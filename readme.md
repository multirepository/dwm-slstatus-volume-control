This is more of a personal note than a manual, but nevertheless, it might help someone.

```ONLY WORKS WITH PULSEAUDIO!!!```

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

Add to slstatus:
```
{ run_command, "  %s ", "pamixer --get-volume-human" },
```

Dependencies for slstatus:
1. ```pamixer```

Have a good day!
