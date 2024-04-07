# Change remote

- https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories

## With new remote

```shell
git remote -v
git remote add origin2 git@github.com:rpanchyk/repo1.git
git push -u origin2 main
git remote rm origin
git remote rename origin2 origin
git remote -v
```

## With updating remote

```shell
git remote -v
git remote set-url origin git@github.com:rpanchyk/repo1.git
git push origin main
git remote -v
```
