# syn #

This package is a wrapper for rsync used to easily synchronize directories with
each other.

Example:
```
syn init svr:/syn/path      # Mark working dir as syn dir
syn pull                    # Pull files from remote dir
<edit files>
syn push                    # Push changed and new files
```

### What is this repository for? ###

* Mark a directory to point to a remote directory, and you can push and pull
  changes.
* You can even push/pull sub directories within the local directory tree.
* To avoid pushing unwanted changes, there is a dry run mode (rsync's --dry-run
  option).
* If synchronizing between similar filesystems (ext4 to hfs, but not ext4 to
  fat32), you can configure the archiving option to preserve attributes, such
  as file permissions (rsync's archive option).
* It will save bandwidth and time by only pushing files with changes, this
  allows for frequent syn calls (rsync's --update option).
* If the current state of the directory is desired, you can push with the -d
  option to delete missing files on the remote server (rsync's --delete option)

### Usage ###
Usage:
    syn command [args...]

Commands:
    init [server:]path
        Configures the current directory as a syn directory with the remote dir
        specified. It's recommended that 'server' is defined in your
        .ssh/config file. It adds a .syn file to the root of the syn directory.
        This file gets sourced when the syn command is run.

    uninit
        Unconfigures the current syn repo (by removing the .syn config file).

    set [server:]path
        Sets the remote directory of the current syn repo.

    stat
        Get details about the current syn directory.

    push -adw
        Pushes files in current directory to remote directory. Note that it
        doesn't push the entire syn directory by default. 

        Options
        -a, Push entire syn directory
        -d, Delete remote files not in local directory
        -n, Perform a dry run on the synchronization

    pull -adn
        Pulls files in current directory to remote directory. Note that it
        doesn't pull the entire syn directory by default. 

        Options
        -a, Pull entire syn directory
        -d, Delete remote files not in local directory
        -n, Perform a dry run on the synchronization

    help
        Displays help information.

### Who do I talk to? ###

* Author: Lucas Wilson
* Email: lkwilson96@gmail.com
* Contributions and suggestions are always welcome!
