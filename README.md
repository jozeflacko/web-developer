Linux Basics

Why linux is important for developers!
it is free operating system
it is flexible, you have many distributions you can choose from and you can find exactly the variant  you need for running your program. There are for example linux system even without graphical interface which are more efficient for running services
examples of linux systems: ubuntu, lubuntu, redHat, centos, fedora ….
because it has a very usable text user interface: terminal
Beauty of linux terminal is that when you will learn it, you will know how to manipulate the whole computer from 1 single window and you will be able to automatically start or stop various programs and execute different tasks. 
You would not believe but with terminal your work will be much more effective.


Terminal
The Linux command line is a text interface to your computer. Also referred to as the shell, terminal, console. In the terminal you can find directories, folders, create, rename and delete them, you can write documents or even send email. 
Terminal gives you a TEXT USER INTERFACE
We also know graphical user interfaces... For example Windows is a graphical user interface because you have nice icons there. 
Another example of a text user interface would be command line cmd in windows.
Terminals are preinstalled on linux machines, that means you do not have to download anything and they are on every linux computer.
Sometimes you will hear about “bash shell” -> this is the program which is running inside of the terminal.

Now let's learn the basics we need: 

Linux special characters:
.   → means this current directory
..  → means parent directory
/   → slash itself represents root directory but it is also a sign of a subdirectory
In windows we use backslashes!
linux has only one root!, root for windows is C:/ or D:/ … depending on which disk you are on
./  → means the same as .
../ → same as ..
sudo → command which allows you run programs as a superuser
		


Most popular Linux (shell) commands: 
man
man is a command to show documentation for terminal commands!
when you open man documentation you will see at the bottom left side colon “ : “.  That means you opened a terminal man program. To quit the program press on keyboard character  “  q  ”
try calling these command in terminal:
man ls
and find what means -l, -a, -h
man rm
and find what means -r, -f

Difference between file1.txt, file2  .file3   .file4.txt  file.abc
everything what begins with dot is a hidden file
file extensions (.txt) in linux are meaningless. They are taken as part of the file name

root 
it is the beginning of the file system
window example would be C:// and D://
linux has only one beginning of file system 
/ 
is a root!
pwd
will show you current position
ls vs.  ls-lah vs.  ls -l -a -h
ls show directory content
ls -lah show directory content as list, with additional info and also hidden files
ls -lah is a shortcut of ls -l -a -h
ls -hal is the same as ls -lah and ls -a -l -h -> order is not important!
cd  
it is a command changing directory. 
Because it is missing 1 parameter it does nothing! 
cd .   
change to current directory -> in other words you change directory to same directory you are currently in → in other words you stay on exactly same position where you are
cd ..  
go parent up.  
cd /   
go root
cd  /dir1/dir2   
go to /dir1/dir2   
cd ../../dir3/dir4  
got 2 parents up and then to dir3 and then to dir4  
cd ./dir3   
go in current directory to subdirectory dir3
cd ./file.txt   
in case that file.txt is a file it will do nothing! it is not possible to change to a new directory because  file.txt is a file!
in case file.txt is a directory (because we know that file extension .txt means nothing) you would navigate to subdirectory file.txt
cd “./my file”
use quotes in case when name of a file or a directory has blank spaces
this is very rare in linux systems

mv ./file1 ./dir3/file2
will ….
rm ./file  
remove item (file or empty directory) with name file in the current directory 
rm ./directory1
remove item (file or empty directory) with name directory1 in the current directory
rm -rf  /dir1/dir2
remove directory recursively → will first delete all content in dir2 and then delete directory dir2
-rf (or -r -f) are 2 parameters of a rm command
rmdir   ../../dir4
remove empty directory dir4 which is in a directory 2 parents from current directory
touch file1  
create text file with name file1 in current directory
touch ./file1
create text file with name file1 in current directory
touch “my file”   
create a text file with name “my file” in the current directory.
We used quotes because we created a file with blank space!
mkdir directory1  
create directory in different directory 
mkdir “my directory”
create directory with blank space in the name
cat ./file1.txt
print context of a text file into terminal
nano ./file2
nano is a text editor
it will open text editor where you can edit text file file2
echo
will print message into the terminal
example: echo “Hello World” → will print Hello World
this is used when you write shell scripts!
find
search for files and folders in your computer
examples:
find . -name '*jpg'
find in current directory everything (folders and files) which ends on jpg
find . \( -iname '*jpeg' -o -iname '*jpg' \) -type f
find in the current directory every file which ends either on jpeg or jpg.
find . -iname '*jpg' -type f -mtime -7
find in current directory all files ending on jpg and where changed in last 7 days
find /var/log -size +1G
find in directory /var/log everything what is bigger than 1GB
grep
search for words in documents or shell outputs
examples:
grep 'word' <filename>
find string ‘word’ in a file called filename
fgrep 'word-to-search' file.txt
...
grep 'word' <file1> <file2> <file3>
find string ‘word’ in listed files
grep 'string1 string2'  <filename>
find string ‘word’ in a file
cat <otherfile> | grep 'something'
Here we use piping!!!. Piping it is a technique for executing multiple commands after each other where results of the previous command can be passed to the next command
take text of a file <otherfile> (do not print it into terminale, but just pass it to the next command after pipe | symbol) and search inside for a string 'something'
command | grep 'something'
execute command and result pass to grep function!
grep --color 'data' <fileName>
highlight string ‘data’ in text in a file <filename>




