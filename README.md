# Bandit_Game

Bandit game is a basic wargame which teaches begineers how to use linux command on real scenarios outside of a lab environment. It will teach the basics needed to be able to play other wargames. 

This repository is my documentation of how I did my bandit challenges. You can also think of this as walkthrough or what I did when solving things.
I made a ton of mistakes and was learning from them, so you also need to make mistakes to learn  from them and improve yourself.

So let's get started...

### LEVEL 0
This game start from level 0 , where you need to learn how to connect to the network of OverTheWire to start playing other lvels. This level consist of connecting with ssh to the server.

"The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. "

So here's how to do it 

<img width="1642" height="972" alt="Bandit0" src="https://github.com/user-attachments/assets/175f9cd6-a8bc-4393-9dd0-c95c267246f2" />

You need login ID and password which are same for this level and then look through which files are there to know what to do next.
There should be a file called readme and when we access it we will get the password for the next level.


### LEVEL 1
After getting the password from the previous level when we access this level and list all the files we will see a dashed(-) file. And when using cat command like this 'cat -', it will give error.
So we need to use absolute path, like this 'cat ./-'

<img width="1434" height="705" alt="Bandit1" src="https://github.com/user-attachments/assets/3d7a449e-772c-46b4-b0d8-706ce9b7b26d" />



### LEVEL 2
The challenge states that :-
"The password for the next level is stored in a file called --spaces in this filename-- located in the home directory"

So after entering the level 2 for this game we will get a file named this '--spaces in this filename--', when listing all the files and directories.
Just like last time we will use the absolute path for the file but with quotes, like cat ./"--spaces in this filename--", this here will tell shell to take the things inside quotes as a single entity.

Linux shells use spaces as delimiters (separators) between command names and their arguments, so quotes are required to tell the shell to treat a filename with a space as a single unit.

Well i got to know about this a little later until then I was trying to only use absolute path :)
<img width="1279" height="709" alt="Bandit_lvl2" src="https://github.com/user-attachments/assets/9dd03e9c-e08b-440f-9159-f6bd2ca4e6f8" />


### LEVEL 3
Challenge :-
"The password for the next level is stored in a hidden file in the inhere directory."

After listing out all the files and directories using ls we will get a directory call 'inhere', which to be honest will be empty. And as the challenge said 'password for the next level is stored in  a hidden file', so we will need to list out all the hidden files using -a option.

So using command like :-

ls -la

will show us all the hidden files and directories inside the inhere directory.

Inside the inhere directory there is a file called '...Hiding-From-You', which you can access using cat command like this :-

cat ./...Hiding-From-You



<img width="1435" height="720" alt="Bandit_Lvl3" src="https://github.com/user-attachments/assets/fabf8db3-34a6-437b-949d-2fdd2f9c7757" />

