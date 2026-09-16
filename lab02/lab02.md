## Comprehending UNIX terminal commands
_The following UNIX commands that we need to know:_  
**date** - shows date and time,  
**echo** - displays text on the screen,  
**cp** - copies files,  
**ls** - displays all files in,  
**mkdir** - creates a folder,  
**whoami** - displays the current user,  
**rm** - deletes files,  
**mv** - moves files,  
**top** - displays processes(memory, cpu),  
**dh** - displays disk space.  

## 1st project
###### display files in a folder

`mkdir test_folder`    
`touch test_folder/file1.txt`    
`touch test_folder/file2.txt`    
`touch test_folder/file3.txt`    
`darina@MacBook-Pro desktop % sudo nano count_files.sh`  
```bash
#!/bin/bash
folder=$1

echo "files in folder '$folder':"

ls "$folder"
```
`darina@MacBook-Pro desktop % sudo chmod +x count_files.sh`  
`darina@MacBook-Pro desktop % ./greeting.sh test_folder`  
`files in folder 'test_folder':`  
`file1.txt	file2.txt	file3.txt`

## 2nd project
###### display file info

`darina@MacBook-Pro desktop % sudo nano file_info.sh`
```bash
#!/bin/bash
file=$1

echo "File info: $file"
echo ""
ls -lh "$file"
```
`darina@MacBook-Pro desktop % sudo chmod +x file_info.sh`  
`darina@MacBook-Pro desktop % echo "Hello World" > size_test.txt`  
`darina@MacBook-Pro desktop % ./file_info.sh size_test.txt`      
`File info: size_test.txt`  

`-rw-r--r--  1 darina  staff    12B Sep 16 13:14 size_test.txt`

## 3rd project
###### rename file

`darina@MacBook-Pro desktop % sudo nano rename_file.sh`
```bash
#!/bin/bash
old_name=$1
new_name=$2
mv "$old_name" "$new_name"
echo "File renamed."
echo "before: $old_name"
echo "after: $new_name"
```
`darina@MacBook-Pro desktop % echo "Test" > old_file.txt`  
`darina@MacBook-Pro desktop % sudo chmod +x rename_file.sh`  
`darina@MacBook-Pro desktop % ./rename_file.sh old_file.txt new_file.txt`  
`File renamed.`  
`before: old_file.txt`  
`after: new_file.txt`  

## 4th project
###### show how much time is left
elements that i used there too:  
**then** - if the condition is true, execute the following code  
**-lt** - "less than" comparison operator  
creating file: `darina@MacBook-Pro desktop % sudo nano time_left.sh  `
```bash
#!/bin/bash
current_time=$(date "+%H:%M") #get current time
echo "current time: $current_time"

work_end_hour=17
work_end_minute=0

current_hour=$(date "+%H")
current_minute=$(date "+%M")

#calculate difference
remaining_hours=$((work_end_hour - current_hour))
remaining_minutes=$((work_end_minute - current_minute))

# if minutes are negative, subtract 1 from hours
if [ $remaining_minutes -lt 0 ]; then
    remaining_hours=$((remaining_hours - 1))
    remaining_minutes=$((60 + remaining_minutes))
fi #end of if statement

echo "Work day ends after $remaining_hours hours and $remaining_minutes minutes"
```
`darina@MacBook-Pro desktop % sudo chmod +x time_left.sh`
![](lab02pic1.png)