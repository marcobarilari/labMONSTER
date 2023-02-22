## Using `screen` to run commands/script on the back ground

`screen` allows, banally, to run a command and then close the remote connection while keeping the monster working for you.

 - create a screen session

 ```bash
 screen -S name-of-the-screen
 ```

- exit a screen session with the keyboard combination `ctrl + a + d`

- you can create multiple screen session, to list the working screen session

 ```bash
 screen -ls
 ```

- enter a specific screen session

 ```bash
 screen -r name-of-the-screen
 ```

- terminate a screen session while in it
 ```bash
 exit
 ```

## Exchange files from and to remote with `scp`

To run it into a terminal not logged into the monster.

- move around a directory recursively (in the example, from the labMonster to local computer)

```bash
scp -r user@machine.ip.numbers:/path/to/remote/source /path/to/local/destination
```
