# GIT

## Prune tracking branches not on the remote

```
git fetch
git remote prune origin
```

## Remove submodule

Source: https://stackoverflow.com/a/1260982

```
git rm <path-to-submodule>
rm -rf .git/modules/<path-to-submodule>
git config --remove-section submodule.<path-to-submodule>
```

## Pull from different user keeping local changes

```
git stash
git pull https://myusername@github.com/projectfolder/projectname.git
git stash pop
```
