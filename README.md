# UIAccess UAC bypass
In this example, we start a host process (msra.exe) that we steal the UIAccess token from. We downgrade the token IL from Medium+ to Medium so we can communicate with the process with keyboard events. We use the token to spawn a new process (uihack.exe) with the UIAccess flag to send keyboard events to msconfig process. Upon success, a elevated console window should appear.

Not designed to be stealthy, but it's for sure possible! This is a demo in Python, just to display how it works.

You need to build the uihack python file to an executable, make sure it stays in *dist* folder. Once you created the uihack executable, you can launch uiap.py from a non-elevated command prompt.

## Build with py2exe:
In order for a successful build, install the py2exe (http://www.py2exe.org) module and use the provided build.py script to compile all the scripts in to a portable executable. This only seems to work on Python 2, not on Python 3.

```python build.py uihack.py```

```python build.py uiap.py```

#### Creds to:
 * https://tyranidslair.blogspot.com/2019/02/accessing-access-tokens-for-uiaccess.html
 
 #### More UAC bypasses:
  * https://github.com/rootm0s/WinPwnage
  * https://github.com/hfiref0x/UACME
