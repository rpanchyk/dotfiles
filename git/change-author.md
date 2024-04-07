# Change author

- https://stackoverflow.com/a/30737248
- https://mhagemann.medium.com/how-to-change-the-user-for-all-your-git-commits-ffefbacf2652

Create and run script `git-change-author-name-email.sh`

```shell
#!/bin/sh

git filter-branch --env-filter '
OLD_EMAIL="old_email@gmail.com"
CORRECT_NAME="new_name"
CORRECT_EMAIL="new_email@gmail.com"

if [ "$GIT_COMMITTER_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_COMMITTER_NAME="$CORRECT_NAME"
    export GIT_COMMITTER_EMAIL="$CORRECT_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_AUTHOR_NAME="$CORRECT_NAME"
    export GIT_AUTHOR_EMAIL="$CORRECT_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags
```

## Apply changes with corrected history

```shell
git push --force --tags origin 'refs/heads/*'
```

## Clean repository

```shell
git fetch origin
git reset --hard origin/main
git for-each-ref --format='delete %(refname)' refs/original | git update-ref --stdin
git reflog expire --expire=now --all
git gc --prune=now
```
