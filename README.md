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



### LEVEL 4
The challenge for this level says that "The password for the next level is stored in the only human-readable file in the inhere directory ".
So for a file to be human readble it should contain  plain text, characters, numbers, and punctuation, etc...
And ASCII files has all these, so we only need to find that.
When using 'ls' command we will see that this challenge has 9 different files and it's a tedious task to check each one of them, so we need something which will tell us what are the file format of the given files.
Now that we already know what kind of file we need to find, we will use :-

file ./*

Here,

file : is a standard Linux utility that determines the type of a file by examining its content, not just its name or extension.

./   : explicitly refers to the current working directory.

"*"    : this is a wildcard character that matches any number of characters (including zero) in a filename.

./*  : when combined it tells shell to list out all non-hidden files and directories present in the current directory.




<img width="1421" height="700" alt="Bandit4" src="https://github.com/user-attachments/assets/67b9d2ce-bfc7-4621-bcf6-699fed233d1d" />




### LEVEL 5

This time the challenge had three requirements to find the file which contains the password.
So the challenge is 

"The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

* human-readable

* 1033 bytes in size

* not executable"

So we know the file is somewhere in 'inhere' directory and possess some special property.

To search we can use command like 'find' as it search for files. And for special properties we can use options like :

-type f : to search for files

. : will search from the current working directory

-size 1033c : for files that are exactly 1033 bytes in size where 'c' is for bytes

-not -executable : finds only non executable files

-exec file {} + : execute the file command on all the results returns by find

grep : to only select the necessary file 

<img width="1384" height="703" alt="Bandit5" src="https://github.com/user-attachments/assets/8dba8de2-e9aa-45c0-9acc-8141d5b67739" />




### LEVEL 6
This challenge states that :-

"The password for the next level is stored somewhere on the server and has all of the following properties:

* owned by user bandit7

* owned by group bandit6

* 33 bytes in size"

Just like last time we will use the 'find' command but instead of using '.' we will use '/', which scans the whole server.

And for the properties of the files like the size, who's the user and who's in the group, we can use options like '-type f' to search for files, '-size' for the specific size of the file and options like '-user' and '-group' to set who's the user and who's in the group.

This will set some of the options for the file search and you will get multiple 'Permission denied' error, but that's okay, and you will find one file position for the required file.

Use 'cat' command on that file and you will get the password for nex level.

<img width="1321" height="637" alt="Bandit6Again" src="https://github.com/user-attachments/assets/f01e52cd-55cb-4743-9f6e-6c7d57cc2547" />
<img width="1318" height="692" alt="Bandit6 Again3" src="https://github.com/user-attachments/assets/a6c8f3e5-167e-48af-8ed5-f83466d33248" />
<img width="1376" height="712" alt="Bandit6" src="https://github.com/user-attachments/assets/c25241d6-c6ac-47b1-a88d-7d54e1d83a0a" />




### LEVEL 7
This challenge is quite easy, 
"The password for the next level is stored in the file data.txt next to the word millionth"

So we just need to use pipelining, starting with 'cat' command then redirect it to the 'grep' command.

* 'cat' : displays the entire content of a file

* 'grep' : used to search for specific text patterns (regular expressions) within files or data streams and print the matching lines
  
<img width="1419" height="680" alt="Bandit7" src="https://github.com/user-attachments/assets/abd11a7a-caca-4fbc-bd21-df563fc55018" />


