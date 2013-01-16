# Make use of named directories.

`~/` gets you to your home directory.
`~user` gets you to `user` home directory.

Generally you can give any path on your filesystem a shortcut.
Just put this into your `.zshrc`:

    dir=/path/to/dir
    : ~dir

And this is not just a replacement for a function named dir that issues
a `cd /path/to/dir` command. If you have `pwd` incorporated in your
shell prompt, then after `~dir` your prompt is going to look like:

    ~dir$

instead of

    /path/to/dir$

*NOTICE*

You should really be puzzled by the presence of `: ~dir` in the
uppermost snippet of code. That line is needed because the shell
will not register the name of the directory until you force it to
by using `~dir` yourself at least once. So we do it in `.zshrc` with
the colon command, which does nothing, but it's arguments are checked
and that makes everything work.

But it is generally a better idea to set the option `AUTO_NAME_DIRS`;
with it, every parameter created which referes to a directory will
automarically be turned into a name.
