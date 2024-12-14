## UNIX / LINUX CHEAT SHEET

### 1) FILE SYSTEM
    $ ls                                # list items in current directory
    $ ls -l                             # list items in current directory and show in long format to see perimissions, size and modification date
    $ ls -a                             # list all items in current directory, including hidden files
    $ ls -F                             # list all items in current directory and show directories with a slash and executables with a star
    $ ls dir                            # list all items in directory dir
    $ cd dir                            # change directory to dir
    $ cd ..                             # go up one directory
    $ cd /                              # go to the root directory
    $ cd ~                              # go to to your home directory
    $ cd -                              # go to the last directory you were just in
    $ pwd                               # show present working directory
    $ mkdir dir                         # make directory dir
    $ rm file                           # remove file
    $ rm -r dir                         # remove directory dir recursively
    $ cp file1 file2                    # copy file1 to file2
    $ cp -r dir1 dir2                   # copy directory dir1 to dir2 recursively
    $ mv file1 file2                    # move (rename) file1 to file2
    $ ln -s file link                   # create symbolic link to file
    $ touch file                        # create or update file
    $ cat file                          # output the contents of file
    $ less file                         # view file with page navigation
    $ head file                         # output the first 10 lines of file
    $ tail file                         # output the last 10 lines of file
    $ tail -f file                      # output the contents of file as it grows, starting with the last 10 lines
    $ vim file                          # edit file
    $ alias name 'command'              # create an alias for a command

### 2) SYSTEM
    $ shutdown                          # shut down machine
    $ reboot                            # restart machine
    $ date                              # show the current date and time
    $ whoami                            # who you are logged in as
    $ finger user                       # display information about user
    $ man command                       # show the manual for command
    $ df                                # show disk usage
    $ du                                # show directory space usage
    $ free                              # show memory and swap usage
    $ whereis app                       # show possible locations of app
    $ which app                         # show which app will be run by default

### 3) PROCESS MANAGEMENT
    $ ps                                # display your currently active processes
    $ top                               # display all running processes
    $ kill pid                          # kill process id pid
    $ kill -9 pid                       # force kill process id pid

### 4) PERMISSIONS
    $ ls -l                             # list items in the current directory and show permissions
    $ chmod ugo file                    # Change permissions of file to ugo. u is the user's permissions, g is the group's permissions and o is everyone else's permissions. The values of u, g and o can be any number between 0 and 7.
##### File Permissions
                                        7 — full permissions
                                        6 — read and write only
                                        5 — read and execute only
                                        4 — read only
                                        3 — write and execute only
                                        2 — write only
                                        1 — execute only
                                        0 — no permissions

    $ chmod 600 file    # you can read and write - good for files
    $ chmod 700 file    # you can read, write, and execute - good for scripts
    $ chmod 644 file    # you can read and write, and everyone else can only read - good for web pages
    $ chmod 755 file    # you can read, write, and execute, and everyone else can read and execute - good for programs that you want to share

### 5) NETWORKING
    $ wget file                         # download a file
    $ curl file                         # download a file
    $ scp user@host:file dir            # secure copy a file from remote server to the dir directory on your machine
    $ scp file user@host:dir            # secure copy a file from your machine to the dir directory on a remote server
    $ scp -r user@host:dir dir          # secure copy the directory dir from remote server to the directory dir on your machine
    $ ssh user@host                     # connect to host as user
    $ ssh -p port user@host             # connect to host on port as user
    $ ssh-copy-id user@host             # add your key to host for user to enable a keyed or passwordless login
    $ ping host                         # ping host and output results
    $ whois domain                      # Get information for domain
    $ dig domain                        # Get DNS information for domain
    $ dig -x host                       # reverse lookup host
    $ lsof -i tcp:1337                  # list all processes running on port 1337

### 6) SEARCHING
    $ grep pattern files                        # search for pattern in files
    $ grep -r pattern dir                       # search recursively for pattern in dir
    $ grep -rn pattern dir                      # search recursively for pattern in dir and show the line number found
    $ grep -r pattern dir --include='*.ext      # search recursively for pattern in dir and only search in files with .ext extension
    $ command | grep pattern                    # search for pattern in the output of command
    $ find file                                 # find all instances of file in real system
    $ locate file                               # find all instances of file using indexed database built from the updatedb command. Much faster than find
    $ sed -i 's/day/night/g' file               # find all occurrences of day in a file and replace them with night - s means substitude and g means global - sed also supports regular expressions

### 7) COMPRESSION
    $ tar cf file.tar files                     # create a tar named file.tar containing files
    $ tar xf file.tar                           # extract the files from file.tar
    $ tar czf file.tar.gz files                 # create a tar with Gzip compression
    $ tar xzf file.tar.gz                       # extract a tar using Gzip
    $ gzip file                                 # compresses file and renames it to file.gz
    $ gzip -d file.gz                           # decompresses file.gz back to file

