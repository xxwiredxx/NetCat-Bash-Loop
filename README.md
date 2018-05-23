# NetCat-Bash-Loop
This is a simple bash script to run a loop to keep a NetCat file stream open. This is great for training.


███╗   ██╗███████╗████████╗ ██████╗ █████╗ ████████╗    ██████╗  █████╗ ███████╗██╗  ██╗    ██╗      ██████╗  ██████╗ ██████╗
████╗  ██║██╔════╝╚══██╔══╝██╔════╝██╔══██╗╚══██╔══╝    ██╔══██╗██╔══██╗██╔════╝██║  ██║    ██║     ██╔═══██╗██╔═══██╗██╔══██╗
██╔██╗ ██║█████╗     ██║   ██║     ███████║   ██║       ██████╔╝███████║███████╗███████║    ██║     ██║   ██║██║   ██║██████╔╝
██║╚██╗██║██╔══╝     ██║   ██║     ██╔══██║   ██║       ██╔══██╗██╔══██║╚════██║██╔══██║    ██║     ██║   ██║██║   ██║██╔═══╝
██║ ╚████║███████╗   ██║   ╚██████╗██║  ██║   ██║       ██████╔╝██║  ██║███████║██║  ██║    ███████╗╚██████╔╝╚██████╔╝██║
╚═╝  ╚═══╝╚══════╝   ╚═╝    ╚═════╝╚═╝  ╚═╝   ╚═╝       ╚═════╝ ╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝    ╚══════╝ ╚═════╝  ╚═════╝ ╚═╝
                                                                                                                XxWiReDxX


This is a guide on how to set up a netcat filestream that automatically creates a session and terminates it in a loop. Two seconds after the active session is created.

# Modulators and Commands
Netcat Modulators used:
   -l = Listen mode (Default is client mode)
   -v = Be verbose, printing out messages on standard error, such as when a connection occurs
   -q = Quit after EOF on stdin and delay of secs (Closes the session after the designated time has past)
   -p = Local port (In listen mode, this is port listened on. In client mode, this is source port for all packets sent)
   < = Sending file
   > = Receiving file

Bash Commands:
   sh    = Enters Bash Command
   exit  = Exits  Bash Command
   while = Bash control statement to run a loop determined by an exit variable such as true, false, x=2, y>0...
   true  = Bash control variable
   do    = Bash control statement to run the command text in the command line
   echo  = Like println for the shell; outputs a message or value ["echo connection refreshed" outputs: "connection refreshed"]
   done  = Bash control statement to close a loop
   sleep = Bash code to have the line execution wait for the designated time in seconds


# NOTE
 * Bash Commands should be separated by the ";" letting Bash know a new line is being executed.
 * If the Bash Script cannot be exited by the exit command or Ctrl c, place "sleep 2;" after "echo refresh"

# Netcat Bash Loop Line Code
sh
while true; do nc -l -v -q 2 -p [port] < /[host/sender_file_path]/[filename.extention]; echo refresh; done
