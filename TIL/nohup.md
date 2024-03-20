---
title: "`nohup` and `&`"
author: "Deven Mistry"
date: "2024-03-20"
categories: [linux, bash]
---
Yesterday, I ran into a problem where I wanted to run a shell script in the background on a linux machine. I knew that

```sh
bash foo.sh &
```

would solve the problem for me, however I was working on a remote machine, which meant that closing the `ssh` connection would terminate the execution of the command.

Enter `nohup`. This is a wonderful bash utility which allows you to run your script in the background on a remote machine even when you close the connection.

`nohup` is just short for `no hang up`. You can use this command in multiple ways. There's a wonderful article on DigitalOcean[^1] explaining this command. I'll just list a few of them here.

By default, `nohup` will save the output of the execution in `nohup.out`. You can change that with the redirect output command.

```sh

nohup ./foo.sh
nohup ./foo.sh > output.txt     # write (redirect) output to output.txt
nohup ./foo.sh & > output.txt   # write (redirect) output to output.txt and run the script in the background
```

Here's another good reference from StackOverFlow[^2]

[^1]: [DigitalOcean](https://www.digitalocean.com/community/tutorials/nohup-command-in-linux)
[^2]: [StackOverFlow](https://stackoverflow.com/questions/44222883/run-a-shell-script-and-immediately-background-it-however-keep-the-ability-to-in)
