e:\VisualStudio\Learn\Git\GitIgnoreFundamentals\
https://github.com/mikolodziejczyk/GitIgnoreFundamentals

First remove the existing e:\VisualStudio\Learn\Git\GitIgnoreFundamentals\
Then start a command line and clone the existing repository:
cd e:\VisualStudio\Learn\Git
git clone https://github.com/mikolodziejczyk/GitIgnoreFundamentals.git

Unzip 
e:\VisualStudio\Learn\Git\GitIgnoreFundamentals\GitIgnoreFundamentalsContents.zip
to the current folder, that is: e:\VisualStudio\Learn\Git\GitIgnoreFundamentals
This adds the files for the practice.

Once you complete you can remove the folder altogether.

1. Can you have .gitignore in subfolders?
2. Blank lines in .gitignore. How are they interpreted?

A. Common tasks

1. Ignore folder: Ignore the node_modules folder and all its contents.
	a. Will it work for node_modules in subfolders? That is you have another nested application with its own node_modules, will this nested node_modules folder and its contents be ignored?
	b. Can you negate the pattern for some specific files?
2. Comments: Add a comment to the previous rule
3. Ignore explicitly specified folder: Assume that we have the compiled output in a dist folder in the solution root folder.
Add an entry that ignores exactly this folder and its contents (not in subfolders).
4. Ranges: Ignore all the bin and Bin folders and their contents anywhere in the solution. Use the range to include both bin and Bin
Can you negate the pattern for some specific files?
5. Ingoring specific files anywhere in the solution: ignore thumbs.db anywhere in the solution
6. Ignoring files by their extension: ignore all .nupkg files anywhere in the solution
7. Ignore folder contents but allow specific exclusion: Ignore all log folders in the solution but in the way that allows exclusion.
8. Negating a pattern: Add an exclusion to the previous rule, the readme.txt files should be preserved. What if you wanted all readme files of any type, e.g. readme.md?
9. Keeping a folder: You have an empty folder "stylesheet/mixins". Configure it to be kept in the source control even if there're no files in it.
10. Keeping a folder but ignore the contents: You have an intermediate folder. We want to keep this folder in the source control but ignore its contents.
	a. by configuring from this folder
	b. by configuring from the parent folder
Use notes.
11. Checking if a file is ignored: Check whether a particular file is ignored and why.

B. Some theory

1. Simple name: You have a simple name entry:
log
What is matched? Files (log)? Folder (log)? Folder contents (log/anything)? Nested folders (any/log)? Their contents (any/log/anything)? Nested files (any/log)
2. Folder name: You have an entry:
logs/
What is matched? Files with this name, nested? Folders with this name, nested? The contents of folders with this name, nested?
3. Folder + file name: You have a rule
logs/debug.log
Does it apply to (a) logs/debug.log, (b) nested folders, e.g. build/logs/debug.log

C. Ignoring already commited files

1. Can you ignore a file / folder that is already commited?
2. You have a file_by_mistake.txt commited. Remove it both from the working tree and from the repository.
3. You have user.config file commited. This file is neccessary but it should not be commited. Remove it from the repository but keep in the working tree. Add a .gitignore rule to prevent it from being commited in future.
4. You have the bower_components folder commited. You want to fix it, the folder should remain in the working tree but shouldn't be in the repository. So that remove this folder from the repository but keep in the working tree. Add a .gitignore rule to prevent it from being commited in future.
