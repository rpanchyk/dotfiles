# Remove file from history

- https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History

```shell
git filter-branch -f --tree-filter "rm -rf file.txt" HEAD
git push --force --tags origin 'refs/heads/*'
```
