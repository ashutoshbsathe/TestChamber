# TestChamber
A Gym environment for training RL agents in Portal 2

## Setup

* Portal 2 must be owned via steam
* Install my custom version of [SourceAutoRecord](https://github.com/ashutoshbsathe/SourceAutoRecord) plugin (need to be compiled for your OS) All the changes done by me can be inspected [here](https://github.com/ashutoshbsathe/SourceAutoRecord/commits?author=ashutoshbsathe)
* Add following to "launch options" of Portal 2 from Steam

```
-vulkan -high -novid -sw -w 180 -h 180 -condebug +map rl_challenge_1 +plugin_load sar +sar_tas_server 1 +sar_tas_debug 1 +sar_tas_playback_rate 100 +hud_quickinfo 0 +sar_quickhud_mode 1 +sar_quickhud_size 4
```
Ignore `-condebug` if your disk is really slow. Replace `rl_challenge_1` with whatever map name you'd use with `map <x>` command in the game console


## Training on a new chamber

* Implement the reward function in [testchamber.py](testchamber.py) (both `__init__` and `reset` methods must be modified accordingly)
* Open Portal 2 with the command line options as specified. Make sure SAR is loaded correctly. You can verify this by typing `sar_about` in the developer console 
* Modify your model/hyperparameters in [train.py](train.py). Run the modified file
* Profit !

Please report to me any issues on this repository

## Trained gent

Top left corner is what the agent sees

https://user-images.githubusercontent.com/22210756/167170153-d46a0d74-e003-4382-b1eb-ecb45188d862.mov

## Extracting data from demo files for supervised training

* Convert your demo to TAS using https://github.com/mlugg/dem2tas
* Add `sar_tas_pause` at the end of each line of the generated `.p2tas` file
* Open Portal 2 with the command line options as before
* Pass a dummy action (all zeros) and simply record the observations coming through
