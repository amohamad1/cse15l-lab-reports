# Lab Report 4: VIM

## Part 1

Here is how to change the name of the start parameter and its uses to base in DocSearchServer.java in Vim, using the least amount of keystrokes possible.

The shortest sequence of keystrokes to accomplish this is the following:

```
/start <enter> cebase <esc> n.n.n. :wq <enter>
```
Which is a total of 23 keystrokes!

Lets go over this step by step.

1\. First we use `/` to search for start

![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot1.png)

Pressing enter to find first instance:
![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot2.png)

2\. Then, we use `ce` to delete the word highlighted

Before typing ce
![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot3.png)

After typing ce
![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot4.png)

3\. We then type the replacement parameter name "base"

![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot5.png)

Pressing \<esc> to return to normal mode
![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot6.png)

4\. Pressing n to find the next instance of "start"

![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot7.png)

5\. Pressing `.` to repeat the previouv vim command; deleting "start" and replacing it with base

![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot8.png)

6\. Pressing n to find the third instance of "start"

![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot9.png)

7\. Replacing the word using `.`

![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot10.png)

8\. Finding the last instance of "start" using `n`

![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot11.png)

9\. Using `.` one last time

![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot12.png)

10\. Saving and quiting the file with `:wq`

![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot13.png)
![Image](https://amohamad1.github.io/cse15l-lab-reports/report4/screenshot14.png)

## Part 2

Method 1 took 49 seconds, while method 2 took 26 seconds.

I would personally prefer to make the edits on the remote server instead of making the edits on the local machine then scp to the remote becuase it is faster and more straightforward if the program needs to run remotely. 

One key aspect that factors into this is whether or not I need any specialized tools or programs such IDEs to make the eidts. If only vim is being used, then I could make the edits on the remote. But if other applications are involved in the , it is probably easier/ crucial to make the edits on the local machine then scp to the remote.