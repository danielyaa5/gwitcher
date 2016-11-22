# gwitcher
A script for switching between github accounts

##Setup
*Notes*: This has only been tested on Mac OS X and will almost surely brake on any other system. Looking for PRs from bash gurus to increase system compatibility.

 
**Requirements**

OpenSSH 7.3 or greater (check version with `ssh -v`, see [here](https://mochtu.de/2015/01/07/updating-openssh-on-mac-os-x-10-10-yosemite/) for OS X upgrade instructions)
###Step 1
Download the script and add to path, *i.e.* in Mac OS X
`mv /directory/to/downloaded/script /usr/local/bin`
###Step 2
Create the gwitcher_config file in `~/.ssh/config`

The formatting of the file should look like this. Note that the comments are required for the command to work correctly. This new file will be included into your main `~/.ssh/config` file. The `Host github.com` settings are used for the current github user. See this [tutorial](https://code.tutsplus.com/tutorials/quick-tip-how-to-work-with-github-and-multiple-accounts--net-22574) on how to set up a git config file for multiple accounts.

```bash
Host github-other_username
  #Username other_username
  #Name Billy Bob
  #Email billbob@gmail.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_other_username

Host github.com
  #Username current_username
  #Name Billy Bob
  #Email current_username@gmail.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_current_username
```
###Step 3
Run the gwitch command like so `gwitch username-to-switch-to` and then restart your terminal.