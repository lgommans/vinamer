# ViNamer (vn)

**Vim-based Renamer**

Want to rename files in bulk, vim-style? Where you have the directory listing
in Vim, make the changes you want (with undo and everything), and just :wq to
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

And obviously you want to get rid of these crappy filenames. Use `vn The*`
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

Then you just `:wq` (or ZZ) and ViNamer will rename the files for you, showing what it is doing:

    Renaming "ThePillarsoftheEarthUnabridgedPart1_mp332__gNXrVjh8TdNub9fZTlfuGbwolaGxdgIPe1zeFhUcv7c6UPWcu53osmW9mbRaQ.aa.mp3" to "The Pillars of the Earth Unabridged Part 1.mp3".
    Renaming "ThePillarsoftheEarthUnabridgedPart2_mp332_u6vu09Cadkkp_18ey_1dhb28qka0LPglEsl_FUwJOZPHkJq5P68gkzRNhtQnXg.aa.mp3" to "The Pillars of the Earth Unabridged Part 2.mp3".
    Renaming "ThePillarsoftheEarthUnabridgedPart3_mp332_lRnZDtCDJfUKDu2odrKGTQaoTJ8VYsq36cDQKONEPM17VeBBG4nhkkGwDLxhBg.aa.mp3" to "The Pillars of the Earth Unabridged Part 3.mp3".
    Renaming "ThePillarsoftheEarthUnabridgedPart4_mp332_lRnZDtCDJfUKDu2odrKGTQaoTJ8VYsq36cDQKONEPM17VeBBG4nhkkGwDLxhBg.aa.mp3" to "The Pillars of the Earth Unabridged Part 4.mp3".
    Renaming "ThePillarsoftheEarthUnabridgedPart5_mp332_UZdWUYq9bKgTnr-WAy7zCD-q3J27EuttG8Z3QpRtgQLSDFtfA_LPFn19DCk4_A.aa.mp3" to "The Pillars of the Earth Unabridged Part 5.mp3".

You can also confirm (or cancel) each rename individually, using `-i` for
interactive mode (`vn -i The*`).

And that's pretty much all there is to it! I've been using it frequently for a
year now. I've used bulk rename tools before, but knowing Vim pretty well, this
beats everything. I hope you enjoy it, too!

## Installation

The `vn` file in this repository is all you need, it's a small Python3 script
that uses only standard libraries.

Download the file or copy the contents into a text file and place it somewhere
in your `$PATH`. If you are not sure what that means, it's easiest to put it in
`/usr/bin/vn` and give it executable permissions with `chmod +x /usr/bin/vn`.
You can now use it as shown in the example above.