Version control

What is the version control system? → It is a system where you can store documents, code, files (in general “source”) with preserving changes. In a system like this you can see how a document looks today and how it looked yesterday or 1 year ago. It keeps track what changes on which files were made by which person and you can also comment on your savings. You can even make duplications of the source and merge changes between duplications.

Why do companies need version control?
Because companies and developers need to keep track of changes. Just imagine you come on monday to the work and you see the application stopped working.  You need to find out why. With version control you can look at what was the last change made in the application and who made it and even why the person did the change. 

Examples of version control systems: 
Git https://git-scm.com/ Most popular nowaday!
Svn (Subversion) -> Was popular 5 years ago for last 15 years
Hg (Mercurial) -> Was popular 5 years ago for last 15 years
Facts about VCS?
Source must be accessible for every member of a team.
That means “original” source will never be on a local computer of your colleague, but somewhere where everybody can reach it and can download it
Team members download the original source to their local computers where they make changes and when they are finished, they push them back. It is not possible to make changes without preserving who and when made change and how it looked before change!
Usually a version control system uses multiple branches. Branch is a copy of a source which has a special name. Original source is also a branch named “master”. 
Typically we have branches:
master → for production, contains the most stable code
testing
development → developers make copies of this branch!
feature1
feature2
…
featureN
Versioning of the source is made in patter: XX.YY.ZZ
XX → MAJOR version when you make incompatible API changes
YY → MINOR version when you add functionality in a backwards compatible manner
ZZ → PATCH version when you make backwards compatible bug fixes.

Sometimes you can find -RC at the end of the version number (example: 1.12.23-RC). This is a temporary mark to show that this version should be released soon and currently is going throw testing process

Versions starting with 0 are pre production products which still have not been initially officially released. example: “0.86”

Git
It is a version control system
currently the most popular!

Why is git so popular?
all version control systems are very similar, they can do the same, but with git you can do it a little easier and the commands are very user friendly


Git is a system which must run on a server. What are the most popular services using git?:
Github 
Owned by Microsoft
Most popular for open source projects!
Bitbucket
paid
Gitlab
paid, 
but the code of this service is public!!!! → Very important
Because the code is public most of the companies just took the code and started a private server with this project in their own company

Git commands: (All commands you must call in your project!)
git init
This command will add a git version control to your project!!
This command will add a hidden git directory (.git) to you project where it will store data needed for version control of you project
inside of this directory you will find several items from which 2 are very important:
file: HEAD → contains commit number, This commit number represents position in timeline where you current source code stands. That means your whole source  code is adjusted to look exactly as it looked when the commit was made (Even if this commit was made 3 year ago)
file: config → It contains basic information about the project. Your user name, email, password for communicating with a remote connection 
example:
[core]
        repositoryformatversion = 0
        filemode = false
        bare = false
        logallrefupdates = true
        symlinks = false
        ignorecase = true
