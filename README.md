
# do-git

`do-git pull` == the simpler, more flexible, cooler version of "gitup" :P

---

`do-git` will concurrently run a git command in multiple directories for you.

`do-git pull` will run `git pull` inside all git directories in your current
directory.

The best way to do this is to run `git branch -u origin/develop` in all your
repos -- assuming that you want git pull to update your current branch with
develop. Then you just run `do-git pull` and you're done with all updates!  Or
run `git branch -u origin/another-branch` if you want that repo to pull from
something else.

`find . -name .git | xargs dirname | do-git diff` will run `git diff` in every
git project under your cwd.

`do-git pull || cat ./repos_with_errors | do-git status` will take all the
repos that failed to git pull, and then run git status on them. Note that if
any occurrance of git fails, then do-git fails

If there's a hardcoded list of repos you always want to use, then create a file
called 'repos', and (unless you pipe something via stdin), do-git will use that
list by default

