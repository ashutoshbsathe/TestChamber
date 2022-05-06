# TestChamber
A Gym environment for training RL agents in Portal 2

## Command line options for Steam
```
-vulkan -high -novid -sw -w 180 -h 180 -condebug +map rl_challenge_1 +plugin_load sar +sar_tas_server 1 +sar_tas_debug 1 +sar_tas_playback_rate 100 +hud_quickinfo 0 +sar_quickhud_mode 1 +sar_quickhud_size 4
```
Ignore `-condebug` if your disk is really slow. Replace `rl_challenge_1` with whatever map name you'd use with `map <x>` command in the game console


## Trained Agent

Top left corner is what the agent sees

https://user-images.githubusercontent.com/22210756/167170153-d46a0d74-e003-4382-b1eb-ecb45188d862.mov

