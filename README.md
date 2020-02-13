# ViNamer (vn)

**Vim-based Renamer**

Are you good with Vim? Do you look at `ls -l` or `find` output wishing you
could just pipe it into `vim` and fix filenames in bulk?
That's what this tool does.

Two examples:

[![asciicast](https://asciinema.org/a/301177.svg)](https://asciinema.org/a/301177)

[![asciicast](https://asciinema.org/a/301180.svg)](https://asciinema.org/a/301180)

I've been using it frequently for a few years now. I've used bulk rename tools before,
but knowing Vim pretty well, this beats everything. I hope you enjoy it, too!

## Installation

The `vn` file in this repository is all you need, it's a small Python3 script
that uses only standard libraries.

Download the file or copy the contents into a text file and place it somewhere
in your `$PATH`. If you are not sure what that means, it's easiest to put it in
`/usr/bin/vn` and give it executable permissions with `chmod +x /usr/bin/vn`.
You can now use it as shown in the example above.
