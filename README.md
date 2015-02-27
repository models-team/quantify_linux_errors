# Quantifying Errors in Linux Kernel
Elvis' master thesis

## Dependencies
python3 (maybe older versions will work)
bash
gcc (or build-tools, or whatever it is called in your distribution)
GNU time (not built-in bash-time or zsh-time, but GNU time)

## Scripts

### make_and_get_errors.sh 
This script will untar, and compile a tarball, which is hardcoded in the file. 
So when changing between for example `linux` and `busybox`, one will have to 
change two lines of code.

saves following files:
  * config      (the configuration, k)
  * analyzer    (which analyzer program did the errorcheck)
  * buginfo     (the results from the analyzer)

### categorize_errors.py
This is a python script, because I had no idea how to use sets, and arrays in
Bash. I have made the script for Python 3.x but it is possible it will work for
earlier versions as well.
This script looks through a specific `buginfo` file, and scrapes all the info
into an aggregate, which can easilier be read.

## Timing of the compiling process
GNU time is used in stead of the normal built-in time command. This is mainly 
to make it easier to get the time into a specific file, and in the format we 
want.



