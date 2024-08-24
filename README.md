    1. Create a user account with the following attribute
        username: islam
        Fullname/comment: islam yahia
        Password: islam
 ola-youssef@oy-pc:~$ sudo adduser islam   
  [sudo] password for ola-youssef: 
  info: Adding user `islam' ...
  info: Selecting UID/GID from range 1000 to 59999 ...
  info: Adding new group `islam' (1001) ...
    7. info: Adding new user `islam' (1001) with group `islam (1001)' ...
    8. info: Creating home directory `/home/islam' ...
    9. info: Copying files from `/etc/skel' ...
    10. New password: 
    11. BAD PASSWORD: The password is shorter than 8 characters
    12. Retype new password: 
    13. Sorry, passwords do not match.
    14. New password: 
    15. BAD PASSWORD: The password is shorter than 8 characters
    16. Retype new password: 
    17. passwd: password updated successfully
    18. Changing the user information for islam
    19. Enter the new value, or press ENTER for the default
    20. 	Full Name []: islam yahia
    21. 	Room Number []: 
    22. 	Work Phone []: 
    23. 	Home Phone []: 
    24. 	Other []: 
    25. Is the information correct? [Y/n] y
    26. info: Adding new user `islam' to supplemental / extra groups `users' ...
    27. info: Adding user `islam' to group `users' ...
    28. Create a user account with the following attribute
        Username: baduser
        Full name/comment: Bad User
        Password: baduser
    29. ola-youssef@oy-pc:~$ sudo adduser baduser
    30. info: Adding user `baduser' ...
    31. info: Selecting UID/GID from range 1000 to 59999 ...
    32. info: Adding new group `baduser' (1002) ...
    33. info: Adding new user `baduser' (1002) with group `baduser (1002)' ...
    34. info: Creating home directory `/home/baduser' ...
    35. info: Copying files from `/etc/skel' ...
    36. New password: 
    37. BAD PASSWORD: The password is shorter than 8 characters
    38. Retype new password: 
    39. passwd: password updated successfully
    40. Changing the user information for baduser
    41. Enter the new value, or press ENTER for the default
    42. 	Full Name []: Bad User
    43. 	Room Number []: 
    44. 	Work Phone []: 
    45. 	Home Phone []: 
    46. 	Other []: 
    47. Is the information correct? [Y/n] y
    48. info: Adding new user `baduser' to supplemental / extra groups `users' ...
    49. info: Adding user `baduser' to group `users' ...
    50. Create a supplementary (Secondary) group called pgroup with group ID of 30000
    51. ola-youssef@oy-pc:~$ sudo groupadd -g 30000 pgroup
    52. ola-youssef@oy-pc:~$ groups
    53. ola-youssef adm cdrom sudo dip plugdev users lpadmin docker
    54. ola-youssef@oy-pc:~$ groups pgroup  
    55. groups: ‘pgroup’: no such user
    56. ola-youssef@oy-pc:~$ getent group pgroup
    57. pgroup:x:30000:
    58. ola-youssef@oy-pc:~$ cat /etc/group
    59. root:x:0:
    60. daemon:x:1:
    61. bin:x:2:
    62. sys:x:3:
    63. adm:x:4:syslog,ola-youssef
    64. tty:x:5:
    65. disk:x:6:
    66. lp:x:7:
    67. mail:x:8:
    68. news:x:9:
    69. uucp:x:10:
    70. man:x:12:
    71. proxy:x:13:
    72. kmem:x:15:
    73. dialout:x:20:
    74. fax:x:21:
    75. voice:x:22:
    76. cdrom:x:24:ola-youssef
    77. floppy:x:25:
    78. tape:x:26:
    79. sudo:x:27:ola-youssef
    80. audio:x:29:
    81. dip:x:30:ola-youssef
    82. www-data:x:33:
    83. backup:x:34:
    84. operator:x:37:
    85. list:x:38:
    86. irc:x:39:
    87. src:x:40:
    88. shadow:x:42:
    89. utmp:x:43:
    90. video:x:44:
    91. sasl:x:45:
    92. plugdev:x:46:ola-youssef
    93. staff:x:50:
    94. games:x:60:
    95. users:x:100:ola-youssef,islam,baduser
    96. nogroup:x:65534:
    97. systemd-journal:x:999:
    98. systemd-network:x:998:
    99. crontab:x:997:
    100. systemd-timesync:x:996:
    101. input:x:995:
    102. sgx:x:994:
    103. kvm:x:993:
    104. render:x:992:
    105. messagebus:x:101:
    106. syslog:x:102:
    107. systemd-resolve:x:991:
    108. uuidd:x:103:
    109. _ssh:x:104:
    110. tss:x:105:
    111. ssl-cert:x:106:
    112. systemd-oom:x:990:
    113. bluetooth:x:107:
    114. rdma:x:108:
    115. whoopsie:x:109:
    116. netdev:x:110:
    117. avahi:x:111:
    118. tcpdump:x:112:
    119. sssd:x:113:
    120. lpadmin:x:114:ola-youssef
    121. fwupd-refresh:x:989:
    122. scanner:x:115:saned
    123. saned:x:116:
    124. geoclue:x:117:
    125. pipewire:x:118:
    126. polkitd:x:988:
    127. rtkit:x:119:
    128. colord:x:120:
    129. gdm:x:121:
    130. nm-openvpn:x:122:
    131. lxd:x:123:
    132. nvidia-persistenced:x:124:
    133. gnome-remote-desktop:x:987:
    134. gamemode:x:986:
    135. gnome-initial-setup:x:985:
    136. ola-youssef:x:1000:
    137. winbindd_priv:x:984:
    138. docker:x:983:ola-youssef
    139. islam:x:1001:
    140. baduser:x:1002:
    141. pgroup:x:30000:
    142. Create a supplementary group called badgroup
    143. ola-youssef@oy-pc:~$ sudo groupadd badgroup
    144. ola-youssef@oy-pc:~$ getent group badgroup
    145. badgroup:x:30001:
    146. Add islam user to the pgroup group as a supplementary group
    147. ola-youssef@oy-pc:~$ sudo usermod -aG pgroup islam
    148. ola-youssef@oy-pc:~$ groups islam   
    149. islam : islam users pgroup
    150. Modify the password of islam's account to password
    151. ola-youssef@oy-pc:~$ sudo passwd islam
    152. New password: 
    153. passwd: password updated successfully
    154. Modify islam's account so the password expires after 30 days
    155. ola-youssef@oy-pc:~$ sudo chage -M 30 islam
    156. Lock bad user account so he can't log in
    157. ola-youssef@oy-pc:~$ sudo passwd -l baduser 
    158. passwd: password changed.
    159. ola-youssef@oy-pc:~$ sudo grep baduser /etc/shadow
    160. baduser:!$y$j9T$2r9sP9b6P5Rf21JiIxaAB.$KTBy5oqG0nXO0Ridek89mBXKWGlj8FNLVOI13kit1s2:19955:0:99999:7:::
    161. Delete bad user account
    162. ola-youssef@oy-pc:~$ sudo userdel -r baduser
    163. userdel: baduser mail spool (/var/mail/baduser) not found
    164. ola-youssef@oy-pc:~$ find / -user baduser
    165. find: ‘baduser’ is not the name of a known user
    166. Delete the supplementary group called badgroup.
    167. ola-youssef@oy-pc:~$ sudo groupdel badgroup
    168. Create a folder called myteam in your home directory and change its permissions to
       read only for the owner.
    169. mkdir myteam
    170. ola-youssef@oy-pc:~$ ls
    171. aws           cprograms  Documents  get-docker.sh  matrials  myteam    Public  Templates
    172. awscliv2.zip  Desktop    Downloads  hosts          Music     Pictures  snap    Videos
    173. ola-youssef@oy-pc:~$ chmod 400 myteam  
    174. ola-youssef@oy-pc:~$ ls -ld myteam  
    175. dr-------- 2 ola-youssef ola-youssef 4096 Aug 20 07:18 myteam
    176. Log out and log in by another user
    177. ola-youssef@oy-pc:~$ su - islam
    178. Password: 
    179. Try to access (by cd command) the folder (myteam)
    180. ola-youssef@oy-pc:~$ chmod 577 /home/ola-youssef/myteam
    181. ola-youssef@oy-pc:~$ ls -ld /home/ola-youssef/myteam
    182. dr-xrwxrwx 2 ola-youssef ola-youssef 4096 Aug 20 09:06 /home/ola-youssef/myteam
    183. ola-youssef@oy-pc:~$ su - islam
    184. Password: 
    185. islam@oy-pc:~$ cd /home/ola-youssef/myteam
    186. -bash: cd: /home/ola-youssef/myteam: Permission denied
    187. Using the command Line
           Change the permissions of oldpasswd file to give owner read and write permissions and for group write and execute and execute only for the others (using chmod in 2 different ways)
           change your default permissions to be as above.
        1. la-youssef@oy-pc:~$ touch oldpasswd
        2. ola-youssef@oy-pc:~$ ls
        3. aws           Desktop    get-docker.sh  Music      Pictures  Templates
        4. awscliv2.zip  Documents  hosts          myteam     Public    Videos
        5. cprograms     Downloads  matrials       oldpasswd  snap
        6. ola-youssef@oy-pc:~$ ls -ld /home/ola-youssef/oldpasswd
        7. -rw-rw-r-- 1 ola-youssef ola-youssef 0 Aug 20 09:59 /home/ola-youssef/oldpasswd (default permissions)
        8. ola-youssef@oy-pc:~$ chmod 631 /home/ola-youssef/oldpasswd
        9. ola-youssef@oy-pc:~$ ls -ld /home/ola-youssef/oldpasswd
        10. -rw--wx--x 1 ola-youssef ola-youssef 0 Aug 20 09:59 /home/ola-youssef/oldpasswd
        11. chmod u=rw,g=wx,o=x /home/ola-youssef/oldpasswd
    188. What is the maximum permission a file can have, by default when it is just created? And what is that for directory.
    189. For Files is 644 
    190. Default permission is 666  = 110 110 110 
    191. Umask value is 002  = 000 000 010
    192. Abstract them = 644 110 110 100
    193. For Directories  is 755
    194. Default permission is 777 = 111 111 111
    195.  Umask value is 002  = 000 000 010
    196. Abstract them = 755 11 101 010
    197. Change your default permissions to be no permission to everyone then create a directory and a file to verify.
    198. ola-youssef@oy-pc:~$ umask 0777
    199. ola-youssef@oy-pc:~$ mkdir testdire
    200. ola-youssef@oy-pc:~$ ls -ld /home/ola-youssef/testdire
    201.  dr-------- 2 ola-youssef ola-youssef 0 Aug 20 10:18 testdire
    202. ola-youssef@oy-pc:~$ touch testfile
    203. ola-youssef@oy-pc:~$ ls -ld /home/ola-youssef/testfile
    204. --------- 1 ola-youssef ola-youssef 0 Aug 20 10:20 testfile
    205. What are the minimum permission needed for:
           Copy a directory (permission for source directory and permissions for target parent directory)
           Copy a file (permission for source file and and permission for target parent directory)
           Delete a file
           Change to a directory
           List a directory content (ls command)
           View a file content (more/cat command)
           Modify a file content
        1. Copy a Directory:
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
        1. 
        2. 
    222. Create a file with permission 444. Try to edit in it and to remove it? Note what happened.
    223. ola-youssef@oy-pc:~$ touch test2file
    224. ola-youssef@oy-pc:~$ chmod 444 /home/ola-youssef/test2file
    225. ola-youssef@oy-pc:~$ echo "hellooo" > test2file
    226. -bash: test2file: Permission denied
    227. ola-youssef@oy-pc:~$ rm test2file
    228. rm: remove write-protected regular file 'test2file'? Y 
    229. ola-youssef@oy-pc:~$ ls
    230. aws           Desktop    get-docker.sh  Music     Public     Videos
    231. awscliv2.zip  Documents  hosts          myteam    snap
    232. cprograms     Downloads  matrials       Pictures  Templates
    233. Note that the file cannot be edited due to the read-only permission, and the rm command requires confirmation to delete the write-protected file.
    234. What is the difference between the “x” permission for a file and for a directory?
    235. File "x" permission: Enables the operating system to run the file as a binary executable or script.
    236. Directory "x" permission:Enables access to the directory's contents, including listing files and subdirectories, and changing into the directory
       
    237. Using vi write your CV in the file mycv. Your CV should include your name, age, school, college, experience,...
    238. Open mycv file using vi command then: Without using arrows state how to:
           Show all lines numbers
           Search for word age
           Step to line 5 (assuming that you are in line 1 and file is more than 5 lines).
           Delete the line you are on and line 5.
       
       
    239. List the available shells in your system.
    240. List the environment variables in your current shell.
    241. List all of the environment variables for the bash shell.
    242. What are the commands that list the value of a specific variable?
    243. Display your current shell name.
    244. State the initialization files of: sh, ksh, bash.
    245. Edit in your profile to display date at login and change your prompt permanently.
    246. Execute the following command :
           echo \ then press enter
           What is the purpose of \ ?
           Notice the prompt ”>” what is that? and how can you change it from “>” to “:”. (Search PS1, PS2, ...)
    247. Create a Bash shell alias named ls for the “ls –l” command

