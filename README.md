# syn #

This package is a wrapper for rsync used to easily
synchronize remote directoires with each other.

### What is this repository for? ###

* Mark a directory to point to a remote directory, and you can push and pull changes.
* You can even push/pull subdirectories within the local directory tree.
* To avoid pushing unwanted changes, there is a whatif mode.
* If synchronizing between similar filesystems (ext4 to hfs, but not ext4 to fat32), you can configure the archiving option to preserve attributes, such as file permissions.

### How can I configure syn? ###

* All configuration files are stored in ~/.syn
* ~/.syn/config contains configuration options and is sourced once per call to syn.
* ~/.syn/map contains the mappings from local directories to remote ones.

### Who do I talk to? ###

* Author: Lucas Wilson
* Email: lkwilson96@gmail.com
* Contributions and suggestions are always welcome!