### 8) SHORTCUTS
    $ ctrl+a                                    # move cursor to beginning of line
    $ ctrl+f                                    # move cursor to end of line
    $ alt+f                                     # move cursor forward 1 word
    $ alt+b                                     # move cursor backward 1 word

### 9) scp copy in aws 
##### For file:
    $ scp -i r_login.pem  artifactory-oss-6.7.2.tar.gz  ec2-user@34.222.132.1:/home/ec2-user
##### For folder:
    $ scp -ir r_login.pem  artifactory-oss-6.7.2.tar.gz  ec2-user@34.222.132.1:/home/ec2-user

<span style="color:red">
Few More Basic Commands
</span>

# Basic LINUX COMMANDS

## 1) File Commands: 

    $ ls                        # directory listing
    $ ls -al                    # formatted listing with hidden files
    $ cd dir                    # change directory to dir
    $ cd                        # change to home
    $ pwd                       # show current directory
    $ mkdir dir                 # create a directory dir
    $ rm file                   # delete file
    $ rm -r dir                 # delete directory dir
    $ rm -f file                # force remove file
    $ rm -rf dir                # force remove directory dir *
    $ cp file1 file2            # copy file1 to file2
    $ cp -r dir1 dir2           # copy dir1 to dir2; create dir2 if it doesn't exist
    $ mv file1 file2            # rename or move file1 to file2, if file2 is an existing directory, moves file1 into directory file2
    $ ln -s file link           # create symbolic link link to file
    $ touch file                # create or update file
    $ cat > file                # places standard input into file
    $ more file                 # output the contents of file
    $ head file                 # output the first 10 lines of file
    $ tail file                 # output the last 10 lines of file
    $ tail -f file              # output the contents of file as it grows, starting with the last 10 lines

### 2) Process Management

    $ ps                        # display your currently active processes
    $ top                       # display all running processes
    $ kill pid                  # kill process id pid
    $ killall proc              # kill all processes named proc *
    $ bg                        # lists stopped or background jobs; resume a stopped job in the background
    $ fg                        # brings the most recent job to foreground
    $ fg n                      # brings job n to the foreground

### 3) SSH

    $ ssh user@host             # connect to host as user
    $ ssh -p port user@host     # connect to host on port

##### port as user
    $ ssh-copy-id user@host     # add your key to host for user to enable a keyed or passwordless login

##### Searching
    $ grep pattern files        # search for pattern in files
    $ grep -r pattern dir       # search recursively for

##### pattern in dir
    $ command | grep pattern    # search for pattern in the

##### output of command
    $ locate file               # find all instances of file

### 4) System Info
    $ date                      # show the current date and time
    $ cal                       # show this month's calendar
    $ uptime                    # show current uptime
    $ w                         # display who is online
    $ whoami                    # who you are logged in as
    $ finger user               # display information about user
    $ uname -a                  # show kernel information
    $ cat /proc/cpuinfo         # cpu information
    $ cat /proc/meminfo         # memory information
    $ man command               # show the manual for command
    $ df                        # show disk usage
    $ du                        # show directory space usage
    $ free                      # show memory and swap usage
    $ whereis app               # show possible locations of app
    $ which app                 # show which app will be run by default

 

### 5) Compression
    $ tar cf file.tar files     # create a tar named
      file.tar containing files
    $ tar xf file.tar           # extract the files from file.tar
    $ tar czf file.tar.gz files # create a tar with

### 6) Gzip compression
    $ tar xzf file.tar.gz       # extract a tar using Gzip
    $ tar cjf file.tar.bz2      # create a tar with Bzip2

### 7) compression
    $ tar xjf file.tar.bz2      # extract a tar using Bzip2
    $ gzip file                 # compresses file and renames it to file.gz
    $ gzip -d file.gz           # decompresses file.gz back to file

### 8) Network
    $ ping host                 # ping host and output results
    $ whois domain              # get whois information for domain
    $ dig domain                # get DNS information for domain
    $ dig -x host               # reverse lookup host
    $ wget file                 # download file
    $ wget -c file              # continue a stopped download


### 9) Installation

Install from source:

./configure

make

make install

    $ dpkg -i pkg.deb           # install a package (Debian)
    $ rpm -Uvh pkg.rpm          # install a package (RPM)

### Shortcuts

    $ Ctrl+C                    # halts the current command
    $ Ctrl+Z                    # stops the current command, resume with
    
fg in the foreground and bg in the background

    $ Ctrl+D                    # log out of current session, similar to exit
    $ Ctrl+W                    # erases one word in the current line
    $ Ctrl+U                    # erases the whole line
    $ Ctrl+R                    # type to bring up a recent command
    $ !!                        # repeats the last command
    $ exit                      # log out of current session