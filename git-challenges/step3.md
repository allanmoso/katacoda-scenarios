The previous step included staging the file changes before making a commit. Sometimes you will need to be able to partially commit changes. To do this you will need to selectively stage changes before making a commit.

To demonstrate this we are going to add two edits to our `test.txt` file: one at the begining of the file and one at the end of the file.
Add "test2" at the beginning of the file
`echo -e "test2\n$(cat test.txt)" > test.txt`{{execute}}
Add "test3" at the end of the file
`echo "test3" >> test.txt`{{execute}}
View the contents of the file
`cat test.txt`{{execute}}

Our goal is to commit these two changes into two separate commits.

First we are going to add to the index the first change (the line with "test2"). To do this we are going to interactively add a patch to the index
`git add -p test.txt`{{execute}}
It will show you a diff of the change that includes the one made at the beginning of the file (with `test2` value) and the one made at the end of the file (with `test3` value).

Type `s` and press `Enter`  to `split` the patch.

Now the diff only contains the change at the beginning of the file (showing `test2`).

Type `y` and press `Enter` to stage the "hunk" of change.

Next it will show you a diff of change that includes the one made at the end of the file (showing `test3`).

For  now we are going to not stage this hunk of change. Type `n` to not stage it.

If you now look at the diff of the staged changes it will only show `test2`.
`git diff --staged`{{execute}}

Now you can commit the staged commit as `Added 'test2'`
`git commit -m "Added 'test2'"`{{execute}}

And separately commit the line with `test3` as a separate commit
`git add -A && git commit -m "Added 'test3'` {{execute}}

