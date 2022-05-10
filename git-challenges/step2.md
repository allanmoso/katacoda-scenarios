
To test that our remote and local repository setup is working propery we are going to commit and push a change.

Add a line in the file
`echo 'test1' > test.txt`{{execute}}

You can see the changes made to file
`git diff`{{execute}}

Stage the change
`git add test.txt`{{execute}}

You can see staged changes before making a commit
`git diff --staged`{{execute}}

Commit the changed file with a commit message "First line added."
`git commit -m 'First line added.'`{{execute}}
At this time we have committed the file but it is not yet committed to the remote repository.

Check that the remote repository still does not have the change by checking the contents of the file in that directory.
`cat ../git-challenges-remote/test.txt`{{execute}}

Push the change to the remote repository.
`git push`{{execute}}


Checking the file again in the remote repository directory should show that the change is now pushed.
`cat ../git-challenges-remote/test.txt`{{execute}}
