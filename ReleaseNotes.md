# Version 2.6.0

* Added json logging
  Using the -j option pipexec now logs in json format that can be
  parsed.  This provides information about status and exit codes
  of child processes.
* Exit with 1 when one child fails
  When at least one child fails, pipexec also fails with '1'.
* Check for rubbish on the command line
  Additional or unparsable command line arguments are now seen
  as an error. Before there were silently ignored.
* Fixed false positive dangling pointer check of gcc 12
  GCC introduces a new dangling pointer check which runs into
  a false positive.
* Add compile check for wide range of compilers
  As public travis access was switched off some time, pipexec now
  uses github CI/CD for compile check. The following compilers
  are checked:
  - gcc: 9, 10, 11, 12
  - clang: 10, 11, 12, 13, 14