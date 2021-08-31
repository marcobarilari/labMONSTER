# Using `screen` to run commands/script on the back ground

`screen` allows, banally, to run a command and then close the remote connection while keppeing the monster working for you.

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
