# cfme_git_integration
Allow syncronization of cfme bits from remote appliance to here over ssh using cfme-rhconsulting-scripts.  Good for using with git.

Depends on https://github.com/rhtconsulting/cfme-rhconsulting-scripts being installed.
Recommend use of SSH keys or other way of caching password.

Create a file in the location you want to push pull from called .cfme with contents of HOST=your_cfme_appliance, for example:

$ cat .cfme 
HOST=cfme04
