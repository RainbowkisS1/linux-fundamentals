# Introductory terms and concepts
We will start our journey with some of the most commmon terms we will be using in this chapter and our rest of the journey.

## 1. Binaries and Applications
- These are files that can be executed. These are usually written in C/C++ or Rust.
- They usually are found in /usr/bin/ or /usr/sbin directories. 
- We can check if a file is a binary by entering the command  **file /usr/bin/ls** in our linux terminal. If the output is **ELF 64-bit LSB executable** , we can definitely say that the file is a binary.
- Examples include commands like ls , cat , ifconfig and applications like airrack-ng and *IDS* (Intrusion Detection system) -- snort.
- Important thing to note here is that not all applications are binaries.
  Applications can be categorised as :
  1) Compiled binaries (true binaries)
      - These are directly executed by the CPU.
      - Examples include:
         ls, cat, wireshark, nmap, airrack-ng etc.
       - These are Fast but hard to read and modify.
       - Check with the help of following command: **file /usr/bin/aircrack-ng**. In output you will see an ELF executible.
 

       
   2) Script-based applications (NOT binaries)
       - These are text files, interpreted by another program (Python, Bash, Ruby, etc.)
       - Examples include : Metasploit (in ruby) , many security tools (in python) and scripts (in python or bash)
       - Check:
         1) *which msfconsole*  
         2)  *file $(which msfconsole)*

            The first command helps us find the actual path of our executable. when we command *which msfconsole* we get output as **/usr/bin/msfconsole**. Now you                  know: i) Where it lives, ii) Which file runs, iii) Whether it’s system-wide or user-installed.

         The second command answers you the question **“Is this a binary, a script, or something else?”**.
          Commanding,   '*file $(which msfconsole)*', We get a output as **/usr/bin/msfconsole: Ruby script, ASCII text executable**.
          Here we can clearly see that this is an text file in ruby.

         
     3) Wrapper scripts (binary-looking, but not really)
        - Sometimes the command you run is just a small script that launches something else.
        - eg. *cat $(which msfconsole)*. 


     4) Hybrid applications
        - Some tools are part binary + part scripts.
        - eg. Metasploit :
            i)  Core logic = Ruby scripts
            ii) Heavy crypto / networking = compiled C extensions
        - This is extremely common in cybersecurity tools.

   ### Importance of binaries and applications in security:
#### A command is not a program:
When we type *msfconsole*, we are running a specific file on disk.        
security always asks, **which file is actually executed and what file path does it follow?**    
Thats why *which msfconsole* matters, as it tells you about the exact path followed to open this file. It is important to know the path as, a malicious file might disguise itself as another file you are familiar with. For instance, **an malicious file named ls or cd could be made to trick the user into running a malware**
Checking its path might give you a hint abaout its malicious nature.

#### An Executable is not always a Binary:
Linux alows any executible to run as a:
 1) Binary (Machine code)
 2) Script (Text files)
 3) Wrapper (WHich launches something else)
    Scripts are easier to read and changable, hence the tools which require frequent formatting and change of internal code, are generally scripts.
    Binaries are are pretty difficult to read and format, and also possess a greater threat as we cannot view what it actually contains.

#### Shebang (!) :
A shebang is the first line of a script that tells Linux which program (interpreter) should run the file.   
It looks like this --- **#!/usr/bin/env python3**.   
This basically tells linux that it should use python interpreter to  run the file.   
Another example to get this is -- **#!/bin/bash** -- **echo 'hi'**    
Internally, Linux follows **/bin/bash 'hi**.     

NOTE that we will be learning what each of these terms in a command mean later on.  

*From a security point of view,*
1) If the interpreter is replaced or hijacked that means that every script using it is compromised.
2) env depends on $PATH → PATH hijacking risk.


#### Why *file* matters:
The command -- *file /usr/bin/msfconsole*, tells you:
1) Script or binary?
2) Text or machine code?
3) Architecture?
**Security point of view:**
1) Spot fake binaries
2) Detect suspicious scripts disguised as commands









 


   

          
          
          

  
     
 
             

         
                 
 
        

        
      
     
     
 




 
 

  
  
