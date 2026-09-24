## Permissions in Linux

```bash
darina@MacBook-Pro ~ % touch file.txt
darina@MacBook-Pro ~ % ls -la file.txt
-rw-r--r--  1 darina  staff  0 Sep 24 12:48 file.txt
echo "information file txt" > file.txt
# giving full permissions only to owner(read, write, execute)
darina@MacBook-Pro ~ % chmod 700 file.txt
darina@MacBook-Pro ~ % ls -la file.txt
-rwx------  1 darina  staff  21 Sep 24 12:50 file.txt
darina@MacBook-Pro ~ % 
# full permissions only to owner^ for groups and others only to read
darina@MacBook-Pro ~ % chmod 744 file.txt
darina@MacBook-Pro ~ % ls -la file.txt
-rwxr--r--  1 darina  staff  21 Sep 24 12:50 file.txt
# also you can give owner all permissions, for groups to read and execute and for others only execute.
darina@MacBook-Pro ~ % chmod 751 file.txt
darina@MacBook-Pro ~ % ls -la file.txt
-rwxr-x--x  1 darina  staff  21 Sep 24 12:50 file.txt

# give back default permissions
darina@MacBook-Pro ~ % chmod 644 file.txt
darina@MacBook-Pro ~ % ls -la file.txt   
-rw-r--r--  1 darina  staff  21 Sep 24 12:50 file.txt

```
### Task1

```bash
darina@MacBook-Pro ~ % touch myfile.txt
darina@MacBook-Pro ~ % echo "smth important" > myfile.txt
darina@MacBook-Pro ~ % ls -la myfile.txt
-rw-r--r--  1 darina  staff  15 Sep 24 13:08 myfile.txt
darina@MacBook-Pro ~ % sudo chown user2 myfile.txt
Password:
darina@MacBook-Pro ~ % ls -la myfile.txt
-rw-r--r--  1 user2  staff  15 Sep 24 13:08 myfile.txt
darina@MacBook-Pro ~ % echo "also smth important" >> myfile.txt
zsh: permission denied: myfile.txt #we can't write
darina@MacBook-Pro ~ % cat myfile.txt #but we can       
smth important #read
darina@MacBook-Pro ~ % sudo chown darina myfile.txt
darina@MacBook-Pro ~ % ls -la myfile.txt
-rw-r--r--  1 darina  staff  15 Sep 24 13:08 myfile.txt
darina@MacBook-Pro ~ % echo "new data important" >> myfile.txt
darina@MacBook-Pro ~ % sudo dscl . -create /Groups/mygroup
darina@MacBook-Pro ~ % sudo dscl . -create /Groups/mygroup gid 800
darina@MacBook-Pro ~ % sudo chown :mygroup myfile.txt
darina@MacBook-Pro ~ % ls -la myfile.txt
-rw-r--r--  1 darina  mygroup  34 Sep 24 13:12 myfile.txt
darina@MacBook-Pro ~ % chmod 660 myfile.txt
darina@MacBook-Pro ~ % sudo dscl . -append /Groups/mygroup GroupMembership user2 
darina@MacBook-Pro ~ % ls -la myfile.txt
-rw-rw----  1 darina  mygroup  34 Sep 24 13:12 myfile.txt
darina@MacBook-Pro ~ % id user2 #adding user2 to group2
uid=502(user2) gid=20(staff) groups=20(staff),700(developers),702(admins),12(everyone),61(localaccounts),800(mygroup),701(com.apple.sharepoint.group.1),100(_lpoperator)
darina@MacBook-Pro ~ % #now user2 can write
#but if we try to user another user 
darina@MacBook-Pro ~ % sudo dscl . -create /Users/alice
darina@MacBook-Pro ~ % sudo dscl . -create /Users/alice uid 505
darina@MacBook-Pro ~ % sudo dscl . -create /Users/alice gid 20
darina@MacBook-Pro ~ % sudo mkdir -p /Users/alice
darina@MacBook-Pro ~ % sudo chown 505:staff /Users/alice
darina@MacBook-Pro ~ % ls -la /Users/alice
total 0
drwxr-xr-x  2 alice  staff   64 Sep 24 13:25 .
drwxr-xr-x  9 root   admin  288 Sep 24 13:25 ..
darina@MacBook-Pro ~ % sudo -u alice sh -c 'echo "test" >> myfile.txt'
sh: myfile.txt: Permission denied #denied
```