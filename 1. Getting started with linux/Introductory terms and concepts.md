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

   

          
          
          

  
     
 
             

         
                 
 
        

        
      
     
     
 




 
 
  ### What Binaries actually are :
  
  
