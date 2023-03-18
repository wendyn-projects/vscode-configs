# Requiered
 * `g++`
 * `gdb`
 * `nvcc`
 * `opencv`
# Common Problems
## Terminal prints: `-bash: nvcc: command not found`
You might not have `nvcc` in your search path. For that you can add this line to `~/.bashrc`:
```bash
export PATH=$PATH:/usr/local/cuda/bin
```
_Because of that  `vscode` needs to run `bash` in interactive mode which is **already** configured in `./.vscode/settings.json`._

## `vscode` doesn't see `opencv`'s include headers
If your `vscode` doesn't see `opencv`'s include headers, you can find them with this command:
```bash
pkg-config --cflags opencv
```
It will print include args for your compiler in this format:
```
-I<path1> -I<path2> -I<path3>...
```
Just add all the paths to `configurations[0].includePath` inside of `./.vscode/c_cpp_properties.json`.