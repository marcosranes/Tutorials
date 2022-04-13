# How to Use tmux (a Terminal Multiplexer)

## Spliting the terminal, Restore old sections...
```
sudo apt install tmux
```
Open you terminal, and simply init running the command 
```
$ tmux
```
Vertical splitting **ctrl+b %**

Horizontal splitting **ctrl+b "**

Toggle betwen **ctrl+b o**

Close your terminal state

$ tmux ls

$ tmux attach-session -t 0

$ tmux kill-session -t 0

Verify Tmux usability

$ man tmux
