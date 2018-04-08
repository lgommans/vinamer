# ViNamer

## Vim-based Renamer

Want to rename a directory vim-style? Where you have the directory listing in
Vim, make the changes you want (with undo and everything), and just :wq to
perform the renames? That's what this tool does.

Imagine you have these files:

	$ ls
	cover.jpg
	info.txt
    ThePillarsoftheEarthUnabridgedPart1_mp332__gNXrVjh8TdNub9fZTlfuGbwolaGxdgIPe1zeFhUcv7c6UPWcu53osmW9mbRaQ.aa.mp3
    ThePillarsoftheEarthUnabridgedPart2_mp332_u6vu09Cadkkp_18ey_1dhb28qka0LPglEsl_FUwJOZPHkJq5P68gkzRNhtQnXg.aa.mp3
    ThePillarsoftheEarthUnabridgedPart3_mp332_lRnZDtCDJfUKDu2odrKGTQaoTJ8VYsq36cDQKONEPM17VeBBG4nhkkGwDLxhBg.aa.mp3
    ThePillarsoftheEarthUnabridgedPart4_mp332_lRnZDtCDJfUKDu2odrKGTQaoTJ8VYsq36cDQKONEPM17VeBBG4nhkkGwDLxhBg.aa.mp3
    ThePillarsoftheEarthUnabridgedPart5_mp332_UZdWUYq9bKgTnr-WAy7zCD-q3J27EuttG8Z3QpRtgQLSDFtfA_LPFn19DCk4_A.aa.mp3

And obviously you want to get rid of these crappy filenames. Use `vinamer The*`
and it will start Vim for you, opening a temporary file with the following
contents:

    ThePillarsoftheEarthUnabridgedPart1_mp332__gNXrVjh8TdNub9fZTlfuGbwolaGxdgIPe1zeFhUcv7c6UPWcu53osmW9mbRaQ.aa.mp3
    ThePillarsoftheEarthUnabridgedPart2_mp332_u6vu09Cadkkp_18ey_1dhb28qka0LPglEsl_FUwJOZPHkJq5P68gkzRNhtQnXg.aa.mp3
    ThePillarsoftheEarthUnabridgedPart3_mp332_lRnZDtCDJfUKDu2odrKGTQaoTJ8VYsq36cDQKONEPM17VeBBG4nhkkGwDLxhBg.aa.mp3
    ThePillarsoftheEarthUnabridgedPart4_mp332_lRnZDtCDJfUKDu2odrKGTQaoTJ8VYsq36cDQKONEPM17VeBBG4nhkkGwDLxhBg.aa.mp3
    ThePillarsoftheEarthUnabridgedPart5_mp332_UZdWUYq9bKgTnr-WAy7zCD-q3J27EuttG8Z3QpRtgQLSDFtfA_LPFn19DCk4_A.aa.mp3

So you make the changes you want, using visual block mode or :%s or something,
and you turn it into this:

    The Pillars of the Earth Unabridged Part 1.mp3
    The Pillars of the Earth Unabridged Part 2.mp3
    The Pillars of the Earth Unabridged Part 3.mp3
    The Pillars of the Earth Unabridged Part 4.mp3
    The Pillars of the Earth Unabridged Part 5.mp3

Then you just `:wq` (or ZZ) and Vinamer will check your changes and ask you:

    You edited 5/5 lines. Do you want to continue? [y/n]

After confirming, it will show you what it is doing while performing the
renames. You can also confirm (or cancel) each rename individually, using `-i`
for interactive mode (`vinamer -i The*`).

Exact invocation is available using `-h` or `--help`.

