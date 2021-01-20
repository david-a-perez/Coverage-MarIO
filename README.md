# Coverage MarI/O
This project is an atempt to gather coverage through the use of NEAT. This is based off of Sethbling's MarI/O project. Unlike MarI/O, instead of using the player's coordinates to calculate fitness, this project uses the code coverage of the currect run to calculate fitness. Note that this project is not intended to be fast.

# Setup
1. Build BizHawk emulator from https://github.com/david-a-perez/BizHawk (this fork provides a way to read coverage data from a Lua plugin)
2. In either SMW or SMB, use `File` > `Save State` > `Save Named State` to save a state while inside a level
3. Then, `Emulation` > `Pause` and `File` > `Load State` > `Load Named State` to get the exact point the plugin will reset to
4. Then, `Config` > `Cores` > `BSNES` for SMW (I'm not sure which Core to use for SMB)
5. Optionally, `Config` > `Speed/Skip` > `Skip 0 (never)` and `Config` > `Speed/Skip` > `Speed 400%`
6. `Tools` > `Code-Data Logger` then inside the new window `File` > `New`
7. Ensure that `File` > `Auto-Start` is enabled`
8. Unpause with `Emulation` > `Pause` and after around 1 minute of no input, inside of the Code-Data Logger, `File` > `Save As`
9. Modify the Lua script from this repo to replace `<STATE FILE>` with the file path of your state file and `<CDL FILE>` with the full path of the file you just saved
10. `Tools` > `Lua Console` and in the new window `Script` > `Open Script` and open the script you just modified
11. It should now be training