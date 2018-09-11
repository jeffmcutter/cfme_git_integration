# cfme_git_integration

*Note that the rhtconsulting/cfme-rhconsulting-scripts now have support for importing and exporting all types making this script somewhat superfluous.  It still works as of now though and does handle moving the parts to/from the appliance to whereever you want them and also includes the ability to automatically commit and push changes to git.*

Allow syncronization of cfme bits from remote appliance to here over ssh using cfme-rhconsulting-scripts.  Good for using with git.

## Requirements
- Requires rsync be installed locally.
- Depends on https://github.com/rhtconsulting/cfme-rhconsulting-scripts, and will attempt to install them onto the CFME appliance.
- Requires rsync and git be installed on the CFME appliance and will attempt to install them.  Repos need to be available to the appliance (you may need to subscription-manager register etc.).
- Recommend use of SSH keys or other way of caching password.

## Usage
Create a file in the location you want to push pull from called .cfme with contents of HOST=your_cfme_appliance and DOMAINS=Domain1 Domain2 etc., for example:

```
$ cat .cfme 
HOST=cfme04
DOMAINS=Domain1 Domain2 Domain3
USER=root

```
Note that the first domain listed will be the lowest priority and the last listed will be the highest priority in Automate.

To use, run the symlink that does what you want:

```
cfme2here     # Export all items to CWD
automate2here # Export only automate to CWD
cfme2git      # Export all items to CWD, commit them to git, and push them to git origin
automate2git  # Export only automate to CWD, commit them to git, and push them to git origin
here2cfme     # Import all items in CWD to CFME
automate2cfme # Import only automate in CWD to CFME
```

Note that these tools can installed on and run against the same host (for example the VMDB appliance (assuming it's not standalone)).
