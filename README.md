
### bash_timeout - code to add to scripts to facilitate a timeout.

bash\_timeout is the bare bones code to implement a timeout in a Bash script. It is intended for users to copy and paste the code into their scripts and then to insert their own code within bash_timeout's logical framework.

The code works well with non-Bash shells. There are some comments in the `bash_timeout` file which explain that the `disown` line may need to be removed and that the `kill` command may need minor modification depending on which version of `kill` the shell uses.

The timeout code follows this methodology:

- Store the time in seconds and nanoseconds.
- Run the command the timeout is required for. The command must be forked with a trailing '&'.
- Store the command's process ID.
- Repeatedly check to see if the command has completed or if the timeout has been exceeded.
- Optionally a period of sleep can be used between these checks.
- If the command did not finish within the timeout period, kill the command.

I hope this helps.
