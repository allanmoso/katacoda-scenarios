Create a new Git repository that will serve as our remote repository.
`mkdir git-challenges-remote && cd git-challenges-remote && git init`{{execute}}

Create a test file.
`touch test.txt`{{execute}}

Commit the test file.
`git add test.txt && git commit -m "Test file."`{{execute}}

Go to the parent directory and clone this "remote" repo.
`cd .. && git clone /home/scrapbook/tutorial/git-challenges-remote/.git git-challenges`{{execute}}

For the purpose of this exercise, the directory `git-challenges-remote` is the remote repository from which the local repository located in the `git-challenges` directory is going to pull from.

