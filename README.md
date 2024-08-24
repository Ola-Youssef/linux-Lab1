    Create a user account with the following attribute
    •  username: islam
    •  Fullname/comment: islam yahia
    •  Password: islam
    • ola-youssef@oy-pc:~$ sudo adduser islam   
    • [sudo] password for ola-youssef: 
    • info: Adding user `islam' ...
    • info: Selecting UID/GID from range 1000 to 59999 ...
    • info: Adding new group `islam' (1001) ...
    • info: Adding new user `islam' (1001) with group `islam (1001)' ...
    • info: Creating home directory `/home/islam' ...
    • info: Copying files from `/etc/skel' ...
    • New password: 
    • BAD PASSWORD: The password is shorter than 8 characters
    • Retype new password: 
    • Sorry, passwords do not match.
    • New password: 
    • BAD PASSWORD: The password is shorter than 8 characters
    • Retype new password: 
    • passwd: password updated successfully
    • Changing the user information for islam
    • Enter the new value, or press ENTER for the default
    • Full Name []: islam yahia
    • Room Number []: 
    • Work Phone []: 
    • Home Phone []: 
    • Other []: 
    • Is the information correct? [Y/n] y
    • info: Adding new user `islam' to supplemental / extra groups `users' ...
    • info: Adding user `islam' to group `users' ...
    • Create a user account with the following attribute
    •  Username: baduser
    •  Full name/comment: Bad User
    •  Password: baduser
    • ola-youssef@oy-pc:~$ sudo adduser baduser
    • info: Adding user `baduser' ...
    • info: Selecting UID/GID from range 1000 to 59999 ...
    • info: Adding new group `baduser' (1002) ...
    • info: Adding new user `baduser' (1002) with group `baduser (1002)' ...
    • info: Creating home directory `/home/baduser' ...
    • info: Copying files from `/etc/skel' ...
    • New password: 
    • BAD PASSWORD: The password is shorter than 8 characters
    • Retype new password: 
    • passwd: password updated successfully
    • Changing the user information for baduser
    • Enter the new value, or press ENTER for the default
    • Full Name []: Bad User
    • Room Number []: 
    • Work Phone []: 
    • Home Phone []: 
    • Other []: 
    • Is the information correct? [Y/n] y
    • info: Adding new user `baduser' to supplemental / extra groups `users' ...
    • info: Adding user `baduser' to group `users' ...
    • Create a supplementary (Secondary) group called pgroup with group ID of 30000
    • ola-youssef@oy-pc:~$ sudo groupadd -g 30000 pgroup
    • ola-youssef@oy-pc:~$ groups
    • ola-youssef adm cdrom sudo dip plugdev users lpadmin docker
    • ola-youssef@oy-pc:~$ groups pgroup  
    • groups: ‘pgroup’: no such user
    • ola-youssef@oy-pc:~$ getent group pgroup
    • pgroup:x:30000:
    • ola-youssef@oy-pc:~$ cat /etc/group
    • root:x:0:
    • daemon:x:1:
    • bin:x:2:
    • sys:x:3:
    • adm:x:4:syslog,ola-youssef
    • tty:x:5:
    • disk:x:6:
    • lp:x:7:
    • mail:x:8:
    • news:x:9:
    • uucp:x:10:
    • man:x:12:
    • proxy:x:13:
    • kmem:x:15:
    • dialout:x:20:
    • fax:x:21:
    • voice:x:22:
    • cdrom:x:24:ola-youssef
    • floppy:x:25:
    • tape:x:26:
    • sudo:x:27:ola-youssef
    • audio:x:29:
    • dip:x:30:ola-youssef
    • www-data:x:33:
    • backup:x:34:
    • operator:x:37:
    • list:x:38:
    • irc:x:39:
    • src:x:40:
    • shadow:x:42:
    • utmp:x:43:
    • video:x:44:
    • sasl:x:45:
    • plugdev:x:46:ola-youssef
    • staff:x:50:
    • games:x:60:
    • users:x:100:ola-youssef,islam,baduser
    • nogroup:x:65534:
    • systemd-journal:x:999:
    • systemd-network:x:998:
    • crontab:x:997:
    • systemd-timesync:x:996:
    • input:x:995:
    • sgx:x:994:
    • kvm:x:993:
    • render:x:992:
    • messagebus:x:101:
    • syslog:x:102:
    • systemd-resolve:x:991:
    • uuidd:x:103:
    • _ssh:x:104:
    • tss:x:105:
    • ssl-cert:x:106:
    • systemd-oom:x:990:
    • bluetooth:x:107:
    • rdma:x:108:
    • whoopsie:x:109:
    • netdev:x:110:
    • avahi:x:111:
    • tcpdump:x:112:
    • sssd:x:113:
    • lpadmin:x:114:ola-youssef
    • fwupd-refresh:x:989:
    • scanner:x:115:saned
    • saned:x:116:
    • geoclue:x:117:
    • pipewire:x:118:
    • polkitd:x:988:
    • rtkit:x:119:
    • colord:x:120:
    • gdm:x:121:
    • nm-openvpn:x:122:
    • lxd:x:123:
    • nvidia-persistenced:x:124:
    • gnome-remote-desktop:x:987:
    • gamemode:x:986:
    • gnome-initial-setup:x:985:
    • ola-youssef:x:1000:
    • winbindd_priv:x:984:
    • docker:x:983:ola-youssef
    • islam:x:1001:
    • baduser:x:1002:
    • pgroup:x:30000:
    • Create a supplementary group called badgroup
    • ola-youssef@oy-pc:~$ sudo groupadd badgroup
    • ola-youssef@oy-pc:~$ getent group badgroup
    • badgroup:x:30001:
    • Add islam user to the pgroup group as a supplementary group
    • ola-youssef@oy-pc:~$ sudo usermod -aG pgroup islam
    • ola-youssef@oy-pc:~$ groups islam   
    • islam : islam users pgroup
    • Modify the password of islam's account to password
    • ola-youssef@oy-pc:~$ sudo passwd islam
    • New password: 
    • passwd: password updated successfully
    • Modify islam's account so the password expires after 30 days
    • ola-youssef@oy-pc:~$ sudo chage -M 30 islam
    • Lock bad user account so he can't log in
    • ola-youssef@oy-pc:~$ sudo passwd -l baduser 
    • passwd: password changed.
    • ola-youssef@oy-pc:~$ sudo grep baduser /etc/shadow
    • baduser:!$y$j9T$2r9sP9b6P5Rf21JiIxaAB.$KTBy5oqG0nXO0Ridek89mBXKWGlj8FNLVOI13kit1s2:19955:0:99999:7:::
    • Delete bad user account
    • ola-youssef@oy-pc:~$ sudo userdel -r baduser
    • userdel: baduser mail spool (/var/mail/baduser) not found
    • ola-youssef@oy-pc:~$ find / -user baduser
    • find: ‘baduser’ is not the name of a known user
    • Delete the supplementary group called badgroup.
    • ola-youssef@oy-pc:~$ sudo groupdel badgroup
    • Create a folder called myteam in your home directory and change its permissions to
    • read only for the owner.
    • ola-youssef@oy-pc:~$ mkdir myteam
    • ola-youssef@oy-pc:~$ ls
    • aws           cprograms  Documents  get-docker.sh  matrials  myteam    Public  Templates
    • awscliv2.zip  Desktop    Downloads  hosts          Music     Pictures  snap    Videos
    • ola-youssef@oy-pc:~$ chmod 400 myteam  
    • ola-youssef@oy-pc:~$ ls -ld myteam  
    • dr-------- 2 ola-youssef ola-youssef 4096 Aug 20 07:18 myteam
    • Log out and log in by another user
    • ola-youssef@oy-pc:~$ su - islam
    • Password: 
    • Try to access (by cd command) the folder (myteam)
    • ola-youssef@oy-pc:~$ chmod 577 /home/ola-youssef/myteam
    • ola-youssef@oy-pc:~$ ls -ld /home/ola-youssef/myteam
    • dr-xrwxrwx 2 ola-youssef ola-youssef 4096 Aug 20 09:06 /home/ola-youssef/myteam
    • ola-youssef@oy-pc:~$ su - islam
    • Password: 
    • islam@oy-pc:~$ cd /home/ola-youssef/myteam
    • -bash: cd: /home/ola-youssef/myteam: Permission denied
    • Using the command Line
        ◦ Change the permissions of oldpasswd file to give owner read and write permissions and for group write and execute and execute only for the others (using chmod in 2 different ways)
        ◦ change your default permissions to be as above.
        ◦ ola-youssef@oy-pc:~$ touch oldpasswd
        ◦ ola-youssef@oy-pc:~$ ls
        ◦ aws           Desktop    get-docker.sh  Music      Pictures  Templates
        ◦ awscliv2.zip  Documents  hosts          myteam     Public    Videos
        ◦ cprograms     Downloads  matrials       oldpasswd  snap
        ◦ ola-youssef@oy-pc:~$ ls -ld /home/ola-youssef/oldpasswd
        ◦ -rw-rw-r-- 1 ola-youssef ola-youssef 0 Aug 20 09:59 /home/ola-youssef/oldpasswd (default permissions)
        ◦ ola-youssef@oy-pc:~$ chmod 631 /home/ola-youssef/oldpasswd
        ◦ ola-youssef@oy-pc:~$ ls -ld /home/ola-youssef/oldpasswd
        ◦ -rw--wx--x 1 ola-youssef ola-youssef 0 Aug 20 09:59 /home/ola-youssef/oldpasswd
        ◦ chmod u=rw,g=wx,o=x /home/ola-youssef/oldpasswd
    • What is the maximum permission a file can have, by default when it is just created? And what is that for directory.
    • For Files is 644 
    • Default permission is 666  = 110 110 110 
    • Umask value is 002  = 000 000 010
    • Abstract them = 644 110 110 100
    • For Directories  is 755
    • Default permission is 777 = 111 111 111
    • Umask value is 002  = 000 000 010
    • Abstract them = 755 11 101 010
    • Change your default permissions to be no permission to everyone then create a directory and a file to verify.
    • ola-youssef@oy-pc:~$ umask 0777
    • ola-youssef@oy-pc:~$ mkdir testdire
    • ola-youssef@oy-pc:~$ ls -ld /home/ola-youssef/testdire
    • dr-------- 2 ola-youssef ola-youssef 0 Aug 20 10:18 testdire
    • ola-youssef@oy-pc:~$ touch testfile
    • ola-youssef@oy-pc:~$ ls -ld /home/ola-youssef/testfile
    • --------- 1 ola-youssef ola-youssef 0 Aug 20 10:20 testfile
    • What are the minimum permission needed for:
        ◦ Copy a directory (permission for source directory and permissions for target parent directory)
        ◦ Copy a file (permission for source file and and permission for target parent directory)
        ◦ Delete a file
        ◦ Change to a directory
        ◦ List a directory content (ls command)
        ◦ View a file content (more/cat command)
        ◦ Modify a file content
        ◦ Copy a Directory:
    • Source: Read (r) and Execute (x).
    • Target Parent: Write (w) and Execute (x).
    • Copy a File:
    • Source: Read (r).
    • Target Parent: Write (w) and Execute (x).
    • Delete a File:
    • Parent Directory: Write (w) and Execute (x).
    • Change to a Directory:
    • Directory: Execute (x).
    • List Directory Content:
    • Directory: Read (r).
    • View File Content:
    • File: Read (r).
    • Modify File Content:
    • File: Write (w).
    • Parent Directory: Write (w) (if needed).
    • Create a file with permission 444. Try to edit in it and to remove it? Note what happened.
    • ola-youssef@oy-pc:~$ touch test2file
    • ola-youssef@oy-pc:~$ chmod 444 /home/ola-youssef/test2file
    • ola-youssef@oy-pc:~$ echo "hellooo" > test2file
    • -bash: test2file: Permission denied
    • ola-youssef@oy-pc:~$ rm test2file
    • rm: remove write-protected regular file 'test2file'? Y 
    • ola-youssef@oy-pc:~$ ls
    • aws           Desktop    get-docker.sh  Music     Public     Videos
    • awscliv2.zip  Documents  hosts          myteam    snap
    • cprograms     Downloads  matrials       Pictures  Templates
    • Note that the file cannot be edited due to the read-only permission, and the rm command requires confirmation to delete the write-protected file.
    • What is the difference between the “x” permission for a file and for a directory?
    • File "x" permission: Enables the operating system to run the file as a binary executable or script.
    • Directory "x" permission:Enables access to the directory's contents, including listing files and subdirectories, and changing into the directory
      
    • Using vi write your CV in the file mycv. Your CV should include your name, age, school, college, experience,…
      
    • ola-youssef@oy-pc:~$ vi mycv
    • ola-youssef@oy-pc:~$ cat mycv
    • MY CV
    • Name: Ola Youssef Mohammed
    • Age: 21
    • School: Sadat Academy for Management Sciences 
    • College: Computer Science 
    • Experience: Software Development Internship
      
    • Open mycv file using vi command then: Without using arrows state how to:
        ◦ Show all lines numbers
          1
        ◦ 2 MY CV
        ◦ 3 
        ◦ 4 Name: Ola Youssef Mohammed
        ◦ 5 Age: 21
        ◦ 6 School: Sadat Academy for Management Sciences
        ◦ 7 College: Computer Science
        ◦ 8 Experience: Software Development Internship
        ◦ ~                                                                               
                                                                                       
        ◦ :set number
          
        ◦ Step to line 5 (assuming that you are in line 1 and file is more than 5 lines).
        ◦ 5G
        ◦ Delete the line you are on and line 5.
        ◦ cat mycv
        ◦ MY CV
        ◦ Name: Ola Youssef Mohammed
        ◦ College: Computer Science 
        ◦ Experience: Software Development Internship
      
    • List the available shells in your system.
    • ola-youssef@oy-pc:~$ cat /etc/shells
    • # /etc/shells: valid login shells
    • /bin/sh
    • /usr/bin/sh
    • /bin/bash
    • /usr/bin/bash
    • /bin/rbash
    • /usr/bin/rbash
    • /usr/bin/dash
    • List the environment variables in your current shell.
    • ola-youssef@oy-pc:~$ printenv
    • List all of the environment variables for the bash shell.
    • ola-youssef@oy-pc:~$ export
    • What are the commands that list the value of a specific variable?
    • Echo $ variable
    • printenv variable
    • Display your current shell name.
    • ola-youssef@oy-pc:~$ echo $SHELL
    • /bin/bash
    • Execute the following command :
        ◦ echo \ then press enter
        ◦ What is the purpose of \ ?
        ◦ The \ character at the end of a command tells the shell that the command is not complete and more input is needed. 
        ◦ Notice the prompt ”>” what is that? and how can you change it from “>” to “:”. (Search PS1, PS2, …)
        ◦ When you press Enter, the shell displays a > prompt, waiting for additional input.
        ◦ ola-youssef@oy-pc:~$ PS2=': '
    • Create a Bash shell alias named ls for the “ls –l” command
    • ola-youssef@oy-pc:~$ alias ls='ls -l'
      
