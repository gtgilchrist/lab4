
# Hey! I'm Filing Here
 
This code creates an ext2 file system with a root directory, a lost+found directory, a file named hello-world with only "Hello world\n" and a symbolic link named hello to hello-world.
 
## Building
 
To build the program run "make".
 
## Running
 
Run the executable “./ext2-create” after you build the program. This makes a “cs111-base.img” file. To make the file system mount, make a directory to mount to with “mkdir mnt” and then mount with “sudo mount -o loop cs111-base.img mnt”. Navigate to the new file system with “cd mnt” and then use “ls -ain” to get the following view of the mounted filesystem:
total 7
      2 drwxr-xr-x 3    0    0 1024 May 26 21:05 .
1203676 drwxr-xr-x 5 1000 1000 4096 May 26 21:05 ..
     13 lrw-r—-r—- 1 1000 1000   11 May 26 21:05 hello -> hello-world
     12 -rw-r—-r—- 1 1000 1000   12 May 26 21:05 hello-world
     11 drwxr-xr-x 2    0    0 1024 May 26 21:05 lost+found
 
## Cleaning up
 
To unmount the filesystem, navigate out of the mnt directory with “cd ..”. Then do “sudo umount mnt” and then “rmdir mnt” to unmount the filesystem and delete the mnt directory as it is no longer needed.
 