### Lab Report 1: Remote Acess and Filesystem
## Installing Visual Studio Code:
1. Download and install VS Code from the link provided in assignment instructions. Once installed, famliarize yourself with the program.
![Image](https://amohamad1.github.io/cse15l-lab-reports/Screenshot2.png)
2. To connect to the remote iegn6 servers you must ssh using the provided course account. First obtain the course account and set its passowrd. Once you have access to the account, open up your teminal and run the following command, replacing the username with your own.  
![Image](https://amohamad1.github.io/cse15l-lab-reports/Screenshot3.png)
3.Try the following commands: $ls to list items in current directory. $cd (directory) to change to specified directory. pwd to print current directory. $mkdir (directory) and $rmdir (directory) to create or delete specified directory. Clear to clear the terminal.
![Image](https://amohamad1.github.io/cse15l-lab-reports/Screenshot4.png)
4. To move files between client and host, you can use the $ scp command. The command is as follows: scp (file)(user:desired directly). See screenshot for example:
![Image](https://amohamad1.github.io/cse15l-lab-reports/Screenshot5.png)
5.Then to run the file that was just copied, you must first ssh back into the remote server machine and find the directory containing the file. Then use javac and java followed by the file name to compile and run the file.
![Image](https://amohamad1.github.io/cse15l-lab-reports/Screenshot6.png)
6. To avoid typing your password everytime you need to ssh into a remote machine, you can set an ssh key on your client. To do so, runt the command ssh-keygen on the client. Then, copy over the resulting public key file to the server machine and place in an ssh directory. 
![Image](https://amohamad1.github.io/cse15l-lab-reports/Screenshot7.png)
7.One helpful tip to optimize remote running is to use the arrow keys to access command history and quickly use past commands. 
![Image](https://amohamad1.github.io/cse15l-lab-reports/Screenshot8.png)