[remote "origin"]
        url = https://github.com/dariala/diary.git
        fetch = +refs/heads/*:refs/remotes/origin/*
[user]
        name = dariala
        password = Marhulka11
        email = silaievadaria@gmail.com

git clone ___some_url___
will download git project to your local computer from defined url address
git status
it will tell you what are your local changes compared to your HEAD
it you have untracked files → which you should add or ignore
if you have uncommitted files
git pull
you will fetch all latest changes from the server
git push
you will push all committed changes to the server
git add 
Add files to the staging area 
We put files into stating area when we want to commit them. 
Develop usually group multiple files he/she changed by adding them into staging area and then he/she must only provide 1 commit message and all these changes will be marked as changed done due to commit.
How to use:
git add . → put everything into staging area
git add <file_name> → cherry pick files by name, relative and absolute path

git diff
will show you all differences which were found by git status
It is always comparing changes with the HEAD
git commit
example: git commit -am “Some message”
every commit will remember all changes you did in files stages in the staging area. It will store when the commit was made, who did the commit, it will generate a unique id with which you can always look at how the source looked exactly when the commit was made!
Staging area will be cleared after a commit was made!
git checkout 
git checkout <commit_number> → set head to <commit number>
You will change your source to look exactly as it looked when commit was made!
git checkout <branch_name> → You will change to branch <branch_name>
git checkout -b <branch_name> → create branch with name <branch_name> and the immediately change to this branch
git remote 
git remote
will print all names of your remotes
git remote -v
will print all names of your remotes and also url links set to them
git remote add <your_remote_name> <url>
will add a new remote connection to your git project
You must always provide name and url! Default name is ‘origin’.
Every name must be unique in your project
git remote rm <your remote_name>
remote remote
git branch
A branch represents an independent line of development.
 The git branch command lets you create, list, rename, and delete branches. 
It doesn't let you switch between branches or put a forked history back together again. For this reason, git branch is tightly integrated with the git checkout and git merge commands.
What is: master (or main) branch, trunk(or dev), <feature> branch
These are the most common branch names used in project. -	
master or main → is the main branch where production code usually lays. 
trunk (dev branch) → here is your latest state of the application
<feature> branch is any branch you create temporarily to implement some feature and when the job is done and feature is merged into dev and production branch you can delete this branch
How to switch between branches
→ look git checkout!
git branch -r 
will show you all remote branches
git show


git fetch
will fetch from a remote repository (it will not do any merging if pulled changes to your project!)
remember: git pull is shortcut for git fetch + git merge
 git config
for configuration purposes. Git has 2 configuration sources. 
One is stored in .git directory at the root of your project in file called: config. It is also called local config!
Secondone is global and is stored where git is installed on your computer!
git config -l
git config --global user.name <your_name>
git config --global user.password <your_password>
git config --global user.email <your_email>
git config --system --unset credential.helper
This you only need when you change the user using git on your local computer (for example Jozef was using, and now is Dasenka using!)
How to find other commands?
git <command> --help
git log
will show you a list of all commits which were made in your project!
every line will contain commit_id, date with time and a commit message. 
on the top of the list are newest commits. At the end are the latest commits
git merge
Merging is a common practice for developers using version control systems. Whether branches are created for testing, bug fixes, or other reasons, merging commits changes to another location. To be more specific, merging takes the contents of a source branch and integrates them with a target branch. In this process, only the target branch is changed. The source branch history remains the same.
git reset --hard HEAD
will reset all your changes to the HEAD state!
What is Readme.md
It is a simple document with stylings where you describe what is your project about
What is .gitignore
It is a file containing rules which will tell git which files in the project should never be tracked with git.
Why do we need this file? Usually we ignore automatically generated files, because these files are unnecessary. Everybody who would download the project, he/she can generate those files
What is pull request?
Pull requests let you tell others about changes you've pushed to a branch in a repository on GitHub. Once a pull request is opened, you can discuss and review the potential changes with collaborators and add follow-up commits before your changes are merged into the base branch.



Test your linux and git skills
turn on your computer with installed linux
open terminal
check if you have internet connection by calling command: ping google.com
you should get a response.
terminate pinging with pressing: control+c
now check if git is installed on your computer by calling command: git
if not then google how to install git on your operating system
probably: How to install git on ubuntu (ubuntu is name of the linux operating system that you most likely use)
check your location
you should be in /home/jozef
try to make here an empty folder “Development”
create empty directory at /home/ called “daria”
because you are currently logged as user jozef manipulating new user daria is forbidden for you. You would have to set up privileges for jozef user or….just use command “sudo” as a prefix before your commands! sudo means: “system user do” 
example: sudo mkdir daria
navigate to /home/daria and create folder with name: Development
do not forget to use sudo prefix! once again you are still logged as a jozef in your computer and you are still manipulating daria data. 
open browser and go to side: https://start.spring.io/
generate project
project type: maven 
language: java 
dependencies: spring web. 
group: at.darialacko
name: todos
keep everything else at default
click on button Generate
you should download todos.zip
unzip this project in downloads directory
/home/jozef/Downloads/ 
open terminal navigate to downloads directory
move this directory to folder /home/daria/Development
then go to /development/todos
initialize git in this project
use command: “git init”
put everything into staging area
with “git add .”
commit everything with message “initial commit”
git commit -m “initial commit”
open browser and go to your github account
create there new repository called todos
create there a new branch “master”
set new remote called  “origin” in your local project with url set to github repository 
to check your remote was correctly set you can call:
git remote -> it should print out all remotes you have. In your case it should print text: origin, because this is the only remote you have
git remote -v (-v stands for “verbose”) -> It will print all remotes and their urls!. you should see something like: 
	origin https://…..todos.git (fetch)
	origin https:// ….todos.git (push)

check git status
you should have nothing in staging area and be 1 commit ahead of your HEAD
pull and push
git pull <name_of_your_remote> <name_of_your_branch>
example: when your remote is “origin” and you want to pull from “master” branch -> git pull origin master

git push <name_of_your_remote> <name_of_your_branch>
example: when your remote is “origin” and you want to push to “master” branch -> git push origin master 
go to browser and check that everything was committed
github default branch is called “main”. The default branch is called “master”!!!! That is why set the viewed branch on github to “master”!
in your project create file README.md
write text there: “This is my todos list” and save the file
print the content into the terminal 
call git status
put README.md into staging area and commit it and push it to the remote
go to your github todos repository and check if README.md exist there
edit this README.md directly on github page and commit it there.
DO NOT CALL “git pull” on your local pc
edit README.md also on your local pc, then stage, commit, pull and push
you should get a merge conflict!
resolve merge conflict
push changes
once again open README.md on your local pc and edit this file
call git diff to see what changes have you done against your head
...branching

ENVIRONMENT VARIABLES

INSTALLING JAVA
 - Integrated development environment
What means IDE
What IDEs you know: Eclipse, IntelliJ, VisualStudio...VSCode, Atom



OOP - Object oriented programming

What is OOP (Object oriented programming)
OOP basics
encapsulation
abstraction
inheritance
polymorphism
Alternatives to OOP are:  
functional programming → Javascript!
structured programming
imperative programming





JAVA

Building blocks of java are classes. Every java file has a class inside with the same name as a filename. For example MyClass.java will have inside defined a class MyClass { }.
What is a class? → It is a template for creating objects. Objects are instances of classes. classes can have  fields and methods and a constructor.
Fields will hold values
methods will provide actions
constructor helps to instantiate class



For example You have a class called Baby. To describe baby you can write into class fields which will hold values 
Inside of Baby you can define the name and height of the baby and a date when it was born. For example:


class Baby {
	
}

What is Java
What is Java and why is so popular? 
How to find java documentation
What is JDK, OpenJDK, JRE
Difference between MyClass1.java vs. MyClass.class
What is compilation
How to compile
What is a main class and how it looks
How to run a class
What are packages
what are default java packages
How to import a class
Access modifiers in Java: 
https://www.javatpoint.com/access-modifiers
private, default, protected, public
What is “final”
What are compile time errors and runtime errors
How to throw an error
What is the current version of java
Java 8 features? ---> You will learn in future
Lambda expressions
Method references
Functional interfaces
Stream API
Default methods
Static methods in interface
Java types primitives vs objects!
int
string
boolean
char
enum
What is class and how to make it
How to make inner class
What is interface
What is abstract class
How to extends a class or implement an interface
How many classes you can extends, how many interfaces you can implement
How to iterate over an Array loop with for, while, forEach




Maven Basics

What is maven
Why we use maven
What means mvn
What is pom.xml
Single module vs. multi module project
What are maven phases and how to call them
clean	-- Delete target directory.
validate -- Validate if the project is correct.
compile -- Compile source code, classes stored in target/classes.
test -- Run tests.
package -- Take the compiled code and package it in its distributable format, e.g. JAR, WAR.
verify	-- Run any checks to verify the MVN package is valid and meets quality criteria.
install	-- Install the package into the local repository.
deploy	-- Copies the final MVN package to the remote repository.
Maven repository: https://mvnrepository.com/
mvn clean vs mvn package
Cheat sheet: https://www.jrebel.com/blog/maven-cheat-sheet


Java Spring

What is Spring framework: w3c spring
What is difference between framework and library
Why do we use spring framework
What is spring boot: w3c spring boot
Official page of spring boot: official page spring boot!!!
what are application.properties
what are annotations
How to create HelloWorld spring boot project


