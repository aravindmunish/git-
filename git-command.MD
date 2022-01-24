# GIT - Version control system - Time Travel
- Git is a version control system, a tool to manage your source code history. (Local Repo) 
- GitHub is a hosting service for Git repositories. (Remote Repo)

So they are not the same thing:

- Git is the tool (Local Repo) 
- GitHub is the service for projects that use Git Repository. (Remote Repo) 
- Where the world builds software.
- Build, ship, and maintain their software.

** Working Directory -> Staging area -> Local Repo -> Remote Repo **
```
RightClick on mouse - select > git bash here
git --version
git update-git-for-windows
mkdir foldername
cd foldername
cd ..
rmdir foldername 
```
## create a new repository on the command line
```
<directory> git init (Create local Repository)
git >> README.md (or) echo >> README.md
git add README.md (or) git add *.css (or) git add .
git commit -m "first commit" (-m -> message)
```
## connect github on the command line
```
git config --global user.email "vasanthedu@gmail.com"
git config --global user.name "vasanthedu"
```
git remote add origin https://github.com/vdevgit/git.git
```
git branch -M main
git push -u origin main (-u -> upstream)

git push origin --delete main{the_remote_branch}
git push origin --delete demo {the_remote_branch}

touch fileName.txt / rm -rf fileName.txt 
git status
git add . / git add fileName.txt / git add *.txt
vi one.txt
	Type any text now @fileName.txt & Esc (Save File)
	:wq
git diff (or) git diff <filename.txt>
git commit one.txt -m  "<message>"
git log
git config user.name 'vasanth kumar'
git config user.email 'vasanthedu@gmail.com'
clear
git commit -a -m "some text deleted" (--amend)
git log (or) git log --oneline (or) git log --pretty=format:%s (%s for the subject; %b for the body; %B for both )
git log --all --oneline
cat one.txt (view/check content written in file)

touch .gitignore (demo/ two.txt)

git branch -a
git branch demo (or) git checkout -b demo
git branch
git checkout demo (navigate to demo folder)
git checkout master
git branch -d demo (delete branch)
git checkout . (if anything wrong in file -> go to latest committed version)
git log
git checkout <commitID>
git checkout master
cat <filename.txt> (view/check content written in file)

git reset --hard <commitID> (remove all above commit)
git checkout master
git log --all --oneline or git log --oneline --all --graph
```
## merge branch
```
git checkout master (go to master)
git merge demo (branch) (Responsible to check any code conflict)

git rm --cached <file> - To unstage
git rm -r * (Remove all files)
git clone https://github.com/vdevgit/GIT-Training.git (repo)
git push -u origin main

git pull origin master
```
## Other command
```
git remote add <name> <url>
git fetch <remote> <branch>
git revert <commit>
git reset <file>

git clean -n (dry run)
git clean -f (force clean untracked files)
git clean -d (remove untracked directories)
git clean -f -x (remove ignored files - .gitignore)
```

## Colloborate with developer in common repo -  dev1 - home - dev2
```
git push ~/desktop/git/home master (error)
mkdir home
cd home
git --bare init (Only push & pull - git status wont work)

cd ../dev1/
git push ~/desktop/git/home master (success)
cd ../home
git log
git ../dev2
git pull ~/desktop/git/home master (error)
git init
git pull ~/desktop/git/home master (success)
---------
Working
---------
git clone https://github.com/vdevgit/git.git
cd git
git status
git add .
git commit -m "first commit"
git fetch origin main
git pull origin main
git push -u origin main
```
-----------------------------

## bareRepo

1.  mkdir bareRepo (Making bareRepo directory)
2.  cd bareRepo/ (Enter into bareRepo folder)
3.  mkdir dev1 (Making dev1 directory)
4.  git init (Making git directory)
5.  mkdir dev2 (Making dev2 directory)
6.  git init (Making git directory)
7.  mkdir home (Making home(bare) directory)
8.  git --bare init (Making bare git directory)
9.  cd dev1 (Enter into dev1 directory)
10. vi index.html (open text editor and create html file)
11. git add . (move file to staging area)
12. git commit -m "html file added" (move file to local repo)
13. git push ~/Desktop/bareRepo/home master (success)
14. cd ../dev2 (Enter into dev2 directory)
15. (before creating any file you can pull from bare repo)
     git pull ~/Desktop/bareRepo/home master (success)
16. vi style.css (open text editor and create css file)
17. git add . (move file to staging area)
18. git commit -m "css file added" (move file to local repo)
19. git push ~/Desktop/bareRepo/home master (success)