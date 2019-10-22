# GIT FUNDAMENTALS


## DOLLY GOOD

`git clone [clone-url-from-github-site] [optional-destination-folder]`

This clones the live repo to your local machine so you can work on it.


## ONE DOES NOT SIMPLY PUSH TO MASTER

`git checkout -b [name-of-new-branch]`

This branches off of master to avoid trying to update it directly which would be a Super Bad Time.
Alternatively, do `git branch [name]` then `git checkout [name]` in 2 steps but seems needless.


## ALL THE WORLD'S A STAGE...

Make changes as needed (e.g. vim notes.txt or whatever) then...

`git add [filename]`

... to add a single to staging _or alternatively..._
	
`git add -A`

... or...

`git add .`

... to add all changes to staging.

`git status`

This just checks that everything is staged and ready to go, acknowledging your changes.


## PUSH THE BUTTON

`git commit -m "[commit-message]"`

This commits staged changes with a note to describe the changes (e.g. "Updated readme" or whatever).

`git status`

Another quick check, as with staging, then finally...

`git push --set-upstream origin [branch-name]`

... which assigns your upstream to branch as opposed to master, then pushes changes to the branch.


## BUT IS EVERYTHING BORKED NOW?

If the local copy isn't up to date with the original then you're up Schitt's Creek sans paddle, so check it:

`git checkout master`

`git pull`

Any changes will be listed in output. If there are changes, you need to merge those into your branch:

`git checkout [branch-name]`
`git merge master`

Hopefully there aren't any merge conflicts. If there are, hulk smash. Basically you'll want to try to
resolve them with a restage and recommit. Then, repeat the push command. Otherwise, there's no need
because they'll get merged automatically with your commit without conflicts when your pull request goes
through.


## PULL THE OTHER ONE

Finally, you need to __request__ that the maintainer __pull__ your changes from the branch into master.
This is done on the Github site interface rather than through command line.

Navigate to the repo, then the "Pull requests" tab, and hit "Compare & pull request".


...


## FORKING HELL MATE

`git remote -v`

states what URLs you can push to (starts with origin)

`git remote add upstream MAIN(beforefork)URLHERE`

but then you could push to the main branch instead of your fork which could be bad (might not have
permission) so you'll want to switch that off:

`git remote set-url --push URLGOESHERE`
