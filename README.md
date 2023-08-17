# kiali-molecule-test-logs
Storage for Kiali molecule test logs

## Purge Logs and Git History
From: https://stackoverflow.com/questions/13716658/how-to-delete-all-commit-history-in-github

To keep the code you have in the current `kind` branch but purge all history:

```
git fetch --all
git checkout kind
git checkout --orphan latest_kind
rm -rf molecule-tests-* # remove all the files you do not want to keep
git add -A
git commit -m "the current files"
git branch -D kind
git branch -m kind
git push -f origin kind
git branch --set-upstream-to=origin/kind kind
git gc
```
