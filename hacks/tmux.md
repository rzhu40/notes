`tmux` is superior to `screen` for many reasons, here are just some examples:

- Windows can be moved between session and even linked to multiple sessions
- Windows can be split horizontally and vertically into panes
- Support for UTF-8 and 256 colour terminals
- Sessions can be controlled from the shell without the need to enter a session

# Basic Functionality

To get the same functionality as explained in the [answer](https://askubuntu.com/a/8657/53508) recommending `screen`, you would need to do the following:

- ssh into the remote machine
- start `tmux` by typing `tmux` into the shell
- start the process you want inside the started `tmux` session
- leave/detach the `tmux` session by typing Ctrl+b and then d

You can now safely log off from the remote machine, your process will keep running inside `tmux`. When you come back again and want to check the status of your process you can use `tmux attach` to attach to your `tmux` session.

If you want to have multiple sessions running side-by-side, you should name each session using Ctrl+b and `$`. You can get a list of the currently running sessions using `tmux list-sessions`, now attach to a running session with command `tmux attach-session -t `.

`tmux` can do much more advanced things than handle a single window in a single session. For more information have a look in `man tmux` or [the tmux GitHub page](http://tmux.github.io/). In particular, [here's an FAQ](https://github.com/tmux/tmux/wiki/FAQ) about the main differences between `screen` and `tmux`.



End session by Ctrl+B then x

