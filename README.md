# syn #

This package is a wrapper for rsync used to easily synchronize remote directories with each other.

### What is this repository for? ###

* Mark a directory to point to a remote directory, and you can push and pull changes.
* You can even push/pull sub directories within the local directory tree.
* To avoid pushing unwanted changes, there is a whatif mode (rsync's TODO option).
* If synchronizing between similar filesystems (ext4 to hfs, but not ext4 to fat32), you can configure the archiving option to preserve attributes, such as file permissions (rsync's archive option).
* It will save bandwidth and time by only pushing files with changes, this allows for frequent syn calls (rsync's --update option).
* If the current state of the directory is desired, you can push with the -d command to delete missing files on the remote server (rsync's --delete option)

### How can I configure syn? ###

* All configuration files are stored in ~/.syn
* ~/.syn/config contains configuration options and is sourced once per call to syn.
* ~/.syn/map contains the mappings from local directories to remote ones.

### Who do I talk to? ###

* Author: Lucas Wilson
* Email: lkwilson96@gmail.com
* Contributions and suggestions are always welcome!