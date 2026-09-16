## Toy shell

```bash
darina@MacBook-Pro ~ % sudo nano /Users/darina/infosec/toy_shell.py 
Password:
darina@MacBook-Pro ~ % python3 toy_shell.py
Toy Shell: List files and folders older than a given date (based on creation time)
Enter a date in the format YYYY-MM-DD or type 'exit' to quit.
toy-shell> 2006-09-03
toy-shell> 2025-09-01
Music (Folder, Created: 2025-08-29 18:10:08)
.zshenv .save (File, Created: 2025-08-29 17:50:08)
.zshenv.save (File, Created: 2025-08-29 17:50:08)
.zprofile.pysave (File, Created: 2025-08-29 17:50:08)
.tl (Folder, Created: 2025-08-29 18:10:06)
***unknown variable aesupportfilepath1*** (Folder, Created: 2025-08-31 16:02:13)
.thumbnails (Folder, Created: 2025-08-29 18:10:06)
.xonshrc (File, Created: 2025-08-29 17:50:08)
.zshrc (File, Created: 2025-08-29 17:50:08)
.vcpkg (Folder, Created: 2025-08-29 18:10:06)
.local (Folder, Created: 2025-08-29 18:10:06)
.zprofile (File, Created: 2025-08-29 17:50:08)
IdeaSnapshots (Folder, Created: 2025-08-29 18:10:06)
.matplotlib (Folder, Created: 2025-08-29 18:10:06)
.conan-clion-plugin (Folder, Created: 2025-08-29 18:10:08)
Creative Cloud Files Personal Account madiyan240783@gmail.com 34F80F705C5C3DF00A495CCD@AdobeID (Folder, Created: 2025-08-29 18:10:06)
.emulator_console_auth_token (File, Created: 2025-08-29 17:49:45)
redshift (Folder, Created: 2025-08-29 18:10:03)
.android (Folder, Created: 2025-08-29 18:10:08)
.cups (Folder, Created: 2025-08-29 18:10:06)
Sites (Folder, Created: 2025-08-29 18:10:08)
Public (Folder, Created: 2025-08-29 18:10:03)
.idlerc (Folder, Created: 2025-08-29 18:10:06)
out3.txt (File, Created: 2025-08-29 18:10:03)
.genarts (Folder, Created: 2025-08-29 18:10:06)
.tcshrc (File, Created: 2025-08-29 17:49:47)
Lockdown (Folder, Created: 2025-08-29 18:10:03)
.conan2 (Folder, Created: 2025-08-29 18:10:08)
.gradle (Folder, Created: 2025-08-29 18:10:06)
.anaconda_backup (Folder, Created: 2025-08-29 18:10:08)
Templates (Folder, Created: 2025-08-29 18:10:03)
IdeaProjects (Folder, Created: 2025-08-29 18:10:06)
.pnpm-state (Folder, Created: 2025-08-29 18:10:06)
.vscode (Folder, Created: 2025-08-29 18:10:06)
.m2 (Folder, Created: 2025-08-29 18:10:06)
.bash_profile (File, Created: 2025-08-29 17:47:52)
AndroidStudioProjects (Folder, Created: 2025-08-29 18:10:06)
.SoulseekQt (Folder, Created: 2025-08-29 18:10:08)
toy-shell> 
exit

darina@MacBook-Pro ~ % sudo mv /Users/darina/infosec/toy_shell.py /usr/local/bin/toy_shell
darina@MacBook-Pro ~ % sudo chmod +x /usr/local/bin/toy_shell
darina@MacBook-Pro ~ % toy_shell
Toy Shell: List files and folders older than a given date (based on creation time)
Enter a date in the format YYYY-MM-DD or type 'exit' to quit.
toy-shell> 
```