| what i used on mac  | linux | mac |
|----------|-------|-----|
| сreate user | `sudo adduser user1` | `sudo dscl . -create /Users/user1` |
| delete user | `sudo deluser --remove-home user1` | `sudo dscl . -delete /Users/user1` |
| check user | `cat /etc/passwd` | `dscl . -read /Users/user1` |
| create group | `sudo groupadd developers` | `sudo dscl . -create /Groups/developers` |
| add to group | `sudo usermod -a -G developers user1` | `sudo dscl . -append /Groups/developers GroupMembership user1` |
| check groups | `id user1` | `id user1` |
| log in | `su - user1` | `su - user1` |

```bash
Last login: Wed Sep 23 17:01:04 on console
darina@MacBook-Pro ~ % sudo dscl . -create /Users/user1
Password:
darina@MacBook-Pro ~ % sudo dscl . -create /Users/user1 RealName "User One"
darina@MacBook-Pro ~ % sudo dscl . -create /Users/user1 home /Users/user1
darina@MacBook-Pro ~ % sudo dscl . -create /Users/user1 shell /bin/zsh
darina@MacBook-Pro ~ % sudo dscl . -create /Users/user1 uid 501
<main> attribute status: eDSRecordAlreadyExists
<dscl_cmd> DS Error: -14135 (eDSRecordAlreadyExists)
darina@MacBook-Pro ~ % sudo dscl . -create /Users/user1 uid 502
darina@MacBook-Pro ~ % sudo dscl . -create /Users/user1 gid 20
darina@MacBook-Pro ~ % sudo mkdir -p /Users/user1
darina@MacBook-Pro ~ % sudo chown user1:staff /Users/user1
darina@MacBook-Pro ~ % dscl . -read /Users/user1
dsAttrTypeNative:accountPolicyData:
 <?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>creationTime</key>
	<real>1790226754.93116</real>
</dict>
</plist>

dsAttrTypeNative:record_daemon_version: 9670000
AppleMetaNodeLocation: /Local/Default
GeneratedUID: 0A6F4C5C-0E70-4287-8393-73E1C30F72E5
NFSHomeDirectory: /Users/user1
Password: ********
PrimaryGroupID: 20
RealName:
 User One
RecordName: user1
RecordType: dsRecTypeStandard:Users
UniqueID: 502
UserShell: /bin/zsh
darina@MacBook-Pro ~ % dscl . -list /Users | grep user1
user1
darina@MacBook-Pro ~ % su - user1
Password:
su: Sorry
darina@MacBook-Pro ~ % sudo passwd user1
Changing password for user1.
New password:
Retype new password:

################################### WARNING ###################################
# This tool does not update the login keychain password.                      #
# To update it, run `security set-keychain-password` as the user in question, #
# or as root providing a path to such user's login keychain.                  #
###############################################################################

darina@MacBook-Pro ~ % su - user1       
Password:
user1@MacBook-Pro ~ % whoami
user1
user1@MacBook-Pro ~ % exit

darina@MacBook-Pro ~ % sudo pkill -KILL -u user1
Password:
darina@MacBook-Pro ~ % sudo dscl . -delete /Users/user1
darina@MacBook-Pro ~ % sudo rm -rf /Users/user1
darina@MacBook-Pro ~ % dscl . -list /Users | grep user1
```

### task1

```bash
#create develoveps group
darina@MacBook-Pro ~ % sudo dscl . -create /Groups/developers
darina@MacBook-Pro ~ % sudo dscl . -create /Groups/developers RealName "Developers Group"
darina@MacBook-Pro ~ % sudo dscl . -create /Groups/developers gid 700
#create admins group
darina@MacBook-Pro ~ % sudo dscl . -create /Groups/admins
darina@MacBook-Pro ~ % sudo dscl . -create /Groups/admins gid 701
<main> attribute status: eDSRecordAlreadyExists
<dscl_cmd> DS Error: -14135 (eDSRecordAlreadyExists)
darina@MacBook-Pro ~ % sudo dscl . -create /Groups/admins gid 702
#create user 2
darina@MacBook-Pro ~ % sudo dscl . -create /Users/user2
darina@MacBook-Pro ~ % sudo dscl . -create /Users/user2 RealName "User Two"
darina@MacBook-Pro ~ % sudo dscl . -create /Users/user2 home /Users/user2
darina@MacBook-Pro ~ % sudo dscl . -create /Users/user2 shell /bin/zsh
darina@MacBook-Pro ~ % sudo dscl . -create /Users/user2 uid 502
darina@MacBook-Pro ~ % sudo dscl . -create /Users/user2 gid 20
darina@MacBook-Pro ~ % sudo mkdir -p /Users/user2  #creating a dir
darina@MacBook-Pro ~ % sudo chown user2:staff /Users/user2 #changing the owner
#add user2 in developers
darina@MacBook-Pro ~ % sudo dscl . -append /Groups/developers GroupMembership user2
#add user2 in admins
darina@MacBook-Pro ~ % sudo dscl . -append /Groups/admins GroupMembership user2
#check user2 info ab groups
darina@MacBook-Pro ~ % id user2
uid=502(user2) gid=20(staff) groups=20(staff),700(developers),702(admins),12(everyone),61(localaccounts),701(com.apple.sharepoint.group.1),100(_lpoperator)
#check who in the dev group
darina@MacBook-Pro ~ % dscl . -read /Groups/developers GroupMembership
GroupMembership: user2
#check who in the admins group
darina@MacBook-Pro ~ % dscl . -read /Groups/admins GroupMembership
GroupMembership: user2
```