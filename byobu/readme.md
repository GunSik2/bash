


## Commands
```
F2  creates new windows within the current session.
F3/F4 scroll left and right through the windows list.
F8 renames the current open window in the list.
F7 lets you view scrollback history in the current window.

CTRL+F9  send the same input to every window
SHIFT+F9 send the same input to every pane.

CTRL+F3/F4 moves the current pane up or down, respectively
SHIFT+F3/F4 navigate between them (SHIFT+LEFT/RIGHT/UP/DOWN).
SHIFT+F11 toggles a pane to fill the whole window temporarily.

SHIFT+F2 creates a horizontal pane; CTRL+F2 creates a vertical one
```

## Scripts
- $BYOBU_CONFIG_DIR/windows.tmux.web
```
new-session 'bash' ;

new-window -n webu ssh -i ~/.ssh/prod.pem ubuntu@portal_web_user1;
split-window -v ssh -i ~/.ssh/prod.pem ubuntu@portal_web_user2;

new-window -n weba ssh -i ~/.ssh/prod.pem ubuntu@portal_web_admin1;
split-window -v ssh -i ~/.ssh/prod.pem ubuntu@portal_web_admin2;

select-layout tiled ;
select-pane -t 0
```

- Execute
```
BYOBU_WINDOWS=web byobu
```

## Reference
- https://www.digitalocean.com/community/tutorials/how-to-install-and-use-byobu-for-terminal-management-on-ubuntu-16-04
