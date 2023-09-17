## The group projects at ALU

                                                            GCS -2 Problems
Write a shell script that will print the strings “one”,” two”,” three”,” four”, and “five” on the screen with each appearing on a separate line. Also, create a text file with each of these on a separate line and the file name starts with today's date “yyyy-mm-dd-file.txt”. Note Don’t add today’s date manually.
Answer 
#!/bin/bash
### yyyy-mm-dd-file.txt ###
date  +’%y-%m-%d’
echo  -e “one\ntwo\nthree\nfour\nfive\n”
Write a script that generates two random numbers, and print each of these numbers and their square roots. Then finally, print the sum of their square roots on the screen.  The expected output is as below
The first random number generated is 20243
The square root is 142
The second random number generated is 9759
The square root is 98
The sum of their square roots is 240

Answer 
#!/bin/bash
a=$RANDOM
b=$RANDOM
square_roota=$(echo “$RANDOM” | awk ‘{print sqrt($1)}’)
square_rootb=$(echo “$RANDOM” | awk ‘{print sqrt($1)}’)
total=’echo $square_roota + $square_rootb | bc’
echo “The first random number generated is $a”
echo “The square root is $square_roota”
echo “The second random number generated is $b”
echo “The square root is $square_rootb”
echo “The sum of their square roots is $total”


Write a shell script that asks the user to type a phrase, then tells the user the number of words in the phrase and the number of white spaces. The expected output;
The number of words is 4
The number of white spaces is 3  

Answer 
            #!/bin/bash
read -p “write any phrase” phrase
word=$(echo -n “$phrase” | wc -w)
space=$(expr length “$phrase” - length ‘echo ”$phrase” | sed “s/ //g”’)
echo “The number of words is $word”
echo “The number of white spaces is $space”

a) Write a shell script that asks the user for two numbers and outputs their products. The expected output should be a statement as such 
The product of 3 and 3 is 9

Answer 
#!/bin/bash
read -p “enter the first number” a
read -p “enter the second number” b
ans=$((a * b))
echo “The product of $a and $b is $ans”

b)Suppose you want to create 4 folders. Create a text file with at least 4 words(folder name on each line). Write a shell script that reads each line of the text file. Then creates a corresponding folder for each folder name.
Answer

A folder is Task4b.txt that contains four words
#!/bin/bash
 while read -r line  #a shell script for reading the each line of Task4b.txt

do #a shell script to create a corresponding folder for each folder name
mkdir $line
done>Task4b.txt

Write a shell script that takes a path, and confirms if it is a directory or not. If it is a directory list all files in that directory, if not ask the user to give the file path of a directory.  Expected output: List of files in the directory path that was provided

           Answer
#a shell script that takes a path, and confirms if it is a directory or not#
#!/bin/bash
           [ -d "/path/to/dir" ] && echo "Directory /path/to/dir exists."
 
## OR ##
[ ! -d "/path/to/dir" ] && echo "Directory /path/to/dir DOES NOT exist."
#the script that lists all files in the directory#

# !/bin/bash
echo "enter the name of directory"
read dir
if[ -d $dir]
then
echo "list of files in the directory"
ls –l $dir|egrep ‘^d’
#the script that asks the user to give the file path of a directory #
FilePath$=InputBox$("Enter file path”)
Suppose that you want to write the same message to many people, except that you want each message personalized with the recipients’ names. This can be achieved using a shell script. 
HINT:
Create a text file with your group member’s first name on each line.
Then have another text file with the message template below.
Happy New Year Recipeints_Name!
May the coming year be full of grand adventures and opportunities.
Finally, write a script that makes use of the sed command to produce a personalized message for each group member in a text file.

Answer
#memebers of the negpod 6
echo  -e “Telesphore\nJoselyne\nIsaiah\nAdoris\nPacifique\nDerrick\nIsrael\nPascal”
            #specialized message.
while read -r line
do
echo "Happy New Year $line !
May the coming year be full of grand adventures and opportunities." >> $line.txt
done < members.txt



Final report instructions: 
Attendance and Group Member's Contribution

Group Member
Attended
Contribution
Adoris Beni Ngoga
Yes 
 the team secretary 
Isaiah Essein 
Yes 
Worked on the project nov6
Joselyne Nyampinga
Yes 
Worked on the project no5&6
Pacifique SHEMA BASHYITSI
Yes
Worked on the project no1&2
Telesphore Uwabera
Yes
coordinated the PLD
Derrick Mwanzia
Yes
Worked on  the project no 3
Chukwuma Pascal Onuoha
yes
Worked on the project no 4
Israel Smart
Yes
Worked on the project 3&4


-We spent two days on the tasks of GCS-2
- The link to GitHub repo is https://github.com/Telesphore-Uwabera/Group6_gcs-2
