# tmux (Cheat Sheet)

Read man page with all docs:

```sh
man tmux
```

Start a new session

```sh
new-session [-AdDEPX] [-c start-directory] [-e environment] [-f flags] [-F format] [-n window-name] [-s session-name] [-t group-name] [-x
             width] [-y height] [shell-command]
                   (alias: new)
             Create a new session with name session-name.
```

```sh
tmux new -s mysession
tmux new-session -s mysession
```

List all sessions:

```sh
tmux ls
```

Attach to session:

```sh
attach-session [-dErx] [-c working-directory] [-f flags] [-t target-session]
                   (alias: attach)
             If run from outside tmux, create a new client in the current terminal and attach it to target-session.  If used from inside, switch the
             current client.  If -d is specified, any other clients attached to the session are detached.  If -x is given, send SIGHUP to the parent
             process of the client as well as detaching the client, typically causing it to exit.  -f sets a comma-separated list of client flags.
```

```sh
tmux attach -t mysession
```

Rename session:

```sh
rename-session [-t target-session] new-name
                   (alias: rename)
             Rename the session to new-name.
```

```sh
tmux rename -t mysession newName
tmux rename-session -t mysession newName
```

Detach from session: `Ctrl`+`b` `d`

Create new window: `Ctrl`+`b` `c`

Rename window: `Ctrl`+`b` `,`

List all windows: `Ctrl`+`b` `w`

Scroll: (Enter copy mode) `Ctrl`+`b` `[` (Exit copy mode) `q`

Split vertically (left/right): `Ctrl`+`b` `%`
Close pane: `Ctrl`+`b` `x`

Split horizontally (top/bottom): `Ctrl`+`b` `"`

Move between panes: `Ctrl`+`b` arrow key

Delete session: 

```sh
tnux kill-session -t <sessionName>
```

Resize window (window with lots of dots)

```sh
tmux a -d -t <SESSION_NUM>
```

> When you attach to a session in two different terminal applications.
> You may notice that some of the window space is filled with dots. 
> That is because the session window before is smaller than the current window.

Source: [jdhao.github.io](https://jdhao.github.io/2018/10/23/tmux_questions_and_trouble_shooting/)
