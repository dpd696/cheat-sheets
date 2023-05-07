# Working with files and directory (touch, mkdir, cp, mv, rm, shred)


COMMAND | DESCRIPTION
---|---
touch filename | # creating a new file or updating the timestamps if the file already exists
mkdir dir1 | # creating a new directory
mkdir -p mydir1/mydir2/mydir3 | # creating a directory and its parents as well


# The cp command
COMMAND | DESCRIPTION
---|---
cp file1 file2 | # copying file1 to file2 in the current directory
cp file1 dir1/file2 | # copying file1 to dir1 as another name (file2)
cp -i file1 file2 | # copying a file prompting the user if it overwrites the destination
cp -p file1 file2 | # preserving the file permissions, group and ownership when copying
cp -v file1 file2 | # being verbose
cp -r dir1 dir2/ | # recursively copying dir1 to dir2 in the current directory
cp -r file1 file2 dir1 dir2 destination_directory/ | # copy more source files and directories to a destination directory


# The mv command ###

COMMAND | DESCRIPTION
---|---
mv file1 file2 | # renaming file1 to file2
mv file1 dir1/ | # moving file1 to dir1 
mv -i file1 dir1/ | # moving a file prompting the user if it overwrites the destination file
mv -n file1 dir1/ | # preventing a existing file from being overwritten
mv -u file1 dir1/ | # moving only if the source file is newer than the destination file or when the destination file is missing
mv file1 dir1/file2 | # moving file1 to dir1 as file2
mv file1 file2 dir1/ dir2/ destination_directory/ | # moving more source files and directories to a destination directory

# The rm command 
COMMAND | DESCRIPTION
---|---
rm file1 | # removing a file
rm -v file1 | # being verbose when removing a file
rm -r dir1/ | # removing a directory
rm -rf dir1/ | # removing a directory without prompting
rm -ri fil1 dir1/ | # removing a file and a directory prompting the user for confirmation
shred -vu -n 100 file1 | # secure removal of a file (verbose with 100 rounds of overwriting)