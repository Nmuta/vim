# Using vi on the mac

Vim is one of the command line editors on Unix based systems.  It allows you edit any file on your system and it's a good way to edit hidden files on your system. 

## Objective:  By the end of today's lesson, students will be able to use basic vi commands to edit system files on the Mac.

### Creating a crontab

Cron ( cronological ) jobs are system based tasks that run on a schedule that you set.  We will be creating or modifying the crontab on your system to find something useful to do with vim. 

To enter the crontab for your system, type: 
<blockquote>  crontab -e  </blockquote> 

in your terminal.   We are now in vim.  Type i to get into 'insert' mode.  Then paste the following lines into your crontab: 
<blockquote>
# Minute   Hour   Day of Month       Month          Day of Week        Command
# (0-59)  (0-23)     (1-31)    (1-12 or Jan-Dec)  (0-6 or Sun-Sat)
   */2       *          *             *                *               cd ~/Desktop  && touch time.txt
</blockquote>


In order to exit insert mode, type :c

To exit and quit, type  :wq 

Now your crontab is installed and will run every 2 minutes.  the /2 means "every two minutes".  If we had just put 2 for the minute parameter, the script would run on the 2nd minute of every hour of every day of every month, etc. etc. 
cd into your Desktop and see if the time file has been created. If it has, go back into your crontab with 
crontab -e , hit i to get back into "insert" mode, and modify the command on that line to say
echo `date +%k:%M:%S` >> ~/Desktop/time.txt

"echo" in bash is basically a 'print' command.  It prints something , and here the double directional arrows are telling it to append to the file. If you use a single arrow, it will overwrite whatever is in that file. 




