# Compile all the things!

Here you find step-by-step recipes on how to compile stuff from source code.

This repository is always a "work in progress". I have (or simply enjoy) to
compile software from source code more often than not. It's a very interesting
world to explore, but it can also be full of dead-ends and frustration.

I'll only add here procedures that I tried by myself and ended up with a
successful result. Let's hope this will help people out there.


## Audience

Developers, SysAdmins, DevOps (whatever they are) and software enthusiasts in
general. You need technical background and has to understand how programming
languages and the terminal work. I won't waste any time explaining what bash
or Make is, for example. Feeling comfortable on the CLI is crucial for all
this to work.

My working computer is a Debian Linux, so expect most of the things to target
this architecture. I also deal with Docker containers quite a lot, so it may
happen sometimes to target other linux distros, like Alpine. Embedded systems
is something I like to do in my free time (which almost never happens...).
Eventually something might pop up about Arduino, ESP32 and similar.

I rarely do anything on MacOS, but if I have to, I'll add it here as well.

No Windows instructions, sorry. Don't ask, please. I don't have any clue how
Windows works and I'm not interested into learning it. I've given up many,
many years ago.


## WARNING!

Compiling stuff is a daily business, but nevertheless potentially dangerous.
You always have the risk of ending up with an unusable machine or severely
damage your OS and/or environment. Make sure you cover yourself with enough
backups and that you perfectly understand everything you are doing.

Please notice that you are the only responsible for the software you compile,
plus eventual responsibility granted by the producers of the software. **Use
this repository at your own risk!** I won't be resposible for any damage, even
if the error was on my side. It's your sole responsibility to check and
research everything before running.

It is strongly recommended to compile software in an isolated environment. Get
yourself an EC2 instance, chroot location or docker container to play around.
Only run run stuff directly on your machine if you really mean it.


## Thanks and have fun!

Having that said, compiling some things is can be sometimes challenging but
it's also fun and very rewarding. Enjoy!
