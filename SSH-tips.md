## Using `screen` to run commands/script on the back ground

### basics

`screen` allows, banally, to run a command and then close the remote connection while keeping the monster working for you.

 - create a screen session

 ```bash
 screen -S name-of-the-screen
 ```

- exit a screen session with the keyboard combination 
  
 | `ctrl` + `a` then `d`

- you can create multiple screen session, to list the working screen sessions

 ```bash
 screen -ls
 ```

- log in a specific screen session

 ```bash
 screen -r name-of-the-screen
 ```

- terminate a screen session while in it

 ```bash
 exit
 ```

### pro level

- how to know if you are already in a screen session

```bash
echo $STY
```

- rename screen session 

> `ctrl` + `a` then `A`

- discover more screen options

> `ctrl` + `a` then `?`

## Exchange files from and to remote

- move around a directory recursively (in the example, from the labMonster to local computer)

```bash
scp -r user@machine.ip.numbers:/path/to/remote/source /path/to/local/destination
```

### datalad
