Description
===========
Replacement 212-git step for rollout.

Depends
=======
The rollout file for this replacement is required. <tt>command()</tt> has been 
modified to accept the run_as => 'string' command, which will pre-append
<tt>sudo -u {run_as} -H</tt> to any command string and run that command literall
as that user.

To make this work, it requires that the rollout run time user ( which unless changed is
<tt>nobody</tt> ) is added to the sudoers list:
```
nobody ALL=(ALL) NOPASSWD:/usr/bin/git
```