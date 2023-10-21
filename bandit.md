#### Writeup on https://overthewire.org/wargames
#### LEVEL 0
````
***ssh bandit0@bandit.labs.overthewire.org -p 2220***
              password: bandit0
````
#### LEVEL 0 -> LEVEL 1
````
***cd*** #to open the home directory
***ls -l*** #to see the file
***cat readme*** #to concatinate the readme file
password:NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
````
#### LEVEL 1 -> LEVEL 2
````
***cat ./-*** #concatenates the dashed
password :rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
````

#### LEVEL 2 -> LEVEL 3
````
***cat 'spaces in this filename'*** #treating space characters as string characters when put in single quotes
password:aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
````
#### LEVEL 3 -> LEVEL 4
````
cd inhere
ls -a
cat .hidden
passoword:2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
````
#### LEVEL 4 -> LEVEL 5
````
***cd inhere***
ls -h
cat <-file01
cat <-file02
cat <-file03
cat <-file04
cat <-file05
cat <-file06
cat <-file07

Password: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
````
#### LEVEL 5 ->LEVEL 6
````
cd inhere
-size 1033c
Password: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
````
#### LEVEL 6 -> LEVEL 7
````
ls -l #it was not giving any list of files it meant there were no files in the home directory so i googled how to find a file from all over the server it showed to use / with find
i watched a video about find command and learned about how files can be searched with particular user and group with -user and -group and since i knew the command -size, i put them together to come up with
find / -user bandit7 -group bandit6 -size 33c
i got confused at first with the number of files i got, then i went through them to find "/var/lib/dpkg/info/bandit7.password" which didn't end with permission denied so i concatenated it!
cat /var/lib/dpkg/info/bandit7.password
PASSWORD:z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
````
#### LEVEL 7 -> LEVEL 8
````
cat data.txt #i tried checking if i can do it manually
Then i watched a video on usage of grep tool and used it
grep millionth data.txt
PASSWORD :TESKZC0XvTetK0S9xNwm25STk5iWrBvP
````
#### LEVEL 8 -> LEVEL 9
````
read about uniq command
used uniq -u data.txt
got many answers read the documentation again and found that it only checks the adjacent lines
so i sorted it first then piped it in uniq
sort data.txt | uniq -u
PASSWORD: EN632PlfYiZbn3PhVK3XOGSlNInNE00t
````
#### LEVEL 9 -> LEVEL 10
````
i read the documentation about strings so just put it use
strings data.txt
it workeed i scrolled and the got the the string with many = as mentioned in qustion
then i remembered about ^ in grep command which can make it more efficient
strings data.txt | grep ^===
PASSWORD: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
````
#### LEVEL 10 -> LEVEL 11
````
read about base64 was quiet simple but i didn't understand how the encryption so watched a video on it
base64 -d data.txt
PASSWORD:6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
````
#### LEVEL 11 -> LEVEL 12
````
