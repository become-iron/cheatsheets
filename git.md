# GIT

## Prune tracking branches not on the remote

`git remote prune origin` 

## Remove submodule

Source: https://stackoverflow.com/a/1260982

```
git rm <path-to-submodule>
rm -rf .git/modules/<path-to-submodule>
git config --remove-section submodule.<path-to-submodule>
```
