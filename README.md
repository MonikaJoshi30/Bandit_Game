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


