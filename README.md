# syn #

This package is a wrapper for rsync used to easily synchronize remote
directories with each other.

### What is this repository for? ###

* Mark a directory to point to a remote directory, and you can push and pull
  changes.
* You can even push/pull sub directories within the local directory tree.
* To avoid pushing unwanted changes, there is a whatif mode (rsync's TODO
  option).
* If synchronizing between similar filesystems (ext4 to hfs, but not ext4 to
  fat32), you can configure the archiving option to preserve attributes, such
  as file permissions (rsync's archive option).
* It will save bandwidth and time by only pushing files with changes, this
  allows for frequent syn calls (rsync's --update option).
* If the current state of the directory is desired, you can push with the -d
  command to delete missing files on the remote server (rsync's --delete
  option)

### TODO ###

combine remote repo vs dir

### Usage ###
This file contains notes used for development.

Usage:
    synctree command [args...]

Commands:
    init [[server:]path]
        Initializes a syn directory in current directory pointing to the remote
        (or local) path. If it is the server directory, don't specify path.
        Edit .ssh/config so rsync can correctly connect to the remote repo.

    uninit
        Unconfigures current syn repo by removing .syn config file.

    set [server:]path
        Sets the remote directory.

    push -adl
        Pushes files in current directory to remote directory.

        Options
        -a, Push entire syn directory
        -d, Delete remote files not in local directory
        -w, Perform a whatif on the synchronization

    pull -adl [path]
        Pulls files from remote directory into current directory.

        Options
        -a, Pull entire syn directory
        -d, Delete remote files not in local directory
        -w, Perform a whatif on the synchronization

    help
        Displays help information.

### Who do I talk to? ###

* Author: Lucas Wilson
* Email: lkwilson96@gmail.com
* Contributions and suggestions are always welcome!
