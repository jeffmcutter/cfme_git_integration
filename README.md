# cfme_git_integration
Allow syncronization of cfme bits from remote appliance to here over ssh using cfme-rhconsulting-scripts.  Good for using with git.

Requires rsync be installed locally.
Depends on https://github.com/rhtconsulting/cfme-rhconsulting-scripts, and will attempt to install them onto the CFME appliance.
Requires rsync and git be installed on the CFME appliance and will attempt to install them.  Repos need to be available to the appliance (you may need to subscription-manager register etc.).
Recommend use of SSH keys or other way of caching password.

Create a file in the location you want to push pull from called .cfme with contents of HOST=your_cfme_appliance, for example:

```
$ cat .cfme 
HOST=cfme04
```
