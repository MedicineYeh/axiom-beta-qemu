# axiom-beta-env
An apertus° AXIOM-beta execution environment for both developer/user.

This repo contains the build environments for all AXIOM-beta scripts and images.

# Instructions

To prepare the build/execution environment, follow the steps:
1. `sudo ./tools/install.sh`
2. `./tools/prepareAll.sh`
3. `./tools/download.sh`

After the above steps, install the `axiom` command and activate its build/execution environment by running:
`source ./installCommands.sh`

Now, you can start to build either the (untested) image or the official build pipeline of beta-software and execute them with:

4. `./guest-images/dev/microzed-image-1.4/build.sh` or `./guest-images/dev/beta-software/build.sh`
5. `./run_image.sh dev/microzed-image-1.4` or `./run_image.sh dev/beta-software`

NOTE: If you fail on command not found or any problem, try `source ./installCommands.sh` and then do it again. This will force system using the binaries comes with this repo.

# AXIOM command (shell function)
This repo has a complete shell completion systems and execution environments. One can install the `axiom` command and use it to run QEMU instance at any where.

Initialize the command by running `source ./installCommands.sh`.

## Example usages
* `axiom image list`
* `axiom image pull dev/microzed-image-1.4@/p2/etc/hostname ./`
* `axiom qemu dev/microzed-image-1.4`

To understand more on the concepts of using this build system, please refer to this [thread](https://github.com/apertus-open-source-cinema/axiom-beta-qemu/issues/6)

# AXIOM command completion
Completion system is available for `axiom`, `image_manager.py` and `runQEMU.sh`.
Run `source ./installCommands.sh` for registering the completion functions.

``` zsh
$ axiom image <TAB>
list   -- List all existing images
push   -- Push a file/folder into image
pull   -- Pull a file/folder from image
ls     -- List files in image folder
rm     -- Remove file/folder from image
mkdir  -- Make a folder in image
...
...
--help  -h  -- Display help message and information of usage.
```

## You can also tab all the way through the file system in image
``` zsh
$ axiom image push README.md dev/microzed-image-1.3@/etc/<TAB>
rch-release      fstab             iproute2/         login.defs        modprobe.d/       pacman.d/         resolvconf.conf   systemd/        
bash.bash_logout  gai.conf          iptables/         logrotate.conf    modules-load.d/   pam.d/            rpc               tmpfiles.d/     
bash.bashrc       group ..................
```
