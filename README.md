Katya@ubuntu:~$ export GITHUB_USERNAME=Ekaterina06-choi
Katya@ubuntu:~$ export GITMAIL=ekaterina.tsoy.2006@gmail.com
Katya@ubuntu:~$ export GITHUB_TOKEN=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
Katya@ubuntu:~$ alias=nano
Katya@ubuntu:~$ cd ${GITHUB_USERNAME}/workspace
Katya@ubuntu:~/Ekaterina06-choi/workspace$ source scripts/activate
Katya@ubuntu:~/Ekaterina06-choi/workspace$ mkdir ~/.config
mkdir: cannot create directory ‘/home/Katya/.config’: File exists
Katya@ubuntu:~/Ekaterina06-choi/workspace$ mkdir -p ~/.config
Katya@ubuntu:~/Ekaterina06-choi/workspace$ cat > ~/.config/hub <<EOF
> github.com:
- user: ${GITHUB_USERNAME}
  oauth_token: ${GITHUB_TOKEN}
  protocol: https
EOF
Katya@ubuntu:~/Ekaterina06-choi/workspace$ gir config --global hub.protokol https
Command 'gir' not found, but can be installed with:
sudo apt install gir-rust-code-generator
Katya@ubuntu:~/Ekaterina06-choi/workspace$ git config --global hub.protokol https
Katya@ubuntu:~/Ekaterina06-choi/workspace$ mkdir projects/lab02 && cd projects/lab02
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint: 	git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint: 	git branch -m <name>
Initialized empty Git repository in /home/Katya/Ekaterina06-choi/workspace/projects/lab02/.git/
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git config --global init.defaultBranch main
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git config --global user.name ${GITHUB_USERNAME}
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git config --global user.email ${GITHUB_EMAIL}
ekaterina.tsoy.2006@gmail.com
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git config -e --global
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab02.git
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git pull origin main
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 1.45 KiB | 371.00 KiB/s, done.
From https://github.com/Ekaterina06-choi/lab02
 * branch            main       -> FETCH_HEAD
 * [new branch]      main       -> origin/main
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ touch README.md
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	README.md

nothing added to commit but untracked files present (use "git add" to track)
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git add README.md
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git commit -m"added README.md"
[master 9e8e3b1] added README.md
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git push origin main
error: src refspec main does not match any
error: failed to push some refs to 'https://github.com/Ekaterina06-choi/lab02.git'
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git branch
* master
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git push origin master
Username for 'https://github.com': Ekaterina06-choi
Password for 'https://Ekaterina06-choi@github.com': 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 291 bytes | 291.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote: 
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/Ekaterina06-choi/lab02/pull/new/master
remote: 
To https://github.com/Ekaterina06-choi/lab02.git
 * [new branch]      master -> master
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git pull origin master
From https://github.com/Ekaterina06-choi/lab02
 * branch            master     -> FETCH_HEAD
Already up to date.
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git log
commit 9e8e3b165ff7040c4cb8e1763887d5b78da93a0d (HEAD -> master, origin/master)
Author: Ekaterina06-choi <ekaterina.tsoy.2006@gmail.com>
Date:   Sun Mar 9 11:54:32 2025 +0000

    added README.md

commit 765277af0cecaebc9de33a2d706c0e832ac94022 (origin/main)
Author: Ekaterina06-choi <ekaterina.tsoy.2006@gmail.com>
Date:   Sun Mar 9 14:34:53 2025 +0300

    Initial commit
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ mkdir sources
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ mkdir include
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ mkdir examples
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ cat > sources/print.cpp <<EOF
> #include <print.hpp>

void print(const std::string& text, std::ostream& out)
{
  out << text;
}

void print(const std::string& text, std::ofstream& out)
{
  out << text;
}
EOF
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ cat > examples/example1.cpp << EOF
> #include <print.hpp>

int main(int argc, char** argv)
{
  print("hello");
}
EOF
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ cat > examples/example2.cpp << EOF
> #include <print.hpp>

#include <fstream>

int main(int argc, char** argv)
{
  std::ofstream file("log.txt");
  print(std::string("hello"), file);
}
EOF
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ edit README.md
Command 'edit' not found, but can be installed with:
sudo apt install mailcap
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ sudo apt install mailcap
[sudo] password for Katya: 
Sorry, try again.
[sudo] password for Katya: 
Installing:                     
  mailcap

Installing dependencies:
  bzip2

Suggested packages:
  bzip2-doc

Summary:
  Upgrading: 0, Installing: 2, Removing: 0, Not Upgrading: 144
  Download size: 58.7 kB
  Space needed: 204 kB / 91.9 GB available

Continue? [Y/n] 
Get:1 http://ru.archive.ubuntu.com/ubuntu oracular/main amd64 bzip2 amd64 1.0.8-6 [34.6 kB]
Get:2 http://ru.archive.ubuntu.com/ubuntu oracular/main amd64 mailcap all 3.72ubuntu1 [24.1 kB]
Fetched 58.7 kB in 0s (449 kB/s)    
Selecting previously unselected package bzip2.
(Reading database ... 154404 files and directories currently installed.)
Preparing to unpack .../bzip2_1.0.8-6_amd64.deb ...
Unpacking bzip2 (1.0.8-6) ...
Selecting previously unselected package mailcap.
Preparing to unpack .../mailcap_3.72ubuntu1_all.deb ...
Unpacking mailcap (3.72ubuntu1) ...
Setting up bzip2 (1.0.8-6) ...
Setting up mailcap (3.72ubuntu1) ...
Processing triggers for man-db (2.12.1-3) ...
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ edit README.md
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	examples/
	sources/

nothing added to commit but untracked files present (use "git add" to track)
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git add .
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git commit -m"added sources"
[master 2b104b9] added sources
 3 files changed, 26 insertions(+)
 create mode 100644 examples/example1.cpp
 create mode 100644 examples/example2.cpp
 create mode 100644 sources/print.cpp
Katya@ubuntu:~/Ekaterina06-choi/workspace/projects/lab02$ git push origin master
Username for 'https://github.com': Ekaterina06-choi
Password for 'https://Ekaterina06-choi@github.com': 
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 8 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (7/7), 764 bytes | 764.00 KiB/s, done.
Total 7 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/Ekaterina06-choi/lab02.git
   9e8e3b1..2b104b9  master -> master
Katya@ubuntu:~/Ekaterina06-choi/workspace
