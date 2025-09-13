# mapi - Minimal Audio Plugin Interface

mapi is, as the acronym stands for, a minimal audio plugin interface, for C and C++.  
It is not a full blown plugin format nor does it intend to be, instead the goal is purely:

 - allow to create opaque audio effects (create, destroy and process functions)
 - set arbitrary parameter values
 - set arbitrary key/value state pairs

Each audio effect is shipped as a binary shared object, so 1 file per effect.
There is intentionally no discovery mechanism, no presets and no UI.

Applications using mapi are expected to know in advance the available effects installed on a system, or alternatively have an internal map between a mapi effect and how to use it.

These very strict limitations make mapi suitable for:

 - projects that want to host audio effects but don't want to deal with complex plugin APIs
 - projects that need a very specific audio effect but have no need for full audio plugin hosting capabilities
 - web-assembly modules (only 5 functions to do everything)
